## <a name="request">创建云应用请求(Create Application Request)</a>

> http://api.htaiyun.com/services/request/create/application

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">Authorization</td><td style="color:#999;">标准HTTP Basic Authentication内容，包括登录用户的sessionToken和sessionSecret</td><td></td></tr>
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
<td style="text-align:center;">long</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">申请人ID</td>
</tr><tr>
<td style="text-align:center;">application</td>
<td style="text-align:center;">long</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">云应用的ID</td>
</tr><tr>
<td style="text-align:center;">params</td>
<td style="text-align:center;">JSONObject String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">申请相关参数，在创建云应用是应当传入配置类型，可选参数：<br/>HIGHEST: 最佳配置<br/>LOWEST: 最低配置<br/>RECOMMENDED: 推荐配置<br/></td>
</tr><tr>
<td style="text-align:center;">start</td>
<td style="text-align:center;">long</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">开始时间</td>
</tr><tr>
<td style="text-align:center;">end</td>
<td style="text-align:center;">long</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">结束时间</td>
</tr><tr>
<td style="text-align:center;">description</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">请求的描述</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{
	"status" : 200,
	"message" : "OK",
	"result" : {
		"unique" : 1
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
<td style="text-align:center;">unique</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">请求ID</td>
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
<td style="text-align:left;">user not exists</td>
<td style="text-align:left;">用户不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">invalid time period</td>
<td style="text-align:left;">时间不适用</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">invalid user</td>
<td style="text-align:left;">用户权限不足</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">application not exists</td>
<td style="text-align:left;">云应用不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">invalid flavor</td>
<td style="text-align:left;">主机类型不适用</td>
</tr></tbody>
</table>

## <a name="request">创建云主机请求(Create Server Request)</a>

> http://api.htaiyun.com/services/request/create/server

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">Authorization</td><td style="color:#999;">标准HTTP Basic Authentication内容，包括登录用户的sessionToken和sessionSecret</td><td></td></tr>
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
<td style="text-align:center;">long</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">申请人ID</td>
</tr><tr>
<td style="text-align:center;">flavor</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">云主机类型的ID</td>
</tr><tr>
<td style="text-align:center;">image</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">镜像的ID</td>
</tr><tr>
<td style="text-align:center;">params</td>
<td style="text-align:center;">JSONObject String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">申请相关参数，如云主机名称等</td>
</tr><tr>
<td style="text-align:center;">start</td>
<td style="text-align:center;">long</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">开始时间</td>
</tr><tr>
<td style="text-align:center;">end</td>
<td style="text-align:center;">long</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">结束时间</td>
</tr><tr>
<td style="text-align:center;">description</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">no</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">请求的描述</td>
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
<td style="text-align:center;">unique</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">请求ID</td>
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
<td style="text-align:left;">user not exists</td>
<td style="text-align:left;">用户不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">invalid time period</td>
<td style="text-align:left;">时间不适用</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">invalid user</td>
<td style="text-align:left;">用户权限不足</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">image not exists</td>
<td style="text-align:left;">镜像不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">invalid flavor</td>
<td style="text-align:left;">主机类型不适用</td>
</tr></tbody>
</table>

## <a name="request">创建云磁盘请求(Create Volume Request)</a>

> http://api.htaiyun.com/services/request/createvolume

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">Authorization</td><td style="color:#999;">标准HTTP Basic Authentication内容，包括登录用户的sessionToken和sessionSecret</td><td></td></tr>
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
<td style="text-align:center;">long</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">申请人ID</td>
</tr><tr>
<td style="text-align:center;">size</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">云磁盘大小, 单位为byte</td>
</tr><tr>
<td style="text-align:center;">params</td>
<td style="text-align:center;">JSONObject String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">申请相关参数，如云磁盘名称、使用镜像等</td>
</tr><tr>
<td style="text-align:center;">start</td>
<td style="text-align:center;">long</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">开始时间</td>
</tr><tr>
<td style="text-align:center;">end</td>
<td style="text-align:center;">long</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">结束时间</td>
</tr><tr>
<td style="text-align:center;">description</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">no</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">请求的描述</td>
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
<td style="text-align:center;">unique</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">请求ID</td>
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
<td style="text-align:left;">user not exists</td>
<td style="text-align:left;">用户不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">invalid time period</td>
<td style="text-align:left;">时间不适用</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">invalid user</td>
<td style="text-align:left;">用户权限不足</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">invalid size</td>
<td style="text-align:left;">磁盘容量不适用</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">application not exists</td>
<td style="text-align:left;">云应用不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">image not exists</td>
<td style="text-align:left;">镜像不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">invalid flavor</td>
<td style="text-align:left;">主机类型不适用</td>
</tr>/tbody>
</table>

## <a name="request">更新请求(Update Request)</a>

> http://api.htaiyun.com/services/request/{requestid}/update

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">Authorization</td><td style="color:#999;">标准HTTP Basic Authentication内容，包括登录用户的sessionToken和sessionSecret</td><td></td></tr>
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
<td style="text-align:center;">start</td>
<td style="text-align:center;">long</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">开始时间</td>
</tr><tr>
<td style="text-align:center;">end</td>
<td style="text-align:center;">long</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">结束时间</td>
</tr><tr>
<td style="text-align:center;">description</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">no</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">请求的描述</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{
	status":200,
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
<td style="text-align:center;">400</td>
<td style="text-align:left;">require parameter:A</td>
<td style="text-align:left;">缺少必须参数A</td>
</tr><tr>
<td style="text-align:center;">403</td>
<td style="text-align:left;">access denied</td>
<td style="text-align:left;">需要的登陆才可以进行操作</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">user not exists</td>
<td style="text-align:left;">用户不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">invalid time period</td>
<td style="text-align:left;">时间不适用</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">invalid user</td>
<td style="text-align:left;">用户权限不足</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">invalid size</td>
<td style="text-align:left;">磁盘容量不适用</td>
</tr></tbody>
</table>

## <a name="request">取消请求(Cancel Request)</a>

> http://api.htaiyun.com/services/request/{requestid}/cancel

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">Authorization</td><td style="color:#999;">标准HTTP Basic Authentication内容，包括登录用户的sessionToken和sessionSecret</td><td></td></tr>
</table>

### 输入参数

### 输出数据

#### 返回实例

<code>
{
	status":200,
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
<td style="text-align:center;">400</td>
<td style="text-align:left;">require parameter:A</td>
<td style="text-align:left;">缺少必须参数A</td>
</tr><tr>
<td style="text-align:center;">403</td>
<td style="text-align:left;">access denied</td>
<td style="text-align:left;">需要的登陆才可以进行操作</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">user not exists</td>
<td style="text-align:left;">用户不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">invalid user</td>
<td style="text-align:left;">用户权限不足</td>
</tr></tbody>
</table>


## <a name="request">同意请求(Approve Request)</a>

> http://api.htaiyun.com/services/request/{requestid}/approve

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">Authorization</td><td style="color:#999;">标准HTTP Basic Authentication内容，包括登录用户的sessionToken和sessionSecret</td><td></td></tr>
</table>

### 输入参数

### 输出数据

#### 返回实例

<code>
{
	status":200,
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
<td style="text-align:center;">400</td>
<td style="text-align:left;">require parameter:A</td>
<td style="text-align:left;">缺少必须参数A</td>
</tr><tr>
<td style="text-align:center;">403</td>
<td style="text-align:left;">access denied</td>
<td style="text-align:left;">需要的登陆才可以进行操作</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">user not exists</td>
<td style="text-align:left;">用户不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">invalid user</td>
<td style="text-align:left;">用户权限不足</td>
</tr></tbody>
</table>

## <a name="request">拒绝请求(Reject Request)</a>

> http://api.htaiyun.com/services/request/{requestid}/reject

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">Authorization</td><td style="color:#999;">标准HTTP Basic Authentication内容，包括登录用户的sessionToken和sessionSecret</td><td></td></tr>
</table>

### 输入参数

### 输出数据

#### 返回实例

<code>
{
	status":200,
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
<td style="text-align:center;">400</td>
<td style="text-align:left;">require parameter:A</td>
<td style="text-align:left;">缺少必须参数A</td>
</tr><tr>
<td style="text-align:center;">403</td>
<td style="text-align:left;">access denied</td>
<td style="text-align:left;">需要的登陆才可以进行操作</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">user not exists</td>
<td style="text-align:left;">用户不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">invalid user</td>
<td style="text-align:left;">用户权限不足</td>
</tr></tbody>
</table>

## <a name="request">删除请求(Delete Request)</a>

> http://api.htaiyun.com/services/request/{requestid}/delete

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">Authorization</td><td style="color:#999;">标准HTTP Basic Authentication内容，包括登录用户的sessionToken和sessionSecret</td><td></td></tr>
</table>

### 输入参数

### 输出数据

#### 返回实例

<code>
{
	status":200,
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
<td style="text-align:center;">400</td>
<td style="text-align:left;">require parameter:A</td>
<td style="text-align:left;">缺少必须参数A</td>
</tr><tr>
<td style="text-align:center;">403</td>
<td style="text-align:left;">access denied</td>
<td style="text-align:left;">需要的登陆才可以进行操作</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">user not exists</td>
<td style="text-align:left;">用户不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">invalid user</td>
<td style="text-align:left;">用户权限不足</td>
</tr></tbody>
</table>

## <a name="request">批量取消请求(Cancel Request)</a>

> http://api.htaiyun.com/services/request/cancel

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">Authorization</td><td style="color:#999;">标准HTTP Basic Authentication内容，包括登录用户的sessionToken和sessionSecret</td><td></td></tr>
</table>

### 输入参数

table border="0" cellpadding="0" cellspacing="0">
<thead><tr>
<td style="text-align:center; background-color:#f5f5f5;">名称</td>
<td style="text-align:center; background-color:#f5f5f5;">类型</td>
<td style="text-align:center; background-color:#f5f5f5;">是否必须</td>
<td style="text-align:center; background-color:#f5f5f5;">默认值</td>
<td style="text-align:center; background-color:#f5f5f5;">说明</td>
</tr></thead>
<tbody><tr>
<td style="text-align:center;">ids</td>
<td style="text-align:center;">long[]</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">请求的id，数组</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{
	"status" : 200,
	"message" : "OK",
	"result" : {
		"success" : 10
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
<td style="text-align:center;">400</td>
<td style="text-align:left;">require parameter:A</td>
<td style="text-align:left;">缺少必须参数A</td>
</tr><tr>
<td style="text-align:center;">403</td>
<td style="text-align:left;">access denied</td>
<td style="text-align:left;">需要的登陆才可以进行操作</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">user not exists</td>
<td style="text-align:left;">用户不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">invalid user</td>
<td style="text-align:left;">用户权限不足</td>
</tr></tbody>
</table>

## <a name="request">批量同意请求(Approve Request)</a>

> http://api.htaiyun.com/services/request/approve

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">Authorization</td><td style="color:#999;">标准HTTP Basic Authentication内容，包括登录用户的sessionToken和sessionSecret</td><td></td></tr>
</table>

### 输入参数

table border="0" cellpadding="0" cellspacing="0">
<thead><tr>
<td style="text-align:center; background-color:#f5f5f5;">名称</td>
<td style="text-align:center; background-color:#f5f5f5;">类型</td>
<td style="text-align:center; background-color:#f5f5f5;">是否必须</td>
<td style="text-align:center; background-color:#f5f5f5;">默认值</td>
<td style="text-align:center; background-color:#f5f5f5;">说明</td>
</tr></thead>
<tbody><tr>
<td style="text-align:center;">ids</td>
<td style="text-align:center;">long[]</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">请求的id，数组</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{
	"status" : 200,
	"message" : "OK",
	"result" : {
		"success" : 10
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
<td style="text-align:center;">400</td>
<td style="text-align:left;">require parameter:A</td>
<td style="text-align:left;">缺少必须参数A</td>
</tr><tr>
<td style="text-align:center;">403</td>
<td style="text-align:left;">access denied</td>
<td style="text-align:left;">需要的登陆才可以进行操作</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">user not exists</td>
<td style="text-align:left;">用户不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">invalid user</td>
<td style="text-align:left;">用户权限不足</td>
</tr></tbody>
</table>

## <a name="request">批量拒绝请求(Reject Request)</a>

> http://api.htaiyun.com/services/request/reject

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">Authorization</td><td style="color:#999;">标准HTTP Basic Authentication内容，包括登录用户的sessionToken和sessionSecret</td><td></td></tr>
</table>

### 输入参数

table border="0" cellpadding="0" cellspacing="0">
<thead><tr>
<td style="text-align:center; background-color:#f5f5f5;">名称</td>
<td style="text-align:center; background-color:#f5f5f5;">类型</td>
<td style="text-align:center; background-color:#f5f5f5;">是否必须</td>
<td style="text-align:center; background-color:#f5f5f5;">默认值</td>
<td style="text-align:center; background-color:#f5f5f5;">说明</td>
</tr></thead>
<tbody><tr>
<td style="text-align:center;">ids</td>
<td style="text-align:center;">long[]</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">请求的id，数组</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{
	"status" : 200,
	"message" : "OK",
	"result" : {
		"success" : 10
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
<td style="text-align:center;">400</td>
<td style="text-align:left;">require parameter:A</td>
<td style="text-align:left;">缺少必须参数A</td>
</tr><tr>
<td style="text-align:center;">403</td>
<td style="text-align:left;">access denied</td>
<td style="text-align:left;">需要的登陆才可以进行操作</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">user not exists</td>
<td style="text-align:left;">用户不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">invalid user</td>
<td style="text-align:left;">用户权限不足</td>
</tr></tbody>
</table>

## <a name="request">批量删除请求(Delete Request)</a>

> http://api.htaiyun.com/services/request/delete

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">Authorization</td><td style="color:#999;">标准HTTP Basic Authentication内容，包括登录用户的sessionToken和sessionSecret</td><td></td></tr>
</table>

### 输入参数

table border="0" cellpadding="0" cellspacing="0">
<thead><tr>
<td style="text-align:center; background-color:#f5f5f5;">名称</td>
<td style="text-align:center; background-color:#f5f5f5;">类型</td>
<td style="text-align:center; background-color:#f5f5f5;">是否必须</td>
<td style="text-align:center; background-color:#f5f5f5;">默认值</td>
<td style="text-align:center; background-color:#f5f5f5;">说明</td>
</tr></thead>
<tbody><tr>
<td style="text-align:center;">ids</td>
<td style="text-align:center;">long[]</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">请求的id，数组</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{
	"status" : 200,
	"message" : "OK",
	"result" : {
		"success" : 10
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
<td style="text-align:center;">400</td>
<td style="text-align:left;">require parameter:A</td>
<td style="text-align:left;">缺少必须参数A</td>
</tr><tr>
<td style="text-align:center;">403</td>
<td style="text-align:left;">access denied</td>
<td style="text-align:left;">需要的登陆才可以进行操作</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">user not exists</td>
<td style="text-align:left;">用户不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">invalid user</td>
<td style="text-align:left;">用户权限不足</td>
</tr></tbody>
</table>

## <a name="request">读取请求(Get Request)</a>

> http://api.htaiyun.com/services/request/{requestid}/get

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">GET</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">Authorization</td><td style="color:#999;">标准HTTP Basic Authentication内容，包括登录用户的sessionToken和sessionSecret</td><td></td></tr>
</table>

### 输入参数

### 输出数据

#### 返回实例

<code>
{  
   "status":200,
   "message":"OK",
   "result":{  
      "unique":1,
      "status":"READY",
      "created":1479261390396,
      "updated":1479261390396,
      "start":100000000,
      "end":110000000,
      "description":null,
      "type":"VOLUME",
      "size":20,
      "links":[  
      ]
   },
   "links":[  
   ]
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
<td style="text-align:left;">user not exists</td>
<td style="text-align:left;">用户不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">invalid user</td>
<td style="text-align:left;">用户权限不足</td>
</tr></tbody>
</table>


## <a name="list">查询申请 (List Applications)</a>

> http://api.htaiyun.com/services/request/list

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
<td style="text-align:center;"></td>
<td style="text-align:left;">申请人ID</td>
</tr><tr>
<td style="text-align:center;">keywords</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">关键词，作用于申请人的name或者申请信息的description字段上</td>
</tr><tr>
<td style="text-align:center;">type</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">ALL_TYPES</td>
<td style="text-align:left;">申请类型</td>
</tr><tr>
<td style="text-align:center;">status</td>
<td style="text-align:center;">String, Restricted</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">ALL_STATUS</td>
<td style="text-align:left;">申请状态，三个选项：<br><b>ALL_STATUS</b>不限状态；<br><b>ACTIVED</b>待审批；<br><b>CANCELLED</b>已取消；<br><b>APPROVAL</b>审批通过；<br><b>DELETED</b>已删除；<br><b>REJECTED</b>申请被拒绝；</td>
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
<td style="text-align:left;">排序字段，可选: created, updated</td>
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
      ""unique":1,
      "status":"READY",
      "created":1479261390396,
      "updated":1479261390396,
      "start":100000000,
      "end":110000000,
      "description":null,
      "type":"VOLUME",
      "size":20,
      "links":[  
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