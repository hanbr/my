# <a name="imageApplication">镜像应用管理 (ImageApplication)</a>

## <a name="create-imageApplication">创建镜像应用 (Create ImageApplication)</a>

> http://api.htaiyun.com/v1/openstack/image/application/create

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
<td style="text-align:center;">name</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">镜像名称</td>
</tr><tr>
<td style="text-align:center;">displayname</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">镜像别名</td>
</tr><tr>
<td style="text-align:center;">picture</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">图片</td>
</tr><tr>
<td style="text-align:center;">description</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">描述</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{
  "status":200,
  "message":"OK",
  "result":{
     "unique":4,"status":"ACTIVED",
	 "created":1494472126109,"updated":1494472126109,
	 "name":"ls-junit","displayName":"测试",
	 "description":"junit测试-可删除",
	 "picture":"6465465786546789874.jpg",
	 "links":[]},
	 "links":[]
}
</code>

#### 数据说明

#### 常见错误信息

## <a name="get-imageApplication">获取镜像应用数据(Get ImageApplication)</a>

> http://api.htaiyun.com/v1/openstack/image/application/{id}/get

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
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">镜像应用ID</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{
  "status":200,
  "message":"OK",
  "result":{
     "unique":4,"status":"ACTIVED",
	 "created":1494472126109,
	 "updated":1494472126109,"name":"ls-junit",
	 "displayName":"测试",
	 "description":"junit测试-可删除",
	 "picture":"6465465786546789874.jpg",
	 "links":[]},
	 "links":[]
}
</code>

## <a name="delete-imageApplication">删除镜像应用 (Delete ImageApplication)</a>

> http://api.htaiyun.com/v1/openstack/image/application/{id}/delete

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
<td style="text-align:left;">镜像应用ID</td>
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

## <a name="list-imageApplication">获取镜像应用列表 (List ImageApplication)</a>

> http://api.htaiyun.com/v1/openstack/image/application/list

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
<td style="text-align:left;">名称</td>
</tr><tr>
<td style="text-align:center;">status</td>
<td style="text-align:center;">Enum</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">ACTIVED、DELETED、ALL_STATUS</td>
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
	     {"unique":"58fb10da37da4dcf69faa544",
		  "status":"NOT_ACTIVED",
		  "created":1492848858513,
		  "updated":1492848858513,
		  "imageName":"测试",
		  "applications":["openstack","guacamole"],
		  "description":"暂无","links":[]
		  },
		  ...
		],"links":[]},"links":[]
}
</code>

## <a name="batchDelete-imageApplication">批处理删除镜像应用 (BatchDelete imageApplication)</a>

> http://api.htaiyun.com/v1/openstack/image/application/{id}/update

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
<td style="text-align:center;">id</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:left;">镜像应用ID</td>
</tr><tr>
<td style="text-align:center;">name</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:left;">名称</td>
</tr><tr>
<td style="text-align:center;">displayname</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:left;">镜像别名</td>
</tr><tr>
<td style="text-align:center;">picture</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:left;">图片</td>
</tr><tr>
<td style="text-align:center;">description</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:left;">描述</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{
  "status":200,
  "message":"OK",
  "result":{
     "unique":4,"status":"ACTIVED",
	 "created":1494472126109,
	 "updated":1494472126109,
	 "name":"ls-junit",
	 "displayName":"测试",
	 "description":"junit测试-可删除",
	 "picture":"6465465786546789874.jpg",
	 "links":[]},
	 "links":[]
}
</code>
