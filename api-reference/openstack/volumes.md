# <a name="volumes">卷管理 (Volumes)</a>

## <a name="create-volume">创建卷 (Create Volume)</a>

> http://api.htaiyun.com/services/openstack/volume/create

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-TOKEN</td><td style="color:#999;">当前用户会话ID</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-SECRET</td><td style="color:#999;">当前用户会话密钥</td></tr>
</table>

### 输入参数

|名称|类型|是否必须|默认值|说明|
|:--:|:--:|:----:|:---:|:--:|
|userid|long|否|N/A|磁盘所有者id|
|name|String|是|N/A|卷名称|
|description|String|否|N/A|描述|
|size|INT|否|N/A|卷的大小，单位为GB|
|image|String|否|N/A|创建卷的的镜像image的id|


### 使用说明
若是从镜像创建卷，size可以不传，否则size为必须的参数

### 输出数据

#### 返回实例

<code>
{
	"status" : 200,
	"message" : "OK",
	"result" : {
		"unique" : 1,
		"name" : "...",
		...
		"status" : "ACTIVED",
		"created" : ...,
		"updated" : ...
	}
}
</code>

#### 数据说明

|名称|说明|
|:--:|:--:|
|unique|UserVolume的唯一标识符|
|created|创建时间戳|
|updated|更新时间戳|
|volumeId|OpenStack中volume的唯一标识符|
|name|volume名称|
|description|描述|
|volumeStatus|volume状态，可能值为CREATING、AVALIABLE等|
|size|卷的大小，单位为GB|
|zone|域，nova|
|volumeType|卷的类型|
|sourceVolid|源卷的id，若是通过clone创建时会存在|
|snapshotId|快照id，若是通过快照创建的会存在|
|bootable|是否可启动|
|attachment|卷的挂载信息|
|migrateStatus|迁移状态|

#### 错误说明

|status|message|description|
|:----:|:-----:|:---------:|
|403|volumes.error.access-denied|用户未登录时返回。没有设置IMR-SESSION-TOKEN和IMR-SESSION-SECRET或者登录状态已过期时返回|
|406|volumes.error.size-invalid|size参数小于等于0|
|406|volumes.error.size-insufficient|系统容量不足|
|406|volumes.error.require-parameter-size|缺少size参数|
|500|volumes.error.create-fail|系统发生错误|

## <a name="get-volume">获取卷 (Get Volume)</a>

> http://api.htaiyun.com/services/openstack/volume/{unique}/get

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-TOKEN</td><td style="color:#999;">当前用户会话ID</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-SECRET</td><td style="color:#999;">当前用户会话密钥</td></tr>
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
		...
		"status" : "ACTIVED",
		"created" : ...,
		"updated" : ...
	}
}
</code>

#### 错误说明

|status|message|description|
|:----:|:-----:|:---------:|
|403|volumes.error.access-denied|用户未登录时返回。没有设置IMR-SESSION-TOKEN和IMR-SESSION-SECRET或者登录状态已过期时返回|
|406|volumes.error.not-exists|volume不存在|

## <a name="clone-volume">克隆 (Clone Volume)</a>

> http://api.htaiyun.com/services/openstack/volume/{unique}/clone

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-TOKEN</td><td style="color:#999;">当前用户会话ID</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-SECRET</td><td style="color:#999;">当前用户会话密钥</td></tr>
</table>

### 输入参数

|名称|类型|是否必须|默认值|说明|
|:--:|:--:|:----:|:---:|:--:|
|uid|Long|是|N/A|用户ID|
|name|String|是|N/A|卷名称|
|description|String|否|N/A|描述|

### 输出数据

#### 返回实例

<code>
{
	"status" : 200,
	"message" : "OK",
	"result" : {
		"unique" : 1,
		"name" : "...",
		...
		"status" : "ACTIVED",
		"created" : ...,
		"updated" : ...
	}
}
</code>

#### 数据说明

|名称|说明|
|:--:|:--:|
|unique|UserVolume的唯一标识符|
|created|创建时间戳|
|updated|更新时间戳|
|volumeId|OpenStack中volume的唯一标识符|
|name|volume名称|
|description|描述|
|volumeStatus|volume状态，可能值为CREATING、AVALIABLE等|
|size|卷的大小，单位为GB|
|zone|域，nova|
|volumeType|卷的类型|
|sourceVolid|源卷的id，若是通过clone创建时会存在|
|snapshotId|快照id，若是通过快照创建的会存在|
|bootable|是否可启动|
|attachments|卷的连接|
|migrateStatus|迁移状态|

#### 错误说明

|status|message|description|
|:----:|:-----:|:---------:|
|403|volumes.error.access-denied|用户未登录时返回。没有设置IMR-SESSION-TOKEN和IMR-SESSION-SECRET或者登录状态已过期时返回|
|406|volumes.error.not-exists|volume不存在|
|406|volumes.error.size-insufficient|系统容量不足|
|500|volumes.error.clone-fail|系统发生错误|


## <a name="update-volume">更新卷 (Update Volume)</a>

> http://api.htaiyun.com/services/openstack/volume/{unique}/update

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-TOKEN</td><td style="color:#999;">当前用户会话ID</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-SECRET</td><td style="color:#999;">当前用户会话密钥</td></tr>
</table>

### 输入参数

|名称|类型|是否必须|默认值|说明|
|:--:|:--:|:----:|:---:|:--:|
|name|String|否|N/A|名称|
|description|是|N/A|描述|

### 输出数据

#### 返回实例

<code>
{
	"status" : 200,
	"message" : "OK"
}
</code>

#### 错误说明

|status|message|description|
|:----:|:-----:|:---------:|
|403|volumes.error.access-denied|用户未登录时返回。没有设置IMR-SESSION-TOKEN和IMR-SESSION-SECRET或者登录状态已过期时返回|
|406|volumes.error.not-exists|volume不存在|
|500|volumes.error.update-fail|系统发生错误|

## <a name="update-volume-single">更新卷单项 (Update Volume)</a>

> http://api.htaiyun.com/services/openstack/volume/{unique}/update/{name}

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-TOKEN</td><td style="color:#999;">当前用户会话ID</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-SECRET</td><td style="color:#999;">当前用户会话密钥</td></tr>
</table>

### 使用说明
路径参数中的unique为uservolume的标识符，name可以为name、description

### 输入参数

|名称|类型|是否必须|默认值|说明|
|:--:|:--:|:----:|:---:|:--:|
|value|String|否|N/A|更改的值|

### 输出数据

#### 返回实例

<code>
{
	"status" : 200,
	"message" : "OK"
}
</code>

#### 错误说明

|status|message|description|
|:----:|:-----:|:---------:|
|403|volumes.error.access-denied|用户未登录时返回。没有设置IMR-SESSION-TOKEN和IMR-SESSION-SECRET或者登录状态已过期时返回|
|406|volumes.error.not-exists|volume不存在|
|500|volumes.error.update-fail|系统发生错误|

## <a name="extend-volume">扩展卷大小 (Extend Volume)</a>

> http://api.htaiyun.com/services/openstack/volume/{unique}/extend

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-TOKEN</td><td style="color:#999;">当前用户会话ID</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-SECRET</td><td style="color:#999;">当前用户会话密钥</td></tr>
</table>

### 输入参数

|名称|类型|是否必须|默认值|说明|
|:--:|:--:|:----:|:---:|:--:|
|size|int|否|N/A|扩展后的卷大小，单位为GB|

### 输出数据

#### 返回实例

<code>
{
	"status" : 200,
	"message" : "OK"
}
</code>

#### 错误说明

|status|message|description|
|:----:|:-----:|:---------:|
|403|volumes.error.access-denied|用户未登录时返回。没有设置IMR-SESSION-TOKEN和IMR-SESSION-SECRET或者登录状态已过期|
|406|volumes.error.not-exists|卷不存在|
|406|volumes.error.size-insufficient|容量不足|
|406|volumes.error.size-invalid|size小于当前的大小|
|500|volumes.error.update-failed|发生系统错误|

## <a name="delete-volume">删除卷 (Delete Volume)</a>

> http://api.htaiyun.com/services/openstack/volume/{unique}/delete

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-TOKEN</td><td style="color:#999;">当前用户会话ID</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-SECRET</td><td style="color:#999;">当前用户会话密钥</td></tr>
</table>

### 输入参数
#### 返回实例

<code>
{
	"status" : 200,
	"message" : "OK"
}
</code>

#### 错误说明

|status|message|description|
|:----:|:-----:|:---------:|
|403|volumes.error.access-denied|用户未登录时返回。没有设置IMR-SESSION-TOKEN和IMR-SESSION-SECRET或者登录状态已过期|
|406|volumes.error.not-exists|卷不存在|
|500|volumes.error.delete-failed|发生系统错误|

## <a name="status-volume">获取卷状态 (Status Volume)</a>

> http://api.htaiyun.com/services/openstack/volume/{unique}/status

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-TOKEN</td><td style="color:#999;">当前用户会话ID</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-SECRET</td><td style="color:#999;">当前用户会话密钥</td></tr>
</table>

### 输入参数
#### 返回实例

<code>
{
	"status" : 200,
	"message" : "OK"，
	"result" : {...}
}
</code>

#### volumestatus 说明

AVAILABLE, ATTACHING, BACKING_UP, CREATING, DELETING, DOWNLOADING, UPLOADING, ERROR, ERROR_DELETING, ERROR_RESTORING, IN_USE, RESTORING_BACKUP, DETACHING, UNRECOGNIZED;

#### 错误说明

|status|message|description|
|:----:|:-----:|:---------:|
|403|volumes.error.access-denied|用户未登录时返回。没有设置IMR-SESSION-TOKEN和IMR-SESSION-SECRET或者登录状态已过期|
|406|volumes.error.not-exists|卷不存在|
|500|volumes.error.get-status-failed|发生系统错误|

## <a name="list-volumes">查询卷 (List Volumes)</a>

> http://api.htaiyun.com/services/openstack/volume/list

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
<td style="text-align:center;">userid</td>
<td style="text-align:center;">long</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">磁盘所有者ID</td>
</tr><tr>
<td style="text-align:center;">keywords</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:left;">关键词，name或者description</td>
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
<td style="text-align:left;">卷ID</td>
</tr><tr>
<td style="text-align:center;">name</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">卷名称</td>
</tr><tr>
<td style="text-align:center;">status</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">卷状态</td>
</tr><tr>
<td style="text-align:center;">created</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">卷创建时间</td>
</tr><tr>
<td style="text-align:center;">updated</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">卷上次更新时间</td>
</tr></tbody>
</table>

|status|message|description|
|:----:|:-----:|:---------:|
|403|volumes.error.access-denied|用户未登录时返回。没有设置IMR-SESSION-TOKEN和IMR-SESSION-SECRET或者登录状态已过期|

## <a name="enable-volumes">启用或禁用云磁盘 (enable Volume)</a>

> http://api.htaiyun.com/services/openstack/volume/{volumeid}/enable

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
<td style="text-align:left;">二个选项：<br><b>ACTIVED</b>启用；<br><b>DISABLED</b>禁用；</td>
</tr><tr>
<td style="text-align:center;">serverId</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:left;">主机ID</td>
</tr></tbody>
</table>

### 使用说明
禁用操作，需要传入主机ID，从主机断开已经绑定的云磁盘

### 输出数据

#### 返回实例

<code>
{
	"status" : 200,
	"message" : "OK"
}
</code>

## <a name="attach-volume">挂载云磁盘 (attach Volume)</a>

> http://api.htaiyun.com/services/openstack/volume/{volumeid}/attach

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
<td style="text-align:center;">serverid</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">磁盘ID</td>
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

## <a name="detach-volume">断开云磁盘 (detach Volume)</a>

> http://api.htaiyun.com/services/openstack/volume/{volumeid}/dettach

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
<td style="text-align:center;">serverid</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">主机ID</td>
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

## <a name="batchenable-volume">批处理启用或禁用云磁盘 (Batchenable Volume)</a>

> http://api.htaiyun.com/services/openstack/volume/batchenableordisable

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
<td style="text-align:center;">serverids</td>
<td style="text-align:center;">String[]</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">磁盘ID集合</td>
</tr><tr>
<td style="text-align:center;">status</td>
<td style="text-align:center;">String, Restricted</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">二个选项：<br><b>ACTIVED</b>启用；<br><b>DISABLED</b>禁用；</td>
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

## <a name="batchdelete-volumes">批处理删除云磁盘 (batchdelete Volumes)</a>

> http://api.htaiyun.com/services/openstack/volume/batchdelete

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
<td style="text-align:center;">volumns</td>
<td style="text-align:center;">String[]</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">云磁盘ID集合</td>
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
