# <a name="serverShare">主机共享管理 (serverShare)</a>

## <a name="create-serverShare">创建共享信息 (Create serverShare)</a>

> http://api.htaiyun.com/v1/openstack/share/created

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
<td style="text-align:center;">serverid</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">云主机ID</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{
   "status":200,
   "message":"OK",
   "result":{
           "unique":"15",
	   "status":"ACTIVED",
	   "created":1492414506262,
	   "updated":1492414506262,
	   "userName":"超级管理员",
	   "userId":0,
	   "userServerId":...,
	   "links":[]},
	   "links":[]
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
<td style="text-align:center;">id</td>
<td style="text-align:center;">Long</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">共享数据ID</td>
</tr><tr>
<td style="text-align:center;">shareUser</td>
<td style="text-align:center;">User</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">共享用户</td>
</tr><tr>
<td style="text-align:center;">user</td>
<td style="text-align:center;">User</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">享受共享者</td>
</tr><tr>
<td style="text-align:center;">userServerId</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">主机ID</td>
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
<td style="text-align:center;">406</td>
<td style="text-align:left;">user not exists</td>
<td style="text-align:left;">用户已经存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">already exists</td>
<td style="text-align:left;">共享已经存在</td>
</tr></tbody>
</table>

## <a name="get-serverShare">获取共享数据(Get serverShare)</a>

> http://api.htaiyun.com/v1/openstack/share/{id}/get

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
<td style="text-align:center;">id</td>
<td style="text-align:center;">long</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">共享主机ID</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{
  "status":200,
  "message":"OK",
  "result":{
         "unique":"15",
	 "status":"ACTIVED",
	 "created":1492414506262,
	 "updated":1492414506262,
	 "userName":"超级管理员",
	 "userId":0,"userServerId":"4654564654654777",
	 "links":[]},
	 "links":[]
}
</code>

## <a name="batchCreate-serverShare">批处理创建共享 (batchCreate serverShare)</a>

> http://api.htaiyun.com/v1/openstack/share/batch/create

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
<td style="text-align:center;">ids</td>
<td style="text-align:center;">List<Long></td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">用户ID</td>
</tr><tr>
<td style="text-align:center;">serverid</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">主机ID</td>
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


## <a name="delete-serverShare">删除主机共享 (Delete ServerShare)</a>

> http://api.htaiyun.com/v1/openstack/stack/{id}/delete

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
<td style="text-align:center;">id</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">云主机共享ID</td>
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

## <a name="list-serverShare">获取主机共享 (List ServerShare)</a>

> http://api.htaiyun.com/v1/openstack/share/list

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
<td style="text-align:center;">serverid</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">主机ID</td>
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
   "status":200,
   "message":"OK",
   "result":{
     "total":2,
     "hasPrevious":false,
     "hasNext":false,
     "entities":[
           {"unique":"11",
           "status":"ACTIVED",
           "created":1492408607854,
           "updated":1492408607854,
           "userName":"liusong",
           "userId":1,
           "userServerId":"65432178541565",
           "links":[]}...
}
</code>

## <a name="batchDelete-serverShare">批处理删除主机共享 (BatchDelete ServerShare)</a>

> http://api.htaiyun.com/v1/openstack/share/batch/delete

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
<td style="text-align:center;">ids</td>
<td style="text-align:center;">List<Long></td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">用户ID</td>
</tr><tr>
<td style="text-align:center;">serverid</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">云主机ID</td>
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
