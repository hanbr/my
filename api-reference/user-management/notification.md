# <a name="notifications">通知管理 (Notifications)</a>

## <a name="createandsend-notification">创建并发送通知 (CreateAndSend Notification)</a>

> http://api.htaiyun.com/services/notify/send

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
<td style="text-align:center;">sid</td>
<td style="text-align:center;">Long</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">发件人的ID</td>
</tr><tr>
<td style="text-align:center;">rid</td>
<td style="text-align:center;">Long</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">收件人的ID</td>
</tr><tr>
<td style="text-align:center;">message</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">消息内容</td>
</tr><tr>
<td style="text-align:center;">type</td>
<td style="text-align:center;">String, Restricted</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">通知类型：<br><b>RequestApproved</b>申请被拒绝<br><b>RequestRejected</b>申请已审批通过</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{
	"status" : 200,
	"message" : "OK",
	"result" : {
      "unique" : 21,
      "sender" : {
        "unique" : "1",
        "className" : "com.htaiyun.users.data.jpa.entities.User",
        "name" : "18011873436",
        "pinyin" : null,
        "avatar" : null,
        "properties" : { },
        "links" : [ ]
      },
      "receiver" : {
        "unique" : "1",
        "className" : "com.htaiyun.users.data.jpa.entities.User",
        "name" : "18011873436",
        "pinyin" : null,
        "avatar" : null,
        "properties" : { },
        "links" : [ ]
      },
      "message" : "您的申请已经审批通过:liyliyl",
      "sended" : true,
      "readed" : false,
	  "type" : "RequestApproved",
	  "created" : 1480940252034,
      "updated" : 1480940252034,
      "links" : [ ]
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
<td style="text-align:left;">通知ID</td>
</tr><tr>
<td style="text-align:center;">sender</td>
<td style="text-align:center;">GlobalDomain</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">发件人信息</td>
</tr><tr>
<td style="text-align:center;">receiver</td>
<td style="text-align:center;">GlobalDomain</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">收件人信息</td>
</tr><tr>
<td style="text-align:center;">message</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">消息内容</td>
</tr><tr>
<td style="text-align:center;">type</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">消息类型</td>
</tr><tr>
<td style="text-align:center;">sended</td>
<td style="text-align:center;">boolean</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">是否已发送</td>
</tr><tr>
<td style="text-align:center;">readed</td>
<td style="text-align:center;">boolean</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">是否已读</td>
</tr><tr>
<td style="text-align:center;">sendtime</td>
<td style="text-align:center;">long</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">发送时间</td>
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
</tr></tbody>
</table>


## <a name="create-notification">创建通知 (Create Notification)</a>

> http://api.htaiyun.com/services/notify/create

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
<td style="text-align:center;">sid</td>
<td style="text-align:center;">Long</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">发件人的ID</td>
</tr><tr>
<td style="text-align:center;">rid</td>
<td style="text-align:center;">Long</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">收件人的ID</td>
</tr><tr>
<td style="text-align:center;">message</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">消息内容</td>
</tr><tr>
<td style="text-align:center;">type</td>
<td style="text-align:center;">String, Restricted</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">通知类型：<br><b>RequestApproved</b>申请被拒绝<br><b>RequestRejected</b>申请已审批通过</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{
	"status" : 200,
	"message" : "OK",
	"result" : {
      "unique" : 21,
      "sender" : {
        "unique" : "1",
        "className" : "com.htaiyun.users.data.jpa.entities.User",
        "name" : "18011873436",
        "pinyin" : null,
        "avatar" : null,
        "properties" : { },
        "links" : [ ]
      },
      "receiver" : {
        "unique" : "1",
        "className" : "com.htaiyun.users.data.jpa.entities.User",
        "name" : "18011873436",
        "pinyin" : null,
        "avatar" : null,
        "properties" : { },
        "links" : [ ]
      },
      "message" : "您的申请已经审批通过:liyliyl",
      "sended" : true,
      "readed" : false,
	  "type" : "RequestApproved",
	  "created" : 1480940252034,
      "updated" : 1480940252034,
      "links" : [ ]
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
<td style="text-align:left;">通知ID</td>
</tr><tr>
<td style="text-align:center;">sender</td>
<td style="text-align:center;">GlobalDomain</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">发件人信息</td>
</tr><tr>
<td style="text-align:center;">receiver</td>
<td style="text-align:center;">GlobalDomain</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">收件人信息</td>
</tr><tr>
<td style="text-align:center;">message</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">消息内容</td>
</tr><tr>
<td style="text-align:center;">type</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">消息类型</td>
</tr><tr>
<td style="text-align:center;">sended</td>
<td style="text-align:center;">boolean</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">是否已发送</td>
</tr><tr>
<td style="text-align:center;">readed</td>
<td style="text-align:center;">boolean</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">是否已读</td>
</tr><tr>
<td style="text-align:center;">sendtime</td>
<td style="text-align:center;">long</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">发送时间</td>
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
</tr></tbody>
</table>

## <a name="get-notification">读取通知 (Get Notification)</a>

> http://api.htaiyun.com/services/notify/{id}/get

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">GET</td><td></td></tr>
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
      "unique" : 21,
      "sender" : {
        "unique" : "1",
        "className" : "com.htaiyun.users.data.jpa.entities.User",
        "name" : "18011873436",
        "pinyin" : null,
        "avatar" : null,
        "properties" : { },
        "links" : [ ]
      },
      "receiver" : {
        "unique" : "1",
        "className" : "com.htaiyun.users.data.jpa.entities.User",
        "name" : "18011873436",
        "pinyin" : null,
        "avatar" : null,
        "properties" : { },
        "links" : [ ]
      },
      "message" : "您的申请已经审批通过:liyliyl",
      "sended" : true,
      "readed" : false,
	  "type" : "RequestApproved",
	  "created" : 1480940252034,
      "updated" : 1480940252034,
      "links" : [ ]
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
<td style="text-align:left;">通知ID</td>
</tr><tr>
<td style="text-align:center;">sender</td>
<td style="text-align:center;">GlobalDomain</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">发件人信息</td>
</tr><tr>
<td style="text-align:center;">receiver</td>
<td style="text-align:center;">GlobalDomain</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">收件人信息</td>
</tr><tr>
<td style="text-align:center;">message</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">消息内容</td>
</tr><tr>
<td style="text-align:center;">type</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">消息类型</td>
</tr><tr>
<td style="text-align:center;">sended</td>
<td style="text-align:center;">boolean</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">是否已发送</td>
</tr><tr>
<td style="text-align:center;">readed</td>
<td style="text-align:center;">boolean</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">是否已读</td>
</tr><tr>
<td style="text-align:center;">sendtime</td>
<td style="text-align:center;">long</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">发送时间</td>
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
<td style="text-align:left;">notification not exists</td>
<td style="text-align:left;">通知不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">unauthorized</td>
<td style="text-align:left;">权限不足</td>
</tr></tbody>
</table>

## <a name="readed-notification">设为已读 (Readed Notification)</a>

> http://api.htaiyun.com/services/notify/{id}/readed

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
<td style="text-align:center;">403</td>
<td style="text-align:left;">access denied</td>
<td style="text-align:left;">需要的登陆才可以进行操作</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">notification not exists</td>
<td style="text-align:left;">通知不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">unauthorized</td>
<td style="text-align:left;">权限不足</td>
</tr></tbody>
</table>

## <a name="massive-readed-notification">批量设为已读 (Massive-Readed Notification)</a>

> http://api.htaiyun.com/services/notify/readed

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
<td style="text-align:center;">Long[]</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">要设为已读的通知的ID(以逗号分隔)</td>
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
<td style="text-align:center;">403</td>
<td style="text-align:left;">access denied</td>
<td style="text-align:left;">需要的登陆才可以进行操作</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">notification not exists</td>
<td style="text-align:left;">通知不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">unauthorized</td>
<td style="text-align:left;">权限不足</td>
</tr></tbody>
</table>

## <a name="delete-notification">删除通知 (Delete Notification)</a>

> http://api.htaiyun.com/services/notify/{id}/delete

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
<td style="text-align:left;">notification not exists</td>
<td style="text-align:left;">通知不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">unauthorized</td>
<td style="text-align:left;">权限不足</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">already sent</td>
<td style="text-align:left;">通知已经发送</td>
</tr></tbody>
</table>

## <a name="massive-delete-notification">批量删除通知 (Massive Delete Notification)</a>

> http://api.htaiyun.com/services/notify/delete/

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
<td style="text-align:center;">Long[]</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">要删除的通知的ID(以逗号分隔)</td>
</tr></tbody>
</table>

### 输出数据

#### 返回实例

<code>
{
	"status":406,
	"message":"Failed",
	"result":[
		{"unique":1,"reason":"already sent"},
		{"unique":2,"reason":"unauthorized"},
		{"unique":3,"reason":"notification not exists"}],
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
<td style="text-align:left;">notification not exists</td>
<td style="text-align:left;">通知不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">unauthorized</td>
<td style="text-align:left;">权限不足</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">already sent</td>
<td style="text-align:left;">通知已经发送</td>
</tr></tbody>
</table>

## <a name="send-notification">发送通知 (Send Notification)</a>

> http://api.htaiyun.com/services/notify/{id}/send/

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-TOKEN</td><td style="color:#999;">当前用户会话ID</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-SECRET</td><td style="color:#999;">当前用户会话密钥</td></tr>
</table>

### 输入参数

### 输出数据

#### 返回实例

<code>
{
	"status":200,
	"message":"Success",
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
<td style="text-align:left;">notification not exists</td>
<td style="text-align:left;">通知不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">unauthorized</td>
<td style="text-align:left;">权限不足</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">already sent</td>
<td style="text-align:left;">通知已经发送</td>
</tr></tbody>
</table>

## <a name="listoutbox-notification">当前用户创建的通知的列表 (Listoutbox Notification)</a>

> http://api.htaiyun.com/services/notify/listoutbox

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
<td style="text-align:left;">关键词，应用于通知的CONTROLLER字段上</td>
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
		"hasPrevious" : false,
		"hasNext" : false,
		"total" : 5,
		"entites" : [{
			"unique" : 1,
			"receiverid" : "1",
			"receiver" : "liyl",
			"message" : "your application already passed"
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
<td style="text-align:left;">群组ID</td>
</tr><tr>
<td style="text-align:center;">receiverid</td>
<td style="text-align:center;">Long</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">接收者用户ID</td>
</tr><tr>
<td style="text-align:center;">receiver</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">接收者用户名称</td>
</tr><tr>
<td style="text-align:center;">message</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">通知内容</td>
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
<td style="text-align:left;">unauthorized</td>
<td style="text-align:left;">权限不足</td>
</tr></tbody>
</table>

## <a name="listinbox-notification">当前用户接到的通知的列表 (Listinbox Notification)</a>

> http://api.htaiyun.com/services/notify/listinbox

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
<td style="text-align:center;">readed</td>
<td style="text-align:center;">String,Restricted</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:left;">是否已读：<br>
<b>true</b>已读<br>
<b>false</b>未读
</td>
</tr><tr>
<td style="text-align:center;">keywords</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:left;">关键词，应用于通知的message字段上</td>
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
		"hasPrevious" : false,
		"hasNext" : false,
		"total" : 5,
		"entites" : [{
			"unique" : 1,
			"senderid" : "1",
			"sender" : "liyl",
			"message" : "your application already passed"
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
<td style="text-align:left;">群组ID</td>
</tr><tr>
<td style="text-align:center;">senderid</td>
<td style="text-align:center;">Long</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">发送者用户ID</td>
</tr><tr>
<td style="text-align:center;">sender</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">发送者用户名称</td>
</tr><tr>
<td style="text-align:center;">message</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">通知内容</td>
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
<td style="text-align:left;">unauthorized</td>
<td style="text-align:left;">权限不足</td>
</tr></tbody>
</table>