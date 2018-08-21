# <a name="relationships">社交关系 (Relationships)</a>

## <a name="create-relationship">创建社交关系 (Create Relationship)</a>

> http://api.htaiyun.com/v1/relationship/create

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
<td style="text-align:center;">user</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">目标用户ID</td>
</tr><tr>
<td style="text-align:center;">type</td>
<td style="text-align:center;">String, Restricted</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">FRIENDS</td>
<td style="text-align:left;">社交关系类型，默认为FRIENDS</td>
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
		"user" : { ... },
		"target" : { ... },
		"type" : "FRIENDS",
		"status" : "NOT_ACTIVED",
		"created" : ...,
		"updated" : ...
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
<td style="text-align:left;">社交关系ID</td>
</tr><tr>
<td style="text-align:center;">type</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">社交关系类型。FRIEND:强关系(比如好友)；FOLLOW:弱关系(比如关注)</td>
</tr><tr>
<td style="text-align:center;">isInitial</td>
<td style="text-align:center;">Boolean</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">是否为社交关系发起人</td>
</tr><tr>
<td style="text-align:center;">target</td>
<td style="text-align:center;">Simple User Object</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">社交关系目标</td>
</tr><tr>
<td style="text-align:center;">labels</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">社交关系的标签，由逗号分隔</td>
</tr><tr>
<td style="text-align:center;">status</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">社交关系状态</td>
</tr><tr>
<td style="text-align:center;">created</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">社交关系创建时间</td>
</tr><tr>
<td style="text-align:center;">updated</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">社交关系上次更新时间</td>
</tr></tbody>
</table>

####说明
当返回的isInitial为false时，表明对方已经发起建立关系，请确认关系


### 错误说明

|status|message|description|
|:----:|:-----:|:---------:|
|403|relationships.error.access-denied|用户未登录时返回。没有设置IMR-SESSION-TOKEN和IMR-SESSION-SECRET或者登录状态已过期时返回|
|406|relationships.errors.targetuser-not-exists|目标用户不存在|
|406|relationships.errors.has-exists|社交关系已经存在|
|406|relationships.errors.require-actived|type为FRIEND时可能返回，已经发起建立社交关系，等待对方确认|

## <a name="delete-relationship">删除社交关系 (Delete Relationship)</a>

> http://api.htaiyun.com/v1/relationship/<relationshipid>/delete

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
	"message" : "OK"
}
</code>

### 错误说明

|status|message|description|
|:----:|:-----:|:---------:|
|403|relationships.error.access-denied|用户未登录时返回。没有设置IMR-SESSION-TOKEN和IMR-SESSION-SECRET或者登录状态已过期时返回|
|406|relationships.errors.not-exists|该社交关系不存在|
|406|relationships.errors.can-not-delete|无法删除该社交关系，当该用户不是该社交关系的拥有者时返回|

## <a name="confirm-relationship">确认社交关系 (Confirm Relationship)</a>

> http://api.htaiyun.com/v1/relationship/{relationshipid}/confirm

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-TOKEN</td><td style="color:#999;">当前用户会话ID</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-SECRET</td><td style="color:#999;">当前用户会话密钥</td></tr>
</table>

#### 使用说明
使用要确认的社交关系的id替换url中的""{relationshipid}"

### 输出数据

#### 返回实例

<code>
{
	"status" : 200,
	"message" : "OK"
}
</code>

### 错误说明
|status|message|description|
|:----:|:-----:|:---------:|
|403|relationships.error.access-denied|用户未登录时返回。没有设置IMR-SESSION-TOKEN和IMR-SESSION-SECRET或者登录状态已过期时返回|
|406|relationships.errors.can-not-confirm|关系的发起者不可确认该关系|
|406|relationships.errors.has-confirmed|关系已经确认|


## <a name="list-relationships">查询社交关系 (List Relationships)</a>

> http://api.htaiyun.com/v1/group/list

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
<tbody>
<tr>
<td style="text-align:center;">type</td>
<td style="text-align:center;">String, Restricted</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">ALL_TYPE</td>
<td style="text-align:left;">查询类型，三个选项：<br><b>ALL_TYPE</b>不限类型；<br><b>FRIEND</b>强类型，朋友；<br/><b>FOLLOW</b>弱类型，关注；</td>
</tr>
<tr>
<td style="text-align:center;">label</td>
<td style="text-align:center;">String, Restricted</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">社交关系标签的名称</td>
</tr>
<tr>
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
<td style="text-align:center;">created</td>
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
		"hasPrevious" : false,
		"hasNext" : false,
		"total" : 5,
		"entites" : [{
			"unique" : 1,
			"user" : { ... },
			"target" : { ... },
			"type" : "FRIENDS",
			"status" : "NOT_ACTIVED",
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
<td style="text-align:left;">社交关系ID</td>
</tr><tr>
<td style="text-align:center;">type</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">社交关系类型</td>
</tr><tr>
<td style="text-align:center;">user</td>
<td style="text-align:center;">Simple User Object</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">社交关系所有人</td>
</tr><tr>
<td style="text-align:center;">target</td>
<td style="text-align:center;">Simple User Object</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">社交关系目标</td>
</tr><tr>
<td style="text-align:center;">status</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">社交关系状态</td>
</tr><tr>
<td style="text-align:center;">created</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">社交关系创建时间</td>
</tr><tr>
<td style="text-align:center;">updated</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">社交关系上次更新时间</td>
</tr></tbody>
</table>

### 错误说明
|status|message|description|
|:----:|:-----:|:---------:|
|403|relationships.error.access-denied|用户未登录时返回。没有设置IMR-SESSION-TOKEN和IMR-SESSION-SECRET或者登录状态已过期时返回|
