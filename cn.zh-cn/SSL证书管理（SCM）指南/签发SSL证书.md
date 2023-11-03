# 签发SSL证书<a name="ccm_01_0107"></a>

SSL证书审核时间取决于您和CA机构之间的配合。CA机构将通过您预留的邮箱和电话与您进行联系，请留意您在申请证书时预留的邮箱和电话。

-   DV型证书在确认完成DNS验证且验证结果无误后，请您耐心等待，CA机构将还需要一段时间进行处理。CA机构审核通过后，将会签发证书。
-   OV、EV型证书在确认完成组织验证后，CA机构将还需要一段时间进行处理，请您耐心等待。CA机构审核通过后，将会签发证书。

不同的SSL证书类型审核周期有所区别，一般情况下，各证书类型的审核周期说明如[表1](#table2029962414717)所示。

**表 1**  证书审核周期

<a name="table2029962414717"></a>
<table><thead align="left"><tr id="row1529916248714"><th class="cellrowborder" valign="top" width="24.779999999999998%" id="mcps1.2.3.1.1"><p id="p429915241375"><a name="p429915241375"></a><a name="p429915241375"></a>证书类型</p>
</th>
<th class="cellrowborder" valign="top" width="75.22%" id="mcps1.2.3.1.2"><p id="p529919241272"><a name="p529919241272"></a><a name="p529919241272"></a>审核周期</p>
</th>
</tr>
</thead>
<tbody><tr id="row1329913245712"><td class="cellrowborder" valign="top" width="24.779999999999998%" headers="mcps1.2.3.1.1 "><p id="p929972420712"><a name="p929972420712"></a><a name="p929972420712"></a>EV</p>
</td>
<td class="cellrowborder" valign="top" width="75.22%" headers="mcps1.2.3.1.2 "><p id="p14184180153015"><a name="p14184180153015"></a><a name="p14184180153015"></a>CA机构人工审核信息。</p>
<p id="p430019246717"><a name="p430019246717"></a><a name="p430019246717"></a>在信息正确的情况下审核周期一般为7～10个<strong id="b4447184210295"><a name="b4447184210295"></a><a name="b4447184210295"></a>工作日</strong>。</p>
</td>
</tr>
<tr id="row13001924879"><td class="cellrowborder" valign="top" width="24.779999999999998%" headers="mcps1.2.3.1.1 "><p id="p193001724274"><a name="p193001724274"></a><a name="p193001724274"></a>OV</p>
</td>
<td class="cellrowborder" valign="top" width="75.22%" headers="mcps1.2.3.1.2 "><p id="p1817413153015"><a name="p1817413153015"></a><a name="p1817413153015"></a>CA机构人工审核信息。</p>
<p id="p330092412714"><a name="p330092412714"></a><a name="p330092412714"></a>在信息正确的情况下审核周期一般为3～5个<strong id="b97741045122910"><a name="b97741045122910"></a><a name="b97741045122910"></a>工作日</strong>。</p>
</td>
</tr>
<tr id="row1630072412716"><td class="cellrowborder" valign="top" width="24.779999999999998%" headers="mcps1.2.3.1.1 "><p id="p2300142419717"><a name="p2300142419717"></a><a name="p2300142419717"></a>DV</p>
</td>
<td class="cellrowborder" valign="top" width="75.22%" headers="mcps1.2.3.1.2 "><p id="p956171543017"><a name="p956171543017"></a><a name="p956171543017"></a>无人工审核。</p>
<p id="p33001924179"><a name="p33001924179"></a><a name="p33001924179"></a>CA机构签发系统自动检查域名授权配置，DNS配置正确的情况下（需要您自行排查DNS配置是否正确）可在数小时内快速颁发。</p>
</td>
</tr>
</tbody>
</table>

## 操作步骤<a name="section14868111418305"></a>

CA机构审核通过后，将会签发证书，证书签发后便立即生效。

证书签发后，可一键部署证书到华为云其他云产品或下载证书并部署到服务器上进行使用。

部署证书操作请参见[部署证书到云产品](https://support.huaweicloud.com/usermanual-ccm/ccm_01_0056.html)。

下载证书操作请参见[下载证书](https://support.huaweicloud.com/usermanual-ccm/ccm_01_0027.html)。

