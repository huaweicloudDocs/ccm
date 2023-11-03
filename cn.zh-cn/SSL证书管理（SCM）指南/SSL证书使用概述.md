# SSL证书使用概述<a name="ccm_01_0073"></a>

华为云SSL证书提供多个品牌和类型的证书，详情请参见[各证书之间的区别](https://support.huaweicloud.com/productdesc-ccm/ccm_01_0219.html)。本文档介绍如何购买和使用华为云SSL证书。

您的网站使用SSL证书后，将会通过HTTPS加密协议来传输数据，可帮助服务器端和客户端之间建立加密链接，从而保证数据传输的安全。

相关流程如[图 证书使用流程](#fig164664141716)所示，具体说明如[表 证书使用流程说明](#table152877314188)所示。

**图 1**  证书使用流程<a name="fig164664141716"></a>  
![](figures/证书使用流程.png "证书使用流程")

**表 1**  证书使用流程说明

<a name="table152877314188"></a>
<table><thead align="left"><tr id="row828783171812"><th class="cellrowborder" valign="top" width="13.23132313231323%" id="mcps1.2.4.1.1"><p id="p8287123161816"><a name="p8287123161816"></a><a name="p8287123161816"></a>步骤</p>
</th>
<th class="cellrowborder" valign="top" width="21.322132213221323%" id="mcps1.2.4.1.2"><p id="p11288153114184"><a name="p11288153114184"></a><a name="p11288153114184"></a>操作</p>
</th>
<th class="cellrowborder" valign="top" width="65.44654465446544%" id="mcps1.2.4.1.3"><p id="p1288931141819"><a name="p1288931141819"></a><a name="p1288931141819"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row128823171819"><td class="cellrowborder" valign="top" width="13.23132313231323%" headers="mcps1.2.4.1.1 "><p id="p1228883116188"><a name="p1228883116188"></a><a name="p1228883116188"></a>1</p>
</td>
<td class="cellrowborder" valign="top" width="21.322132213221323%" headers="mcps1.2.4.1.2 "><p id="p1928803171818"><a name="p1928803171818"></a><a name="p1928803171818"></a><a href="https://support.huaweicloud.com/usermanual-ccm/ccm_01_0074.html" target="_blank" rel="noopener noreferrer">购买SSL证书</a></p>
</td>
<td class="cellrowborder" valign="top" width="65.44654465446544%" headers="mcps1.2.4.1.3 "><p id="p17288163114188"><a name="p17288163114188"></a><a name="p17288163114188"></a>在SSL证书管理平台，根据您的域名类型选购对应的证书。</p>
<p id="p62882318182"><a name="p62882318182"></a><a name="p62882318182"></a>各类型证书之间的区别以及选择请参见<a href="https://support.huaweicloud.com/productdesc-ccm/ccm_01_0219.html" target="_blank" rel="noopener noreferrer">各类型SSL证书之间的区别</a>、<a href="https://support.huaweicloud.com/ccm_faq/ccm_01_0271.html" target="_blank" rel="noopener noreferrer">如何选择SSL证书？</a>。</p>
</td>
</tr>
<tr id="row172891831171811"><td class="cellrowborder" valign="top" width="13.23132313231323%" headers="mcps1.2.4.1.1 "><p id="p1128943119188"><a name="p1128943119188"></a><a name="p1128943119188"></a>2</p>
</td>
<td class="cellrowborder" valign="top" width="21.322132213221323%" headers="mcps1.2.4.1.2 "><p id="p129143113184"><a name="p129143113184"></a><a name="p129143113184"></a><a href="https://support.huaweicloud.com/usermanual-ccm/ccm_01_0075.html" target="_blank" rel="noopener noreferrer">提交SSL证书申请</a></p>
</td>
<td class="cellrowborder" valign="top" width="65.44654465446544%" headers="mcps1.2.4.1.3 "><p id="p22910316181"><a name="p22910316181"></a><a name="p22910316181"></a>成功购买证书后，您需要为证书绑定域名、填写证书申请人的详细信息并提交审核。</p>
</td>
</tr>
<tr id="row192917319187"><td class="cellrowborder" valign="top" width="13.23132313231323%" headers="mcps1.2.4.1.1 "><p id="p029183111819"><a name="p029183111819"></a><a name="p029183111819"></a>3</p>
</td>
<td class="cellrowborder" valign="top" width="21.322132213221323%" headers="mcps1.2.4.1.2 "><p id="p13291133119185"><a name="p13291133119185"></a><a name="p13291133119185"></a><a href="https://support.huaweicloud.com/usermanual-ccm/ccm_01_0103.html" target="_blank" rel="noopener noreferrer">域名验证</a></p>
</td>
<td class="cellrowborder" valign="top" width="65.44654465446544%" headers="mcps1.2.4.1.3 "><p id="p102911231141815"><a name="p102911231141815"></a><a name="p102911231141815"></a>按照CA中心的规范，证书提交申请后您需要配合完成域名授权验证来证明您对所申请绑定域名的所有权。</p>
<p id="p6291331141812"><a name="p6291331141812"></a><a name="p6291331141812"></a>SCM提供有以下几种验证方式：</p>
<a name="ul19291203171816"></a><a name="ul19291203171816"></a><ul id="ul19291203171816"><li>自动DNS验证：符合<a href="https://support.huaweicloud.com/usermanual-ccm/ccm_01_0077.html#section0" target="_blank" rel="noopener noreferrer">条件</a>的证书可选。</li><li>手动DNS验证：所有类型证书均可选。</li><li>邮箱验证：仅OV、EV型证书可选。</li><li>文件验证：仅IP证书支持。</li></ul>
</td>
</tr>
<tr id="row172921231121817"><td class="cellrowborder" valign="top" width="13.23132313231323%" headers="mcps1.2.4.1.1 "><p id="p10292031111814"><a name="p10292031111814"></a><a name="p10292031111814"></a>4</p>
</td>
<td class="cellrowborder" valign="top" width="21.322132213221323%" headers="mcps1.2.4.1.2 "><p id="p4292173114189"><a name="p4292173114189"></a><a name="p4292173114189"></a><a href="https://support.huaweicloud.com/usermanual-ccm/ccm_01_0089.html" target="_blank" rel="noopener noreferrer">组织验证（OV、EV）</a></p>
</td>
<td class="cellrowborder" valign="top" width="65.44654465446544%" headers="mcps1.2.4.1.3 "><p id="p162921631181820"><a name="p162921631181820"></a><a name="p162921631181820"></a>仅当申请OV、OV Pro、EV和EV Pro类型证书时，需要该操作。</p>
<p id="p22923312187"><a name="p22923312187"></a><a name="p22923312187"></a>域名验证完成后，CA机构需要确认企业/组织是否发起了此次的证书订单申请。</p>
</td>
</tr>
<tr id="row17292123110187"><td class="cellrowborder" valign="top" width="13.23132313231323%" headers="mcps1.2.4.1.1 "><p id="p112921531171815"><a name="p112921531171815"></a><a name="p112921531171815"></a>5</p>
</td>
<td class="cellrowborder" valign="top" width="21.322132213221323%" headers="mcps1.2.4.1.2 "><p id="p52921231181810"><a name="p52921231181810"></a><a name="p52921231181810"></a><a href="https://support.huaweicloud.com/usermanual-ccm/ccm_01_0107.html" target="_blank" rel="noopener noreferrer">签发SSL证书</a></p>
</td>
<td class="cellrowborder" valign="top" width="65.44654465446544%" headers="mcps1.2.4.1.3 "><p id="p1729263131812"><a name="p1729263131812"></a><a name="p1729263131812"></a>验证完成后，CA机构还需要一段时间进行处理，请您耐心等待。具体申请时间请参见<a href="https://support.huaweicloud.com/ccm_faq/ccm_01_0060.html" target="_blank" rel="noopener noreferrer">各证书的申请时长</a>。</p>
<p id="p92935315184"><a name="p92935315184"></a><a name="p92935315184"></a>CA机构审核通过后，将签发证书。证书自签发之时开始生效，有效期为1年。</p>
</td>
</tr>
<tr id="row729319318183"><td class="cellrowborder" valign="top" width="13.23132313231323%" headers="mcps1.2.4.1.1 "><p id="p1829303141820"><a name="p1829303141820"></a><a name="p1829303141820"></a>6</p>
</td>
<td class="cellrowborder" valign="top" width="21.322132213221323%" headers="mcps1.2.4.1.2 "><p id="p82935316186"><a name="p82935316186"></a><a name="p82935316186"></a><a href="https://support.huaweicloud.com/usermanual-ccm/ccm_01_0080.html" target="_blank" rel="noopener noreferrer">安装SSL证书</a></p>
</td>
<td class="cellrowborder" valign="top" width="65.44654465446544%" headers="mcps1.2.4.1.3 "><p id="p162931631111811"><a name="p162931631111811"></a><a name="p162931631111811"></a>证书签发后，您可以一键部署证书到华为云其他云产品或下载证书并安装到服务器上进行使用。</p>
<a name="ul229313312188"></a><a name="ul229313312188"></a><ul id="ul229313312188"><li>将证书部署到其他云产品后，将帮助您提升对应云产品访问数据的安全性。</li><li>SSL证书安装到Web服务器后，您的Web服务器才能实现HTTPS加密通信，实现通信安全。</li></ul>
</td>
</tr>
<tr id="row112931831191817"><td class="cellrowborder" valign="top" width="13.23132313231323%" headers="mcps1.2.4.1.1 "><p id="p1829333117182"><a name="p1829333117182"></a><a name="p1829333117182"></a>7</p>
</td>
<td class="cellrowborder" valign="top" width="21.322132213221323%" headers="mcps1.2.4.1.2 "><p id="p17293431191817"><a name="p17293431191817"></a><a name="p17293431191817"></a><a href="https://support.huaweicloud.com/usermanual-ccm/ccm_01_0120.html" target="_blank" rel="noopener noreferrer">续费SSL证书</a></p>
</td>
<td class="cellrowborder" valign="top" width="65.44654465446544%" headers="mcps1.2.4.1.3 "><p id="p11294731141817"><a name="p11294731141817"></a><a name="p11294731141817"></a>自2020年9月1日起，全球CA机构颁发的SSL证书有效期最长为一年，证书到期后将不再被浏览器信任，建议您提前开通自动续费或在证书即将到期前三十天进行手动续费，避免因证书过期对您的业务产生影响。</p>
<p id="p16294231161815"><a name="p16294231161815"></a><a name="p16294231161815"></a>SSL证书续费操作相当于重新申请了一张与原证书规格（即证书品牌、证书类型、域名类型、域名数量、主域名）<strong id="b4294193113185"><a name="b4294193113185"></a><a name="b4294193113185"></a>完全相同</strong>的证书。证书续费后，您需要将续费签发的新证书重新安装到您的Web服务器或部署到华为云其他云产品，替换即将过期的旧证书。</p>
</td>
</tr>
<tr id="row2294193181817"><td class="cellrowborder" valign="top" width="13.23132313231323%" headers="mcps1.2.4.1.1 "><p id="p16294431151816"><a name="p16294431151816"></a><a name="p16294431151816"></a>8</p>
</td>
<td class="cellrowborder" valign="top" width="21.322132213221323%" headers="mcps1.2.4.1.2 "><p id="p16294231161810"><a name="p16294231161810"></a><a name="p16294231161810"></a><a href="https://support.huaweicloud.com/usermanual-ccm/ccm_01_0052.html" target="_blank" rel="noopener noreferrer">吊销SSL证书</a></p>
</td>
<td class="cellrowborder" valign="top" width="65.44654465446544%" headers="mcps1.2.4.1.3 "><p id="p4294183101812"><a name="p4294183101812"></a><a name="p4294183101812"></a>如果您不再需要某张已签发的SSL证书或某张SSL证书密钥丢失或出于其他安全因素考虑，可以在SSL证书管理控制台申请吊销证书。</p>
<p id="p829473113186"><a name="p829473113186"></a><a name="p829473113186"></a>吊销证书指将已签发的证书从CA签发机构处注销。证书吊销后将失去加密效果，浏览器不再信任该证书。</p>
</td>
</tr>
</tbody>
</table>

