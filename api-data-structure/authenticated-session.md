# 认证会话 (Authenticated Session)

认证会话通常用于完成用户认证后返回结果。这个数据结构的设计原则为：

> 一次性返回执行登录操作后可能需要的数据

数据结构如下：

<table border="0" cellpadding="0" cellspacing="0">
<thead><tr>
<td style="text-align:center; background-color:#f5f5f5;">名称</td>
<td style="text-align:center; background-color:#f5f5f5;">类型</td>
<td style="text-align:center; background-color:#f5f5f5;">是否必须</td>
<td style="text-align:center; background-color:#f5f5f5;">说明</td>
</tr></thead>
<tbody><tr>
<td style="text-align:center;">sessionToken</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">用户会话ID</td>
</tr><tr>
<td style="text-align:center;">sessionSecret</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">用户会话密钥</td>
</tr><tr>
<td style="text-align:center;">expired</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">用户会话过期时间戳（以服务器时间为准）</td>
</tr><tr>
<td style="text-align:center;">unique</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">用户的帐号ID</td>
</tr><tr>
<td style="text-align:center;">username</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">用户的登录名</td>
</tr><tr>
<td style="text-align:center;">type</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">用户的帐号类型</td>
</tr><tr>
<td style="text-align:center;">name</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">用户的名字</td>
</tr><tr>
<td style="text-align:center;">country</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">国籍</td>
</tr><tr>
<td style="text-align:center;">province</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">省份</td>
</tr><tr>
<td style="text-align:center;">city</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">所在城市</td>
</tr><tr>
<td style="text-align:center;">gender</td>
<td style="text-align:center;">Options: ['MALE', 'FEMALE']</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">性别</td>
</tr><tr>
<td style="text-align:center;">age</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">年龄</td>
</tr><tr>
<td style="text-align:center;">avatrUrl</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">头像图片链接</td>
</tr><tr>
<td style="text-align:center;">signature</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">个性签名</td>
</tr><tr>
<td style="text-align:center;">roles</td>
<td style="text-align:center;">Array</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">用户的角色列表</td>
</tr></tbody>
</table>