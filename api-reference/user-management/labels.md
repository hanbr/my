# <a name="label">标签</a>

## <a name="label-create">创建标签</a>

<http://api.htaiyun.com/services/label/create>

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-TOKEN</td><td style="color:#999;">当前用户会话ID</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-SECRET</td><td style="color:#999;">当前用户会话密钥</td></tr>
</table>

### 输入参数

|名称|类型|是否必须|默认值|说明|
|:--:|:--:|:----:|:---:|:--:|
|name|String|是|N/A|标签名称|


### 输出数据

#### 输出示例
<code>
  {
  "status" : 200,
  "message" : "OK",
  "result" : {
  "unique" : "12345678",
  "status" : "ACTIVED",
  "created" : "",
  "updated" : "",
  "name" : "",
  "pinyin" : "",
  }
  }
</code>

### 错误说明

|status|message|description|
|:----:|:-----:|:---------:|
|403|labels.error.access-denied|用户未登录时返回。没有设置IMR-SESSION-TOKEN和IMR-SESSION-SECRET或者登录状态已过期时返回|
|406|labels.errors.name-format-invalid|name中含有非法字符，只可以为0-9a-zA-Z和中文|
|406|labels.errors.has-exists|该名称的label已经存在|

## <a name="label-delete">删除标签</a>

<http://api.htaiyun.com/services/label/{id}/delete>

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-TOKEN</td><td style="color:#999;">当前用户会话ID</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-SECRET</td><td style="color:#999;">当前用户会话密钥</td></tr>
</table>
#### 使用说明
使用要删除的标签的唯一表示符代替url中的{id}

### 输入参数

### 输出数据

#### 输出示例

<code>
  {
    "status" : 200,
    "message" : "OK"
  }
</code>

### 错误说明

|status|message|description|
|:----:|:-----:|:---------:|
|403|labels.error.access-denied|用户未登录时返回。没有设置IMR-SESSION-TOKEN和IMR-SESSION-SECRET或者登录状态已过期时返回|
|406|labels.errors.not-exists|此标签不存在|

## <a name="label-update">更新标签</a>

<http://api.htaiyun.com/services/label/{id}/update>

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-TOKEN</td><td style="color:#999;">当前用户会话ID</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-SECRET</td><td style="color:#999;">当前用户会话密钥</td></tr>
</table>

#### 使用说明
使用要更新的标签的唯一表示符代替url中的{id}

### 输入参数

|名称|类型|是否必须|默认值|说明|
|:--:|:--:|:----:|:---:|:--:|
|name|String|是|N/A|修改后的标签的名称|

### 输出数据

#### 输出示例
<code>
  {
    "status" : 200,
    "message" : "OK"
  }
</code>

### 错误说明

|status|message|description|
|:----:|:-----:|:---------:|
|403|labels.error.access-denied|用户未登录时返回。没有设置IMR-SESSION-TOKEN和IMR-SESSION-SECRET或者登录状态已过期时返回|
|406|labels.errors.not-exists|此标签不存在|

## <a name="label-addrelationship">给社交关系添加标签</a>

<http://api.htaiyun.com/services/label/relationship/add>

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-TOKEN</td><td style="color:#999;">当前用户会话ID</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-SECRET</td><td style="color:#999;">当前用户会话密钥</td></tr>
</table>

### 输入参数

|名称|类型|是否必须|默认值|说明|
|:--:|:--:|:----:|:---:|:--:|
|label|String|是|N/A|标签的id|
|relationship|是|N/A|社交关系的id|

### 输出数据

#### 输出示例
<code>
  {
    "status" : 200,
    "message" : "OK"
  }
</code>

### 错误说明

|status|message|description|
|:----:|:-----:|:---------:|
|403|labels.error.access-denied|用户未登录时返回。没有设置IMR-SESSION-TOKEN和IMR-SESSION-SECRET或者登录状态已过期时返回|
|406|labels.errors.not-exists|该标签不存在|
|406|labels.errors.relationship-not-exists|该社交关系不存在|

## <a name="label-removerelationship">给社交关系删除标签</a>

<http://api.htaiyun.com/services/label/relationship/remove>

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-TOKEN</td><td style="color:#999;">当前用户会话ID</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-SECRET</td><td style="color:#999;">当前用户会话密钥</td></tr>
</table>

### 输入参数

|名称|类型|是否必须|默认值|说明|
|:--:|:--:|:----:|:---:|:--:|
|label|String|是|N/A|标签的id|
|relationship|是|N/A|社交关系的id|

### 输出数据

#### 输出示例

<code>
  {
    "status" : 200,
    "message" : "OK"
  }
</code>

### 错误说明

|status|message|description|
|:----:|:-----:|:---------:|
|403|labels.error.access-denied|用户未登录时返回。没有设置IMR-SESSION-TOKEN和IMR-SESSION-SECRET或者登录状态已过期时返回|
|406|labels.errors.not-exists|该标签不存在|
|406|labels.errors.relationship-not-exists|该社交关系不存在|

## <a name="label-list">查询标签</a>

<http://api.htaiyun.com/services/label/list>

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">GET</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-TOKEN</td><td style="color:#999;">当前用户会话ID</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-SECRET</td><td style="color:#999;">当前用户会话密钥</td></tr>
</table>

### 输入参数
|名称|类型|是否必须|默认值|说明|
|:--:|:--:|:----:|:---:|:--:|
|keyword|String|否|N/A|查询标签的关键字，可为拼音|
|page|String|否|1|当前页码，从1开始|
|offset|String|否|20|每页记录数|
|order|String|否|created|排序字段，可选: created, updated,name,pinyin|
|asc|Boolean|否|false|是否升序|

### 输出数据

#### 输出示例

<code>
{
	"status" : 200,
	"message" : "OK",
	"result" : {
		"hasPrevious" : false,
		"hasNext" : false,
		"total" : 5,
		"entites" : [{
    "unique" : "12345678",
    "status" : "ACTIVED",
    "created" : "",
    "updated" : "",
    "name" : "",
    "pinyin" : "",
		},...]
	}
}}
</code>

### 错误说明

|status|message|description|
|:----:|:-----:|:---------:|
|403|labels.error.access-denied|用户未登录时返回。没有设置IMR-SESSION-TOKEN和IMR-SESSION-SECRET或者登录状态已过期时返回|

## <a name="label-list-all-entity">查询出该标签下的某种类型的所有实体</a>

<http://api.htaiyun.com/services/label/{id}/list/all>

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">GET</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-TOKEN</td><td style="color:#999;">当前用户会话ID</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-SECRET</td><td style="color:#999;">当前用户会话密钥</td></tr>
</table>

#### 使用说明
使用标签的唯一表示符代替url中的{id}

### 输入参数
|名称|类型|是否必须|默认值|说明|
|:--:|:--:|:----:|:---:|:--:|
|class|String|否|Relationship|类别名，目前只可为Relationship|
