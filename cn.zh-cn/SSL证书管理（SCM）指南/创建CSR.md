# 创建CSR<a name="ccm_01_0363"></a>

## 操作步骤<a name="section959454310814"></a>

1.  登录[管理控制台](https://console.huaweicloud.com/)。
2.  单击页面左上方的![](figures/icon-servicelist-14.png)，选择“安全与合规  \>  云证书管理服务“，进入云证书管理界面。
3.  在左侧导航栏选择“SSL证书管理 \>SSL证书证书列表 \> CSR管理“，进入CSR管理界面。
4.  单击“创建CSR“。
5.  在弹出页面完成参数配置，如[图 创建CSR](#fig161011562080)。

    **图 1**  创建CSR<a name="fig161011562080"></a>  
    ![](figures/创建CSR.png "创建CSR")

    参数说明如[表 参数说明](#table661012561811)。

    **表 1**  参数说明

    <a name="table661012561811"></a>
    <table><thead align="left"><tr id="row18610956489"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p14610115613815"><a name="p14610115613815"></a><a name="p14610115613815"></a>参数名称</p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p061010562816"><a name="p061010562816"></a><a name="p061010562816"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row761019561982"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1061014561788"><a name="p1061014561788"></a><a name="p1061014561788"></a>CSR名称</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p10610256786"><a name="p10610256786"></a><a name="p10610256786"></a>为创建的CSR自定义一个名称。</p>
    <p id="p26101056389"><a name="p26101056389"></a><a name="p26101056389"></a>支持使用英文大小写字母（a~z和A~Z）、阿拉伯数字（0~9）、下划线（_）、短划线（-）。长度不超过50个字符。</p>
    </td>
    </tr>
    <tr id="row106113561286"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p1561185612812"><a name="p1561185612812"></a><a name="p1561185612812"></a>绑定域名/IP</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p461120568812"><a name="p461120568812"></a><a name="p461120568812"></a>填写要申请证书的域名。</p>
    <p id="p761118564812"><a name="p761118564812"></a><a name="p761118564812"></a>如果您想在提交证书申请时使用该CSR，必须确保证书绑定域名包含此处设置的域名。</p>
    <p id="p1961118561489"><a name="p1961118561489"></a><a name="p1961118561489"></a>示例：假设您在此处设置域名为huaweiyun.com，则证书申请中的证书绑定域名必须包含huaweiyun.com，才可以匹配到该CSR。</p>
    </td>
    </tr>
    <tr id="row8611556884"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p561185612815"><a name="p561185612815"></a><a name="p561185612815"></a>绑定附加域名</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p186115568810"><a name="p186115568810"></a><a name="p186115568810"></a>填写与已设置的域名共用一张证书的其他域名。支持填写多个域名，多域名之间使用半角逗号（,）分隔。</p>
    </td>
    </tr>
    <tr id="row18611195616811"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p176115563812"><a name="p176115563812"></a><a name="p176115563812"></a>密钥算法</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p7611756586"><a name="p7611756586"></a><a name="p7611756586"></a>选择密钥算法的类型。可选项：</p>
    <a name="ul126114569810"></a><a name="ul126114569810"></a><ul id="ul126114569810"><li>RSA_2048</li><li>RSA_3072</li><li>RSA_4096</li><li>EC_P256</li><li>EC_P384</li><li>SM2</li></ul>
    </td>
    </tr>
    <tr id="row126123566815"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p146120561782"><a name="p146120561782"></a><a name="p146120561782"></a>CSR用途</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p126123561282"><a name="p126123561282"></a><a name="p126123561282"></a>选择您生成的CSR用途。可选项：</p>
    <a name="ul166129567813"></a><a name="ul166129567813"></a><ul id="ul166129567813"><li>个人证书</li><li>企业证书</li></ul>
    </td>
    </tr>
    </tbody>
    </table>

6.  单击“确定“生成CSR。

## 后续操作<a name="section141741670105"></a>

-   完成创建CSR后，您可以在CSR列表 查看已创建的CSR详情。
-   后续您在提交证书申请时，可以将**CSR生成方式**设置为**选择已有的CSR**并从匹配到的CSR中选择目标CSR。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >您还可以在CSR列表的操作栏对现有CSR进行“编辑“和“删除“操作。
    >-   编辑操作仅支持修改CSR名称。
    >-   删除CSR后无法恢复，请谨慎操作。

