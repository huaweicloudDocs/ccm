# 上传CSR<a name="ccm_01_0364"></a>

如您在申请证书时需要使用未在云证书管理服务控制台创建的CSR，可参考本章节上传已有的CSR，并对其进行统一管理。

## 操作步骤<a name="section928822891317"></a>

1.  登录[管理控制台](https://console.huaweicloud.com/)。
2.  单击页面左上方的![](figures/icon-servicelist-15.png)，选择“安全与合规  \>  云证书管理服务“，进入云证书管理界面。
3.  在左侧导航栏选择“SSL证书管理 \>SSL证书证书列表 \> CSR管理“，进入CSR管理界面。
4.  单击“上传CSR“。
5.  在弹出页面单击上传，分别上传证书文件和证书私钥，如[图 上传CSR](#fig126205271517)。

    **图 1**  上传CSR<a name="fig126205271517"></a>  
    ![](figures/上传CSR.png "上传CSR")

    **表 1**  参数说明

    <a name="table081472220176"></a>
    <table><thead align="left"><tr id="row6814202221710"><th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.1"><p id="p148151422111710"><a name="p148151422111710"></a><a name="p148151422111710"></a>参数名称</p>
    </th>
    <th class="cellrowborder" valign="top" width="50%" id="mcps1.2.3.1.2"><p id="p1881552214176"><a name="p1881552214176"></a><a name="p1881552214176"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row178156226178"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p98151722161710"><a name="p98151722161710"></a><a name="p98151722161710"></a>CSR名称</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p10610256786"><a name="p10610256786"></a><a name="p10610256786"></a>为创建的CSR自定义一个名称。</p>
    <p id="p26101056389"><a name="p26101056389"></a><a name="p26101056389"></a>支持使用英文大小写字母（a~z和A~Z）、阿拉伯数字（0~9）、下划线（_）、短划线（-）。长度不超过50个字符。</p>
    </td>
    </tr>
    <tr id="row1881562271717"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p581510221173"><a name="p581510221173"></a><a name="p581510221173"></a>证书文件</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p1881552218173"><a name="p1881552218173"></a><a name="p1881552218173"></a>上传目标CSR文件</p>
    <p id="p1886092320198"><a name="p1886092320198"></a><a name="p1886092320198"></a>单击文本框下的<span class="uicontrol" id="uicontrol11509489207"><a name="uicontrol11509489207"></a><a name="uicontrol11509489207"></a>“上传”</span>并选择存储在本地计算机的CSR文件，将文件内容上传到文本框。</p>
    </td>
    </tr>
    <tr id="row1581512261715"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.1 "><p id="p10815102201716"><a name="p10815102201716"></a><a name="p10815102201716"></a>证书私钥</p>
    </td>
    <td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.3.1.2 "><p id="p281562212174"><a name="p281562212174"></a><a name="p281562212174"></a>上传证书私钥文件</p>
    <p id="p37313215214"><a name="p37313215214"></a><a name="p37313215214"></a>单击文本框下的<span class="uicontrol" id="uicontrol199511221102115"><a name="uicontrol199511221102115"></a><a name="uicontrol199511221102115"></a>“上传”</span>并选择存储在本地计算机的证书私钥文件，将文件内容上传到文本框。</p>
    </td>
    </tr>
    </tbody>
    </table>

6.  单击“确定“完成CSR上传。

## 后续操作<a name="section141741670105"></a>

-   完成上传CSR后，您可以在CSR列表 查看已上传的CSR详情。
-   后续您在提交证书申请时，可以将**CSR生成方式**设置为**选择已有的CSR**并从匹配到的CSR中选择目标CSR。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >您还可以在CSR列表的操作栏对现有CSR进行“编辑“和“删除“操作。
    >-   编辑操作仅支持修改CSR名称。
    >-   删除CSR后无法恢复，请谨慎操作。

