## <a name="create">创建云应用实例实例(Create ApplicationInstance)</a>

> http://api.htaiyun.com/v1/applicationinstance/create

<table border="0" cellpadding="0" cellspacing="0">
	<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
<tr><td style="text-align:left;">Authorization</td><td style="color:#999;">标准HTTP Basic Authentication内容，包括登录用户的sessionToken和sessionSecret</td></tr>
</table>

提供创建云应用实例接口，在产品需求中，管理员可以直接创建云应用实例。基本流程如下：

1. 输入云应用实例的名称、显示名、描述；选择所有者、云应用、配置类型；
2. 提交云应用实例申请表单，提交前需验证：

	a. 云应用实例名称是否不为空，长度不超过200；
	
	b. 云应用实例显示名是否不为空；
	
	c. 所有者、云应用、配置类型、是否不为空；
		

3. 如果创建成功，系统将返回创建成功的云应用实例对象数据；如果创建失败，则系统返回错误信息。

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
<td style="text-align:left;">云应用实例的名称，须确保系统级全局唯一</td>
</tr><tr>
<td style="text-align:center;">displayname</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">云应用实例显示名</td>
</tr><tr>
<td style="text-align:center;">description</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">云应用实例描述</td>
</tr><tr>
<td style="text-align:center;">userid</td>
<td style="text-align:center;">long</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">实例所有者的用户ID</td>
</tr><tr>
<td style="text-align:center;">applicationid</td>
<td style="text-align:center;">long</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">云应用ID</td>
</tr><tr>
<td style="text-align:center;">flavorconfig</td>
<td style="text-align:center;">String,Restricted</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">配置类型，有三个可选项：<br>LOWEST(最低配置);<br>RECOMMENDED(推荐配置);<br>HIGHEST(最高配置);</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{
  	"status": 200,
    "message": "OK",
    "result": {
        "unique": 3,
        "status": "ACTIVED",
        "created": 1479885261773,
        "updated": 1479885261773,
        "name": "appinsliylins",
        "displayName": "appinsliylins",
        "description": null,
        "applicationDomain": {
            "unique": 2,
            "status": "ACTIVED",
            "created": 1479883908575,
            "updated": 1479883908575,
            "name": "appliylapp",
            "displayName": "appliylapp",
            "description": null,
            "picture": null,
            "fileId": "58353c0b239dfd1971418847",
            "links": []
        },
        "flavorConfig": "lOWEST",
		"userStack" :{
			"unique" : "5835412b239d68d11c08c33f",    
		    "name" : "stackliyl",
			"stackId" : "7f784229-1457-4d4f-bd1f-fb03d375feb3",
			"userServer" : {
				"unique" : "5825cb51b26cb225016ba248",    
			    "name" : "serverliyl",
				"serverId" : "967942b2-4983-48b5-8a25-4d88c2015d1b",
				"flavor" : {
					"unique" : "582d4984239d9a99eba405c9",
					"flavorId" : "a7bbece1-3ebd-4713-b848-941655da5c1d",
					...
				},
				...
			},
			...
		},
		 "owner": {
	            "unique": 1,
	            "status": "ACTIVED",
	            "created": 1479456060780,
	            "updated": 1479456060951,
	            "username": "18011873436",
	            "type": "PERSONAL",
	            "name": null,
	            "mobile": "18011873436",
	            "email": "18011873436",
	            "avatarUrl": "null/avatar/preset/default-user.jpg",
	            "links": []
	        },
	        "links": []
	    },
	    "links": []
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
<td style="text-align:center;">name</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">云应用实例的名称</td>
</tr><tr>
<td style="text-align:center;">displayName</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">云应用实例显示名</td>
</tr><tr>
<td style="text-align:center;">description</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:left;">云应用实例描述</td>
</tr><tr>
<td style="text-align:center;">applicationDomain</td>
<td style="text-align:center;">ApplicationDomain</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">云应用信息</td>
</tr><tr>
<td style="text-align:center;">flavorConfig</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">主机配置</td>
</tr><tr>
<td style="text-align:center;">userStack</td>
<td style="text-align:center;">UserStackDomain</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">Stack信息</td>
</tr><tr>
<td style="text-align:center;">owner</td>
<td style="text-align:center;">UserSimpleDomain</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">云应用实例所有者信息</td>
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
<td style="text-align:left;">无效的应用实例名，表示已经被占用</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">application not exists</td>
<td style="text-align:left;">所选云应用不存在</td>
</tr><tr>
<td style="text-align:center;">500</td>
<td style="text-align:left;">*</td>
<td style="text-align:left;">可能是创建服务器失败</td>
</tr></tbody>
</table>


## <a name="update">修改云应用实例(Update ApplicationInstance)</a>

> http://api.htaiyun.com/v1/applicationinstance/{id}/update

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
<td style="text-align:left;">云应用实例的名称，须确保系统级全局唯一</td>
</tr><tr>
<td style="text-align:center;">displayname</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">云应用实例显示名</td>
</tr><tr>
<td style="text-align:center;">description</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">云应用实例描述</td>
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
<td style="text-align:left;">无效的云应用实例名，表示应用名已经被占用</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">application not exits</td>
<td style="text-align:left;">所要修改的云应用实例不存在</td>
</tr>
</tbody>
</table>

## <a name="delete">删除云应用实例 (Delete ApplicationInstance)</a>

> http://api.htaiyun.com/v1/applicationinstance/{id}/delete

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
<td style="text-align:left;">所要删除的云应用实例不存在</td>
</tr>
</tbody>
</table>

## <a name="batch-delete">批量删除云应用实例 (Batch Delete ApplicationInstance)</a>

> http://api.htaiyun.com/v1/applicationinstance/delete

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
<td style="text-align:center;">ids</td>
<td style="text-align:center;">Long[]</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:left;">逗号分隔的要删除的云应用实例ID</td>
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
<td style="text-align:left;">application not exits</td>
<td style="text-align:left;">所要删除的云应用实例不存在</td>
</tr>
</tbody>
</table>

## <a name="add-instance-user">添加云应用实例的用户 (Add ApplicationInstance User)</a>

> http://192.168.96.211/applicationinstance/{id}/user/add

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
<td style="text-align:center;">userid</td>
<td style="text-align:center;">Long</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:left;">用户ID</td>
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
<td style="text-align:left;"> user not exists!</td>
<td style="text-align:left;">所选用户不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">role not found</td>
<td style="text-align:left;">云应用实例不存在</td>
</tr></tbody>
</table>

## <a name="delete-instance-user">删除云应用实例的用户 (Delete InstanceUser )</a>

> http://192.168.96.211/applicationinstance/{id}/user/delete

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
<td style="text-align:center;">userid</td>
<td style="text-align:center;">Long</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:left;">用户ID</td>
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
<td style="text-align:left;"> user not exists!</td>
<td style="text-align:left;">云应用实例不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">role not found</td>
<td style="text-align:left;">用户不存在</td>
</tr></tbody>
</table>

## <a name="batch-add-instanceuser">批量添加云应用实例的用户 (Bactch Add InstanceUser )</a>

> http://192.168.96.211/applicationinstance/{id}/user/batchadd

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
<td style="text-align:center;">userids</td>
<td style="text-align:center;">Long[]</td>
<td style="text-align:center;">Yes</td>
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
<td style="text-align:left;"> user not exists!</td>
<td style="text-align:left;">所选用户不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">role not found</td>
<td style="text-align:left;">云应用实例不存在</td>
</tr></tbody>
</table>

## <a name="batch-delete-instanceuser">批量删除云应用实例的用户 (Batch Delete InstanceUser )</a>

> http://192.168.96.211/applicationinstance/{id}/user/batchdelete

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
<td style="text-align:center;">userids</td>
<td style="text-align:center;">Long[]</td>
<td style="text-align:center;">Yes</td>
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
<td style="text-align:left;"> user not exists!</td>
<td style="text-align:left;">云应用实例不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">role not found</td>
<td style="text-align:left;">用户不存在</td>
</tr></tbody>
</table>

## <a name="user-list">查询云应用实例的用户 (List InstanceUsers)</a>

> http://api.htaiyun.com/v1/applicationinstance/{id}/user/list

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
<td style="text-align:left;">关键词，应用于用户的name字段上</td>
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
      "status" : "ACTIVED",
	  "optionalflavorids" : "1,2,3",
	  "optionalflavorids" : "1,2,3",
      "created" : 1478515351896,
      "updated" : 1478515351896,
      "name" : "liyl",
      "mobile" : "18921214565",
	  ...
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
<td style="text-align:left;">具体用户信息</td>
</tr></tbody>
</table>

## <a name="get">读取云应用实例(Get ApplicationInstance)</a>

> http://api.htaiyun.com/v1/applicationinstance/{id}/get

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
  	"status": 200,
    "message": "OK",
    "result": {
        "unique": 3,
        "status": "ACTIVED",
        "created": 1479885261773,
        "updated": 1479885261773,
        "name": "appinsliylins",
        "displayName": "appinsliylins",
        "description": null,
        "applicationDomain": {
            "unique": 2,
            "status": "ACTIVED",
            "created": 1479883908575,
            "updated": 1479883908575,
            "name": "appliylapp",
            "displayName": "appliylapp",
            "description": null,
            "picture": null,
            "fileId": "58353c0b239dfd1971418847",
            "links": []
        },
        "flavorConfig": "lOWEST",
		"userStack" :{
			"unique" : "5835412b239d68d11c08c33f",    
		    "name" : "stackliyl",
			"stackId" : "7f784229-1457-4d4f-bd1f-fb03d375feb3",
			"userServer" : {
				"unique" : "5825cb51b26cb225016ba248",    
			    "name" : "serverliyl",
				"serverId" : "967942b2-4983-48b5-8a25-4d88c2015d1b",
				"flavor" : {
					"unique" : "582d4984239d9a99eba405c9",
					"flavorId" : "a7bbece1-3ebd-4713-b848-941655da5c1d",
					...
				},
				...
			},
			...
		},
		 "owner": {
	            "unique": 1,
	            "status": "ACTIVED",
	            "created": 1479456060780,
	            "updated": 1479456060951,
	            "username": "18011873436",
	            "type": "PERSONAL",
	            "name": null,
	            "mobile": "18011873436",
	            "email": "18011873436",
	            "avatarUrl": "null/avatar/preset/default-user.jpg",
	            "links": []
	        },
	        "links": []
	    },
	    "links": []
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
<td style="text-align:center;">name</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">云应用实例的名称</td>
</tr><tr>
<td style="text-align:center;">displayName</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">云应用实例显示名</td>
</tr><tr>
<td style="text-align:center;">description</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:left;">云应用实例描述</td>
</tr><tr>
<td style="text-align:center;">applicationDomain</td>
<td style="text-align:center;">ApplicationDomain</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">云应用信息</td>
</tr><tr>
<td style="text-align:center;">flavorConfig</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">主机配置</td>
</tr><tr>
<td style="text-align:center;">userStack</td>
<td style="text-align:center;">UserStackDomain</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">Stack信息</td>
</tr><tr>
<td style="text-align:center;">owner</td>
<td style="text-align:center;">UserSimpleDomain</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">云应用实例所有者信息</td>
</tr></tbody>
</table>


## <a name="applicationinstance-list">查询云应用实例 (List ApplicationInstance)</a>

> http://api.htaiyun.com/v1/applicationinstance/list

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
<td style="text-align:center;">userid</td>
<td style="text-align:center;">long</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:left;">用户ID</td>
</tr><tr>
<td style="text-align:center;">applicationid</td>
<td style="text-align:center;">long</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:left;">云应用ID</td>
</tr><tr>
<td style="text-align:center;">keywords</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:left;">关键词，应用于用户的name字段上</td>
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
        "unique": 3,
        "status": "ACTIVED",
        "created": 1479885261773,
        "updated": 1479885261773,
        "name": "appinsliylins",
        "displayName": "appinsliylins",
        "description": null,
        "applicationDomain": {
            "unique": 2,
            "status": "ACTIVED",
            "created": 1479883908575,
            "updated": 1479883908575,
            "name": "appliylapp",
            "displayName": "appliylapp",
            "description": null,
            "picture": null,
            "fileId": "58353c0b239dfd1971418847",
            "links": []
        },
        "flavorConfig": "lOWEST",
		"userStack" :{
			"unique" : "5835412b239d68d11c08c33f",    
		    "name" : "stackliyl",
			"stackId" : "7f784229-1457-4d4f-bd1f-fb03d375feb3",
			"userServer" : {
				"unique" : "5825cb51b26cb225016ba248",    
			    "name" : "serverliyl",
				"serverId" : "967942b2-4983-48b5-8a25-4d88c2015d1b",
				"flavor" : {
					"unique" : "582d4984239d9a99eba405c9",
					"flavorId" : "a7bbece1-3ebd-4713-b848-941655da5c1d",
					...
				},
				...
			},
			...
		},
		 "owner": {
	            "unique": 1,
	            "status": "ACTIVED",
	            "created": 1479456060780,
	            "updated": 1479456060951,
	            "username": "18011873436",
	            "type": "PERSONAL",
	            "name": null,
	            "mobile": "18011873436",
	            "email": "18011873436",
	            "avatarUrl": "null/avatar/preset/default-user.jpg",
	            "links": []
	        },
	        "links": [] 
    },,,,,,],
    "links" : [ ]
  },
  "links" : [ ]
}
</code>
