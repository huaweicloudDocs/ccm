# 方式二：手动DNS验证<a name="ccm_01_0078"></a>

按照CA中心的规范，如果您申请了SSL证书，则必须完成域名验证（又称验证域名所有权）来证明待申请证书要绑定的域名属于您。

手动DNS验证，是指您需要在域名的DNS解析服务商手动修改域名的DNS解析记录，在解析记录中添加一条用于验证的记录。CA机构验证添加的记录能被解析，则表示验证通过。

如果您在申请证书时域名验证方式选择了手动DNS验证，请参照本章节进行处理。

## 约束与限制<a name="zh-cn_topic_0000001169740848_section171131943135017"></a>

手动DNS验证的域名解析只能在您的域名管理平台上进行操作，具体的解析方法以域名服务商提供的解析方法为准。

## 前提条件<a name="section5476111517558"></a>

绑定的域名须做实名认证，如果未做实名认证，请前往您的域名服务商处完成域名实名认证。

## 步骤一：确认验证步骤<a name="section1373014169223"></a>

**DNS验证只能在域名管理平台（即您的域名托管平台）上进行解析**。请根据域名管理平台类型执行验证步骤：

<a name="table1119811962312"></a>
<table><thead align="left"><tr id="row0199169202316"><th class="cellrowborder" valign="top" width="20.06%" id="mcps1.1.3.1.1"><p id="p1419912915239"><a name="p1419912915239"></a><a name="p1419912915239"></a>域名管理平台类型</p>
</th>
<th class="cellrowborder" valign="top" width="79.94%" id="mcps1.1.3.1.2"><p id="p719979182318"><a name="p719979182318"></a><a name="p719979182318"></a>验证步骤</p>
</th>
</tr>
</thead>
<tbody><tr id="row01996932316"><td class="cellrowborder" valign="top" width="20.06%" headers="mcps1.1.3.1.1 "><p id="p15770122817407"><a name="p15770122817407"></a><a name="p15770122817407"></a>域名管理平台是华为云</p>
</td>
<td class="cellrowborder" valign="top" width="79.94%" headers="mcps1.1.3.1.2 "><p id="p519989142313"><a name="p519989142313"></a><a name="p519989142313"></a>继续执行后续所有步骤。</p>
</td>
</tr>
<tr id="row71991799233"><td class="cellrowborder" valign="top" width="20.06%" headers="mcps1.1.3.1.1 "><p id="p288664920408"><a name="p288664920408"></a><a name="p288664920408"></a>域名管理平台不是华为云</p>
</td>
<td class="cellrowborder" valign="top" width="79.94%" headers="mcps1.1.3.1.2 "><div class="p" id="p899533082414"><a name="p899533082414"></a><a name="p899533082414"></a>请确认是否愿意把域名从其他服务商迁移到华为云DNS？<a name="ul286223015245"></a><a name="ul286223015245"></a><ul id="ul286223015245"><li>是。请执行以下操作步骤：<a name="ol11862330202419"></a><a name="ol11862330202419"></a><ol id="ol11862330202419"><li>请参见<a href="https://support.huaweicloud.com/dns_faq/dns_faq_001.html" target="_blank" rel="noopener noreferrer">怎样把域名从其他服务商迁移到华为云DNS？</a>，把域名从其他服务商迁移到华为云DNS。</li><li>继续执行后续所有步骤。</li></ol>
</li><li>否。请在相应的平台上进行DNS验证。例如，域名托管在阿里云，则需要到阿里云的云解析DNS控制台进行相关配置。</li></ul>
</div>
</td>
</tr>
</tbody>
</table>

## 步骤二：获取验证信息<a name="zh-cn_topic_0000001169740848_section7859163414285"></a>

1.  登录[管理控制台](https://console.huaweicloud.com/)。
2.  单击页面左上方的![](figures/icon-servicelist.png)，选择“安全与合规  \>  云证书管理服务“，进入云证书管理界面。
3.  在左侧导航栏选择“SSL证书管理“，并SSL证书页面中待域名验证的证书所在行的“操作“列，单击“域名验证“，系统从右面弹出域名验证详细页面。
4.  在证书的域名验证页面，查看并记录“主机记录“、“记录类型“和“记录值“，如[图1](#zh-cn_topic_0000001169740848_fig1272351623219)所示。

    如果界面未显示，则请登录邮箱（申请证书时填写的邮箱）进行查看。

    **图 1**  查看主机记录<a name="zh-cn_topic_0000001169740848_fig1272351623219"></a>  
    ![](figures/查看主机记录.png "查看主机记录")

## 步骤三：在华为云云解析服务上进行DNS验证<a name="zh-cn_topic_0000001169740848_section106621344202816"></a>

1.  登录[管理控制台](https://console.huaweicloud.com/)。
2.  选择“网络  \>  云解析服务“，并在云解析页面左侧导航栏，选择“公网域名“，进入“公网域名“页面。
3.  在“公网域名“页面的域名列表中，单击待添加记录集的域名，并在解析记录页面右上角单击“添加记录集“，进入“添加记录集“页面。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   不同域名类型的证书做DNS验证时，需要添加记录集的域名如下：
    >    -   单域名证书，为证书绑定的域名添加记录集（域名带www时例外，域名带www时为其上一级域名添加记录集。例如证书绑定的域名为www.example.com，为域名example.com添加记录集）。
    >    -   多域名证书，需要为证书绑定的所有域名添加记录集。
    >    -   泛域名证书，为泛域名相应的上一级域名添加记录集。
    >        例如：证书绑定的域名为\*.example.com，只需为域名example.com添加记录集。
    >-   如果在“解析记录“的域名列表中，已存在带解析域名且相同记录类型的记录值，直接在目标域名的“操作“列，单击“修改“，进入“修改记录集“页面。

    **图 2**  添加记录集<a name="zh-cn_topic_0000001169740848_fig714610206552"></a>  
    ![](figures/添加记录集.png "添加记录集")

    **表 1**  添加记录集参数说明

    <a name="zh-cn_topic_0000001169740848_table14460150102412"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0000001169740848_row18461150152415"><th class="cellrowborder" valign="top" width="19.57%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0000001169740848_p1146112062417"><a name="zh-cn_topic_0000001169740848_p1146112062417"></a><a name="zh-cn_topic_0000001169740848_p1146112062417"></a>参数名称</p>
    </th>
    <th class="cellrowborder" valign="top" width="80.43%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0000001169740848_p1346116092415"><a name="zh-cn_topic_0000001169740848_p1346116092415"></a><a name="zh-cn_topic_0000001169740848_p1346116092415"></a>参数说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0000001169740848_row14461140172417"><td class="cellrowborder" valign="top" width="19.57%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0000001169740848_p1746150132411"><a name="zh-cn_topic_0000001169740848_p1746150132411"></a><a name="zh-cn_topic_0000001169740848_p1746150132411"></a><strong id="zh-cn_topic_0000001169740848_b48623202716"><a name="zh-cn_topic_0000001169740848_b48623202716"></a><a name="zh-cn_topic_0000001169740848_b48623202716"></a>主机记录</strong></p>
    </td>
    <td class="cellrowborder" valign="top" width="80.43%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0000001169740848_p1946115082413"><a name="zh-cn_topic_0000001169740848_p1946115082413"></a><a name="zh-cn_topic_0000001169740848_p1946115082413"></a>证书的<span class="wintitle" id="zh-cn_topic_0000001169740848_wintitle109021113112510"><a name="zh-cn_topic_0000001169740848_wintitle109021113112510"></a><a name="zh-cn_topic_0000001169740848_wintitle109021113112510"></a>“域名验证”</span>页面，域名服务商返回的<span class="parmname" id="zh-cn_topic_0000001169740848_parmname157969311523"><a name="zh-cn_topic_0000001169740848_parmname157969311523"></a><a name="zh-cn_topic_0000001169740848_parmname157969311523"></a>“主机记录”</span>。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0000001169740848_row346119011242"><td class="cellrowborder" valign="top" width="19.57%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0000001169740848_p1946117012414"><a name="zh-cn_topic_0000001169740848_p1946117012414"></a><a name="zh-cn_topic_0000001169740848_p1946117012414"></a><strong id="zh-cn_topic_0000001169740848_b934916613275"><a name="zh-cn_topic_0000001169740848_b934916613275"></a><a name="zh-cn_topic_0000001169740848_b934916613275"></a>类型</strong></p>
    </td>
    <td class="cellrowborder" valign="top" width="80.43%" headers="mcps1.2.3.1.2 "><p id="p118571424141418"><a name="p118571424141418"></a><a name="p118571424141418"></a>证书的<span class="wintitle" id="wintitle2768124619219"><a name="wintitle2768124619219"></a><a name="wintitle2768124619219"></a>“域名验证”</span>页面，域名服务商返回的<span class="parmname" id="parmname126971454172112"><a name="parmname126971454172112"></a><a name="parmname126971454172112"></a>“记录类型”</span>。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0000001169740848_row2814104310328"><td class="cellrowborder" valign="top" width="19.57%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0000001169740848_p1781514316327"><a name="zh-cn_topic_0000001169740848_p1781514316327"></a><a name="zh-cn_topic_0000001169740848_p1781514316327"></a>别名</p>
    </td>
    <td class="cellrowborder" valign="top" width="80.43%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0000001169740848_p15815743133213"><a name="zh-cn_topic_0000001169740848_p15815743133213"></a><a name="zh-cn_topic_0000001169740848_p15815743133213"></a>选择“否”。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0000001169740848_row19461905246"><td class="cellrowborder" valign="top" width="19.57%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0000001169740848_p64611306244"><a name="zh-cn_topic_0000001169740848_p64611306244"></a><a name="zh-cn_topic_0000001169740848_p64611306244"></a>线路类型</p>
    </td>
    <td class="cellrowborder" valign="top" width="80.43%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0000001169740848_p1646117019243"><a name="zh-cn_topic_0000001169740848_p1646117019243"></a><a name="zh-cn_topic_0000001169740848_p1646117019243"></a>选择“全网默认”。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0000001169740848_row134611801240"><td class="cellrowborder" valign="top" width="19.57%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0000001169740848_p94611012419"><a name="zh-cn_topic_0000001169740848_p94611012419"></a><a name="zh-cn_topic_0000001169740848_p94611012419"></a>TTL (秒)</p>
    </td>
    <td class="cellrowborder" valign="top" width="80.43%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0000001169740848_p2461160192417"><a name="zh-cn_topic_0000001169740848_p2461160192417"></a><a name="zh-cn_topic_0000001169740848_p2461160192417"></a>一般建议设置为5分钟。TTL值越大，则DNS记录的同步和更新越慢。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0000001169740848_row5360938132418"><td class="cellrowborder" valign="top" width="19.57%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0000001169740848_p12361138192410"><a name="zh-cn_topic_0000001169740848_p12361138192410"></a><a name="zh-cn_topic_0000001169740848_p12361138192410"></a><strong id="zh-cn_topic_0000001169740848_b131981198274"><a name="zh-cn_topic_0000001169740848_b131981198274"></a><a name="zh-cn_topic_0000001169740848_b131981198274"></a>值</strong></p>
    </td>
    <td class="cellrowborder" valign="top" width="80.43%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0000001169740848_p123611038122410"><a name="zh-cn_topic_0000001169740848_p123611038122410"></a><a name="zh-cn_topic_0000001169740848_p123611038122410"></a>证书的<span class="wintitle" id="zh-cn_topic_0000001169740848_wintitle192041759142510"><a name="zh-cn_topic_0000001169740848_wintitle192041759142510"></a><a name="zh-cn_topic_0000001169740848_wintitle192041759142510"></a>“域名验证”</span>页面，域名服务商返回的<span class="parmname" id="zh-cn_topic_0000001169740848_parmname020435902510"><a name="zh-cn_topic_0000001169740848_parmname020435902510"></a><a name="zh-cn_topic_0000001169740848_parmname020435902510"></a>“记录值”</span>。</p>
    <div class="note" id="zh-cn_topic_0000001169740848_note15306172610266"><a name="zh-cn_topic_0000001169740848_note15306172610266"></a><a name="zh-cn_topic_0000001169740848_note15306172610266"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="zh-cn_topic_0000001169740848_p9306226182610"><a name="zh-cn_topic_0000001169740848_p9306226182610"></a><a name="zh-cn_topic_0000001169740848_p9306226182610"></a>记录值必须用英文引号引用后粘贴在文本框中。</p>
    </div></div>
    </td>
    </tr>
    <tr id="zh-cn_topic_0000001169740848_row10837134414246"><td class="cellrowborder" colspan="2" valign="top" headers="mcps1.2.3.1.1 mcps1.2.3.1.2 "><p id="zh-cn_topic_0000001169740848_p7837944142410"><a name="zh-cn_topic_0000001169740848_p7837944142410"></a><a name="zh-cn_topic_0000001169740848_p7837944142410"></a>其他的设置保持不变。</p>
    </td>
    </tr>
    </tbody>
    </table>

4.  单击“确定“，记录集添加成功。

    当记录集的状态显示为“正常“时，表示记录集添加成功。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >该记录集在证书签发后才可以删除。

## 步骤四：查看域名验证是否生效<a name="zh-cn_topic_0000001169740848_section19224220112912"></a>

1.  在Windows系统中，单击“开始“，输入“cmd“，进入命令提示符对话框。
2.  根据不同的记录类型，选择执行[表 验证命令](#table1424551951911)所示命令，查看DNS验证配置是否已经生效。

    **表 2**  验证命令

    <a name="table1424551951911"></a>
    <table><thead align="left"><tr id="row924661921912"><th class="cellrowborder" valign="top" width="23.630000000000003%" id="mcps1.2.3.1.1"><p id="p11246121913198"><a name="p11246121913198"></a><a name="p11246121913198"></a>记录类型</p>
    </th>
    <th class="cellrowborder" valign="top" width="76.37%" id="mcps1.2.3.1.2"><p id="p1424619197195"><a name="p1424619197195"></a><a name="p1424619197195"></a>验证命令</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row1624611961920"><td class="cellrowborder" valign="top" width="23.630000000000003%" headers="mcps1.2.3.1.1 "><p id="p024610198197"><a name="p024610198197"></a><a name="p024610198197"></a>TXT</p>
    </td>
    <td class="cellrowborder" valign="top" width="76.37%" headers="mcps1.2.3.1.2 "><p id="p946135018212"><a name="p946135018212"></a><a name="p946135018212"></a><b><span class="cmdname" id="cmdname64611850132113"><a name="cmdname64611850132113"></a><a name="cmdname64611850132113"></a>nslookup -q=TXT</span></b> <i><span class="varname" id="varname13461125072114"><a name="varname13461125072114"></a><a name="varname13461125072114"></a>xxx</span></i></p>
    </td>
    </tr>
    <tr id="row1024611193197"><td class="cellrowborder" valign="top" width="23.630000000000003%" headers="mcps1.2.3.1.1 "><p id="p12461219131913"><a name="p12461219131913"></a><a name="p12461219131913"></a>CNAME</p>
    </td>
    <td class="cellrowborder" valign="top" width="76.37%" headers="mcps1.2.3.1.2 "><p id="p189905492117"><a name="p189905492117"></a><a name="p189905492117"></a><b><span class="cmdname" id="cmdname1189985416212"><a name="cmdname1189985416212"></a><a name="cmdname1189985416212"></a>nslookup -q=CNAME</span></b> <i><span class="varname" id="varname5899105416219"><a name="varname5899105416219"></a><a name="varname5899105416219"></a>xxx</span></i></p>
    </td>
    </tr>
    </tbody>
    </table>

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >_xxx_代表域名服务商返回的“主机记录“值。

    -   如果界面回显的记录值（text的值）与域名服务商返回的“记录值“一致，如[图3](#zh-cn_topic_0000001169740848_fig1141255248)所示，说明域名授权验证配置已经生效。

        **图 3**  域名授权验证配置生效<a name="zh-cn_topic_0000001169740848_fig1141255248"></a>  
        ![](figures/域名授权验证配置生效.png "域名授权验证配置生效")

    -   如果界面未回显记录值，显示为“Non-existent domain“，说明域名授权验证配置未生效。

        **图 4**  域名授权验证配置未生效<a name="zh-cn_topic_0000001169740848_fig9346102419212"></a>  
        ![](figures/域名授权验证配置未生效.png "域名授权验证配置未生效")

3.  如果DNS验证配置未生效，请根据以下可能原因进行排除修改，直至验证生效。

    **表 3**  排查处理

    <a name="zh-cn_topic_0000001169740848_table628812514416"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0000001169740848_row1828919251041"><th class="cellrowborder" valign="top" width="28.939999999999998%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0000001169740848_p1228919253413"><a name="zh-cn_topic_0000001169740848_p1228919253413"></a><a name="zh-cn_topic_0000001169740848_p1228919253413"></a>可能原因</p>
    </th>
    <th class="cellrowborder" valign="top" width="71.06%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0000001169740848_p528917253414"><a name="zh-cn_topic_0000001169740848_p528917253414"></a><a name="zh-cn_topic_0000001169740848_p528917253414"></a>处理方法</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row3835259114413"><td class="cellrowborder" valign="top" width="28.939999999999998%" headers="mcps1.2.3.1.1 "><p id="p1734010915319"><a name="p1734010915319"></a><a name="p1734010915319"></a>域名管理平台选择错误</p>
    </td>
    <td class="cellrowborder" valign="top" width="71.06%" headers="mcps1.2.3.1.2 "><p id="p2034011919312"><a name="p2034011919312"></a><a name="p2034011919312"></a>DNS验证只能在域名管理平台（即您的域名托管平台）上进行解析，请确认您进行DNS验证的平台是否为您的域名托管平台。</p>
    </td>
    </tr>
    <tr id="row72411331111615"><td class="cellrowborder" valign="top" width="28.939999999999998%" headers="mcps1.2.3.1.1 "><p id="p92421631161617"><a name="p92421631161617"></a><a name="p92421631161617"></a>旧解析记录未删除</p>
    </td>
    <td class="cellrowborder" valign="top" width="71.06%" headers="mcps1.2.3.1.2 "><p id="p1934537132118"><a name="p1934537132118"></a><a name="p1934537132118"></a>证书签发后添加的解析记录即可删除。</p>
    <p id="p82421231141615"><a name="p82421231141615"></a><a name="p82421231141615"></a>若您上一次申请证书时添加的解析记录未删除，本次申请证书添加的解析记录将不会生效，请您确认是否未删除上一次解析记录。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0000001169740848_row62896252047"><td class="cellrowborder" valign="top" width="28.939999999999998%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0000001169740848_p162891625847"><a name="zh-cn_topic_0000001169740848_p162891625847"></a><a name="zh-cn_topic_0000001169740848_p162891625847"></a>记录配置出错</p>
    </td>
    <td class="cellrowborder" valign="top" width="71.06%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0000001169740848_p2028917251146"><a name="zh-cn_topic_0000001169740848_p2028917251146"></a><a name="zh-cn_topic_0000001169740848_p2028917251146"></a>请您检查<span class="parmname" id="parmname6136112142417"><a name="parmname6136112142417"></a><a name="parmname6136112142417"></a>“主机记录”</span>、<span class="parmname" id="zh-cn_topic_0000001169740848_parmname179218391043"><a name="zh-cn_topic_0000001169740848_parmname179218391043"></a><a name="zh-cn_topic_0000001169740848_parmname179218391043"></a>“类型”</span>或<span class="parmname" id="zh-cn_topic_0000001169740848_parmname11925391545"><a name="zh-cn_topic_0000001169740848_parmname11925391545"></a><a name="zh-cn_topic_0000001169740848_parmname11925391545"></a>“记录值”</span>是否填写正确。</p>
    <div class="fignone" id="fig1777716535510"><a name="fig1777716535510"></a><a name="fig1777716535510"></a><span class="figcap"><b>图1 </b>配置记录</span><br><a name="zh-cn_topic_0000001169740848_image19510352341"></a><a name="zh-cn_topic_0000001169740848_image19510352341"></a><span><img id="zh-cn_topic_0000001169740848_image19510352341" src="figures/配置记录.png" height="182.21" width="332.5"></span></div>
    </td>
    </tr>
    <tr id="zh-cn_topic_0000001169740848_row1428962511415"><td class="cellrowborder" valign="top" width="28.939999999999998%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0000001169740848_p52891325940"><a name="zh-cn_topic_0000001169740848_p52891325940"></a><a name="zh-cn_topic_0000001169740848_p52891325940"></a>配置的生效时间过长，生效时间还未到，因此无法查询到数据。</p>
    </td>
    <td class="cellrowborder" valign="top" width="71.06%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0000001169740848_p1328919259410"><a name="zh-cn_topic_0000001169740848_p1328919259410"></a><a name="zh-cn_topic_0000001169740848_p1328919259410"></a>请您检查生效时间（TTL）是否设置过长，建议将生效时间修改为5分钟。不同的域名提供商的DNS配置不一样，如华为云的DNS（云解析服务）默认是5分钟后生效，如下图所示。</p>
    <p id="zh-cn_topic_0000001169740848_p189929331369"><a name="zh-cn_topic_0000001169740848_p189929331369"></a><a name="zh-cn_topic_0000001169740848_p189929331369"></a>若配置的生效时间未到，请等时间到了后再进行验证。</p>
    <div class="fignone" id="fig15300173714510"><a name="fig15300173714510"></a><a name="fig15300173714510"></a><span class="figcap"><b>图2 </b>生效时间</span><br><a name="zh-cn_topic_0000001169740848_image8639239852"></a><a name="zh-cn_topic_0000001169740848_image8639239852"></a><span><img id="zh-cn_topic_0000001169740848_image8639239852" src="figures/生效时间.png" height="246.74160000000003" width="266"></span></div>
    </td>
    </tr>
    </tbody>
    </table>

## 步骤五：DNS验证结果审核<a name="section122205195812"></a>

-   **OV、EV证书**

    按CA机构审核邮件要求完成验证后，请耐心等待，CA机构需要2-3个工作日对DNS验证信息进行审核，审核通过后，才会签发证书。

    如遇验证失败或其他问题，请根据CA机构审核邮件中提供的联系方式，与CA机构联系。

-   **DV证书**

    您可以在域名验证页面，手动验证结果。

    1.  登录[管理控制台](https://console.huaweicloud.com/)。
    2.  单击页面左上方的![](figures/icon-servicelist.png)，选择“安全与合规  \>  云证书管理服务“，进入云证书管理界面。
    3.  在左侧导航栏选择“SSL证书管理“，并SSL证书页面中待域名验证的证书所在行的“操作“列，单击“域名验证“，系统从右面弹出域名验证详细页面。
    4.  单击“验证“，验证DNS解析配置。
        -   界面提示“验证成功，证书签发审核中，请等待“：证书将在1分钟内签发，请您及时刷新页面查看证书状态。
        -   验证失败，请参照[DV证书DNS验证失败如何处理？](#section208510215313)排查并修改问题后，等待3-5分钟重新验证。

## DV证书DNS验证失败如何处理？<a name="section208510215313"></a>

<a name="table1851421134"></a>
<table><thead align="left"><tr id="row128501126313"><th class="cellrowborder" valign="top" width="24.26%" id="mcps1.1.3.1.1"><p id="p15850172236"><a name="p15850172236"></a><a name="p15850172236"></a>失败提示信息</p>
</th>
<th class="cellrowborder" valign="top" width="75.74%" id="mcps1.1.3.1.2"><p id="p9850625319"><a name="p9850625319"></a><a name="p9850625319"></a>解决方案</p>
</th>
</tr>
</thead>
<tbody><tr id="row385092932"><td class="cellrowborder" valign="top" width="24.26%" headers="mcps1.1.3.1.1 "><p id="p208501521936"><a name="p208501521936"></a><a name="p208501521936"></a>提交验证频繁，请稍后再试</p>
</td>
<td class="cellrowborder" valign="top" width="75.74%" headers="mcps1.1.3.1.2 "><p id="p1345211312433"><a name="p1345211312433"></a><a name="p1345211312433"></a>验证过于频繁，建议您等待3-5分钟后，执行验证操作。</p>
</td>
</tr>
<tr id="row15851722312"><td class="cellrowborder" valign="top" width="24.26%" headers="mcps1.1.3.1.1 "><p id="p208501215319"><a name="p208501215319"></a><a name="p208501215319"></a>DNS记录值不匹配</p>
</td>
<td class="cellrowborder" valign="top" width="75.74%" headers="mcps1.1.3.1.2 "><p id="p1385011218320"><a name="p1385011218320"></a><a name="p1385011218320"></a>您配置的DNS记录值不正确，请参照<a href="https://support.huaweicloud.com/usermanual-ccm/ccm_01_0078.html#section3" target="_blank" rel="noopener noreferrer">步骤二：获取验证信息</a>获取正确记录值后，重新配置。</p>
</td>
</tr>
<tr id="row9851821036"><td class="cellrowborder" valign="top" width="24.26%" headers="mcps1.1.3.1.1 "><p id="p7851921134"><a name="p7851921134"></a><a name="p7851921134"></a>DNS验证失败，请稍后再试。</p>
</td>
<td class="cellrowborder" valign="top" width="75.74%" headers="mcps1.1.3.1.2 "><p id="p1851122132"><a name="p1851122132"></a><a name="p1851122132"></a>请排查是否存在以下问题：</p>
<a name="ul3851328319"></a><a name="ul3851328319"></a><ul id="ul3851328319"><li>可能问题一：DNS记录值配置未生效。<p id="p7727193914162"><a name="p7727193914162"></a><a name="p7727193914162"></a>解决方案：DNS记录值配置完后不会立即生效（具体生效时间为您域名服务器中设置的TTL缓存时间），建议您等待3-5分钟后，执行验证操作。</p>
</li><li>可能问题二：DNS记录值正确配置，且一段时间后验证依然失败。<p id="p14680030141919"><a name="p14680030141919"></a><a name="p14680030141919"></a>解决方案：CA验证服务器位于国外，部分时间可能存在网络问题，导致验证DNS失败，请等待1-2小时，或尝试重新发起申请。</p>
</li><li>可能问题三：域名未完成备案或实名认证。<p id="p5851729316"><a name="p5851729316"></a><a name="p5851729316"></a>解决方案：请完成域名备案和实名认证后，进行域名所有权验证。</p>
</li><li>可能问题四：域名存在CAA类型的解析记录。<p id="p085192334"><a name="p085192334"></a><a name="p085192334"></a>解决方案：CAA记录会导致验证失败，您需要在域名解析记录中删除所有CAA类型的记录。</p>
</li><li>可能问题五：CA验证服务器没有检测到DNS解析记录。<p id="p185111213316"><a name="p185111213316"></a><a name="p185111213316"></a>解决方案：CA验证服务器位于国外，需要您放开该域名国外的访问限制。</p>
</li></ul>
</td>
</tr>
</tbody>
</table>

