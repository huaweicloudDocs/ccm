# 创建私有CA<a name="ccm_01_0016"></a>

华为云云证书管理服务提供有PCA服务，可以帮助您通过简单的可视化操作，以低投入的方式创建企业内部CA并使用它签发证书。

本章节帮助您通过云证书管理控制台创建私有CA（支持创建根CA和从属CA）。

## 背景信息<a name="zh-cn_topic_0000001124217631_section3301940144516"></a>

-   私有CA分为根CA和从属CA（即中间CA或子CA），从属CA隶属于根CA，根CA下可以包含多个从属CA。
-   首次创建私有CA时，须先创建根CA。
-   每个用户可以创建100个CA，已计划删除的私有CA也将计入CA限制值内，直到计划删除CA执行删除为止。

## 前提条件<a name="section1120512435470"></a>

创建私有CA的帐号拥有“PCA FullAccess“权限。

## 操作步骤<a name="zh-cn_topic_0000001124217631_section6126131255913"></a>

1.  登录[管理控制台](https://console.huaweicloud.com/)。
2.  单击页面左上方的![](figures/服务列表.png)，选择“安全与合规  \>  云证书管理服务“，并在左侧导航栏选择“私有证书管理  \>  私有CA“进入私有CA管理界面。
3.  在私有CA列表右上角，单击“创建CA“，进入创建CA界面。
4.  配置私有CA信息。

    您需要配置“基本信息“、“证书唯一标识名称（DN）“、“企业项目“和“证书吊销配置“信息。

    1.  配置基本信息，如[\#ccm\_01\_0016/zh-cn\_topic\_0000001124217631\_fig19641142713913](#zh-cn_topic_0000001124217631_fig19641142713913)所示，参数说明如[表1](#zh-cn_topic_0000001124217631_table1577194719541)所示。

        ![](figures/zh-cn_image_0000001448746893.png)

        **表 1**  基本信息参数说明

        <a name="zh-cn_topic_0000001124217631_table1577194719541"></a>
        <table><thead align="left"><tr id="zh-cn_topic_0000001124217631_row1578447205416"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0000001124217631_zh-cn_topic_0195832400_p172511610548"><a name="zh-cn_topic_0000001124217631_zh-cn_topic_0195832400_p172511610548"></a><a name="zh-cn_topic_0000001124217631_zh-cn_topic_0195832400_p172511610548"></a>参数名称</p>
        </th>
        <th class="cellrowborder" valign="top" width="53.14%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0000001124217631_zh-cn_topic_0195832400_p202515620548"><a name="zh-cn_topic_0000001124217631_zh-cn_topic_0195832400_p202515620548"></a><a name="zh-cn_topic_0000001124217631_zh-cn_topic_0195832400_p202515620548"></a>参数说明</p>
        </th>
        <th class="cellrowborder" valign="top" width="21.86%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0000001124217631_zh-cn_topic_0195832400_p7291410182"><a name="zh-cn_topic_0000001124217631_zh-cn_topic_0195832400_p7291410182"></a><a name="zh-cn_topic_0000001124217631_zh-cn_topic_0195832400_p7291410182"></a>取值样例</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="zh-cn_topic_0000001124217631_row17864719549"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0000001124217631_p147944765417"><a name="zh-cn_topic_0000001124217631_p147944765417"></a><a name="zh-cn_topic_0000001124217631_p147944765417"></a>CA类型</p>
        </td>
        <td class="cellrowborder" valign="top" width="53.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0000001124217631_p191122154417"><a name="zh-cn_topic_0000001124217631_p191122154417"></a><a name="zh-cn_topic_0000001124217631_p191122154417"></a>选择待创建的私有证书颁发机构的类型。</p>
        <p id="zh-cn_topic_0000001124217631_p579154735419"><a name="zh-cn_topic_0000001124217631_p579154735419"></a><a name="zh-cn_topic_0000001124217631_p579154735419"></a>CA类型：</p>
        <a name="zh-cn_topic_0000001124217631_ul1015222311814"></a><a name="zh-cn_topic_0000001124217631_ul1015222311814"></a><ul id="zh-cn_topic_0000001124217631_ul1015222311814"><li>根CA：如果要建立新的CA层次结构，则选择此项。<div class="note" id="zh-cn_topic_0000001124217631_note89161927113110"><a name="zh-cn_topic_0000001124217631_note89161927113110"></a><a name="zh-cn_topic_0000001124217631_note89161927113110"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="zh-cn_topic_0000001124217631_p1291702718318"><a name="zh-cn_topic_0000001124217631_p1291702718318"></a><a name="zh-cn_topic_0000001124217631_p1291702718318"></a>首次创建私有CA，则须创建根CA。</p>
        </div></div>
        </li><li>从属CA：用于在现有的CA层次结构中增加新的层次。</li></ul>
        </td>
        <td class="cellrowborder" valign="top" width="21.86%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0000001124217631_p18790474546"><a name="zh-cn_topic_0000001124217631_p18790474546"></a><a name="zh-cn_topic_0000001124217631_p18790474546"></a>根CA</p>
        </td>
        </tr>
        <tr id="zh-cn_topic_0000001124217631_row37934714541"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0000001124217631_p77918479548"><a name="zh-cn_topic_0000001124217631_p77918479548"></a><a name="zh-cn_topic_0000001124217631_p77918479548"></a>密钥算法</p>
        </td>
        <td class="cellrowborder" valign="top" width="53.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0000001124217631_p14790477546"><a name="zh-cn_topic_0000001124217631_p14790477546"></a><a name="zh-cn_topic_0000001124217631_p14790477546"></a>选择密钥算法和密钥的位大小。</p>
        <a name="zh-cn_topic_0000001124217631_ul24361567148"></a><a name="zh-cn_topic_0000001124217631_ul24361567148"></a><ul id="zh-cn_topic_0000001124217631_ul24361567148"><li>RSA2048</li><li>RSA4096</li><li>EC256</li><li>EC384</li><li>SM2</li></ul>
        </td>
        <td class="cellrowborder" valign="top" width="21.86%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0000001124217631_p1579104745410"><a name="zh-cn_topic_0000001124217631_p1579104745410"></a><a name="zh-cn_topic_0000001124217631_p1579104745410"></a>RSA2048</p>
        </td>
        </tr>
        <tr id="zh-cn_topic_0000001124217631_row20796476545"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0000001124217631_p9791475542"><a name="zh-cn_topic_0000001124217631_p9791475542"></a><a name="zh-cn_topic_0000001124217631_p9791475542"></a>签名哈希算法</p>
        </td>
        <td class="cellrowborder" valign="top" width="53.14%" headers="mcps1.2.4.1.2 "><p id="p194315277611"><a name="p194315277611"></a><a name="p194315277611"></a><span class="parmname" id="parmname1143022718611"><a name="parmname1143022718611"></a><a name="parmname1143022718611"></a>“CA类型”</span>选择<span class="parmvalue" id="parmvalue174311327469"><a name="parmvalue174311327469"></a><a name="parmvalue174311327469"></a>“根CA”</span>时，显示该参数。</p>
        <p id="p196571798916"><a name="p196571798916"></a><a name="p196571798916"></a>当<span class="parmname" id="parmname8657179495"><a name="parmname8657179495"></a><a name="parmname8657179495"></a>“密钥算法”</span>选择<span class="parmvalue" id="parmvalue6657393919"><a name="parmvalue6657393919"></a><a name="parmvalue6657393919"></a>“SM2”</span>时，签名哈希算法默认为<span class="parmvalue" id="parmvalue146571791298"><a name="parmvalue146571791298"></a><a name="parmvalue146571791298"></a>“SM3”</span>无需进行选择。</p>
        <p id="zh-cn_topic_0000001124217631_p1679154712542"><a name="zh-cn_topic_0000001124217631_p1679154712542"></a><a name="zh-cn_topic_0000001124217631_p1679154712542"></a>当密钥算法选择非SM2时，可选择签名哈希算法：</p>
        <a name="zh-cn_topic_0000001124217631_ul716162091715"></a><a name="zh-cn_topic_0000001124217631_ul716162091715"></a><ul id="zh-cn_topic_0000001124217631_ul716162091715"><li>SHA256</li><li>SHA384</li><li>SHA512</li></ul>
        </td>
        <td class="cellrowborder" valign="top" width="21.86%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0000001124217631_p1279124785419"><a name="zh-cn_topic_0000001124217631_p1279124785419"></a><a name="zh-cn_topic_0000001124217631_p1279124785419"></a>SHA256</p>
        </td>
        </tr>
        <tr id="zh-cn_topic_0000001124217631_row2791475548"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0000001124217631_p4791847135410"><a name="zh-cn_topic_0000001124217631_p4791847135410"></a><a name="zh-cn_topic_0000001124217631_p4791847135410"></a>有效期</p>
        </td>
        <td class="cellrowborder" valign="top" width="53.14%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0000001124217631_p9791947105415"><a name="zh-cn_topic_0000001124217631_p9791947105415"></a><a name="zh-cn_topic_0000001124217631_p9791947105415"></a><span class="parmname" id="zh-cn_topic_0000001124217631_parmname876513191615"><a name="zh-cn_topic_0000001124217631_parmname876513191615"></a><a name="zh-cn_topic_0000001124217631_parmname876513191615"></a>“CA类型”</span>选择<span class="parmvalue" id="zh-cn_topic_0000001124217631_parmvalue176515191615"><a name="zh-cn_topic_0000001124217631_parmvalue176515191615"></a><a name="zh-cn_topic_0000001124217631_parmvalue176515191615"></a>“根CA”</span>时，显示该参数。</p>
        <p id="zh-cn_topic_0000001124217631_p221323317165"><a name="zh-cn_topic_0000001124217631_p221323317165"></a><a name="zh-cn_topic_0000001124217631_p221323317165"></a>选择私有证书颁发机构有效期，可选择最长有效期为30年。</p>
        </td>
        <td class="cellrowborder" valign="top" width="21.86%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0000001124217631_p37904705417"><a name="zh-cn_topic_0000001124217631_p37904705417"></a><a name="zh-cn_topic_0000001124217631_p37904705417"></a>3年</p>
        </td>
        </tr>
        </tbody>
        </table>

    2.  配置证书唯一标识名称（Distinguished Name，DN）信息，如[图1](#zh-cn_topic_0000001124217631_fig78301415114014)所示，参数说明如[表2](#zh-cn_topic_0000001124217631_table104346261582)所示。

        **图 1**  DN信息<a name="zh-cn_topic_0000001124217631_fig78301415114014"></a>  
        ![](figures/DN信息.png "DN信息")

        **表 2**  DN信息参数说明

        <a name="zh-cn_topic_0000001124217631_table104346261582"></a>
        <table><thead align="left"><tr id="zh-cn_topic_0000001124217631_row15434172611587"><th class="cellrowborder" valign="top" width="24.97%" id="mcps1.2.4.1.1"><p id="zh-cn_topic_0000001124217631_p643416263586"><a name="zh-cn_topic_0000001124217631_p643416263586"></a><a name="zh-cn_topic_0000001124217631_p643416263586"></a>参数名称</p>
        </th>
        <th class="cellrowborder" valign="top" width="49.66%" id="mcps1.2.4.1.2"><p id="zh-cn_topic_0000001124217631_p843492610586"><a name="zh-cn_topic_0000001124217631_p843492610586"></a><a name="zh-cn_topic_0000001124217631_p843492610586"></a>参数说明</p>
        </th>
        <th class="cellrowborder" valign="top" width="25.369999999999997%" id="mcps1.2.4.1.3"><p id="zh-cn_topic_0000001124217631_p18853143253813"><a name="zh-cn_topic_0000001124217631_p18853143253813"></a><a name="zh-cn_topic_0000001124217631_p18853143253813"></a>取值样例</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="zh-cn_topic_0000001124217631_row03895345512"><td class="cellrowborder" valign="top" width="24.97%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0000001124217631_p1839011341452"><a name="zh-cn_topic_0000001124217631_p1839011341452"></a><a name="zh-cn_topic_0000001124217631_p1839011341452"></a>CA名称（CN）</p>
        </td>
        <td class="cellrowborder" valign="top" width="49.66%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0000001124217631_p113909341455"><a name="zh-cn_topic_0000001124217631_p113909341455"></a><a name="zh-cn_topic_0000001124217631_p113909341455"></a>自定义私有CA名称。</p>
        </td>
        <td class="cellrowborder" valign="top" width="25.369999999999997%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0000001124217631_p188531320385"><a name="zh-cn_topic_0000001124217631_p188531320385"></a><a name="zh-cn_topic_0000001124217631_p188531320385"></a>-</p>
        </td>
        </tr>
        <tr id="zh-cn_topic_0000001124217631_row09164369351"><td class="cellrowborder" valign="top" width="24.97%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0000001124217631_p1591733619350"><a name="zh-cn_topic_0000001124217631_p1591733619350"></a><a name="zh-cn_topic_0000001124217631_p1591733619350"></a>国家/地区</p>
        </td>
        <td class="cellrowborder" valign="top" width="49.66%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0000001124217631_p0917123633516"><a name="zh-cn_topic_0000001124217631_p0917123633516"></a><a name="zh-cn_topic_0000001124217631_p0917123633516"></a>申请单位所属国家或地区，只能是两个字母的国家或地区代码。</p>
        </td>
        <td class="cellrowborder" valign="top" width="25.369999999999997%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0000001124217631_p1853173210385"><a name="zh-cn_topic_0000001124217631_p1853173210385"></a><a name="zh-cn_topic_0000001124217631_p1853173210385"></a>CN</p>
        </td>
        </tr>
        <tr id="zh-cn_topic_0000001124217631_row061084693511"><td class="cellrowborder" valign="top" width="24.97%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0000001124217631_p46101046103511"><a name="zh-cn_topic_0000001124217631_p46101046103511"></a><a name="zh-cn_topic_0000001124217631_p46101046103511"></a>省/市</p>
        </td>
        <td class="cellrowborder" valign="top" width="49.66%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0000001124217631_p4610246143512"><a name="zh-cn_topic_0000001124217631_p4610246143512"></a><a name="zh-cn_topic_0000001124217631_p4610246143512"></a>申请单位所在省名或市名，可以是中文或英文。</p>
        </td>
        <td class="cellrowborder" valign="top" width="25.369999999999997%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0000001124217631_p485383243820"><a name="zh-cn_topic_0000001124217631_p485383243820"></a><a name="zh-cn_topic_0000001124217631_p485383243820"></a>ShenZhen</p>
        </td>
        </tr>
        <tr id="zh-cn_topic_0000001124217631_row204931546358"><td class="cellrowborder" valign="top" width="24.97%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0000001124217631_p3494145411357"><a name="zh-cn_topic_0000001124217631_p3494145411357"></a><a name="zh-cn_topic_0000001124217631_p3494145411357"></a>城市</p>
        </td>
        <td class="cellrowborder" valign="top" width="49.66%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0000001124217631_p1849455473511"><a name="zh-cn_topic_0000001124217631_p1849455473511"></a><a name="zh-cn_topic_0000001124217631_p1849455473511"></a>申请单位所在城市名，可以是中文或英文。</p>
        </td>
        <td class="cellrowborder" valign="top" width="25.369999999999997%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0000001124217631_p19853113213387"><a name="zh-cn_topic_0000001124217631_p19853113213387"></a><a name="zh-cn_topic_0000001124217631_p19853113213387"></a>GuangZhou</p>
        </td>
        </tr>
        <tr id="zh-cn_topic_0000001124217631_row933710614365"><td class="cellrowborder" valign="top" width="24.97%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0000001124217631_p1333816613364"><a name="zh-cn_topic_0000001124217631_p1333816613364"></a><a name="zh-cn_topic_0000001124217631_p1333816613364"></a>公司名称（O）</p>
        </td>
        <td class="cellrowborder" valign="top" width="49.66%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0000001124217631_p53388623617"><a name="zh-cn_topic_0000001124217631_p53388623617"></a><a name="zh-cn_topic_0000001124217631_p53388623617"></a>申请单位法定名称，可以是中文或英文。</p>
        </td>
        <td class="cellrowborder" valign="top" width="25.369999999999997%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0000001124217631_p13853113203812"><a name="zh-cn_topic_0000001124217631_p13853113203812"></a><a name="zh-cn_topic_0000001124217631_p13853113203812"></a>-</p>
        </td>
        </tr>
        <tr id="zh-cn_topic_0000001124217631_row1875961318366"><td class="cellrowborder" valign="top" width="24.97%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0000001124217631_p57605135366"><a name="zh-cn_topic_0000001124217631_p57605135366"></a><a name="zh-cn_topic_0000001124217631_p57605135366"></a>部门名称（OU）</p>
        </td>
        <td class="cellrowborder" valign="top" width="49.66%" headers="mcps1.2.4.1.2 "><p id="zh-cn_topic_0000001124217631_p37601813133618"><a name="zh-cn_topic_0000001124217631_p37601813133618"></a><a name="zh-cn_topic_0000001124217631_p37601813133618"></a>申请单位的所在部门，可以是中文或英文。</p>
        </td>
        <td class="cellrowborder" valign="top" width="25.369999999999997%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0000001124217631_p1285313211389"><a name="zh-cn_topic_0000001124217631_p1285313211389"></a><a name="zh-cn_topic_0000001124217631_p1285313211389"></a>Cloud Dept.</p>
        </td>
        </tr>
        </tbody>
        </table>

    3.  （可选）在“企业项目“下拉列表中选择您所在的企业项目。

        企业项目针对企业用户使用，只有开通了企业项目的客户，或者权限为企业主帐号的客户才可见。

        如需使用该功能，请[开通企业管理功能](https://support.huaweicloud.com/usermanual-em/em_am_0008.html)。企业项目是一种云资源管理方式，企业项目管理服务提供统一的云资源按项目管理，以及项目内的资源管理、成员管理。

        >![](public_sys-resources/icon-note.gif) **说明：** 
        >“default“为默认企业项目，帐号下原有资源和未选择企业项目的资源均在默认企业项目内。

    4.  （可选）配置证书吊销信息。

        如果需要PCA为私有CA吊销的证书发布证书吊销列表（Certificate Revocation List，CRL），则可配置证书吊销信息。

        若无需配置，请直接跳过该步骤。

        配置证书吊销信息，如[图2](#zh-cn_topic_0000001124217631_fig1912819018456)所示，参数说明如[表3](#zh-cn_topic_0000001124217631_table9948417509)所示。

        **图 2**  证书吊销<a name="zh-cn_topic_0000001124217631_fig1912819018456"></a>  
        ![](figures/证书吊销.png "证书吊销")

        **表 3**  证书吊销参数说明

        <a name="zh-cn_topic_0000001124217631_table9948417509"></a>
        <table><thead align="left"><tr id="zh-cn_topic_0000001124217631_row99463120502"><th class="cellrowborder" valign="top" width="33.33%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0000001124217631_p189461115506"><a name="zh-cn_topic_0000001124217631_p189461115506"></a><a name="zh-cn_topic_0000001124217631_p189461115506"></a>参数名称</p>
        </th>
        <th class="cellrowborder" valign="top" width="66.67%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0000001124217631_p2946201165018"><a name="zh-cn_topic_0000001124217631_p2946201165018"></a><a name="zh-cn_topic_0000001124217631_p2946201165018"></a>参数说明</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="zh-cn_topic_0000001124217631_row1271693910366"><td class="cellrowborder" valign="top" width="33.33%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0000001124217631_p394720115509"><a name="zh-cn_topic_0000001124217631_p394720115509"></a><a name="zh-cn_topic_0000001124217631_p394720115509"></a>OBS授权</p>
        </td>
        <td class="cellrowborder" valign="top" width="66.67%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0000001124217631_p3630518132914"><a name="zh-cn_topic_0000001124217631_p3630518132914"></a><a name="zh-cn_topic_0000001124217631_p3630518132914"></a>确认是否授权PCA服务访问您的OBS桶并上传CRL文件。</p>
        <p id="zh-cn_topic_0000001124217631_p1356063615533"><a name="zh-cn_topic_0000001124217631_p1356063615533"></a><a name="zh-cn_topic_0000001124217631_p1356063615533"></a>若确认授权，则单击<span class="uicontrol" id="zh-cn_topic_0000001124217631_uicontrol1819180195411"><a name="zh-cn_topic_0000001124217631_uicontrol1819180195411"></a><a name="zh-cn_topic_0000001124217631_uicontrol1819180195411"></a>“立即授权”</span>，并根据提示完成授权。</p>
        <p id="zh-cn_topic_0000001124217631_p860513219447"><a name="zh-cn_topic_0000001124217631_p860513219447"></a><a name="zh-cn_topic_0000001124217631_p860513219447"></a>授权成功后，取消授权需要到统一身份认证服务控制台委托服务列表中删除委托。</p>
        <p id="zh-cn_topic_0000001124217631_p65824324299"><a name="zh-cn_topic_0000001124217631_p65824324299"></a><a name="zh-cn_topic_0000001124217631_p65824324299"></a>若已授权，则无需再次授权。</p>
        </td>
        </tr>
        <tr id="zh-cn_topic_0000001124217631_row199477114502"><td class="cellrowborder" valign="top" width="33.33%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0000001124217631_p1994631165017"><a name="zh-cn_topic_0000001124217631_p1994631165017"></a><a name="zh-cn_topic_0000001124217631_p1994631165017"></a>启用CRL发布</p>
        </td>
        <td class="cellrowborder" valign="top" width="66.67%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0000001124217631_p59472114508"><a name="zh-cn_topic_0000001124217631_p59472114508"></a><a name="zh-cn_topic_0000001124217631_p59472114508"></a>确认是否启用CRL发布。</p>
        </td>
        </tr>
        <tr id="zh-cn_topic_0000001124217631_row109471614503"><td class="cellrowborder" valign="top" width="33.33%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0000001124217631_p1094710119501"><a name="zh-cn_topic_0000001124217631_p1094710119501"></a><a name="zh-cn_topic_0000001124217631_p1094710119501"></a>OBS桶</p>
        </td>
        <td class="cellrowborder" valign="top" width="66.67%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0000001124217631_p394771175015"><a name="zh-cn_topic_0000001124217631_p394771175015"></a><a name="zh-cn_topic_0000001124217631_p394771175015"></a>选择已有的OBS桶，或单击<span class="uicontrol" id="zh-cn_topic_0000001124217631_uicontrol3981143184211"><a name="zh-cn_topic_0000001124217631_uicontrol3981143184211"></a><a name="zh-cn_topic_0000001124217631_uicontrol3981143184211"></a>“创建新的OBS桶”</span>来创建新的OBS桶。</p>
        </td>
        </tr>
        <tr id="zh-cn_topic_0000001124217631_row694814195018"><td class="cellrowborder" valign="top" width="33.33%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0000001124217631_p99483195019"><a name="zh-cn_topic_0000001124217631_p99483195019"></a><a name="zh-cn_topic_0000001124217631_p99483195019"></a>CRL更新周期</p>
        </td>
        <td class="cellrowborder" valign="top" width="66.67%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0000001124217631_p27798442045"><a name="zh-cn_topic_0000001124217631_p27798442045"></a><a name="zh-cn_topic_0000001124217631_p27798442045"></a>CRL更新的周期。私有证书管理服务将在指定时间内重新生成CRL。</p>
        <p id="zh-cn_topic_0000001124217631_p580162474012"><a name="zh-cn_topic_0000001124217631_p580162474012"></a><a name="zh-cn_topic_0000001124217631_p580162474012"></a>可设置为7~30的整数更新天数，如果未设置则默认为7天。</p>
        </td>
        </tr>
        </tbody>
        </table>

5.  单击“下一步“，进入确认信息页面。
6.  确认信息以及价格无误后，单击“确认并创建“，完成创建私有CA操作。

    若创建的是**根CA**，则创建后便已激活；若创建的为从属CA，则需要进行激活操作。

    私有**从属CA**创建后，如需立即安装CA证书并激活CA，则单击“立即激活“；如需后续再激活，单击“稍后再激活“。

## 后续处理<a name="zh-cn_topic_0000001124217631_section028319144496"></a>

私有**根CA**创建成功后，即可用于签发私有证书，申请私有证书详细操作请参见[申请私有证书](申请私有证书.md)。

私有**从属CA**创建成功后，需要安装证书并激活CA，具体操作请参见[激活私有CA](激活私有CA.md)。

