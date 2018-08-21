# <a name="templates">模板管理 (Templates)</a>

## <a name="create-template">创建模板 (Create Template)</a>

> http://api.htaiyun.com/v1/openstack/template/create

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-TOKEN</td><td style="color:#999;">当前用户会话ID</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-SECRET</td><td style="color:#999;">当前用户会话密钥</td></tr>
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
<td style="text-align:center;">uid</td>
<td style="text-align:center;">long</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">用户ID</td>
</tr><tr>
<td style="text-align:center;">name</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">模板名称</td>
</tr><tr>
<td style="text-align:center;">template</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">模板内容（JSON格式）</td>
</tr><tr>
<td style="text-align:center;">description</td>
<td style="text-align:center;"></td>
<td style="text-align:center;">NO</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">描述</td>
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
		"name" : "..."
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
<td style="text-align:left;">模板ID</td>
</tr><tr>
<td style="text-align:center;">name</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">模板名称</td>
</tr><tr>
<td style="text-align:center;">template</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">模板内容</td>
</tr><tr>
<td style="text-align:center;">description</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">模板描述</td>
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
<td style="text-align:center;">403</td>
<td style="text-align:left;">access denied</td>
<td style="text-align:left;">需要的登陆才可以进行操作</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">template unable empty</td>
<td style="text-align:left;">模板创建失败</td>
</tr></tbody>
</table>

## <a name="delete-template">删除模板 (Delete Template)</a>

> http://api.htaiyun.com/v1/openstack/template/{templateid}/delete

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-TOKEN</td><td style="color:#999;">当前用户会话ID</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-SECRET</td><td style="color:#999;">当前用户会话密钥</td></tr>
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
<td style="text-align:center;">templateid</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">模板ID</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{
	"status" : 200,
	"message" : "OK",
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
<td style="text-align:center;">403</td>
<td style="text-align:left;">access denied</td>
<td style="text-align:left;">需要的登陆才可以进行操作</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">template not exists</td>
<td style="text-align:left;">删除失败</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">template not owned</td>
<td style="text-align:left;">删除失败</td>
</tr></tbody>
</table>

## <a name="get-template">获取模版 (Get Template)</a>

> http://api.htaiyun.com/v1/openstack/template/{templateid}/get

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">GET</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-TOKEN</td><td style="color:#999;">当前用户会话ID</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-SECRET</td><td style="color:#999;">当前用户会话密钥</td></tr>
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
<td style="text-align:center;">templateid</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">模板ID</td>
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
		"name" : "..."
	}
}
</code>

## <a name="list-template">查询模版集合 (List Template)</a>

> http://api.htaiyun.com/v1/openstack/template/list

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">GET</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-TOKEN</td><td style="color:#999;">当前用户会话ID</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-SECRET</td><td style="color:#999;">当前用户会话密钥</td></tr>
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
<td style="text-align:center;"></td>
<td style="text-align:left;">关键词，应用于template的name</td>
</tr><tr>
<td style="text-align:center;">status</td>
<td style="text-align:center;">String, Restricted</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">ALL_STATUS</td>
<td style="text-align:left;">查询状态，选项：<br><b>ALL_STATUS</b>不限状态；<br><b>ACTIVED</b>可用状态；<br><b>DISABLED</b>停用状态；</td>
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
<td style="text-align:center;">asc</td>
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
			...,
			"status" : "ACTIVED",
			"created" : ...,
			"updated" : ...
		},...]
	}
}
}
</code>

## <a name="enable-template">启用或禁用模板 (enable template)</a>

> http://api.htaiyun.com/v1/openstack/template/{templateid}/enable


<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-TOKEN</td><td style="color:#999;">当前用户会话ID</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-SECRET</td><td style="color:#999;">当前用户会话密钥</td></tr>
</table>

### 输入参数

<table border="0" cellpadding="0" cellspacing="0">
<thead><tr>
<td style="text-align:center; background-color:#f5f5f5;">名称</td>
<td style="text-align:center; background-color:#f5f5f5;">类型</td>
<td style="text-align:center; background-color:#f5f5f5;">是否必须</td>
<td style="text-align:center; background-color:#f5f5f5;">说明</td>
</tr></thead>
<tbody><tr>
<td style="text-align:center;">status</td>
<td style="text-align:center;">String, Restricted</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">二个选项：<br><b>ACTIVED</b>启用模板；<br><b>DISABLED</b>禁用模板；</td>
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