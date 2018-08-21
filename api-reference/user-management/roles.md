# <a name="roles">角色管理 (Roles)</a>

## <a name="create-role">创建角色 (Create Role)</a>

> http://192.168.96.211/services/role/create

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
<td style="text-align:center;">keyname</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">角色名，须确保系统级全局唯一，要求由小写英文字符或数字组成，首字母必须为英文字符，长度为3到40个字符。</td>
</tr><tr>
<td style="text-align:center;">name</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">角色显示名，2到40个字符组成</td>
</tr><tr>
<td style="text-align:center;">description</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">""</td>
<td style="text-align:left;">角色描述信息，120个字符以内</td>
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

---

## <a name="update-role">更新角色 (Update Role)</a>

> http://192.168.96.211/services/role/{roleid}/update

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
<td style="text-align:center;">keyname</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">角色名，须确保系统级全局唯一，要求由小写英文字符或数字组成，首字母必须为英文字符，长度为3到40个字符。</td>
</tr><tr>
<td style="text-align:center;">name</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">角色显示名，2到40个字符组成</td>
</tr><tr>
<td style="text-align:center;">description</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">""</td>
<td style="text-align:left;">角色描述信息，120个字符以内</td>
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

## <a name="delete-role">删除角色 (Delete Role)</a>

> http://192.168.96.211/services/role/{roleid}/delete

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

## <a name="delete-roles">批量删除角色 (Delete Roles)</a>

> http://192.168.96.211/services/role/delete

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
<td style="text-align:center;">roles</td>
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

## <a name="enable-role">启用角色 (Enable Role)</a>

> http://192.168.96.211/services/role/{roleid}/enable

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

## <a name="enalbe-roles">批量启用角色 (Enable Roles)</a>

> http://192.168.96.211/services/role/enable

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
<td style="text-align:center;">roles</td>
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

## <a name="disable-role">停用角色 (Disable Role)</a>

> http://192.168.96.211/services/role/{roleid}/disable

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

## <a name="disable-roles">批量停用角色 (Disable Roles)</a>

> http://192.168.96.211/services/role/enable

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
<td style="text-align:center;">roles</td>
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

## <a name="list-roles">查询角色 (List Roles)</a>

> http://192.168.96.211/services/role/list

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
<td style="text-align:left;">关键词，应用于角色的name和displayName两个字段上</td>
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
			"name" : "administrator",
			"displayName" : "超级管理员",
			"status" : "ACTIVED",
			"total" : 10,
			"created" : 0,
			"updated" : 0
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
<td style="text-align:left;">角色ID</td>
</tr><tr>
<td style="text-align:center;">name</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">角色唯一名，由小写英文字符和数字组成，首字母只能是英文字符</td>
</tr><tr>
<td style="text-align:center;">displayName</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">角色显示名，长度不少于2个字符，不超过40个字符</td>
</tr><tr>
<td style="text-align:center;">status</td>
<td style="text-align:center;">String, Retricted</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">角色状态，可选值包括：<br/>ACTIVED: 可用<br/>DISABLED: 不可用</td>
</tr><tr>
<td style="text-align:center;">created</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">角色创建时间戳，以服务器时间为准</td>
</tr><tr>
<td style="text-align:center;">updated</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">角色属性上次更新时间戳，以服务器时间为准</td>
</tr></tbody>
</table>

## <a name="list-user-roles">查询用户角色 (List User Roles)</a>

> http://192.168.96.211/services/role/{roleid}/users

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
<td style="text-align:center;">user</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">要查询的用户ID</td>
</tr><tr>
<td style="text-align:center;">keywords</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:left;">关键词，应用于角色的name和displayName两个字段上</td>
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
		"name" : "administrator",
		"displayName" : "超级管理员"
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
<td style="text-align:center;">unique</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">角色ID</td>
</tr><tr>
<td style="text-align:center;">name</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">角色唯一名，由小写英文字符和数字组成，首字母只能是英文字符</td>
</tr><tr>
<td style="text-align:center;">displayName</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">角色显示名，长度不少于2个字符，不超过40个字符</td>
</tr></tbody>
</table>

## <a name="add-user-role">添加角色用户 (Add Role User)</a>

> http://192.168.96.211/services/role/{roleid}/user/add

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
<td style="text-align:left;">用户ID</td>
</tr></tbody>
</table>

注意：角色ID和角色名至少需要提交一个

### 输出数据

#### 返回实例

<code>
{ 
"status" : 200, 
"message" : "OK"
}
</code>

## <a name="add-role-users"> 批量添加角色用户 (Add Role Users)</a>

> http://192.168.96.211/services/role/{roleid}/users/add

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
<td style="text-align:center;">users</td>
<td style="text-align:center;">JSONArray</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:left;">用户ID数组，样式为[1, 3, 4]</td>
</tr></tbody>
</table>

注意：角色ID和角色名至少需要提交一个

### 输出数据

#### 返回实例

<code>
{ 
"status" : 200, 
"message" : "OK"
}
</code>

## <a name="delete-role-user">删除角色用户(Delete Role User)</a>

> http://192.168.96.211/services/role/{roleid}/user/delete

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
<td style="text-align:left;">用户ID数组</td>
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


## <a name="delete-role-users">批量删除角色用户(Delete Role Users)</a>

> http://192.168.96.211/services/role/{roleid}/users/delete

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
<td style="text-align:center;">users</td>
<td style="text-align:center;">JSONArray</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:left;">用户ID数组，样式为[1, 3, 4]</td>
</tr></tbody>
</table>

注意：角色ID和角色名至少需要提交一个

### 输出数据

#### 返回实例

<code>
{ 
	"status" : 200, 
	"message" : "OK"
}
</code>

