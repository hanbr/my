## <a name="create">创建云应用(Create Application)</a>

> http://api.htaiyun.com/v1/application/create

<table border="0" cellpadding="0" cellspacing="0">
	<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
<tr><td style="text-align:left;">Authorization</td><td style="color:#999;">标准HTTP Basic Authentication内容，包括登录用户的sessionToken和sessionSecret</td></tr>
</table>

提供创建云应用信息接口，在产品需求中，管理员可以创建云应用信息。基本流程如下：

1. 输入应用名称、描述、允许的license数量，并选择模板文件，选择云应用的LOGO。
2. 提交云应用表单，提交前需验证：

	a. 云应用名称是否不为空，长度不超过200；
	
	b. 云应用显示名是否不为空；
	
	c. 允许的license数量是否不为空；
	
	d. 模板文件是否不为空；
	
	e. LOGO是否不为空；

3. 如果创建成功，系统将返回创建成功的云应用对象数据；如果创建失败，则系统返回错误信息。

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
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">云应用的名称，须确保系统级全局唯一</td>
</tr><tr>
<td style="text-align:center;">displayname</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">云应用显示名</td>
</tr><tr>
<td style="text-align:center;">description</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">云应用描述，介绍应用的功能特点等</td>
</tr><tr>
<td style="text-align:center;">licensecount</td>
<td style="text-align:center;">Long</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">允许的license数量</td>
</tr><tr>
<td style="text-align:center;">picture</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">云应用的LOGO图标信息，两种情况：<br>
如果是默认LOGO,则为"default:"+图片名称，即图片名称加前缀"default:"；<br>
如果是自定义，则为上传的图片文件的unique；</td>
</tr><tr>
<td style="text-align:center;">lowest</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">主机类型最低配置</td>
</tr><tr>
<td style="text-align:center;">highest</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">主机类型最高配置</td>
</tr><tr>
<td style="text-align:center;">recommended</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">主机类型推荐配置</td>
</tr><tr>
<td style="text-align:center;">image</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">镜像名称</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{
  "status" : 200,
  "message" : "OK",
  "result" : {
    "unique" : 8,    
    "name" : "58到家",
    "description" : "58到家为您提供专业、便捷、安心的标准化的到家服务,主要包括家政保洁、丽人美甲、搬家速运三大项自营服务,以及月嫂、化妆、洗车等平台服务。",
    "picture" : "default:1.img",
	"templete": "{\r\n    \"heat_template_version\": \"2015-10-15\",\r\n    \"description\": \"Launch a basic 			 instance with..}",
	"licenseCount":5,
	"instanceCount":0,
	"status" : "ACTIVED",
    "created" : 1478515351896,
    "updated" : 1478515351896,
    "links" : [ ]
  },
  "links" : [ ]
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
<td style="text-align:center;">Long</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">应用的ID</td>
</tr><tr>
<td style="text-align:center;">name</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">应用名称</td>
</tr><tr>
<td style="text-align:center;">displayName</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">应用显示名</td>
</tr><tr>
<td style="text-align:center;">description</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:left;">对应用的功能、特点的描述</td>
</tr><tr>
<td style="text-align:center;">picture</td>
<td style="text-align:center;">String/FileDomain</td>
<td style="text-align:center;">No</td>
<td style="text-align:left;">应用的LOGO图标信息</td>
</tr><tr>
<td style="text-align:center;">templete</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">模板内容</td>
</tr><tr>
<td style="text-align:center;">licenseCount</td>
<td style="text-align:center;">Long</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">许可的license数量</td>
</tr><tr>
<td style="text-align:center;">instancecount</td>
<td style="text-align:center;">Long</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">已创建的实例数量</td>
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
<td style="text-align:left;">当前登录的用户身份校验未通过，可能是用户session过期、无效session、或者不存在的用户</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">application name already used</td>
<td style="text-align:left;">无效的应用名，表示应用名已经被占用</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">flavor not exists</td>
<td style="text-align:left;">所选配置文件不存在</td>
</tr></tbody>
</table>


## <a name="update">修改云应用(Update Application)</a>

> http://api.htaiyun.com/v1/application/{id}/update

<table border="0" cellpadding="0" cellspacing="0">
	<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
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
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">应用的名称，须确保系统级全局唯一</td>
</tr><tr>
<td style="text-align:center;">displayname</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">应用显示名</td>
</tr><tr>
<td style="text-align:center;">description</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">应用描述，介绍应用的功能特点等</td>
</tr><tr>
<td style="text-align:center;">picture</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">云应用的LOGO图标信息，两种情况：<br>
如果是默认LOGO,则为"default:"+图片名称，即图片名称加前缀"default:"；<br>
如果是自定义，则为上传的图片文件的unique；</td>
</tr><tr>
<td style="text-align:center;">licensecount</td>
<td style="text-align:center;">Long</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">允许的license数量</td>
</tr><tr>
<td style="text-align:center;">lowest</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">主机类型最低配置</td>
</tr><tr>
<td style="text-align:center;">highest</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">主机类型最高配置</td>
</tr><tr>
<td style="text-align:center;">recommended</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">主机类型推荐配置</td>
</tr><tr>
<td style="text-align:center;">image</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">镜像名称</td>
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

#### 数据说明

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
<td style="text-align:left;">当前登录的用户身份校验未通过，可能是用户session过期、无效session、或者不存在的用户</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">application name already used</td>
<td style="text-align:left;">无效的应用名，表示应用名已经被占用</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">application not exits</td>
<td style="text-align:left;">所要修改的应用不存在</td>
</tr>
</tbody>
</table>

## <a name="delete">删除云应用 (Delete Application)</a>

> http://api.htaiyun.com/v1/application/{id}/delete

<table border="0" cellpadding="0" cellspacing="0">
	<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
<tr><td style="text-align:left;">Authorization</td><td style="color:#999;">标准HTTP Basic Authentication内容，包括登录用户的sessionToken和sessionSecret</td></tr>
</table>

### 输入参数

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
<td style="text-align:center;">403</td>
<td style="text-align:left;">access denied</td>
<td style="text-align:left;">当前登录的用户身份校验未通过，可能是用户session过期、无效session、或者不存在的用户</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">application not exits</td>
<td style="text-align:left;">所要删除的应用不存在</td>
</tr>
</tbody>
</table>

## <a name="enable-application">启用云应用 (Enable Application)</a>

> http://192.168.96.211/services/application/{applicationid}/enable

<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
<tr><td style="text-align:left;">Authorization</td><td style="color:#999;">标准HTTP Basic Authentication内容，包括登录用户的sessionToken和sessionSecret</td></tr>
</table>


### 输入参数


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
<td style="text-align:center;">403</td>
<td style="text-align:left;">access denied</td>
<td style="text-align:left;">当前登录的用户身份校验未通过，可能是用户session过期、无效session、或者不存在的用户</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">application not exists</td>
<td style="text-align:left;">所要启用的应用不存在</td>
</tr></tbody>
</table>

## <a name="disable-application">禁用云应用 (Disable Application)</a>

> http://192.168.96.211/services/application/{applicationid}/disable

<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
<tr><td style="text-align:left;">Authorization</td><td style="color:#999;">标准HTTP Basic Authentication内容，包括登录用户的sessionToken和sessionSecret</td></tr>
</table>

### 输入参数


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
<td style="text-align:center;">403</td>
<td style="text-align:left;">access denied</td>
<td style="text-align:left;">当前登录的用户身份校验未通过，可能是用户session过期、无效session、或者不存在的用户</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">application not exists</td>
<td style="text-align:left;">所要禁用的应用不存在</td>
</tr></tbody>
</table>

## <a name="list">查询云应用 (List Application)</a>

> http://api.htaiyun.com/v1/application/list

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">GET</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
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
<td style="text-align:left;">关键词，应用于name,displayName字段上</td>
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
    "total" : 7,
    "hasPrevious" : false,
    "hasNext" : false,
    "entities" : [ {
	    "unique" : 8,    
	    "name" : "58到家",
	    "description" : "58到家为您提供专业、便捷、安心的标准化的到家服务,主要包括家政保洁、丽人美甲、搬家速运三大项自营服务,以及月嫂、化妆、洗车等平台服务。",
	    "picture" : "default:1.img",
		"templete": "{\r\n    \"heat_template_version\": \"2015-10-15\",\r\n    \"description\": \"Launch a basic 			 instance with..}",
		"licenseCount":5,
		"instanceCount":0,
		"status" : "ACTIVED",
	    "created" : 1478515351896,
	    "updated" : 1478515351896,
	    "links" : [ ]
  },,,,,,],
    "links" : [ ]
  },
  "links" : [ ]
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
<td style="text-align:center;">total</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">记录条数</td>
</tr><tr>
<td style="text-align:center;">hasPrevious</td>
<td style="text-align:center;">boolean</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">是否有上一页</td>
</tr><tr>
<td style="text-align:center;">hasNext</td>
<td style="text-align:center;">boolean</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">是否有下一页</td>
</tr><tr>
<td style="text-align:center;">entities</td>
<td style="text-align:center;">array</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">具体应用记录信息</td>
</tr></tbody>
</table>

## <a name="get">读取云应用(Get Application)</a>

> http://api.htaiyun.com/v1/application/{applicationid}/get

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">GET</td><td></td></tr>
	<tr><th rowspan=2 style="text-align:right; background-color:#f5f5f5;">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">Authorization</td><td style="color:#999;">标准HTTP Basic Authentication内容，包括登录用户的sessionToken和sessionSecret</td></tr>
</table>

### 输入参数

### 输出数据

#### 返回实例

<code>
{
  "status" : 200,
  "message" : "OK",
  "result" : {
    "unique" : 8,    
    "name" : "58到家",
    "description" : "58到家为您提供专业、便捷、安心的标准化的到家服务,主要包括家政保洁、丽人美甲、搬家速运三大项自营服务,以及月嫂、化妆、洗车等平台服务。",
    "picture" : "default:1.img",
	"templete": "{\r\n    \"heat_template_version\": \"2015-10-15\",\r\n    \"description\": \"Launch a basic 			 instance with..}",
	"licenseCount":5,
	"instanceCount":0,
	"status" : "ACTIVED",
    "created" : 1478515351896,
    "updated" : 1478515351896,
    "links" : [ ]
  },
  "links" : [ ]
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
<td style="text-align:center;">Long</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">应用的ID</td>
</tr><tr>
<td style="text-align:center;">name</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">应用名称</td>
</tr><tr>
<td style="text-align:center;">displayName</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">应用显示名</td>
</tr><tr>
<td style="text-align:center;">description</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:left;">对应用的功能、特点的描述</td>
</tr><tr>
<td style="text-align:center;">picture</td>
<td style="text-align:center;">String/FileDomain</td>
<td style="text-align:center;">No</td>
<td style="text-align:left;">应用的LOGO图标信息</td>
</tr><tr>
<td style="text-align:center;">templete</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">模板内容</td>
</tr><tr>
<td style="text-align:center;">licenseCount</td>
<td style="text-align:center;">Long</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">许可的license数量</td>
</tr><tr>
<td style="text-align:center;">instancecount</td>
<td style="text-align:center;">Long</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">已创建的实例数量</td>
</tr></tbody>
</table>

## <a name="batch-enable-application">批量启用云应用 (Batch Enable Application)</a>

> http://192.168.96.211/services/application/batchenable

<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
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
<td style="text-align:center;">ids</td>
<td style="text-align:center;">Long[]</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">云应用ID数组</td>
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
<td style="text-align:center;">403</td>
<td style="text-align:left;">access denied</td>
<td style="text-align:left;">当前登录的用户身份校验未通过，可能是用户session过期、无效session、或者不存在的用户</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">application not exists</td>
<td style="text-align:left;">所要启用的应用不存在</td>
</tr></tbody>
</table>

## <a name="batch-disable-application">批量禁用云应用 (Batch Disable Application)</a>

> http://192.168.96.211/services/application/batchdisable

<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
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
<td style="text-align:center;">ids</td>
<td style="text-align:center;">Long[]</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">云应用ID数组</td>
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
<td style="text-align:center;">403</td>
<td style="text-align:left;">access denied</td>
<td style="text-align:left;">当前登录的用户身份校验未通过，可能是用户session过期、无效session、或者不存在的用户</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">application not exists</td>
<td style="text-align:left;">所要禁用的应用不存在</td>
</tr></tbody>
</table>


