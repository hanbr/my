## <a name="create">创建单个文件(Create File)</a>

> http://api.htaiyun.com/v1/file/create

<table border="0" cellpadding="0" cellspacing="0">
	<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
<tr><td style="text-align:left;">Authorization</td><td style="color:#999;">标准HTTP Basic Authentication内容，包括登录用户的sessionToken和sessionSecret</td></tr>
<tr><td style="text-align:left;">content-type</td><td style="color:#999;">非multipart/form-data类型</td></tr>
</table>

提供创建并上传单个文件的接口，在产品需求中，用户可以输入文件信息并上传文件。基本流程如下：

1. 输入名称、描述，选择要上传的文件、文件类型。
2. 提交文件表单，提交前需验证：

	a. 文件是否不为空；

3. 如果创建成功，系统将返回创建成功的文件对象数据；如果创建失败，则系统返回错误信息。

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
<td style="text-align:center;">filename</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">根据当前时间随机生成</td>
<td style="text-align:left;">文件名</td>
</tr><tr>
<td style="text-align:center;">name</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">filename</td>
<td style="text-align:left;">名称</td>
</tr><tr>
<td style="text-align:center;">description</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">文件内容简介、用途等</td>
</tr><tr>
<td style="text-align:center;">contenttype</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">application/octet-stream</td>
<td style="text-align:left;">文件类型</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{
  "status" : 200,
  "message" : "OK",
  "result" : {
      "unique" : "582ebbb6239d84568171c213",           
      "name" : "fa",
      "filename" : "ceshi.txt",
      "alias" : "",
      "pinyin" : "fa",
      "description" : "",
      "size" : 0,
	  "contentType" : "application/octet-stream",
	  "url" : "null/file/582ebbb6239d84568171c213/download",
	  "keyname" : "ceshi.txt-fa-1479457659847",
      "md5" : "d41d8cd98f00b204e9800998ecf8427e",      
 	  "status" : "ACTIVED",
      "created" : 1479457659847,
      "updated" : 1479457711038,
      "properties" : { },
      "indexes" : { },
      "tags" : [ ],
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
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">文件信息的ID</td>
</tr><tr>
<td style="text-align:center;">name</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">名称</td>
</tr><tr>
<td style="text-align:center;">filename</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">上传的文件的名称</td>
</tr><tr>
<td style="text-align:center;">description</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:left;">对应用的功能、特点的描述</td>
</tr><tr>
<td style="text-align:center;">size</td>
<td style="text-align:center;">long</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">文件大小</td>
</tr><tr>
<td style="text-align:center;">contentType</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">文件类型</td>
</tr><tr>
<td style="text-align:center;">url</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">文件下载时的url</td>
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
</tr></tbody>
</table>

## <a name="create">创建一个或多个文件(Create File)</a>

> http://api.htaiyun.com/v1/file/create

<table border="0" cellpadding="0" cellspacing="0">
	<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
<tr><td style="text-align:left;">Authorization</td><td style="color:#999;">标准HTTP Basic Authentication内容，包括登录用户的sessionToken和sessionSecret</td></tr>
<tr><td style="text-align:left;">content-type</td><td style="color:#999;">multipart/form-data</td></tr>
</table>

提供创建并上传一个或多个文件的接口，在产品需求中，用户可以输入文件信息并上传文件。基本流程如下：

1. 输入名称、描述、文件类型，选择要上传的一个或多个文件。
2. 提交文件表单，提交前需验证：

	a. 至少有一个文件不为空；

3. 如果创建成功，系统将返回创建成功的文件对象数据；如果创建失败，则系统返回错误信息。

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
<td style="text-align:center;">filename(一个或多个)</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">根据当前时间随机生成</td>
<td style="text-align:left;">文件名</td>
</tr><tr>
<td style="text-align:center;">name</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">filename</td>
<td style="text-align:left;">名称</td>
</tr><tr>
<td style="text-align:center;">description</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">描述，文件内容简介、用途等</td>
</tr><tr>
<td style="text-align:center;">contenttype</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">application/octet-stream</td>
<td style="text-align:left;">文件类型</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{
  "status" : 200,
  "message" : "OK",
  "result" : {
    "total" : 2,
    "hasPrevious" : false,
    "hasNext" : false,
    "entities" : [ {
      "unique" : "58353c0b239dfd1971418847",
      "status" : "ACTIVED",
      "created" : 1479883778891,
      "updated" : 1479883784517,
      "keyname" : "jsontemplete.txt-jsontemplete-1479883778891",
      ...
    },...],
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
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">文件信息的ID</td>
</tr><tr>
<td style="text-align:center;">name</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">名称</td>
</tr><tr>
<td style="text-align:center;">filename</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">上传的文件的名称</td>
</tr><tr>
<td style="text-align:center;">description</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:left;">对应用的功能、特点的描述</td>
</tr><tr>
<td style="text-align:center;">size</td>
<td style="text-align:center;">long</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">文件大小</td>
</tr><tr>
<td style="text-align:center;">contentType</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">文件类型</td>
</tr><tr>
<td style="text-align:center;">url</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">文件下载时的url</td>
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
</tr></tbody>
</table>


## <a name="delete">删除文件 (Delete File)</a>

> http://api.htaiyun.com/v1/file/{id}/delete

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
<td style="text-align:left;">mongoFile not found</td>
<td style="text-align:left;">所要删除的文件不存在</td>
</tr>
</tbody>
</table>

## <a name="list">查询文件 (List Files)</a>

> http://api.htaiyun.com/v1/file/list

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
<td style="text-align:left;">关键词，应用于name字段上</td>
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
    "total" : 2,
    "hasPrevious" : false,
    "hasNext" : false,
    "entities" : [ {
      "unique" : "58353c0b239dfd1971418847",
      "status" : "ACTIVED",
      "created" : 1479883778891,
      "updated" : 1479883784517,
      "keyname" : "jsontemplete.txt-jsontemplete-1479883778891",
      ...
    },...],
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
<td style="text-align:left;">具体文件记录信息</td>
</tr></tbody>
</table>

## <a name="get">读取云应用(Get File)</a>

> http://api.htaiyun.com/v1/file/{id}/get

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
      "unique" : "582ebbb6239d84568171c213",           
      "name" : "fa",
      "filename" : "ceshi.txt",
      "alias" : "",
      "pinyin" : "fa",
      "description" : "",
      "size" : 0,
	  "contentType" : "application/octet-stream",
	  "url" : "null/file/582ebbb6239d84568171c213/download",
	  "keyname" : "ceshi.txt-fa-1479457659847",
      "md5" : "d41d8cd98f00b204e9800998ecf8427e",      
 	  "status" : "ACTIVED",
      "created" : 1479457659847,
      "updated" : 1479457711038,
      "properties" : { },
      "indexes" : { },
      "tags" : [ ],
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
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">文件信息的ID</td>
</tr><tr>
<td style="text-align:center;">name</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">名称</td>
</tr><tr>
<td style="text-align:center;">filename</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">上传的文件的名称</td>
</tr><tr>
<td style="text-align:center;">description</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:left;">对应用的功能、特点的描述</td>
</tr><tr>
<td style="text-align:center;">size</td>
<td style="text-align:center;">long</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">文件大小</td>
</tr><tr>
<td style="text-align:center;">contentType</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">文件类型</td>
</tr><tr>
<td style="text-align:center;">url</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">文件下载时的url</td>
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
<td style="text-align:left;">mongoFile not found</td>
<td style="text-align:left;">要读取的文件不存在</td>
</tr>
</tbody>
</table>

## <a name="download">下载文件(Download File)</a>

> http://api.htaiyun.com/v1/file/{id}/download

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">GET</td><td></td></tr>
	<tr><th rowspan=2 style="text-align:right; background-color:#f5f5f5;">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">Authorization</td><td style="color:#999;">标准HTTP Basic Authentication内容，包括登录用户的sessionToken和sessionSecret</td></tr>
</table>

### 输入参数

### 输出数据

#### 返回实例

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
<td style="text-align:left;"> not found</td>
<td style="text-align:left;">所要下载的文件不存在</td>
</tr>
</tbody>
</table>