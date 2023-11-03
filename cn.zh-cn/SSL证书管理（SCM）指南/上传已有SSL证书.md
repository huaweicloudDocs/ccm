# 上传已有SSL证书<a name="ccm_01_0011"></a>

您可以将您所拥有的SSL证书（已在其他平台购买并签发的SSL证书）上传到云证书管理平台，以便在云证书管理平台对您的证书进行统一管理。证书上传后，均支持证书下载、证书到期提醒设置，另外国际标准证书支持部署到华为云其他云产品。

该任务指导您如何在本地将外部SSL证书上传到云证书管理平台。

## 前提条件<a name="zh-cn_topic_0000001124401715_zh-cn_topic_0110866194_section2256777914731"></a>

已准备好需要上传证书的相关文件，具体如下：

-   PEM编码格式的证书文件（文件后缀是PEM或者CRT）
-   PEM编码格式的证书私钥文件（文件后缀是KEY）

>![](public_sys-resources/icon-note.gif) **说明：** 
>-   目前SSL证书管理平台只支持上传PEM格式的证书。其他格式的证书需要转化成PEM格式后才能上传，具体操作请参见[如何将证书格式转换为PEM格式？](https://support.huaweicloud.com/ccm_faq/ccm_01_0128.html)。
>    更多关于证书链的相关配置请参见[证书链配置说明](https://support.huaweicloud.com/ccm_faq/ccm_01_0106.html)。
>-   证书私钥需要是无密码保护的，更多详细介绍请参见[为什么要使用无密码保护的私钥？](https://support.huaweicloud.com/ccm_faq/ccm_01_0274.html)。
>-   上传的证书，SCM会在证书到期前30天提醒您证书即将到期，同时还支持配置消息提醒，设置后SSL证书管理系统会在证书到期前两个月、一个月、一周、三天、一天和到期时，发送邮件和短信提醒用户，具体配置操作请参见[如何配置SSL证书到期提醒？](https://support.huaweicloud.com/ccm_faq/ccm_01_0204.html)。

## 约束与限制<a name="section230519569423"></a>

不支持上传已过期的证书和证书链长度为1的证书。

## 操作步骤<a name="zh-cn_topic_0000001124401715_zh-cn_topic_0110866194_section2756238314925"></a>

1.  登录[管理控制台](https://console.huaweicloud.com/)。
2.  单击页面左上方的![](figures/icon-servicelist.png)，选择“安全与合规  \>  云证书管理服务“，进入云证书管理界面。
3.  在左侧导航栏选择“SSL证书管理 \> SSL证书列表“，进入SSL证书列表页面。
4.  在证书列表左上角，单击“上传原有证书“，进入“上传原有证书“界面。
5.  在“上传原有证书“对话框中，输入证书信息，如[图1](#zh-cn_topic_0000001124401715_zh-cn_topic_0110866194_fig17246889161023)所示，上传国际标准证书参数说明如[表 上传国际标准证书参数说明](#table8942124473317)所示，上传国密（SM）证书参数说明如[表 上传国密（SM）证书参数说明](#table11493101615154)所示。

    **图 1**  上传原有证书<a name="zh-cn_topic_0000001124401715_zh-cn_topic_0110866194_fig17246889161023"></a>  
    ![](figures/上传原有证书.png "上传原有证书")

    **表 1**  上传国际标准证书参数说明

    <a name="table8942124473317"></a>
    <table><thead align="left"><tr id="row13942244113317"><th class="cellrowborder" valign="top" width="18.8%" id="mcps1.2.3.1.1"><p id="p59433445337"><a name="p59433445337"></a><a name="p59433445337"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="81.2%" id="mcps1.2.3.1.2"><p id="p49439448336"><a name="p49439448336"></a><a name="p49439448336"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row16943104463313"><td class="cellrowborder" valign="top" width="18.8%" headers="mcps1.2.3.1.1 "><p id="p1094317444331"><a name="p1094317444331"></a><a name="p1094317444331"></a>证书标准</p>
    </td>
    <td class="cellrowborder" valign="top" width="81.2%" headers="mcps1.2.3.1.2 "><p id="p16943144433314"><a name="p16943144433314"></a><a name="p16943144433314"></a>选择国际标准证书。</p>
    </td>
    </tr>
    <tr id="row6943144420335"><td class="cellrowborder" valign="top" width="18.8%" headers="mcps1.2.3.1.1 "><p id="p179431144153318"><a name="p179431144153318"></a><a name="p179431144153318"></a>证书名称</p>
    </td>
    <td class="cellrowborder" valign="top" width="81.2%" headers="mcps1.2.3.1.2 "><p id="p1943124412337"><a name="p1943124412337"></a><a name="p1943124412337"></a>用户自定义。</p>
    </td>
    </tr>
    <tr id="row1794414413320"><td class="cellrowborder" valign="top" width="18.8%" headers="mcps1.2.3.1.1 "><p id="p1594414412336"><a name="p1594414412336"></a><a name="p1594414412336"></a>企业项目</p>
    </td>
    <td class="cellrowborder" valign="top" width="81.2%" headers="mcps1.2.3.1.2 "><p id="p1094454423315"><a name="p1094454423315"></a><a name="p1094454423315"></a>将上传的SSL证书分配至对应的企业项目中。</p>
    </td>
    </tr>
    <tr id="row39447444337"><td class="cellrowborder" valign="top" width="18.8%" headers="mcps1.2.3.1.1 "><p id="p494414443316"><a name="p494414443316"></a><a name="p494414443316"></a>证书文件</p>
    </td>
    <td class="cellrowborder" valign="top" width="81.2%" headers="mcps1.2.3.1.2 "><p id="p14944164418333"><a name="p14944164418333"></a><a name="p14944164418333"></a>以文本方式打开待上传证书里的PEM格式的文件（后缀名为<span class="parmvalue" id="parmvalue159444449336"><a name="parmvalue159444449336"></a><a name="parmvalue159444449336"></a>“.pem”</span>），将证书内容复制到此处。</p>
    <p id="p1794419446335"><a name="p1794419446335"></a><a name="p1794419446335"></a>按照“服务器证书-证书链”的顺序依次排列上传。具体方法请参见<a href="https://support.huaweicloud.com/ccm_faq/ccm_01_0187.html" target="_blank" rel="noopener noreferrer">如何上传证书文件？</a>。</p>
    </td>
    </tr>
    <tr id="row169441644123318"><td class="cellrowborder" valign="top" width="18.8%" headers="mcps1.2.3.1.1 "><p id="p1094434433313"><a name="p1094434433313"></a><a name="p1094434433313"></a>证书私钥</p>
    </td>
    <td class="cellrowborder" valign="top" width="81.2%" headers="mcps1.2.3.1.2 "><p id="p594454413320"><a name="p594454413320"></a><a name="p594454413320"></a>以文本方式打开待上传证书里的KEY格式的文件（后缀名为<span class="parmvalue" id="parmvalue1994454493318"><a name="parmvalue1994454493318"></a><a name="parmvalue1994454493318"></a>“.key”</span>），将私钥内容复制到此处。</p>
    </td>
    </tr>
    </tbody>
    </table>

    **表 2**  上传国密（SM）证书参数说明

    <a name="table11493101615154"></a>
    <table><thead align="left"><tr id="row15494151615151"><th class="cellrowborder" valign="top" width="18.8%" id="mcps1.2.3.1.1"><p id="p1149416160151"><a name="p1149416160151"></a><a name="p1149416160151"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="81.2%" id="mcps1.2.3.1.2"><p id="p2049471631519"><a name="p2049471631519"></a><a name="p2049471631519"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row16330845112018"><td class="cellrowborder" valign="top" width="18.8%" headers="mcps1.2.3.1.1 "><p id="p8331645142013"><a name="p8331645142013"></a><a name="p8331645142013"></a>证书标准</p>
    </td>
    <td class="cellrowborder" valign="top" width="81.2%" headers="mcps1.2.3.1.2 "><p id="p533119453204"><a name="p533119453204"></a><a name="p533119453204"></a>选择国密（SM）证书。</p>
    </td>
    </tr>
    <tr id="row949451601513"><td class="cellrowborder" valign="top" width="18.8%" headers="mcps1.2.3.1.1 "><p id="p149431617155"><a name="p149431617155"></a><a name="p149431617155"></a>证书名称</p>
    </td>
    <td class="cellrowborder" valign="top" width="81.2%" headers="mcps1.2.3.1.2 "><p id="p249515162157"><a name="p249515162157"></a><a name="p249515162157"></a>用户自定义。</p>
    </td>
    </tr>
    <tr id="row849515163150"><td class="cellrowborder" valign="top" width="18.8%" headers="mcps1.2.3.1.1 "><p id="p649571691520"><a name="p649571691520"></a><a name="p649571691520"></a>企业项目</p>
    </td>
    <td class="cellrowborder" valign="top" width="81.2%" headers="mcps1.2.3.1.2 "><p id="p24951416171516"><a name="p24951416171516"></a><a name="p24951416171516"></a>将上传的SSL证书分配至对应的企业项目中。</p>
    </td>
    </tr>
    <tr id="row174951416121510"><td class="cellrowborder" valign="top" width="18.8%" headers="mcps1.2.3.1.1 "><p id="p4495131691513"><a name="p4495131691513"></a><a name="p4495131691513"></a>签名证书</p>
    </td>
    <td class="cellrowborder" valign="top" width="81.2%" headers="mcps1.2.3.1.2 "><p id="p1049611613150"><a name="p1049611613150"></a><a name="p1049611613150"></a>以文本方式打开待上传证书里的签名证书PEM格式的文件（后缀名为<span class="parmvalue" id="parmvalue1149651681519"><a name="parmvalue1149651681519"></a><a name="parmvalue1149651681519"></a>“.pem”</span>），将证书内容复制到此处。</p>
    <p id="p449610164156"><a name="p449610164156"></a><a name="p449610164156"></a>按照“服务器证书-证书链”的顺序依次排列上传。具体方法请参见<a href="https://support.huaweicloud.com/ccm_faq/ccm_01_0187.html" target="_blank" rel="noopener noreferrer">如何上传证书文件？</a>。</p>
    </td>
    </tr>
    <tr id="row1049612164159"><td class="cellrowborder" valign="top" width="18.8%" headers="mcps1.2.3.1.1 "><p id="p1910144291716"><a name="p1910144291716"></a><a name="p1910144291716"></a>签名私钥</p>
    </td>
    <td class="cellrowborder" valign="top" width="81.2%" headers="mcps1.2.3.1.2 "><p id="p549681651512"><a name="p549681651512"></a><a name="p549681651512"></a>以文本方式打开待上传证书里的签名私钥KEY格式的文件（后缀名为<span class="parmvalue" id="parmvalue11496161613150"><a name="parmvalue11496161613150"></a><a name="parmvalue11496161613150"></a>“.key”</span>），将私钥复制到此处。</p>
    </td>
    </tr>
    <tr id="row16801195721717"><td class="cellrowborder" valign="top" width="18.8%" headers="mcps1.2.3.1.1 "><p id="p188021957141712"><a name="p188021957141712"></a><a name="p188021957141712"></a>加密证书</p>
    </td>
    <td class="cellrowborder" valign="top" width="81.2%" headers="mcps1.2.3.1.2 "><p id="p17946035122320"><a name="p17946035122320"></a><a name="p17946035122320"></a>以文本方式打开待上传证书里的加密证书PEM格式的文件（后缀名为<span class="parmvalue" id="parmvalue189461835112310"><a name="parmvalue189461835112310"></a><a name="parmvalue189461835112310"></a>“.pem”</span>），将证书内容复制到此处。</p>
    <p id="p862317470237"><a name="p862317470237"></a><a name="p862317470237"></a>此处无需上传证书链。</p>
    </td>
    </tr>
    <tr id="row6756144310181"><td class="cellrowborder" valign="top" width="18.8%" headers="mcps1.2.3.1.1 "><p id="p167562431182"><a name="p167562431182"></a><a name="p167562431182"></a>加密私钥</p>
    </td>
    <td class="cellrowborder" valign="top" width="81.2%" headers="mcps1.2.3.1.2 "><p id="p663913455229"><a name="p663913455229"></a><a name="p663913455229"></a>以文本方式打开待上传证书里的加密私钥KEY格式的文件（后缀名为<span class="parmvalue" id="parmvalue463910458228"><a name="parmvalue463910458228"></a><a name="parmvalue463910458228"></a>“.key”</span>），将私钥内容复制到此处。</p>
    </td>
    </tr>
    </tbody>
    </table>

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   上传的原有证书和密钥必须是一一对应的。
    >-   保证私钥无密码保护，更多详细介绍请参见[为什么要使用无密码保护的私钥？](https://support.huaweicloud.com/ccm_faq/ccm_01_0274.html)。

6.  单击“确定“，完成上传证书。

    证书上传成功，证书列表中新增一条状态为“托管中“的证书。

    上传的国际标准证书可以部署到云产品中。

## 相关操作<a name="zh-cn_topic_0000001124401715_zh-cn_topic_0110866194_section7740135116176"></a>

上传国际标准证书可部署到华为云其他云产品中，具体操作请参见[部署国际标准SSL证书到华为云产品](部署国际标准SSL证书到华为云产品.md)。

