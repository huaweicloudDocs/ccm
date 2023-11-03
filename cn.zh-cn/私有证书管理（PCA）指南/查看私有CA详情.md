# 查看私有CA详情<a name="ccm_01_0018"></a>

本章节指导用户查看已创建私有CA的信息，包括私有CA名称、部门名称、类型和状态等。

## 前提条件<a name="zh-cn_topic_0000001124519795_section556861155951"></a>

已创建私有CA，详细操作请参见[创建私有CA](创建私有CA.md)。

## 操作步骤<a name="zh-cn_topic_0000001124519795_section146921116194016"></a>

1.  登录[管理控制台](https://console.huaweicloud.com/)。
2.  单击页面左上方的![](figures/服务列表.png)，选择“安全与合规  \>  云证书管理服务“，并在左侧导航栏选择“私有证书管理  \>  私有CA“进入私有CA管理界面。
3.  在私有CA列表中，查看私有CA信息，如[图1](#zh-cn_topic_0000001124519795_fig1864632765513)所示，证书参数说明如[表1](#zh-cn_topic_0000001124519795_table1731752125212)所示。

    **图 1**  私有CA列表<a name="zh-cn_topic_0000001124519795_fig1864632765513"></a>  
    ![](figures/私有CA列表.png "私有CA列表")

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   在“所有类型“（或“所有状态“）搜索栏选择CA类型（或状态），私有CA列表界面将只显示对应类型（或状态）的CA。
    >-   在私有CA列表右上角的搜索框中输入CA名称，单击![](figures/搜索.png)或按“Enter“，可以搜索指定的CA。

    **表 1**  CA参数说明

    <a name="zh-cn_topic_0000001124519795_table1731752125212"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0000001124519795_row17485275216"><th class="cellrowborder" valign="top" width="23.36%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0000001124519795_p12414527529"><a name="zh-cn_topic_0000001124519795_p12414527529"></a><a name="zh-cn_topic_0000001124519795_p12414527529"></a>参数名称</p>
    </th>
    <th class="cellrowborder" valign="top" width="76.64%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0000001124519795_p4410529525"><a name="zh-cn_topic_0000001124519795_p4410529525"></a><a name="zh-cn_topic_0000001124519795_p4410529525"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0000001124519795_row641052195214"><td class="cellrowborder" valign="top" width="23.36%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0000001124519795_p124352105219"><a name="zh-cn_topic_0000001124519795_p124352105219"></a><a name="zh-cn_topic_0000001124519795_p124352105219"></a>CA名称 （CN）</p>
    </td>
    <td class="cellrowborder" valign="top" width="76.64%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0000001124519795_p20405216521"><a name="zh-cn_topic_0000001124519795_p20405216521"></a><a name="zh-cn_topic_0000001124519795_p20405216521"></a>用户自定义的CA名称。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0000001124519795_row71927536541"><td class="cellrowborder" valign="top" width="23.36%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0000001124519795_p2194195314546"><a name="zh-cn_topic_0000001124519795_p2194195314546"></a><a name="zh-cn_topic_0000001124519795_p2194195314546"></a>类型</p>
    </td>
    <td class="cellrowborder" valign="top" width="76.64%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0000001124519795_p41944535549"><a name="zh-cn_topic_0000001124519795_p41944535549"></a><a name="zh-cn_topic_0000001124519795_p41944535549"></a>私有CA的类型，说明如下：</p>
    <a name="zh-cn_topic_0000001124519795_ul2929591558"></a><a name="zh-cn_topic_0000001124519795_ul2929591558"></a><ul id="zh-cn_topic_0000001124519795_ul2929591558"><li>根CA：私有CA属于根CA，可用于签发其他从属CA。</li><li>从属CA：私有CA属于从属CA。</li></ul>
    </td>
    </tr>
    <tr id="zh-cn_topic_0000001124519795_row141252195216"><td class="cellrowborder" valign="top" width="23.36%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0000001124519795_p1617114351620"><a name="zh-cn_topic_0000001124519795_p1617114351620"></a><a name="zh-cn_topic_0000001124519795_p1617114351620"></a>部门名称 （OU）</p>
    </td>
    <td class="cellrowborder" valign="top" width="76.64%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0000001124519795_p97320516115"><a name="zh-cn_topic_0000001124519795_p97320516115"></a><a name="zh-cn_topic_0000001124519795_p97320516115"></a>私有CA所属的部门名称。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0000001124519795_row43804325553"><td class="cellrowborder" valign="top" width="23.36%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0000001124519795_p11380183205513"><a name="zh-cn_topic_0000001124519795_p11380183205513"></a><a name="zh-cn_topic_0000001124519795_p11380183205513"></a>签发CA名称</p>
    </td>
    <td class="cellrowborder" valign="top" width="76.64%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0000001124519795_p5380163255512"><a name="zh-cn_topic_0000001124519795_p5380163255512"></a><a name="zh-cn_topic_0000001124519795_p5380163255512"></a>签发该私有CA对应CA的名称。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0000001124519795_row153881514185618"><td class="cellrowborder" valign="top" width="23.36%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0000001124519795_p1388111414560"><a name="zh-cn_topic_0000001124519795_p1388111414560"></a><a name="zh-cn_topic_0000001124519795_p1388111414560"></a>创建时间</p>
    </td>
    <td class="cellrowborder" valign="top" width="76.64%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0000001124519795_p18388131485619"><a name="zh-cn_topic_0000001124519795_p18388131485619"></a><a name="zh-cn_topic_0000001124519795_p18388131485619"></a>私有CA创建的时间。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0000001124519795_row178769243566"><td class="cellrowborder" valign="top" width="23.36%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0000001124519795_p987717241561"><a name="zh-cn_topic_0000001124519795_p987717241561"></a><a name="zh-cn_topic_0000001124519795_p987717241561"></a>到期时间</p>
    </td>
    <td class="cellrowborder" valign="top" width="76.64%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0000001124519795_p1087772435618"><a name="zh-cn_topic_0000001124519795_p1087772435618"></a><a name="zh-cn_topic_0000001124519795_p1087772435618"></a>私有CA到期的时间。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0000001124519795_row034581514542"><td class="cellrowborder" valign="top" width="23.36%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0000001124519795_p123451715185416"><a name="zh-cn_topic_0000001124519795_p123451715185416"></a><a name="zh-cn_topic_0000001124519795_p123451715185416"></a>状态</p>
    </td>
    <td class="cellrowborder" valign="top" width="76.64%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0000001124519795_p1275612415912"><a name="zh-cn_topic_0000001124519795_p1275612415912"></a><a name="zh-cn_topic_0000001124519795_p1275612415912"></a>私有CA的状态，说明如下：</p>
    <a name="zh-cn_topic_0000001124519795_ul39355114576"></a><a name="zh-cn_topic_0000001124519795_ul39355114576"></a><ul id="zh-cn_topic_0000001124519795_ul39355114576"><li>待激活：私有CA处于待激活状态。</li><li>已激活：私有CA处于已激活状态。</li><li>已禁用：私有CA处于已禁用状态。</li><li>计划删除：私有CA处于计划删除状态。</li><li>已过期：私有CA处于已过期状态。</li></ul>
    </td>
    </tr>
    <tr id="zh-cn_topic_0000001124519795_row1450415155182"><td class="cellrowborder" valign="top" width="23.36%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0000001124519795_p125041615151820"><a name="zh-cn_topic_0000001124519795_p125041615151820"></a><a name="zh-cn_topic_0000001124519795_p125041615151820"></a>操作</p>
    </td>
    <td class="cellrowborder" valign="top" width="76.64%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0000001124519795_p450551531817"><a name="zh-cn_topic_0000001124519795_p450551531817"></a><a name="zh-cn_topic_0000001124519795_p450551531817"></a>用户可以在操作栏中，执行激活、启用、禁用CA等操作。</p>
    </td>
    </tr>
    </tbody>
    </table>

4.  用户可单击私有CA名称，查看私有CA的详细信息，如[图2](#fig56195371919)所示。

    您可在CA详情页单击“添加标签“标识CA。如果您需要使用同一标签标识多种云资源，即所有服务均可在标签输入框下选择同一标签，建议在TMS中创建预定义标签。

    **图 2**  私有CA详细信息<a name="fig56195371919"></a>  
    ![](figures/私有CA详细信息.png "私有CA详细信息")

