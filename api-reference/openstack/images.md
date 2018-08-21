# <a name="images">镜像管理 (Images)</a>

## <a name="create-image">创建镜像 (Create Image)</a>

> http://api.htaiyun.com/v1/openstack/image/create

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
<td style="text-align:center;">yes</td>
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:center;">镜像名称</td>
</tr><tr>
<td style="text-align:center;">containerFormat</td>
<td style="text-align:center;">Enum</td>
<td style="text-align:center;">yes</td>
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:center;">容器格式：1、BARE 2、OVF 3、AKI 4、ARI 5、AMI 6、DOCKER 7、UNRECOGNIZED</td>
</tr><tr>
<td style="text-align:center;">diskFormat</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">yes</td>
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:center;">磁盘格式：1、RAW 2、VHD 3、VMDK 4、VDI 5、ISO 6、QCOW2 7、AKI 8、ARI 9、AMI 10、UNRECOGNIZED</td>
</tr><tr>
<td style="text-align:center;">imageAddress</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">yes</td>
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:center;">镜像文件路径</td>
</tr><tr>
<td style="text-align:center;">applicationNames</td>
<td style="text-align:center;">String[]</td>
<td style="text-align:center;">yes</td>
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:center;">镜像应用名称集合</td>
</tr><tr>
<td style="text-align:center;">applicationNames</td>
<td style="text-align:center;">String[]</td>
<td style="text-align:center;">yes</td>
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:center;">镜像应用名称集合</td>
</tr><tr>
<td style="text-align:center;">description</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">no</td>
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:center;">镜像描述</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{
  "status":200,
  "message":"OK",
  "result":{
     "unique":"5913d2e59778c38af32ec032",
	 "status":"ACTIVED","created":1494471397428,
	 "updated":1494471397428,"name":"ls-junit",
	 "displayName":"windows7","minLimit":4,
	 "size":13287936,"minRam":0,"minDisk":0,
	 "description":"junit测试-可删除",
	 "imageApplications":[1,2,3],
	 "containerFormat":"bare","diskFormat":"qcow2",
	 "links":[]},
	 "links":[]
}
</code>

#### 数据说明

## <a name="update-image">修改镜像 (Update Image)</a>

> http://api.htaiyun.com/v1/openstack/image/<imageid>/update

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
<td style="text-align:center;">imageId</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">yes</td>
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:center;">镜像ID</td>
</tr><tr>
<td style="text-align:center;">name</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">NO</td>
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:center;">镜像名称</td>
</tr><tr>
<td style="text-align:center;">name</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">NO</td>
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:center;">镜像名称</td>
</tr><tr>
<td style="text-align:center;">minLimit</td>
<td style="text-align:center;">Long</td>
<td style="text-align:center;">NO</td>
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:center;">最低要求内存</td>
</tr><tr>
<td style="text-align:center;">description</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">NO</td>
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:center;">描述</td>
</tr><tr>
<td style="text-align:center;">imageApplications</td>
<td style="text-align:center;">String[]</td>
<td style="text-align:center;">NO</td>
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:center;">镜像应用ID集合</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{
  "status":200,
  "message":"OK",
  "result":{
    "unique":"5913d2e59778c38af32ec032",
	"status":"ACTIVED","created":1494471397428,"updated":1494471397428,
	"name":"test","displayName":"windows7",
	"minLimit":4,"size":13287936,
	"minRam":0,"minDisk":0,"description":"junit测试-可删除",
	"imageApplications":[1,2,3],"containerFormat":"bare",
	"diskFormat":"qcow2",
	"links":[]},
	"links":[]
}
</code>

#### 数据说明

## <a name="read-image">读取镜像 (Read Image)</a>

> http://api.htaiyun.com/v1/openstack/image/<imageid>/get

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
<td style="text-align:center;">imageId</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">yes</td>
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:center;">镜像ID</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{ 
   "status":200,
   "message":"OK",
   "result":{
       "unique":"590d77bb37da647417197552",
	   "status":"ACTIVED",
	   "created":1494054843518,
	   "updated":1494054843518,
	   "name":"ls-junit",
	   "size":13287936,"minRam":0,"minDisk":0,
	   "description":"junit测试-可删除",
	   "applicationNames":["viewer","QQ","mysql"],
	   "containerFormat":null,"diskFormat":null,
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
<td style="text-align:center;">unique</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">镜像ID</td>
</tr><tr>
<td style="text-align:center;">name</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">镜像名称</td>
</tr><tr>
<td style="text-align:center;">size</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">镜像大小</td>
</tr><tr>
<td style="text-align:center;">isPublic</td>
<td style="text-align:center;">Boolean</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">镜像是否为公共访问权限</td>
</tr><tr>
<td style="text-align:center;">isProtected</td>
<td style="text-align:center;">Boolean</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">镜像是否为保护状态</td>
</tr><tr>
<td style="text-align:center;">minRam</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">镜像要求的最小内存空间，0表示无限制</td>
</tr><tr>
<td style="text-align:center;">minDisk</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">镜像要求的最小磁盘空间，0表示无限制</td>
</tr><tr>
<td style="text-align:center;">status</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">镜像状态</td>
</tr><tr>
<td style="text-align:center;">created</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">镜像创建时间</td>
</tr><tr>
<td style="text-align:center;">updated</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">镜像上次更新时间</td>
</tr></tbody>
</table>


## <a name="list-images">查询镜像 (List Images)</a>

> http://api.htaiyun.com/v1/openstack/image/list

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
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:left;">关键词，应用于群组的name和displayName两个字段上</td>
</tr><tr>
<td style="text-align:center;">status</td>
<td style="text-align:center;">Enum,Restricted</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">ALL_STATUS</td>
<td style="text-align:left;">查询状态，选项：<br><b>ALL_STATUS</b>不限状态；<br><b>UNRECOGNIZED</b>无法识别；<br><b>ACTIVE</b>可用状态；<br/><b>SAVING</b>保存状态；<br/><b>QUEUED</b>等待状态；<br/><b>KILLED</b>停止状态；<br/><b>PENDING_DELETE</b>待删除状态；<br/><b>DELETED</b>删除状态</td>
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
      "total":1,
	  "hasPrevious":false,"hasNext":false,
	  "entities":[{
	      "unique":"590d77bb37da647417197552",
		  "status":"ACTIVED","created":1494054843518,
		  "updated":1494054843518,"name":"ls-junit",
		  "size":13287936,"minRam":0,
		  "minDisk":0,
		  "description":"junit测试-可删除",
		  "applicationNames":["viewer","QQ","mysql"],
		  "containerFormat":null,
		  "diskFormat":null,"links":[]}],
		  "links":[]},"links":[]
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
<td style="text-align:left;">镜像ID</td>
</tr><tr>
<td style="text-align:center;">name</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">镜像名称</td>
</tr><tr>
<td style="text-align:center;">size</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">镜像大小</td>
</tr><tr>
<td style="text-align:center;">isPublic</td>
<td style="text-align:center;">Boolean</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">镜像是否为公共访问权限</td>
</tr><tr>
<td style="text-align:center;">isProtected</td>
<td style="text-align:center;">Boolean</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">镜像是否为保护状态</td>
</tr><tr>
<td style="text-align:center;">minRam</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">镜像要求的最小内存空间，0表示无限制</td>
</tr><tr>
<td style="text-align:center;">minDisk</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">镜像要求的最小磁盘空间，0表示无限制</td>
</tr><tr>
<td style="text-align:center;">status</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">镜像状态</td>
</tr><tr>
<td style="text-align:center;">created</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">镜像创建时间</td>
</tr><tr>
<td style="text-align:center;">updated</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">镜像上次更新时间</td>
</tr></tbody>
</table>

## <a name="delete-image">删除镜像 (Delete Image)</a>

> http://api.htaiyun.com/v1/openstack/image/<imageid>/delete

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
<td style="text-align:center;">imageId</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">yes</td>
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:center;">镜像ID</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{
   "status":200,
   "message":"OK","links":[]
}
</code>
