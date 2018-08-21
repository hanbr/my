# <a name="Enterprise">企业管理 (Enterprise)</a>

## <a name="register-enterprise">注册企业 (Register Enterprise)</a>

> http://api.htaiyun.com/service/enterprise/register

<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
<tr><td style="text-align:left;">HT-SESSION-TOKEN</td><td style="color:#999;">当前用户会话ID</td></tr>
<tr><td style="text-align:left;">HT-SESSION-SECRET</td><td style="color:#999;">当前用户会话密钥</td></tr>
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
<td style="text-align:left;">企业名</td>
</tr><tr>
<td style="text-align:center;">tel</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">企业联系方式</td>
</tr><tr>
<td style="text-align:center;">email</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">企业邮箱</td>
</tr><tr>
<td style="text-align:center;">address</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">企业地址</td>
</tr><tr>
<td style="text-align:center;">description</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">""</td>
<td style="text-align:left;">企业描述信息，200个字符以内</td>
</tr><tr>
<td style="text-align:center;">country</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">国籍</td>
</tr><tr>
<td style="text-align:center;">province</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">省份</td>
</tr><tr>
<td style="text-align:center;">city</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">所在城市</td>
</tr><tr>
<td style="text-align:center;">zipcode</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">邮编</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{
	"status":200,
	"message":"OK",
	"result":{"unique":1,
						"status":"NOT_ACTIVED",
						...
						"admin":{
											"id":1,
											username":"18330382308",
											...,
										}
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
<td style="text-align:left;">企业的ID</td>
</tr><tr>
<td style="text-align:center;">name</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">企业的名字</td>
</tr><tr>
<td style="text-align:center;">tel</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">企业联系方式</td>
</tr><tr>
<td style="text-align:center;">email</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">企业邮箱</td>
</tr><tr>
<td style="text-align:center;">address</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">企业地址</td>
</tr><tr>
<td style="text-align:center;">description</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">企业描述信息，200个字符以内</td>
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
<td style="text-align:center;">zipcode</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:left;">邮编</td>
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
<td style="text-align:left;">invalid name format</td>
<td style="text-align:left;">无效的企业名格式</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">invalid tel format</td>
<td style="text-align:left;">无效的联系电话格式</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">invalid email format</td>
<td style="text-align:left;">无效的企业邮箱格式</td>
</tr>
<tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">no authorized</td>
<td style="text-align:left;">没有足够的权限</td>
</tr></tbody>
</table>

## <a name="update-enterprise">更新企业 (Update Enterprise)</a>

> http://api.htaiyun.com/service/enterprise/{enterpriseid}/update

<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
<tr><td style="text-align:left;">HT-SESSION-TOKEN</td><td style="color:#999;">当前用户会话ID</td></tr>
<tr><td style="text-align:left;">HT-SESSION-SECRET</td><td style="color:#999;">当前用户会话密钥</td></tr>
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
<td style="text-align:center;">No</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">企业名</td>
</tr><tr>
<td style="text-align:center;">tel</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">企业联系方式</td>
</tr><tr>
<td style="text-align:center;">email</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">企业邮箱</td>
</tr><tr>
<td style="text-align:center;">address</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">企业地址</td>
</tr><tr>
<td style="text-align:center;">description</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">""</td>
<td style="text-align:left;">企业描述信息，200个字符以内</td>
</tr><tr>
<td style="text-align:center;">country</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">国籍</td>
</tr><tr>
<td style="text-align:center;">province</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">省份</td>
</tr><tr>
<td style="text-align:center;">city</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">所在城市</td>
</tr><tr>
<td style="text-align:center;">zipcode</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">邮编</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{
	"status":200,
	"message":"OK",
	"result":{"unique":1,
						"status":"NOT_ACTIVED",
						...
						"admin":{
											"id":1,
											username":"18330382308",
											...,
										}
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
<td style="text-align:left;">企业的ID</td>
</tr><tr>
<td style="text-align:center;">name</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">企业的名字</td>
</tr><tr>
<td style="text-align:center;">tel</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">企业联系方式</td>
</tr><tr>
<td style="text-align:center;">email</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">企业邮箱</td>
</tr><tr>
<td style="text-align:center;">address</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">企业地址</td>
</tr><tr>
<td style="text-align:center;">description</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">企业描述信息，200个字符以内</td>
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
<td style="text-align:center;">zipcode</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:left;">邮编</td>
</tr><tr>
<td style="text-align:center;">admin</td>
<td style="text-align:center;">Array</td>
<td style="text-align:center;">No</td>
<td style="text-align:left;">企业创建者</td>
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
<td style="text-align:left;">invalid name format</td>
<td style="text-align:left;">无效的企业名格式</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">invalid tel format</td>
<td style="text-align:left;">无效的联系电话格式</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">invalid email format</td>
<td style="text-align:left;">无效的企业邮箱格式</td>
</tr>
<tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">no authorized</td>
<td style="text-align:left;">没有足够的权限</td>
</tr></tbody>
</table>

## <a name="get-enterprise">读取企业 (Get Enterprise)</a>

> http://api.htaiyun.com/service/enterprise/{enterpriseid}/get

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">GET</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">HT-SESSION-TOKEN</td><td style="color:#999;">当前用户会话ID</td></tr>
	<tr><td style="text-align:left;">HT-SESSION-SECRET</td><td style="color:#999;">当前用户会话密钥</td></tr>
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
<td style="text-align:center;">enterpriseid</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">yes</td>
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:center;">企业ID</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{
	"status":200,
	"message":"OK",
	"result":{"unique":1,
						"status":"NOT_ACTIVED",
						...
						"admin":{
											"id":1,
											username":"18330382308",
											...,
										}
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
<td style="text-align:left;">企业的ID</td>
</tr><tr>
<td style="text-align:center;">name</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">企业的名字</td>
</tr><tr>
<td style="text-align:center;">tel</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">企业联系方式</td>
</tr><tr>
<td style="text-align:center;">email</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">企业邮箱</td>
</tr><tr>
<td style="text-align:center;">address</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">企业地址</td>
</tr><tr>
<td style="text-align:center;">description</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">企业描述信息，200个字符以内</td>
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
<td style="text-align:center;">zipcode</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:left;">邮编</td>
</tr><tr>
<td style="text-align:center;">admin</td>
<td style="text-align:center;">Array</td>
<td style="text-align:center;">No</td>
<td style="text-align:left;">企业创建者</td>
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
<td style="text-align:left;">enterprise not exists</td>
<td style="text-align:left;">企业不存在</td>
</tr></tbody>
</table>

## <a name="list-enterprises">查询企业 (List Enterprises)</a>

> http://api.htaiyun.com/service/enterprise/list

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">GET</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">HT-SESSION-TOKEN</td><td style="color:#999;">当前用户会话ID</td></tr>
	<tr><td style="text-align:left;">HT-SESSION-SECRET</td><td style="color:#999;">当前用户会话密钥</td></tr>
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
<td style="text-align:left;">关键词</td>
</tr><tr>
<td style="text-align:center;">status</td>
<td style="text-align:center;">String,Restricted</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">ALL_STATUS</td>
<td style="text-align:left;">查询状态，选项：<br><b>ALL_STATUS</b>不限状态；<br><b>UNRECOGNIZED</b>无法识别；<br><b>ACTIVED</b>可用状态；<br/><b>SAVING</b>保存状态；<br/><b>QUEUED</b>等待状态；<br/><b>KILLED</b>停止状态；<br/><b>PENDING_DELETE</b>待删除状态；<br/><b>DELETED</b>删除状态</td>
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
		"entites" : ["unique":1,
							"status":"NOT_ACTIVED",
							...
							"admin":{
												"id":1,
												username":"18330382308",
												...,
											}
		,...]
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
<td style="text-align:left;">企业的ID</td>
</tr><tr>
<td style="text-align:center;">name</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">企业的名字</td>
</tr><tr>
<td style="text-align:center;">tel</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">企业联系方式</td>
</tr><tr>
<td style="text-align:center;">email</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">企业邮箱</td>
</tr><tr>
<td style="text-align:center;">address</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">企业地址</td>
</tr><tr>
<td style="text-align:center;">description</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">企业描述信息，200个字符以内</td>
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
<td style="text-align:center;">zipcode</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:left;">邮编</td>
</tr></tbody>
</table>

## <a name="delete-enterprise">删除企业 (Delete Enterprise)</a>

> http://api.htaiyun.com/services/enterprise/{enterpriseid}/delete

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
<tbody></tbody>
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
<td style="text-align:left;">enterprise not exists</td>
<td style="text-align:left;">找不到指定的企业</td>
</tr></tbody>
</table>

## <a name="add-employee">添加员工 (Add Employee)</a>

> http://api.htaiyun.com/service/enterprise/{enterpriseid}/employee/add

<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
<tr><td style="text-align:left;">HT-SESSION-TOKEN</td><td style="color:#999;">当前用户会话ID</td></tr>
<tr><td style="text-align:left;">HT-SESSION-SECRET</td><td style="color:#999;">当前用户会话密钥</td></tr>
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
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">员工ID</td>
</tr><</tbody>
</table>

### 输出数据

#### 返回实例

<code>
{
	"status":200,
	"message":"OK",
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
<td style="text-align:left;">unauthorized user</td>
<td style="text-align:left;">没有足够的权限</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">enterprise not exists</td>
<td style="text-align:left;">企业不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">no authorized</td>
<td style="text-align:left;">企业未激活</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">user not exists</td>
<td style="text-align:left;">用户不存在</td>
</tr></tbody>
</table>

## <a name="remove-employee">删除企业员工 (Remove Employee)</a>

> http://api.htaiyun.com/services/enterprise/{enterpriseid}/employee/delete

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
<tbody></tbody>
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
<td style="text-align:left;">需要的登陆才可以进行操作</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">unauthorized user</td>
<td style="text-align:left;">没有足够的权限</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">enterprise not exists</td>
<td style="text-align:left;">企业不存在</td>
</tr></tbody>
</table>


## <a name="list-employee">查询员工 (List Employee)</a>

> http://api.htaiyun.com/service/enterprise/{enterpriseid}/employee/list

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">GET</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">HT-SESSION-TOKEN</td><td style="color:#999;">当前用户会话ID</td></tr>
	<tr><td style="text-align:left;">HT-SESSION-SECRET</td><td style="color:#999;">当前用户会话密钥</td></tr>
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
<td style="text-align:left;">关键词</td>
</tr><tr>
<td style="text-align:center;">status</td>
<td style="text-align:center;">String,Restricted</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">ALL_STATUS</td>
<td style="text-align:left;">查询状态，选项：<br><b>ALL_STATUS</b>不限状态；<br><b>UNRECOGNIZED</b>无法识别；<br><b>ACTIVED</b>可用状态；<br/><b>SAVING</b>保存状态；<br/><b>QUEUED</b>等待状态；<br/><b>KILLED</b>停止状态；<br/><b>PENDING_DELETE</b>待删除状态；<br/><b>DELETED</b>删除状态</td>
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
		"entites" : [
		{
			"unique" : 1,
			"username" : "USERNAME",
			"type" : "PERSONAL",
			"status" : "ACTIVED",
			"creted" : 0,
			"updated" : 0
		}
		,...]
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
</tr></tbody>
</table>

## <a name="create-department">创建部门 (Create Department)</a>

> http://api.htaiyun.com/service/enterprise/department/{enterpriseid}/create

<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
<tr><td style="text-align:left;">HT-SESSION-TOKEN</td><td style="color:#999;">当前用户会话ID</td></tr>
<tr><td style="text-align:left;">HT-SESSION-SECRET</td><td style="color:#999;">当前用户会话密钥</td></tr>
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
<td style="text-align:center;">parentid</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">YES</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">上级部门ID（创建一级节点可不填写，创建子节点为必须值）</td>
</tr><tr>
<td style="text-align:center;">name</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">YES</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">部门名称</td>
</tr><tr>
<td style="text-align:center;">mobile</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">YES</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">部门电话</td>
</tr><tr>
<td style="text-align:center;">description</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">YES</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">部门描述信息，200个字符以内</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{
	"status":200,
    "message":"OK",
    "result":{
       "unique":...,
       "status":...,
       "created":...,
       "updated":...,
         "enterprise":{
            "status":...
          "admin":{
	        "status":...
		    }
		  },
		  ...
    }
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
<td style="text-align:left;">department not exists</td>
<td style="text-align:left;">部门不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">enterprise not exists</td>
<td style="text-align:left;">企业不存在</td>
</tr></tbody>
</table>

## <a name="update-department">更新部门 (Update Department)</a>

> http://api.htaiyun.com/service/enterprise/department/{enterpriseid}/update

<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
<tr><td style="text-align:left;">HT-SESSION-TOKEN</td><td style="color:#999;">当前用户会话ID</td></tr>
<tr><td style="text-align:left;">HT-SESSION-SECRET</td><td style="color:#999;">当前用户会话密钥</td></tr>
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
<td style="text-align:center;">departmentid</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">YES</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">部门ID</td>
</tr><tr>
<td style="text-align:center;">name</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">NO</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">部门名称</td>
</tr><tr>
<td style="text-align:center;">parentid</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">NO</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">上级部门ID（为空不变更上下级关系）</td>
</tr><tr>
<td style="text-align:center;">mobile</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">NO</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">部门电话</td>
</tr><tr>
<td style="text-align:center;">description</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">NO</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">部门描述信息，200个字符以内</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{
	"status":200,
    "message":"OK"
}
</code>

## <a name="delete-department">删除部门 (Delete Department)</a>

> http://api.htaiyun.com/service/enterprise/department/{enterpriseid}/delete

<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
<tr><td style="text-align:left;">HT-SESSION-TOKEN</td><td style="color:#999;">当前用户会话ID</td></tr>
<tr><td style="text-align:left;">HT-SESSION-SECRET</td><td style="color:#999;">当前用户会话密钥</td></tr>
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
<td style="text-align:center;">departmentidList</td>
<td style="text-align:center;">String[]</td>
<td style="text-align:center;">YES</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">部门ID集合</td>
</tr><tr>
<td style="text-align:center;">departmentid</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">YES</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">部门ID</td>
</tr><tr>
<td style="text-align:center;">islink</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">YES</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">是否级联删除（默认级联，需要传入departmentidList；不级联删除，传入departmentid，islink设为false）</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{
	"status":200,
    "message":"OK"
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
<td style="text-align:left;">enterprise not exists</td>
<td style="text-align:left;">企业不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">department not exists</td>
<td style="text-align:left;">部门不存在</td>
</tr><tr>
<td style="text-align:center;">403</td>
<td style="text-align:left;">child nodes exists</td>
<td style="text-align:left;">有子节点存在</td>
</tr></tbody>
</table>

## <a name="list-department">查询部门 (Department List)</a>

> http://api.htaiyun.com/service/enterprise/department/{enterpriseid}/list

<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
<tr><td style="text-align:left;">HT-SESSION-TOKEN</td><td style="color:#999;">当前用户会话ID</td></tr>
<tr><td style="text-align:left;">HT-SESSION-SECRET</td><td style="color:#999;">当前用户会话密钥</td></tr>
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
<td style="text-align:center;">departmentidList</td>
<td style="text-align:center;">String[]</td>
<td style="text-align:center;">YES</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">部门ID集合（不输入默认查询一级节点）</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{
	"status":200,
    "message":"OK",
    "result":{
     "total":1,
	 "hasPrevious":false,
	 "hasNext":false,
	 "entities":[{
	    "unique":...,
		"status":....
		"enterprise":{
		"status":...,
		"created":...,
		"updated":....
		"admin":{
		   "status":...,
		   "created":...,
		   "updated":....
		   }},
		  ...
		}],
		...
	}
}
</code>

## <a name="levellist-department">查询部门 (Department levellist)</a>

> http://api.htaiyun.com/service/enterprise/department/{enterpriseid}/levellist

<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
<tr><td style="text-align:left;">HT-SESSION-TOKEN</td><td style="color:#999;">当前用户会话ID</td></tr>
<tr><td style="text-align:left;">HT-SESSION-SECRET</td><td style="color:#999;">当前用户会话密钥</td></tr>
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
<td style="text-align:center;">level</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">YES</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">部门等级</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{
	"status":200,
    "message":"OK",
    "result":{
     "total":1,
	 "hasPrevious":false,
	 "hasNext":false,
	 "entities":[{
	    "unique":...,
		"status":....
		"enterprise":{
		"status":...,
		"created":...,
		"updated":....
		"admin":{
		   "status":...,
		   "created":...,
		   "updated":....
		   }},
		  ...
		}],
		...
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
<td style="text-align:left;">部门ID</td>
</tr><tr>
<td style="text-align:center;">name</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">部门名称</td>
</tr><tr>
<td style="text-align:center;">mobile</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">部门电话</td>
</tr><tr>
<td style="text-align:center;">pinyin</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">部门拼音名称</td>
</tr><tr>
<td style="text-align:center;">level</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">部门等级</td>
</tr><tr>
<td style="text-align:center;">description</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">部门描述信息，200个字符以内</td>
</tr></tbody>
</table>

## <a name="create-departmentmember">创建部门成员 (Create DepartmentMember)</a>

> http://api.htaiyun.com/service/enterprise/department/{enterpriseid}/departmentmember/create

<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
<tr><td style="text-align:left;">HT-SESSION-TOKEN</td><td style="color:#999;">当前用户会话ID</td></tr>
<tr><td style="text-align:left;">HT-SESSION-SECRET</td><td style="color:#999;">当前用户会话密钥</td></tr>
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
<td style="text-align:center;">did</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">YES</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">部门ID</td>
</tr><tr>
<td style="text-align:center;">uid</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">YES</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">用户ID</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{
	"status":200,
    "message":"OK",
    "result":{
     "unique":...,
	 "status":...,
	 "created":...,
	 "updated":...,
	 "department":{
	      "status":...,
		  "created":...,
		  "updated":...,
		  "id":...,
		  "name":....
		  "enterprise":{
		    "status":...,
			"created":....,
			"updated":...,
			"id":....
			"admin":{
			    "status":...,
				"created":...,
				"updated":...,
				"id":...,
				"type":....
				}}},
	  "employee":{
		  "status":...,
		  "created":....,
		  "updated":...,
		  "id":..,
		    "enterprise":{
				  ...,
			  "admin":{
					   .....
					}},
		    "user":{
				 ...
			  }},
		...
	}
}
</code>

## <a name="delete-departmentmember">删除部门成员 (Delete DepartmentMember)</a>

> http://api.htaiyun.com/service/enterprise/department/{enterpriseid}/departmentmember/delete

<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
<tr><td style="text-align:left;">HT-SESSION-TOKEN</td><td style="color:#999;">当前用户会话ID</td></tr>
<tr><td style="text-align:left;">HT-SESSION-SECRET</td><td style="color:#999;">当前用户会话密钥</td></tr>
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
<td style="text-align:center;">did</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">YES</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">部门ID</td>
</tr><tr>
<td style="text-align:center;">uid</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">YES</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">用户ID</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{
	"status":200,
    "message":"OK",
}
</code>

## <a name="list-departmentmember">查询部门成员 (List DepartmentMember)</a>

> http://api.htaiyun.com/service/enterprise/department/{enterpriseid}/departmentmember/list

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">GET</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">HT-SESSION-TOKEN</td><td style="color:#999;">当前用户会话ID</td></tr>
	<tr><td style="text-align:left;">HT-SESSION-SECRET</td><td style="color:#999;">当前用户会话密钥</td></tr>
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
<td style="text-align:center;">did</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">部门ID</td>
</tr><tr>
<td style="text-align:center;">uid</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">用户ID</td>
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
	"status":200,
    "message":"OK",
    "result":{
    "total":1,
	"hasPrevious":false,
	"hasNext":false,
	"entities":[{
	     "unique":...,
		 "status":...,
		 "created":...,
		 "updated":...,
		 "department":{
		     "status":...,
			 "created":...,
			 "updated":...
			 "enterprise":{
			     "status":...,
				 "created":...,
				 "updated":...
				 "admin":{
				     ....
					 }}},
					 "employee":{
					      ...
						  "enterprise":{
						     ...
							  "admin":{
							  ...
						  }},
						  "user":{
						      ...
							 }},
							 ...
		 }],
							 ...
	}
}
</code>

## <a name="batchupdate-departmentmember">更新部门成员 (BatchUpdate DepartmentMember)</a>

> http://api.htaiyun.com/service/enterprise/department/{enterpriseid}/departmentmember/update

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">GET</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">HT-SESSION-TOKEN</td><td style="color:#999;">当前用户会话ID</td></tr>
	<tr><td style="text-align:left;">HT-SESSION-SECRET</td><td style="color:#999;">当前用户会话密钥</td></tr>
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
<td style="text-align:center;">departmentid</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">YES</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">目标部门ID</td>
</tr><tr>
<td style="text-align:center;">employeeidList</td>
<td style="text-align:center;">String[]</td>
<td style="text-align:center;">YES</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">成员ID集合</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{
	"status":200,
    "message":"OK"
}
</code>

## <a name="batchdel-departmentmember">删除部门成员 (BatchDel DepartmentMember)</a>

> http://api.htaiyun.com/service/enterprise/department/{enterpriseid}/departmentmember/batchdel

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">GET</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">HT-SESSION-TOKEN</td><td style="color:#999;">当前用户会话ID</td></tr>
	<tr><td style="text-align:left;">HT-SESSION-SECRET</td><td style="color:#999;">当前用户会话密钥</td></tr>
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
<td style="text-align:center;">employeeidList</td>
<td style="text-align:center;">String[]</td>
<td style="text-align:center;">YES</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">成员ID集合</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{
	"status":200,
    "message":"OK"
}
</code>

## <a name="get-employeebyuser">根据用户ID查询Employee (get employeeByUser)</a>

> http://api.htaiyun.com/service/enterprise/user/employee

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">GET</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">HT-SESSION-TOKEN</td><td style="color:#999;">当前用户会话ID</td></tr>
	<tr><td style="text-align:left;">HT-SESSION-SECRET</td><td style="color:#999;">当前用户会话密钥</td></tr>
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
<td style="text-align:center;">String</td>
<td style="text-align:center;">YES</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">用户ID</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{
	"status":200,
    "message":"OK",
	"result":{...}
}
</code>