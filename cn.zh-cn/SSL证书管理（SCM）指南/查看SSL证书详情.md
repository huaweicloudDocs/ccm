# 查看SSL证书详情<a name="ccm_01_0050"></a>

该任务指导用户查看已购买证书的详细信息，包括已购买的付费证书和测试证书以及上传的第三方证书。

您还可以参考本章节进行查看证书审核进度、修改证书名称和描述的操作，以及证书是否即将到期的提醒。托管中和已签发的证书到期前30天，云证书管理控制台在SSL证书列表的“状态/申请进度“栏会提示您有即将到期的证书。

## 前提条件<a name="zh-cn_topic_0000001124519785_zh-cn_topic_0110866182_section556861155951"></a>

已购买证书或者已上传原有证书。

## 操作步骤<a name="zh-cn_topic_0000001124519785_zh-cn_topic_0110866182_section408105191602"></a>

1.  登录[管理控制台](https://console.huaweicloud.com/)。
2.  单击页面左上方的![](figures/icon-servicelist.png)，选择“安全与合规  \>  云证书管理服务“，进入云证书管理界面。
3.  在左侧导航栏选择“SSL证书管理 \> SSL证书列表“，进入SSL证书列表页面。
4.  查看证书信息，如[图 证书列表](#fig6932559386)，证书参数说明如[表 证书参数说明](#table8938458380)所示。
    -   查看付费证书信息，请单击“SSL证书“页签。
    -   查看上传证书信息，请单击“上传证书“页签。
    -   查看测试证书信息，请单击“测试证书“页签。

        **图 1**  证书列表<a name="fig6932559386"></a>  
        ![](figures/证书列表.png "证书列表")

        >![](public_sys-resources/icon-note.gif) **说明：** 
        >-   在搜索栏选择证书筛选条件，并输入相应内容，单击或按“Enter“，可以搜索指定的证书。
        >-   单击证书名称，可以查看证书的详细信息。
        >-   托管中和已签发的证书到期前30天，云证书管理控制台在SSL证书列表的“状态/申请进度“栏会提示您有即将到期的证书。

        **表 1**  证书参数说明

        <a name="table8938458380"></a>
        <table><thead align="left"><tr id="row129330563817"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.3.1.1"><p id="p16933857387"><a name="p16933857387"></a><a name="p16933857387"></a>参数名称</p>
        </th>
        <th class="cellrowborder" valign="top" width="80%" id="mcps1.2.3.1.2"><p id="p1193316533813"><a name="p1193316533813"></a><a name="p1193316533813"></a>说明</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row893415173811"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p13933145143813"><a name="p13933145143813"></a><a name="p13933145143813"></a>证书名称</p>
        </td>
        <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p16934357388"><a name="p16934357388"></a><a name="p16934357388"></a>成功购买证书后，证书名称由系统自动生成，用户可以修改证书名称。具体操作请参见<a href="#zh-cn_topic_0000001124519785_zh-cn_topic_0110866182_section7550844182213">修改证书名称和描述</a>。</p>
        </td>
        </tr>
        <tr id="row1393475183815"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p79349511383"><a name="p79349511383"></a><a name="p79349511383"></a>绑定域名</p>
        </td>
        <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p209341652387"><a name="p209341652387"></a><a name="p209341652387"></a>证书绑定的域名信息。</p>
        </td>
        </tr>
        <tr id="row1593416519383"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p5934155163818"><a name="p5934155163818"></a><a name="p5934155163818"></a>证书类型</p>
        </td>
        <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p893414533818"><a name="p893414533818"></a><a name="p893414533818"></a>购买证书时选择的证书类型。</p>
        </td>
        </tr>
        <tr id="row1193455133817"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p12934145153811"><a name="p12934145153811"></a><a name="p12934145153811"></a>描述</p>
        </td>
        <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p1793420510386"><a name="p1793420510386"></a><a name="p1793420510386"></a>证书的补充信息，用户可以修改描述内容。具体操作请参见<a href="#zh-cn_topic_0000001124519785_zh-cn_topic_0110866182_section7550844182213">修改证书名称和描述</a>。</p>
        </td>
        </tr>
        <tr id="row1693410514383"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p7934135123817"><a name="p7934135123817"></a><a name="p7934135123817"></a>到期时间</p>
        </td>
        <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p493413583813"><a name="p493413583813"></a><a name="p493413583813"></a>证书到期的日期。</p>
        <div class="note" id="note7934135183819"><a name="note7934135183819"></a><a name="note7934135183819"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p49344515381"><a name="p49344515381"></a><a name="p49344515381"></a>已签发的证书，系统会在证书到期前两个月、一个月、一周、三天、一天和到期时，发送邮件和短信提醒用户。</p>
        </div></div>
        </td>
        </tr>
        <tr id="row393814513814"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p89355563812"><a name="p89355563812"></a><a name="p89355563812"></a>状态/申请进度</p>
        </td>
        <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p393515563818"><a name="p393515563818"></a><a name="p393515563818"></a>证书状态/申请进度说明如下：</p>
        <a name="ul69381652389"></a><a name="ul69381652389"></a><ul id="ul69381652389"><li>待申请<p id="p119356593812"><a name="p119356593812"></a><a name="p119356593812"></a>购买的证书需要提交域名和用户信息。具体操作请参见<a href="提交SSL证书申请.md">提交SSL证书申请</a>。</p>
        <p id="p193575113814"><a name="p193575113814"></a><a name="p193575113814"></a>申请进度为0%。</p>
        </li><li>待完成域名验证<p id="p179368520389"><a name="p179368520389"></a><a name="p179368520389"></a>已提交申请证书的请求，需要按照CA机构的要求完成域名授权验证。具体操作请参见<a href="域名验证.md">域名验证</a>。</p>
        <p id="p16936458387"><a name="p16936458387"></a><a name="p16936458387"></a>申请进度为40%。</p>
        </li><li>待完成组织验证<p id="p179367512386"><a name="p179367512386"></a><a name="p179367512386"></a>如果您申请的是OV或EV类型的证书，域名验证完成后，CA机构将还会确认组织是否发起了此次的证书订单申请。具体操作请参见<a href="组织验证（OV-EV）.md">组织验证（OV、EV）</a>。</p>
        <p id="p1393617543814"><a name="p1393617543814"></a><a name="p1393617543814"></a>申请进度为70%。</p>
        </li><li>即将签发<p id="p79361658388"><a name="p79361658388"></a><a name="p79361658388"></a>购买的证书已完成申请证书、域名验证和组织验证，正在等待CA机构签发证书。</p>
        <p id="p1293610513384"><a name="p1293610513384"></a><a name="p1293610513384"></a>申请进度为90%。</p>
        </li><li>已签发<p id="p1593665173818"><a name="p1593665173818"></a><a name="p1593665173818"></a>域名验证、组织验证成功以及用户信息验证通过。</p>
        <p id="p1593615517383"><a name="p1593615517383"></a><a name="p1593615517383"></a>申请进度为100%。</p>
        </li><li>审核失败<p id="p6936125183819"><a name="p6936125183819"></a><a name="p6936125183819"></a>用户信息验证失败。</p>
        </li><li>CA审核中（重签）<p id="p093713543816"><a name="p093713543816"></a><a name="p093713543816"></a>已签发的证书执行了重新签发操作，正在等待CA机构审核。具体操作请参见<a href="重新签发.md">重新签发</a>。</p>
        </li><li>CA审核中（追加域名）<p id="p3937195143814"><a name="p3937195143814"></a><a name="p3937195143814"></a>多域名证书已提交追加域名的申请，CA机构正在对新增的附加域名进行审核。具体操作请参见<a href="新增附加域名.md">新增附加域名</a>。</p>
        </li><li>CA审核中（撤回申请）<p id="p13937165203817"><a name="p13937165203817"></a><a name="p13937165203817"></a>购买的证书已提交撤回申请，正在等待CA机构审核。具体操作请参见<a href="撤回SSL证书申请.md">撤回证书申请</a>。</p>
        </li><li>CA审核中（吊销）<p id="p9937558387"><a name="p9937558387"></a><a name="p9937558387"></a>购买的证书已提交吊销申请，正在等待CA机构审核。</p>
        </li><li>已吊销<p id="p1593714553816"><a name="p1593714553816"></a><a name="p1593714553816"></a>证书已吊销。</p>
        </li><li>托管中<p id="p39371523811"><a name="p39371523811"></a><a name="p39371523811"></a>上传的证书的状态为托管中。</p>
        </li><li>已到期<p id="p1693835143818"><a name="p1693835143818"></a><a name="p1693835143818"></a>证书已到期。证书到期后无法续费，只能重新购买并申请新证书。</p>
        </li><li>吊销审核中（待域名验证）<p id="p14938350389"><a name="p14938350389"></a><a name="p14938350389"></a>已提交吊销证书的请求，需要按照CA机构的要求完成域名授权验证。</p>
        </li></ul>
        </td>
        </tr>
        <tr id="row8938185173819"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.3.1.1 "><p id="p1993815514387"><a name="p1993815514387"></a><a name="p1993815514387"></a>操作</p>
        </td>
        <td class="cellrowborder" valign="top" width="80%" headers="mcps1.2.3.1.2 "><p id="p1793895153820"><a name="p1793895153820"></a><a name="p1793895153820"></a>用户可以在操作栏中，执行申请证书、域名验证、组织验证、撤销申请等操作。</p>
        </td>
        </tr>
        </tbody>
        </table>

## 修改证书名称和描述<a name="zh-cn_topic_0000001124519785_zh-cn_topic_0110866182_section7550844182213"></a>

1.  登录[管理控制台](https://console.huaweicloud.com/)。
2.  单击页面左上方的![](figures/icon-servicelist.png)，选择“安全与合规  \>  云证书管理服务“，进入云证书管理界面。
3.  在左侧导航栏选择“SSL证书管理 \> SSL证书列表“，进入SSL证书列表页面。
4.  单击需要修改的证书名称，系统从右面弹出证书的详情页面。
5.  修改证书名称和描述。

    单击“证书名称“（或“描述“）栏后的![](figures/icon-edit.png)展开编辑框，在编辑框中输入证书名称（或描述信息）后，单击![](figures/icon-complete.png)保存修改的信息，页面右上角弹出“修改成功“，则说明修改证书名称（或描述信息）成功，如[图2](#zh-cn_topic_0000001124519785_zh-cn_topic_0110866182_fig989510710273)所示。

    >![](public_sys-resources/icon-caution.gif) **注意：** 
    >修改证书名称会造成账单实际出账名称和证书修改后名称不一致，请谨慎修改。

    **图 2**  修改证书名称和描述<a name="zh-cn_topic_0000001124519785_zh-cn_topic_0110866182_fig989510710273"></a>  
    ![](figures/修改证书名称和描述.png "修改证书名称和描述")

