# 在Tomcat服务器上安装SSL证书<a name="ccm_01_0081"></a>

本文以Linux操作系统中的Tomcat7服务器为例介绍SSL证书的安装步骤，您在安装国际标准证书时可以进行参考。证书安装好后，您的Web服务器才能支持SSL通信，实现通信安全。

>![](public_sys-resources/icon-note.gif) **说明：** 
>由于服务器系统版本或服务器环境配置不同，在安装SSL证书过程中使用的命令或修改的配置文件信息可能会略有不同，云证书管理服务提供的安装证书示例，仅供参考，请以您的实际情况为准。
>若参考文档安装证书后，HTTPS仍然不生效或遇到其他问题，请单击[一对一咨询](https://marketplace.huaweicloud.com/contents/917d16b0-33c4-49d3-bfe9-dd9219ea084e#productid=00301-120142-0--0)购买SSL证书配置优化服务，联系专业工程师为您排查具体问题。

## 前提条件<a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_section487617561143"></a>

-   证书已签发且“证书状态“为“已签发“。
-   已下载SSL证书，具体操作请参见[下载证书](下载SSL证书.md)。
-   已安装OpenSSL工具。

    您可以从“https://www.openssl.org/source/“下载最新的OpenSSL工具安装包（要求OpenSSL版本必须是1.0.1g或以上版本）。

-   已安装Keytool工具。

    Keytool工具一般包含在Java Development Kit（JDK）工具包中。

-   待安装证书为国际标准证书。

## 约束条件<a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_section5414154419315"></a>

-   证书安装前，务必在安装SSL证书的服务器上开启“443“端口，同时在安全组增加“443“端口，避免安装后仍然无法启用HTTPS。
-   如果一个域名有多个服务器，则每一个服务器上都要部署。
-   待安装证书的服务器上需要运行的域名，必须与证书的域名一一对应，即购买的是哪个域名的证书，则用于哪个域名。否则安装部署后，浏览器将提示不安全。

## 操作步骤<a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_section6411655151013"></a>

在Tomcat7服务器上安装SSL证书的流程如下所示：

[①获取文件](#zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_section5644742133315)  →  [②创建目录](#zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_section573753618407)  →  [③修改配置文件](#zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_section183001410164118)  →  [④重启Tomcat](#zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_section1694619114441)  →  [⑤效果验证](#zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_section186262524017)

## 步骤一：获取文件<a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_section5644742133315"></a>

安装证书前，需要获取证书文件和密码文件，请根据申请证书时选择的“证书请求文件“生成方式来选择操作步骤：

-   如果申请证书时，“证书请求文件“选择“系统生成CSR“，具体操作请参见：[系统生成CSR](#zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_li16102103493417)。
-   如果申请证书时，“证书请求文件“选择“自己生成CSR“，具体操作请参见：[自己生成CSR](#zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_li81041349344)。

具体操作如下：

-   <a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_li16102103493417"></a>**系统生成CSR**
    1.  在本地解压已下载的证书文件。

        下载的文件包含了“Apache“、“IIS“、“Nginx“、“Tomcat“4个文件夹和1个“domain.csr“文件，如[图1](#zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_fdd76c20249e24d95b7a52872f72f84fd)所示。

        **图 1**  本地解压SSL证书<a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_fdd76c20249e24d95b7a52872f72f84fd"></a>  
        ![](figures/本地解压SSL证书.png "本地解压SSL证书")

    2.  从“_证书ID_\__证书绑定的域名_\_Tomcat“文件夹内获得证书文件“_证书ID_\__证书绑定的域名_\_server.jks“和密码文件“_证书ID_\__证书绑定的域名_\_keystorePass.txt“。

-   <a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_li81041349344"></a>**自己生成CSR**
    1.  解压已下载的证书压缩包，获得“_证书ID_\__证书绑定的域名_\_server.pem“文件。

        “_证书ID_\__证书绑定的域名_\_server.pem“文件包括两段证书代码“-----BEGIN CERTIFICATE-----“和“-----END CERTIFICATE-----“，分别为服务器证书和中级CA证书。

    2.  <a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_zh-cn_topic_0168518253_li5678941865"></a>使用OpenSSL工具，将pem格式证书转换为PFX格式证书，得到“server.pfx“文件。
        1.  “pem“文件和生成CSR时的私钥“server.key“放在OpenSSL工具安装目录的bin目录下。
        2.  在OpenSSL工具安装目录的bin目录下，执行以下命令将pem格式证书转换为PFX格式证书，按“Enter”。

            **openssl pkcs12 -export -out server.pfx -inkey server.key -in** _证书ID_\__证书绑定的域名_\_**server.pem**

            回显信息如下：

            ```
            Enter Export Password:
            ```

        3.  <a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_zh-cn_topic_0168518253_li76851541564"></a>输入PFX证书密码，按“Enter”。

            此处输入的密码为用户自定义密码，请根据自己的需求进行设置并输入密码。

            回显信息如下：

            ```
            Verifying - Enter Export Password:
            ```

            >![](public_sys-resources/icon-note.gif) **说明：** 
            >请牢记此处输入的PFX证书密码。后续设置JKS密码需要与此处设置的PFX密码保持一致，否则可能会导致Tomcat启动失败。
            >为提高用户密码安全性，建议按以下复杂度要求设置密码：
            >-   密码长度为8～32个字符。
            >-   至少需要包含大写字母、小写字母、数字、空格、特殊字符\~\`!@\#$%^&\*\(\)\_+|\{\}:"<\>?-=\\\[\];',./中的3种类型字符。

        4.  再次输入PFX证书密码，按“Enter”。

            当系统没有回显任何错误信息，表示已在OpenSSL工具安装目录下成功生成“server.pfx“文件。

    3.  使用Keytool工具，将PFX格式证书文件转换成JKS格式，得到“server.jks“文件。
        1.  将[2](#zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_zh-cn_topic_0168518253_li5678941865)中生成的“server.pfx“文件复制到“%JAVA\_HOME%/jdk/bin“目录下。
        2.  在“%JAVA\_HOME%/jdk/bin“目录下，执行以下命令，按“Enter”。

            **keytool -importkeystore -srckeystore server.pfx -destkeystore server.jks -srcstoretype PKCS12 -deststoretype JKS**

            回显信息如下：

            ```
            输入目标密钥库口令：
            ```

        3.  输入JKS证书密码，按“Enter”。

            >![](public_sys-resources/icon-notice.gif) **须知：** 
            >请将JKS密码设置为与PFX证书密码相同的密码，否则可能会导致Tomcat启动失败。

            回显信息如下：

            ```
            再次输入新口令：
            ```

        4.  再次输入JKS证书密码，按“Enter”。

            回显信息如下：

            ```
            输入源密钥库口令：
            ```

        5.  输入[2.c](#zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_zh-cn_topic_0168518253_li76851541564)中设置PFX证书密码，按“Enter”。

            回显类似如下信息时，则表示转换成功，已在OpenSSL工具安装目录下成功生成“server.jks“文件。

            ```
            已成功导入别名1的条目。
            已完成导入命令：1个条目成功导入，0个条目失败或取消
            ```

        6.  在“%JAVA\_HOME%/jdk/bin“目录下新建一个“keystorePass.txt“文件，将JKS的密码保存在该文件中。

    4.  将转换后的证书文件“server.jks“和新建的密码文件“keystorePass.txt“放在同一目录下。

## 步骤二：创建目录<a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_section573753618407"></a>

在Tomcat的安装目录下创建“cert“目录，并且将证书文件“server.jks“和密码文件“keystorePass.txt“复制到“cert“目录中。

## 步骤三：修改配置文件<a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_section183001410164118"></a>

>![](public_sys-resources/icon-notice.gif) **须知：** 
>修改配置文件前，请将配置文件进行备份，并建议先在测试环境中进行部署，配置无误后，再在现网环境进行配置，避免出现配置错误导致服务不能正常启动等问题，影响您的业务。

在Tomcat7安装证书的具体操作如下：

1.  在Tomcat安装目录conf目录下“server.xml“文件中找到如下参数：

    ```
    <!--
        <Connector port="8443" protocol="org.apache.coyote.http11.Http11Protocol"
                   maxThreads="150" SSLEnabled="true" scheme="https" secure="true"
                   clientAuth="false" sslProtocol="TLS" />
        -->
    ```

2.  找到以上参数，去掉<!- - 和 - -\>这对注释符。
3.  增加以下2个参数，请根据[表1](#zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_ta67047d5985940a4a548c68bd7f1960b)修改参数的值。

    ```
    keystoreFile="cert/server.jks"
    keystorePass="证书密码"
    ```

    完整配置参考如下，其余参数请根据实际情况进行修改：

    ```
    <Connector port="443" protocol="org.apache.coyote.http11.Http11Protocol"
                   maxThreads="150" SSLEnabled="true" scheme="https" secure="true"
          keystoreFile="cert/server.jks"
          keystorePass="证书密码"
          clientAuth="false" sslProtocol="TLS" />
    ```

    >![](public_sys-resources/icon-notice.gif) **须知：** 
    >不要直接复制所有配置，只需添加“keystoreFile“，“keystorePass“参数即可，其它参数请根据自己的实际情况修改。

    **表 1**  参数说明（一）

    <a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_ta67047d5985940a4a548c68bd7f1960b"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_r67df352686cc4a658647fdc78b35bfae"><th class="cellrowborder" valign="top" width="32.29%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_zh-cn_topic_0168518253_p316602111915"><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_zh-cn_topic_0168518253_p316602111915"></a><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_zh-cn_topic_0168518253_p316602111915"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="67.71000000000001%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_zh-cn_topic_0168518253_p81664211094"><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_zh-cn_topic_0168518253_p81664211094"></a><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_zh-cn_topic_0168518253_p81664211094"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_r6b364524b901417dbbc77e2d3764623b"><td class="cellrowborder" valign="top" width="32.29%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_zh-cn_topic_0168518253_p151662211914"><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_zh-cn_topic_0168518253_p151662211914"></a><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_zh-cn_topic_0168518253_p151662211914"></a>port</p>
    </td>
    <td class="cellrowborder" valign="top" width="67.71000000000001%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_a7ec83f6fc103456ab7c408e8f4f6b7d1"><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_a7ec83f6fc103456ab7c408e8f4f6b7d1"></a><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_a7ec83f6fc103456ab7c408e8f4f6b7d1"></a>指定服务器要使用的端口号，建议配置为<span class="parmvalue" id="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_pb9680faefecc46c78e6340cdddac7397"><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_pb9680faefecc46c78e6340cdddac7397"></a><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_pb9680faefecc46c78e6340cdddac7397"></a>“443”</span>。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_rab9d7c63741a4796b648cec33c2eeab1"><td class="cellrowborder" valign="top" width="32.29%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_zh-cn_topic_0168518253_p15166121394"><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_zh-cn_topic_0168518253_p15166121394"></a><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_zh-cn_topic_0168518253_p15166121394"></a>protocol</p>
    </td>
    <td class="cellrowborder" valign="top" width="67.71000000000001%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_a81ea998f5a744d12a537d36a88e1f3ce"><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_a81ea998f5a744d12a537d36a88e1f3ce"></a><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_a81ea998f5a744d12a537d36a88e1f3ce"></a>设置HTTP协议，保持缺省值即可。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_r4aaa7681ab9b4130b1319274970dd370"><td class="cellrowborder" valign="top" width="32.29%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_zh-cn_topic_0168518253_p216632116913"><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_zh-cn_topic_0168518253_p216632116913"></a><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_zh-cn_topic_0168518253_p216632116913"></a>keystoreFile</p>
    </td>
    <td class="cellrowborder" valign="top" width="67.71000000000001%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_zh-cn_topic_0168518253_p11664219915"><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_zh-cn_topic_0168518253_p11664219915"></a><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_zh-cn_topic_0168518253_p11664219915"></a><span class="filepath" id="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_f9864cb7c252549188889dbc21fd1a82e"><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_f9864cb7c252549188889dbc21fd1a82e"></a><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_f9864cb7c252549188889dbc21fd1a82e"></a>“server.jks”</span>文件存放路径，绝对路径和相对路径均可。示例：cert/server.jks</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_rd2fe9775052c490b9b1627f41bbc3b2b"><td class="cellrowborder" valign="top" width="32.29%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_a454be4a55757417db796a449645b2848"><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_a454be4a55757417db796a449645b2848"></a><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_a454be4a55757417db796a449645b2848"></a>keystorePass</p>
    </td>
    <td class="cellrowborder" valign="top" width="67.71000000000001%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_zh-cn_topic_0168518253_p21676213911"><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_zh-cn_topic_0168518253_p21676213911"></a><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_zh-cn_topic_0168518253_p21676213911"></a><span class="filepath" id="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_f44280eacea774b499e3df9674cfbe726"><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_f44280eacea774b499e3df9674cfbe726"></a><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_f44280eacea774b499e3df9674cfbe726"></a>“server.jks”</span>的密码。填写<span class="filepath" id="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_f7cf5e65a199d44009552416579cd69bd"><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_f7cf5e65a199d44009552416579cd69bd"></a><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_f7cf5e65a199d44009552416579cd69bd"></a>“keystorePass.txt”</span>文件内的密码。</p>
    <div class="notice" id="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_note118771122133116"><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_note118771122133116"></a><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_note118771122133116"></a><span class="noticetitle"> 须知： </span><div class="noticebody"><p id="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_p1687872218315"><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_p1687872218315"></a><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_p1687872218315"></a>如果密码中包含<strong id="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_b1075825220319"><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_b1075825220319"></a><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_b1075825220319"></a><span class="parmname" id="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_parmname66211956173220"><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_parmname66211956173220"></a><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_parmname66211956173220"></a>“&amp;”</span></strong>，请将其替换成<strong id="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_b17963939183212"><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_b17963939183212"></a><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_b17963939183212"></a><span class="parmname" id="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_parmname75291505335"><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_parmname75291505335"></a><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_parmname75291505335"></a>“&amp;amp;”</span></strong>，以免配置不成功。</p>
    <p id="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_p8608124915338"><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_p8608124915338"></a><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_p8608124915338"></a>示例：</p>
    <p id="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_p13926175414333"><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_p13926175414333"></a><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_p13926175414333"></a>如果keystorePass="Ix6<strong id="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_b127665710356"><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_b127665710356"></a><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_b127665710356"></a>&amp;</strong>APWgcHf72DMu"，则修改为keystorePass="Ix6<strong id="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_b85241119359"><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_b85241119359"></a><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_b85241119359"></a>&amp;amp;</strong>APWgcHf72DMu"。</p>
    </div></div>
    </td>
    </tr>
    <tr id="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_rabb6ab1216164bcd83f833c4bf66df06"><td class="cellrowborder" valign="top" width="32.29%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_zh-cn_topic_0168518253_p721512452161"><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_zh-cn_topic_0168518253_p721512452161"></a><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_zh-cn_topic_0168518253_p721512452161"></a>clientAuth</p>
    </td>
    <td class="cellrowborder" valign="top" width="67.71000000000001%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_a0884c954dbde4fbcb525ecd67d46fe01"><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_a0884c954dbde4fbcb525ecd67d46fe01"></a><a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_zh-cn_topic_0110866190_a0884c954dbde4fbcb525ecd67d46fe01"></a>是否要求所有的SSL客户出示安全证书，对SSL客户进行身份验证，保持缺省值即可。</p>
    </td>
    </tr>
    </tbody>
    </table>

4.  在Tomcat安装目录conf目录下“server.xml“文件中找到如下参数：

    ```
    <Host name="localhost"  appBase="webapps"
          unpackWARs="true" autoDeploy="true">
    ```

5.  将“Host name“改为证书绑定的域名。

    完整配置如下（以“www.domain.com“为例）：

    ```
    <Host name="www.domain.com"  appBase="webapps"
          unpackWARs="true" autoDeploy="true">
    ```

6.  修改完成后保存配置文件。

## 步骤四：重启Tomcat<a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_section1694619114441"></a>

在Tomcat bin目录下执行****./shutdown.sh****命令停止Tomcat服务；

等待10秒后，再执行****./startup.sh****命令（若进程被守护进程自动拉起，则无需手动启动），启动Tomcat服务。

## 效果验证<a name="zh-cn_topic_0000001399305390_zh-cn_topic_0000001303178856_zh-cn_topic_0000001124519755_zh-cn_topic_0171809250_section186262524017"></a>

部署成功后，可在浏览器的地址栏中输入“https://域名“，按“Enter“。

如果浏览器地址栏显示安全锁标识，则说明证书安装成功。

-   如果网站仍然出现不安全提示，请参见[为什么部署了SSL证书后，网站仍然出现不安全提示？](https://support.huaweicloud.com/ccm_faq/ccm_01_0098.html)。
-   如果通过域名访问网站时，无法打开网站，请参见[为什么部署了SSL证书后，通过域名访问网站时，无法打开网站？](https://support.huaweicloud.com/ccm_faq/ccm_01_0099.html)进行处理。
-   如果仍未解决或出现其他问题，华为云市场提供SSL证书配置优化服务，专业工程师一对一服务，请直接单击[一对一咨询](https://marketplace.huaweicloud.com/contents/917d16b0-33c4-49d3-bfe9-dd9219ea084e#productid=00301-120142-0--0)进行购买，购买服务后，联系工程师进行处理。

