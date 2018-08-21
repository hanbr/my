# <a name="groups">群组管理 (Groups)</a>

## <a name="create-group">创建群组 (Create Group)</a>

> http://192.168.96.211/services/group/create

<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td colspan="2" style="text-align:left;">POST</td></tr>
<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
<tr><td style="text-align:left;">Authorization</td><td style="color:#999;">标准HTTP Basic Authentication内容，包括登录用户的sessionToken和sessionSecret</td></tr>
</table>

### 输入参数

<table border="0" cellpadding="0" cellspacing="0">
<thead><tr>
<td style="text-align:center; background-color:#f5f5f5;">名称</td>
<td style="text-align:center; background-color:#f5f5f5;">类型</td>
<td style="text-align:center; background-color:#f5f5f5;">是否必须</td>
<td style="text-align:center; background-color:#f5f5f5;">默认值</td>
<td style="text-align:center; background-color:#f5f5f5;">说明</td>
</tr></thead>
<tbody><tr>
<td style="text-align:center;">name</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">群组标识名，须全局唯一</td>
</tr><tr>
<td style="text-align:center;">keyname</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">群组显示名，由2到40个字符组成</td>
</tr><tr>
<td style="text-align:center;">type</td>
<td style="text-align:center;">String, Restricted</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">群组类型，可选项：<br/><b>COMMON</b>:&nbsp;普通群组<br/><b>PROJECT</b>:&nbsp;项目群组<br/><b>CHATUS</b>:&nbsp;ChatUs群组<br/><b>COWORK</b>:&nbsp;协作群组</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{
	"status" : 200,
	"message" : "OK",
	"result" : {
		"unique" : 1,
		"name" : "...",
		"displayName" : "...",
		"type" : "COMMON",
		"description" : "...",
		"owner" : {
			"unique" : 2,
			...
		},
		"administrators" : [{
			"unique" : 2,
			...
		},{
			"unique" : 3,
			...
		}],
		"status" : "ACTIVED",
		"created" : ...,
		"updated" : ...
	}
}
</code>

#### 数据说明

<table border="0" cellpadding="0" cellspacing="0">
<thead><tr>
<td style="text-align:center; background-color:#f5f5f5;">名称</td>
<td style="text-align:center; background-color:#f5f5f5;">类型</td>
<td style="text-align:center; background-color:#f5f5f5;">是否必须</td>
<td style="text-align:center; background-color:#f5f5f5;">说明</td>
</tr></thead>
<tbody><tr>
<td style="text-align:center;">unique</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">群组ID</td>
</tr><tr>
<td style="text-align:center;">name</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">群组唯一名，由小写英文字符和数字组成，首字母只能是英文字符</td>
</tr><tr>
<td style="text-align:center;">displayName</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">群组显示名，长度不少于2个字符，不超过40个字符</td>
</tr><tr>
<td style="text-align:center;">type</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">群组类型</td>
</tr><tr>
<td style="text-align:center;">description</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">群组文字描述</td>
</tr><tr>
<td style="text-align:center;">owner</td>
<td style="text-align:center;">Simple User Object</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">群组所有人</td>
</tr><tr>
<td style="text-align:center;">administrators</td>
<td style="text-align:center;">Arrays of Simple User Object</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">群组管理员</td>
</tr><tr>
<td style="text-align:center;">status</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">群组状态</td>
</tr><tr>
<td style="text-align:center;">created</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">群组创建时间</td>
</tr><tr>
<td style="text-align:center;">updated</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">群组上次更新时间</td>
</tr></tbody>
</table>

#### 常见错误信息

<table border="0" cellpadding="0" cellspacing="0">
<thead><tr>
<td style="text-align:center; background-color:#f5f5f5;">status</td>
<td style="text-align:center; background-color:#f5f5f5;">message</td>
<td style="text-align:center; background-color:#f5f5f5;">说明</td>
</tr></thead>
<tbody><tr>
<td style="text-align:center;">400</td>
<td style="text-align:left;">require parameter:A</td>
<td style="text-align:left;">缺少必须参数A</td>
</tr><tr>
<td style="text-align:center;">403</td>
<td style="text-align:left;">access denied</td>
<td style="text-align:left;">需要的登陆才可以进行操作</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">unrecongnized group type</td>
<td style="text-align:left;">无法识别的群组类型</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">invalid group name</td>
<td style="text-align:left;">无效的群组名</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">invalid group displayname</td>
<td style="text-align:left;">无效的群组显示名</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">group name already used</td>
<td style="text-align:left;">群组名已被使用</td>
</tr></tbody>
</table>

### 前端功能

#### 群组添加

字段：

（1）群组名称：小写英文字符组成，服务器端将判断唯一，前端调用IsValidKeyname校验

（2）群组显示名：中文和英文字符组成，前端调用IsValidName校验

（3）群组描述：不超过120字，可以为空


## <a name="create-group">更新群组 (Update Group)</a>

> http://192.168.96.211/services/group/{groupid}/update

<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td colspan="2" style="text-align:left;">POST</td></tr>
<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
<tr><td style="text-align:left;">Authorization</td><td style="color:#999;">标准HTTP Basic Authentication内容，包括登录用户的sessionToken和sessionSecret</td></tr>
</table>

### 输入参数

<table border="0" cellpadding="0" cellspacing="0">
<thead><tr>
<td style="text-align:center; background-color:#f5f5f5;">名称</td>
<td style="text-align:center; background-color:#f5f5f5;">类型</td>
<td style="text-align:center; background-color:#f5f5f5;">是否必须</td>
<td style="text-align:center; background-color:#f5f5f5;">默认值</td>
<td style="text-align:center; background-color:#f5f5f5;">说明</td>
</tr></thead>
<tbody><tr>
<td style="text-align:center;">name</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">群组标识名，须全局唯一</td>
</tr><tr>
<td style="text-align:center;">keyname</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">群组显示名，由2到40个字符组成</td>
</tr><tr>
<td style="text-align:center;">type</td>
<td style="text-align:center;">String, Restricted</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">群组类型，可选项：<br/><b>COMMON</b>:&nbsp;普通群组<br/><b>PROJECT</b>:&nbsp;项目群组<br/><b>CHATUS</b>:&nbsp;ChatUs群组<br/><b>COWORK</b>:&nbsp;协作群组</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{
	"status" : 200,
	"message" : "OK"
}
</code>

#### 常见错误信息

<table border="0" cellpadding="0" cellspacing="0">
<thead><tr>
<td style="text-align:center; background-color:#f5f5f5;">status</td>
<td style="text-align:center; background-color:#f5f5f5;">message</td>
<td style="text-align:center; background-color:#f5f5f5;">说明</td>
</tr></thead>
<tbody><tr>
<td style="text-align:center;">400</td>
<td style="text-align:left;">require parameter:A</td>
<td style="text-align:left;">缺少必须参数A</td>
</tr><tr>
<td style="text-align:center;">403</td>
<td style="text-align:left;">access denied</td>
<td style="text-align:left;">需要的登陆才可以进行操作</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">unrecongnized group type</td>
<td style="text-align:left;">无法识别的群组类型</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">invalid group name</td>
<td style="text-align:left;">无效的群组名</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">invalid group displayname</td>
<td style="text-align:left;">无效的群组显示名</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">group name already exists</td>
<td style="text-align:left;">群组名已被使用</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">group not exists</td>
<td style="text-align:left;">此群组不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">not group admin</td>
<td style="text-align:left;">没有足够的权限执行此操作-不是群组管理员</td>
</tr></tbody>
</table>

### 前端功能

#### 群组编辑

字段：

（1）群组名称：小写英文字符组成，服务器端将判断唯一，前端调用IsValidKeyname校验

（2）群组显示名：中文和英文字符组成，前端调用IsValidName校验

（3）群组描述：不超过120字，可以为空



## <a name="delete-group">删除群组 (Delete Group)</a>

> http://192.168.96.211/services/group/{groupid}/delete

<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td colspan="2" style="text-align:left;">POST</td></tr>
<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
<tr><td style="text-align:left;">Authorization</td><td style="color:#999;">标准HTTP Basic Authentication内容，包括登录用户的sessionToken和sessionSecret</td></tr>
</table>

### 输出数据

#### 返回实例

<code>
{ 
"status" : 200, 
"message" : "OK"
}
</code>

## <a name="delete-groups">批量删除群组 (Delete Groups)</a>

> http://192.168.96.211/services/group/delete

<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td colspan="2" style="text-align:left;">POST</td></tr>
<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
<tr><td style="text-align:left;">Authorization</td><td style="color:#999;">标准HTTP Basic Authentication内容，包括登录用户的sessionToken和sessionSecret</td></tr>
</table>

### 输入参数

<table border="0" cellpadding="0" cellspacing="0">
<thead><tr>
<td style="text-align:center; background-color:#f5f5f5;">名称</td>
<td style="text-align:center; background-color:#f5f5f5;">类型</td>
<td style="text-align:center; background-color:#f5f5f5;">是否必须</td>
<td style="text-align:center; background-color:#f5f5f5;">默认值</td>
<td style="text-align:center; background-color:#f5f5f5;">说明</td>
</tr></thead>
<tbody><tr>
<td style="text-align:center;">groups</td>
<td style="text-align:center;">JSON Array</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">[]</td>
<td style="text-align:left;">要删除的角色ID列表，例如[1, 2, 4]</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{ 
"status" : 200, 
"message" : "OK"
}
</code>

## <a name="disable-group">禁用群组 (Disable Group)</a>

> http://192.168.96.211/services/group/{groupid}/disable

<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td colspan="2" style="text-align:left;">POST</td></tr>
<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
<tr><td style="text-align:left;">Authorization</td><td style="color:#999;">标准HTTP Basic Authentication内容，包括登录用户的sessionToken和sessionSecret</td></tr>
</table>

### 输出数据

#### 返回实例

<code>
{
	"status" : 200,
	"message" : "OK"
}
</code>

#### 常见错误信息

<table border="0" cellpadding="0" cellspacing="0">
<thead><tr>
<td style="text-align:center; background-color:#f5f5f5;">status</td>
<td style="text-align:center; background-color:#f5f5f5;">message</td>
<td style="text-align:center; background-color:#f5f5f5;">说明</td>
</tr></thead>
<tbody>
<tr>
<td style="text-align:center;">403</td>
<td style="text-align:left;">access denied</td>
<td style="text-align:left;">需要的登陆才可以进行操作</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">group not exists</td>
<td style="text-align:left;">此群组不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">not group owner</td>
<td style="text-align:left;">没有足够的权限执行此操作-不是群组拥有者</td>
</tr></tbody>
</table>

## <a name="disable-groups">批量删除群组 (Disable Groups)</a>

> http://192.168.96.211/services/group/disable

<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td colspan="2" style="text-align:left;">POST</td></tr>
<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
<tr><td style="text-align:left;">Authorization</td><td style="color:#999;">标准HTTP Basic Authentication内容，包括登录用户的sessionToken和sessionSecret</td></tr>
</table>

### 输入参数

<table border="0" cellpadding="0" cellspacing="0">
<thead><tr>
<td style="text-align:center; background-color:#f5f5f5;">名称</td>
<td style="text-align:center; background-color:#f5f5f5;">类型</td>
<td style="text-align:center; background-color:#f5f5f5;">是否必须</td>
<td style="text-align:center; background-color:#f5f5f5;">默认值</td>
<td style="text-align:center; background-color:#f5f5f5;">说明</td>
</tr></thead>
<tbody><tr>
<td style="text-align:center;">groups</td>
<td style="text-align:center;">JSON Array</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">[]</td>
<td style="text-align:left;">要删除的角色ID列表，例如[1, 2, 4]</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{ 
"status" : 200, 
"message" : "OK"
}
</code>


## <a name="enable-group">启用群组 (Enable Group)</a>

> http://192.168.96.211/services/group/{groupid}/enable

<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td colspan="2" style="text-align:left;">POST</td></tr>
<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
<tr><td style="text-align:left;">Authorization</td><td style="color:#999;">标准HTTP Basic Authentication内容，包括登录用户的sessionToken和sessionSecret</td></tr>
</table>

### 输出数据

#### 返回实例

<code>
{
	"status" : 200,
	"message" : "OK"
}
</code>

#### 常见错误信息

<table border="0" cellpadding="0" cellspacing="0">
<thead><tr>
<td style="text-align:center; background-color:#f5f5f5;">status</td>
<td style="text-align:center; background-color:#f5f5f5;">message</td>
<td style="text-align:center; background-color:#f5f5f5;">说明</td>
</tr></thead>
<tbody>
<tr>
<td style="text-align:center;">403</td>
<td style="text-align:left;">access denied</td>
<td style="text-align:left;">需要的登陆才可以进行操作</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">group not exists</td>
<td style="text-align:left;">此群组不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">not group owner</td>
<td style="text-align:left;">没有足够的权限执行此操作-不是群组拥有者</td>
</tr></tbody>
</table>

## <a name="enable-groups">批量启用群组 (Enable Groups)</a>

> http://192.168.96.211/services/group/enable

<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td colspan="2" style="text-align:left;">POST</td></tr>
<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
<tr><td style="text-align:left;">Authorization</td><td style="color:#999;">标准HTTP Basic Authentication内容，包括登录用户的sessionToken和sessionSecret</td></tr>
</table>

### 输入参数

<table border="0" cellpadding="0" cellspacing="0">
<thead><tr>
<td style="text-align:center; background-color:#f5f5f5;">名称</td>
<td style="text-align:center; background-color:#f5f5f5;">类型</td>
<td style="text-align:center; background-color:#f5f5f5;">是否必须</td>
<td style="text-align:center; background-color:#f5f5f5;">默认值</td>
<td style="text-align:center; background-color:#f5f5f5;">说明</td>
</tr></thead>
<tbody><tr>
<td style="text-align:center;">groups</td>
<td style="text-align:center;">JSON Array</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">[]</td>
<td style="text-align:left;">要删除的角色ID列表，例如[1, 2, 4]</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{ 
"status" : 200, 
"message" : "OK"
}
</code>

## <a name="list-groups">查询群组 (List Groups)</a>

> http://192.168.96.211/services/group/list

<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td colspan="2" style="text-align:left;">GET</td></tr>
<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
<tr><td style="text-align:left;">Authorization</td><td style="color:#999;">标准HTTP Basic Authentication内容，包括登录用户的sessionToken和sessionSecret</td></tr>
</table>

### 输入参数

<table border="0" cellpadding="0" cellspacing="0">
<thead><tr>
<td style="text-align:center; background-color:#f5f5f5;">名称</td>
<td style="text-align:center; background-color:#f5f5f5;">类型</td>
<td style="text-align:center; background-color:#f5f5f5;">是否必须</td>
<td style="text-align:center; background-color:#f5f5f5;">默认值</td>
<td style="text-align:center; background-color:#f5f5f5;">说明</td>
</tr></thead>
<tbody><tr>
<td style="text-align:center;">keywords</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:left;">关键词，应用于群组的name和displayName两个字段上</td>
</tr><tr>
<td style="text-align:center;">status</td>
<td style="text-align:center;">String, Restricted</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">ALL_STATUS</td>
<td style="text-align:left;">查询状态，三个选项：<br><b>ALL_STATUS</b>不限状态；<br><b>ACTIVED</b>可用状态；<br/><b>DISABLED</b>停用状态；</td>
</tr><tr>
<td style="text-align:center;">page</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">1</td>
<td style="text-align:left;">当前页码，从1开始</td>
</tr><tr>
<td style="text-align:center;">offset</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">20</td>
<td style="text-align:left;">每页记录数量</td>
</tr><tr>
<td style="text-align:center;">order</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:left;">排序字段，可选: name, created, updated</td>
</tr><tr>
<td style="text-align:center;">acs</td>
<td style="text-align:center;">Boolean</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">false</td>
<td style="text-align:left;">是否升序排列</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{
	"status" : 200,
	"message" : "OK",
	"result" : {
		"hasPrevious" : false,
		"hasNext" : false,
		"total" : 5,
		"entites" : [{
			"unique" : 1,
			"name" : "...",
			"displayName" : "...",
			"type" : "COMMON",
			"description" : "...",
			"owner" : {
				"unique" : 2,
				...
			},
			"administrators" : [{
				"unique" : 2,
				...
			},{
				"unique" : 3,
				...
			}],
			"status" : "ACTIVED",
			"created" : ...,
			"updated" : ...
		},...]
	}
}
</code>

#### 数据说明

<table border="0" cellpadding="0" cellspacing="0">
<thead><tr>
<td style="text-align:center; background-color:#f5f5f5;">名称</td>
<td style="text-align:center; background-color:#f5f5f5;">类型</td>
<td style="text-align:center; background-color:#f5f5f5;">是否必须</td>
<td style="text-align:center; background-color:#f5f5f5;">说明</td>
</tr></thead>
<tbody><tr>
<td style="text-align:center;">hasPrevious</td>
<td style="text-align:center;">Boolean</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">是否有上一页</td>
</tr><tr>
<td style="text-align:center;">hasNext</td>
<td style="text-align:center;">Boolean</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">是否有下一页</td>
</tr><tr>
<td style="text-align:center;">total</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">总的记录数量</td>
</tr><tr>
<td style="text-align:center;">unique</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">群组ID</td>
</tr><tr>
<td style="text-align:center;">name</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">群组唯一名，由小写英文字符和数字组成，首字母只能是英文字符</td>
</tr><tr>
<td style="text-align:center;">displayName</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">群组显示名，长度不少于2个字符，不超过40个字符</td>
</tr><tr>
<td style="text-align:center;">type</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">群组类型</td>
</tr><tr>
<td style="text-align:center;">description</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">群组文字描述</td>
</tr><tr>
<td style="text-align:center;">owner</td>
<td style="text-align:center;">Simple User Object</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">群组所有人</td>
</tr><tr>
<td style="text-align:center;">administrators</td>
<td style="text-align:center;">Arrays of Simple User Object</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">群组管理员</td>
</tr><tr>
<td style="text-align:center;">status</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">群组状态</td>
</tr><tr>
<td style="text-align:center;">created</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">群组创建时间</td>
</tr><tr>
<td style="text-align:center;">updated</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">群组上次更新时间</td>
</tr></tbody>
</table>

#### 常见错误信息

<table border="0" cellpadding="0" cellspacing="0">
<thead><tr>
<td style="text-align:center; background-color:#f5f5f5;">status</td>
<td style="text-align:center; background-color:#f5f5f5;">message</td>
<td style="text-align:center; background-color:#f5f5f5;">说明</td>
</tr></thead>
<tbody>
<tr>
<td style="text-align:center;">403</td>
<td style="text-align:left;">access denied</td>
<td style="text-align:left;">需要的登陆才可以进行操作</td>
</tr></tbody>
</table>

## <a name="group-add-member">添加成员 (Add Group Member)</a>

> http://192.168.96.211/services/group/{groupid}/member/add

<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td colspan="2" style="text-align:left;">POST</td></tr>
<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
<tr><td style="text-align:left;">Authorization</td><td style="color:#999;">标准HTTP Basic Authentication内容，包括登录用户的sessionToken和sessionSecret</td></tr>
</table>

### 输入参数

<table border="0" cellpadding="0" cellspacing="0">
<thead><tr>
<td style="text-align:center; background-color:#f5f5f5;">名称</td>
<td style="text-align:center; background-color:#f5f5f5;">类型</td>
<td style="text-align:center; background-color:#f5f5f5;">是否必须</td>
<td style="text-align:center; background-color:#f5f5f5;">默认值</td>
<td style="text-align:center; background-color:#f5f5f5;">说明</td>
</tr></thead>
<tbody><tr>
<td style="text-align:center;">user</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:left;">用户ID，要添加为成员的用户ID</td>
</tr><tr>
<td style="text-align:center;">username</td>
<td style="text-align:center;">String, Restricted</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:left;">要添加为成员的用户名，即手机号码或电子邮件地址</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{
	"status" : 200,
	"message" : "OK"
}
</code>

#### 常见错误信息

<table border="0" cellpadding="0" cellspacing="0">
<thead><tr>
<td style="text-align:center; background-color:#f5f5f5;">status</td>
<td style="text-align:center; background-color:#f5f5f5;">message</td>
<td style="text-align:center; background-color:#f5f5f5;">说明</td>
</tr></thead>
<tbody>
<tr>
<td style="text-align:center;">400</td>
<td style="text-align:left;">must specify a user</td>
<td style="text-align:left;">必须指定一个用户</td>
</tr><tr>
<td style="text-align:center;">403</td>
<td style="text-align:left;">access denied</td>
<td style="text-align:left;">需要的登陆才可以进行操作</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">group not exists</td>
<td style="text-align:left;">此群组不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">user not exists</td>
<td style="text-align:left;">此用户不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">user already added</td>
<td style="text-align:left;">此用户已经在群组中了</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">not group admin</td>
<td style="text-align:left;">没有足够的权限执行此操作-不是群组管理员</td>
</tr></tbody>
</table>


## <a name="group-delete-member">删除成员 (Delete Group Member)</a>

> http://192.168.96.211/services/group/{groupid}/member/delete

<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td colspan="2" style="text-align:left;">POST</td></tr>
<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
<tr><td style="text-align:left;">Authorization</td><td style="color:#999;">标准HTTP Basic Authentication内容，包括登录用户的sessionToken和sessionSecret</td></tr>
</table>

### 输入参数

<table border="0" cellpadding="0" cellspacing="0">
<thead><tr>
<td style="text-align:center; background-color:#f5f5f5;">名称</td>
<td style="text-align:center; background-color:#f5f5f5;">类型</td>
<td style="text-align:center; background-color:#f5f5f5;">是否必须</td>
<td style="text-align:center; background-color:#f5f5f5;">默认值</td>
<td style="text-align:center; background-color:#f5f5f5;">说明</td>
</tr></thead>
<tbody><tr>
<td style="text-align:center;">user</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:left;">用户ID，要添加为成员的用户ID</td>
</tr><tr>
<td style="text-align:center;">username</td>
<td style="text-align:center;">String, Restricted</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:left;">要添加为成员的用户名，即手机号码或电子邮件地址</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{
	"status" : 200,
	"message" : "OK"
}
</code>

#### 常见错误信息

<table border="0" cellpadding="0" cellspacing="0">
<thead><tr>
<td style="text-align:center; background-color:#f5f5f5;">status</td>
<td style="text-align:center; background-color:#f5f5f5;">message</td>
<td style="text-align:center; background-color:#f5f5f5;">说明</td>
</tr></thead>
<tbody>
<tr>
<td style="text-align:center;">400</td>
<td style="text-align:left;">must specify a user</td>
<td style="text-align:left;">必须指定一个用户</td>
</tr><tr>
<td style="text-align:center;">403</td>
<td style="text-align:left;">access denied</td>
<td style="text-align:left;">需要的登陆才可以进行操作</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">group not exists</td>
<td style="text-align:left;">此群组不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">user not exists</td>
<td style="text-align:left;">此用户不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">user not exists in group</td>
<td style="text-align:left;">此用户在群组中不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">not group admin</td>
<td style="text-align:left;">没有足够的权限执行此操作-不是群组管理员</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">cannot remove group owner</td>
<td style="text-align:left;">你不能移除自己</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">not group owner</td>
<td style="text-align:left;">没有足够的权限执行此操作-不是群组拥有者</td>
</tr></tbody>
</table>

## <a name="group-set-administrator">设为管理员 (Set Group Administrator)</a>

> http://192.168.96.211/services/group/{groupid}/administrator/set

<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td colspan="2" style="text-align:left;">POST</td></tr>
<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
<tr><td style="text-align:left;">Authorization</td><td style="color:#999;">标准HTTP Basic Authentication内容，包括登录用户的sessionToken和sessionSecret</td></tr>
</table>

### 输入参数

<table border="0" cellpadding="0" cellspacing="0">
<thead><tr>
<td style="text-align:center; background-color:#f5f5f5;">名称</td>
<td style="text-align:center; background-color:#f5f5f5;">类型</td>
<td style="text-align:center; background-color:#f5f5f5;">是否必须</td>
<td style="text-align:center; background-color:#f5f5f5;">默认值</td>
<td style="text-align:center; background-color:#f5f5f5;">说明</td>
</tr></thead>
<tbody><tr>
<td style="text-align:center;">user</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:left;">用户ID，要设为管理员的用户ID</td>
</tr><tr>
<td style="text-align:center;">username</td>
<td style="text-align:center;">String, Restricted</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:left;">要设为管理员的用户名，即手机号码或电子邮件地址</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{
	"status" : 200,
	"message" : "OK"
}
</code>

#### 常见错误信息

<table border="0" cellpadding="0" cellspacing="0">
<thead><tr>
<td style="text-align:center; background-color:#f5f5f5;">status</td>
<td style="text-align:center; background-color:#f5f5f5;">message</td>
<td style="text-align:center; background-color:#f5f5f5;">说明</td>
</tr></thead>
<tbody>
<tr>
<td style="text-align:center;">400</td>
<td style="text-align:left;">must specify a user</td>
<td style="text-align:left;">必须指定一个用户</td>
</tr><tr>
<td style="text-align:center;">403</td>
<td style="text-align:left;">access denied</td>
<td style="text-align:left;">需要的登陆才可以进行操作</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">group not exists</td>
<td style="text-align:left;">此群组不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">user not exists</td>
<td style="text-align:left;">此用户不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">admin already added</td>
<td style="text-align:left;">此用户已经是管理员了</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">not group owner</td>
<td style="text-align:left;">没有足够的权限执行此操作-不是群组拥有者</td>
</tr></tbody>
</table>

## <a name="group-clear-administrator">清除管理员 (Clear Group Administrator)</a>

> http://192.168.96.211/services/group/{groupid}/administrator/clear

<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td colspan="2" style="text-align:left;">POST</td></tr>
<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
<tr><td style="text-align:left;">Authorization</td><td style="color:#999;">标准HTTP Basic Authentication内容，包括登录用户的sessionToken和sessionSecret</td></tr>
</table>

### 输入参数

<table border="0" cellpadding="0" cellspacing="0">
<thead><tr>
<td style="text-align:center; background-color:#f5f5f5;">名称</td>
<td style="text-align:center; background-color:#f5f5f5;">类型</td>
<td style="text-align:center; background-color:#f5f5f5;">是否必须</td>
<td style="text-align:center; background-color:#f5f5f5;">默认值</td>
<td style="text-align:center; background-color:#f5f5f5;">说明</td>
</tr></thead>
<tbody><tr>
<td style="text-align:center;">user</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:left;">用户ID，要清除管理员的用户ID</td>
</tr><tr>
<td style="text-align:center;">username</td>
<td style="text-align:center;">String, Restricted</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:left;">要清除管理员的用户名，即手机号码或电子邮件地址</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{
	"status" : 200,
	"message" : "OK"
}
</code>

#### 常见错误信息

<table border="0" cellpadding="0" cellspacing="0">
<thead><tr>
<td style="text-align:center; background-color:#f5f5f5;">status</td>
<td style="text-align:center; background-color:#f5f5f5;">message</td>
<td style="text-align:center; background-color:#f5f5f5;">说明</td>
</tr></thead>
<tbody>
<tr>
<td style="text-align:center;">400</td>
<td style="text-align:left;">must specify a user</td>
<td style="text-align:left;">必须指定一个用户</td>
</tr><tr>
<td style="text-align:center;">403</td>
<td style="text-align:left;">access denied</td>
<td style="text-align:left;">需要的登陆才可以进行操作</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">group not exists</td>
<td style="text-align:left;">此群组不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">user not exists</td>
<td style="text-align:left;">此用户不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">admin not exists</td>
<td style="text-align:left;">此管理员不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">cannot remove yourself</td>
<td style="text-align:left;">你不能移除自己</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">not group owner</td>
<td style="text-align:left;">没有足够的权限执行此操作-不是群组拥有者</td>
</tr></tbody>
</table>

## <a name="list-group-members">查询群组成员 (List Group Members)</a>

> http://192.168.96.211/services/group/{groupid}/member/list

<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td colspan="2" style="text-align:left;">GET</td></tr>
<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
<tr><td style="text-align:left;">Authorization</td><td style="color:#999;">标准HTTP Basic Authentication内容，包括登录用户的sessionToken和sessionSecret</td></tr>
</table>

### 输入参数

<table border="0" cellpadding="0" cellspacing="0">
<thead><tr>
<td style="text-align:center; background-color:#f5f5f5;">名称</td>
<td style="text-align:center; background-color:#f5f5f5;">类型</td>
<td style="text-align:center; background-color:#f5f5f5;">是否必须</td>
<td style="text-align:center; background-color:#f5f5f5;">默认值</td>
<td style="text-align:center; background-color:#f5f5f5;">说明</td>
</tr></thead>
<tbody><tr>
<td style="text-align:center;">keywords</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:left;">关键词，应用于用户的name、mobile和email三个字段上</td>
</tr><tr>
<td style="text-align:center;">status</td>
<td style="text-align:center;">String, Restricted</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">ALL_STATUS</td>
<td style="text-align:left;">查询状态，三个选项：<br><b>ALL_STATUS</b>不限状态；<br><b>ACTIVED</b>可用状态；<br/><b>DISABLED</b>停用状态；</td>
</tr><tr>
<td style="text-align:center;">page</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">1</td>
<td style="text-align:left;">当前页码，从1开始</td>
</tr><tr>
<td style="text-align:center;">offset</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">20</td>
<td style="text-align:left;">每页记录数量</td>
</tr><tr>
<td style="text-align:center;">order</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:left;">排序字段，可选: name, created, updated</td>
</tr><tr>
<td style="text-align:center;">acs</td>
<td style="text-align:center;">Boolean</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">false</td>
<td style="text-align:left;">是否升序排列</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{
	"status" : 200,
	"message" : "OK",
	"result" : {
		"hasPrevious" : false,
		"hasNext" : false,
		"total" : 5,
		"entites" : [{
			"unique" : 1,
			"name" : "张三",
			"gender" : "MALE",
			"age" : 28,
			"enterprises" : ["894320483","483920843"],
			"mobile" : "...",
			"email" : "...",
			"country" : "CHINA",
			"province" : "BEIJING",
			"city" : "HAIDIAN",
			"address" : "",
			"avatarUrl" : "http://...",
			"signature" : "..."
		},...]
	}
}
</code>

#### 数据说明

<table border="0" cellpadding="0" cellspacing="0">
<thead><tr>
<td style="text-align:center; background-color:#f5f5f5;">名称</td>
<td style="text-align:center; background-color:#f5f5f5;">类型</td>
<td style="text-align:center; background-color:#f5f5f5;">是否必须</td>
<td style="text-align:center; background-color:#f5f5f5;">说明</td>
</tr></thead>
<tbody><tr>
<td style="text-align:center;">hasPrevious</td>
<td style="text-align:center;">Boolean</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">是否有上一页</td>
</tr><tr>
<td style="text-align:center;">hasNext</td>
<td style="text-align:center;">Boolean</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">是否有下一页</td>
</tr><tr>
<td style="text-align:center;">total</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">总的记录数量</td>
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
</tr><tr>
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
</tr></tbody>
</table>

#### 常见错误信息

<table border="0" cellpadding="0" cellspacing="0">
<thead><tr>
<td style="text-align:center; background-color:#f5f5f5;">status</td>
<td style="text-align:center; background-color:#f5f5f5;">message</td>
<td style="text-align:center; background-color:#f5f5f5;">说明</td>
</tr></thead>
<tbody>
<tr>
<td style="text-align:center;">403</td>
<td style="text-align:left;">access denied</td>
<td style="text-align:left;">需要的登陆才可以进行操作</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">group access denied</td>
<td style="text-align:left;">此群组不存在</td>
</tr></tbody>
</table>
