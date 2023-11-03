# 在Apache服务器上安装SSL证书<a name="ccm_01_0083"></a>

本文以CentOS 7操作系统中的Apache 2.4.6服务器为例介绍SSL证书的安装步骤，您在安装国际标准证书时可以进行参考。证书安装好后，您的Web服务器才能支持SSL通信，实现通信安全。

>![](public_sys-resources/icon-note.gif) **说明：** 
>由于服务器系统版本或服务器环境配置不同，在安装SSL证书过程中使用的命令或修改的配置文件信息可能会略有不同，云证书管理服务提供的安装证书示例，仅供参考，请以您的实际情况为准。
>若参考文档安装证书后，HTTPS仍然不生效或遇到其他问题，请单击[一对一咨询](https://marketplace.huaweicloud.com/contents/917d16b0-33c4-49d3-bfe9-dd9219ea084e#productid=00301-120142-0--0)购买SSL证书配置优化服务，联系专业工程师为您排查具体问题。

## 前提条件<a name="zh-cn_topic_0000001399625106_zh-cn_topic_0000001355818953_zh-cn_topic_0000001124401671_zh-cn_topic_0171809252_section171927174218"></a>

-   证书已签发且“证书状态“为“已签发“。

-   已下载SSL证书，具体操作请参见[下载证书](下载SSL证书.md)。
-   Apache服务器上已安装了mod\_ssl.so模块（启用SSL功能）。

## 约束条件<a name="zh-cn_topic_0000001399625106_zh-cn_topic_0000001355818953_zh-cn_topic_0000001124217601_zh-cn_topic_0171809251_section13500821131513"></a>

-   证书安装前，务必在安装SSL证书的服务器上开启“443“端口，同时在安全组增加“443“端口，避免安装后仍然无法启用HTTPS。
-   如果一个域名有多个服务器，则每一个服务器上都要部署。
-   待安装证书的服务器上需要运行的域名，必须与证书的域名一一对应，即购买的是哪个域名的证书，则用于哪个域名。否则安装部署后，浏览器将提示不安全。
-   待安装证书为国际标准证书。

## 操作步骤<a name="zh-cn_topic_0000001399625106_zh-cn_topic_0000001355818953_zh-cn_topic_0000001124401671_zh-cn_topic_0171809252_section6411655151013"></a>

在CentOS 7操作系统中的Apache 2.4.6服务器上安装SSL证书的流程如下所示：

[①获取文件](#zh-cn_topic_0000001399625106_zh-cn_topic_0000001355818953_zh-cn_topic_0000001124401671_zh-cn_topic_0171809252_section13170712181812)  →  [②创建目录](#zh-cn_topic_0000001399625106_zh-cn_topic_0000001355818953_zh-cn_topic_0000001124401671_zh-cn_topic_0171809252_section33321255183)  →  [③修改配置文件](#zh-cn_topic_0000001399625106_zh-cn_topic_0000001355818953_zh-cn_topic_0000001124401671_zh-cn_topic_0171809252_section5388193419188)  →  [④重启Apache](#zh-cn_topic_0000001399625106_zh-cn_topic_0000001355818953_zh-cn_topic_0000001124401671_zh-cn_topic_0171809252_section19278184418180)  →  [⑤效果验证](#zh-cn_topic_0000001399625106_zh-cn_topic_0000001355818953_zh-cn_topic_0000001124217601_zh-cn_topic_0171809251_section17691911165112)

## 步骤一：获取文件<a name="zh-cn_topic_0000001399625106_zh-cn_topic_0000001355818953_zh-cn_topic_0000001124401671_zh-cn_topic_0171809252_section13170712181812"></a>

安装证书前，需要获取证书文件和密码文件，请根据申请证书时选择的“证书请求文件“生成方式来选择操作步骤：

-   如果申请证书时，“证书请求文件“选择“系统生成CSR“，具体操作请参见：[系统生成CSR](#zh-cn_topic_0000001399625106_zh-cn_topic_0000001355818953_zh-cn_topic_0000001124401671_zh-cn_topic_0171809252_li1836951018198)。
-   如果申请证书时，“证书请求文件“选择“自己生成CSR“，具体操作请参见：[自己生成CSR](#zh-cn_topic_0000001399625106_zh-cn_topic_0000001355818953_zh-cn_topic_0000001124401671_zh-cn_topic_0171809252_li19371171014199)。

具体操作如下：

-   <a name="zh-cn_topic_0000001399625106_zh-cn_topic_0000001355818953_zh-cn_topic_0000001124401671_zh-cn_topic_0171809252_li1836951018198"></a>**系统生成CSR**
    1.  在本地解压已下载的证书文件。

        下载的文件包含了“Apache“、“IIS“、“Nginx“、“Tomcat“4个文件夹和1个“domain.csr“文件，如[图1](#zh-cn_topic_0000001399625106_zh-cn_topic_0000001355818953_zh-cn_topic_0000001124217601_zh-cn_topic_0000001073213596_zh-cn_topic_0171809250_zh-cn_topic_0110866190_fdd76c20249e24d95b7a52872f72f84fd)所示。

        **图 1**  本地解压SSL证书<a name="zh-cn_topic_0000001399625106_zh-cn_topic_0000001355818953_zh-cn_topic_0000001124217601_zh-cn_topic_0000001073213596_zh-cn_topic_0171809250_zh-cn_topic_0110866190_fdd76c20249e24d95b7a52872f72f84fd"></a>  
        ![](figures/本地解压SSL证书-2.png "本地解压SSL证书-2")

    2.  从“_证书ID_\__证书绑定的域名_\_Apache“文件夹内获得证书文件“_证书ID_\__证书绑定的域名_\_ca.crt“，“_证书ID_\__证书绑定的域名_\_server.crt“和私钥文件“_证书ID_\__证书绑定的域名_\_server.key“。
        -   “_证书ID_\__证书绑定的域名_\_ca.crt“文件包括一段中级CA证书代码“-----BEGIN CERTIFICATE-----“和“-----END CERTIFICATE-----“。
        -   “_证书ID_\__证书绑定的域名_\_server.crt“文件包括一段服务器证书代码“-----BEGIN CERTIFICATE-----“和“-----END CERTIFICATE-----“。
        -   “_证书ID_\__证书绑定的域名_\_server.key“文件包括一段私钥代码“-----BEGIN RSA PRIVATE KEY-----“和“-----END RSA PRIVATE KEY-----“。

-   <a name="zh-cn_topic_0000001399625106_zh-cn_topic_0000001355818953_zh-cn_topic_0000001124401671_zh-cn_topic_0171809252_li19371171014199"></a>**自己生成CSR**
    1.  解压已下载的证书压缩包，获得“_证书ID_\__证书绑定的域名_\_server.pem“文件。

        “_证书ID_\__证书绑定的域名_\_server.pem“文件包括两段证书代码“-----BEGIN CERTIFICATE-----“和“-----END CERTIFICATE-----“，分别为服务器证书和中级CA证书。

    2.  复制“_证书ID_\__证书绑定的域名_\_server.pem“文件的第一段证书代码（服务器证书），并另存为“server.crt“文件。
    3.  复制“_证书ID_\__证书绑定的域名_\_server.pem“文件的第二段证书代码（中级CA），并另存为“ca.crt“文件。
    4.  将“ca.crt“、“server.crt“和生成CSR时的私钥“server.key“放在任意文件夹内。

## 步骤二：创建目录<a name="zh-cn_topic_0000001399625106_zh-cn_topic_0000001355818953_zh-cn_topic_0000001124401671_zh-cn_topic_0171809252_section33321255183"></a>

在Apache的安装目录下创建“cert“目录，并且将“server.key“、“server.crt“和“ca.crt“复制到“cert“目录下。

## 步骤三：修改配置文件<a name="zh-cn_topic_0000001399625106_zh-cn_topic_0000001355818953_zh-cn_topic_0000001124401671_zh-cn_topic_0171809252_section5388193419188"></a>

>![](public_sys-resources/icon-notice.gif) **须知：** 
>修改配置文件前，请将配置文件进行备份，并建议先在测试环境中进行部署，配置无误后，再在现网环境进行配置，避免出现配置错误导致服务不能正常启动等问题，影响您的业务。

1.  打开Apache根目录下“conf.d/ssl.conf“文件。
2.  配置证书绑定的域名。

    找到并修改如下参数：

    ```
    ServerName www.example.com:443 
    ```

    完整配置如下（以“www.domain.com“为例）：

    ```
    ServerName www.domain.com:443 #用户服务器的域名
    ```

3.  配置证书公钥。

    找到并修改如下参数：

    ```
    SSLCertificateFile "${SRVROOT}/conf/server.crt" 
    ```

    设置证书公钥文件“server.crt“文件的路径，且路径中不能包含中文字符，例如“cert/server.crt“。

    完整配置如下：

    ```
    SSLCertificateFile "cert/server.crt"
    ```

4.  配置证书私钥。

    找到并修改如下参数：

    ```
    SSLCertificateKeyFile "${SRVROOT}/conf/server.key" 
    ```

    设置为“server.key“文件的路径，且路径中不能包含中文字符，例如“cert/server.key“。

    完整配置如下：

    ```
    SSLCertificateKeyFile "cert/server.key"
    ```

5.  配置证书链。

    找到并修改如下参数：

    ```
    #SSLCertificateChainFile "${SRVROOT}/conf/server-ca.crt" 
    ```

    删除行首的配置语句注释符号“\#“，并设置为“ca.crt“文件的路径，且路径中不能包含中文字符，例如“cert/ca.crt“。

    完整配置如下：

    ```
    SSLCertificateChainFile "cert/ca.crt"
    ```

6.  修改后，保存“ssl.conf“文件并退出编辑。

## 步骤四：重启Apache<a name="zh-cn_topic_0000001399625106_zh-cn_topic_0000001355818953_zh-cn_topic_0000001124401671_zh-cn_topic_0171809252_section19278184418180"></a>

执行以下操作重启Apache，使配置生效。

1.  执行**service httpd stop**命令停止Apache服务。
2.  执行**service httpd start**命令启动Apache服务。

## 效果验证<a name="zh-cn_topic_0000001399625106_zh-cn_topic_0000001355818953_zh-cn_topic_0000001124217601_zh-cn_topic_0171809251_section17691911165112"></a>

部署成功后，可在浏览器的地址栏中输入“https://域名“，按“Enter“。

如果浏览器地址栏显示安全锁标识，则说明证书安装成功。

-   如果网站仍然出现不安全提示，请参见[为什么部署了SSL证书后，网站仍然出现不安全提示？](https://support.huaweicloud.com/ccm_faq/ccm_01_0098.html)。
-   如果通过域名访问网站时，无法打开网站，请参见[为什么部署了SSL证书后，通过域名访问网站时，无法打开网站？](https://support.huaweicloud.com/ccm_faq/ccm_01_0099.html)进行处理。
-   如果仍未解决或出现其他问题，华为云市场提供SSL证书配置优化服务，专业工程师一对一服务，请直接单击[一对一咨询](https://marketplace.huaweicloud.com/contents/917d16b0-33c4-49d3-bfe9-dd9219ea084e#productid=00301-120142-0--0)进行购买，购买服务后，联系工程师进行处理。

