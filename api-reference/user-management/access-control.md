# <a name="access-controler">访问控制 (Access Control)</a>

## <a name="register">注册 (Register)</a>

> http://api.htaiyun.com/v1/access/register

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
</table>

提供用户注册接口，在产品需求中，用户可以使用自己的电子邮件地址和手机号码完成注册。基本流程如下：

1. 输入手机号码或电子邮件地址
2. 获取短信验证码或邮件验证码
3. 输入其他注册信息，包括：验证码、登录密码、名字、帐号类型、所在公司、公司联系电话
4. 提交注册表单，提交前需验证：

	a. 验证码是否为六位数字组成；
	
	b. 登录密码是否为数字、大小写英文字母、其他可见英文字符组成；
	
	c. 名字是否为2到40个字符组成；
	
	d. 帐号类型是否为PERSONAL或ENTERPRISE；
	
	e. 如果为ENTERPRISE帐号，则须验证是否提供了公司名称和联系电话；

5. 如果注册成功，系统将返回注册成功的用户对象数据；如果注册失败，则系统返回错误信息。

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
<td style="text-align:center;">username</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">用户的登录名，可为手机号码或电子邮件地址，须确保系统级全局唯一</td>
</tr><tr>
<td style="text-align:center;">captcha</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">手机或电子邮件验证码，为六位数字组成</td>
</tr><tr>
<td style="text-align:center;">password</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">用户的登录密码，指定为6到20位ASCII字符，要求由字母、数字组成</td>
</tr><tr>
<td style="text-align:center;">name</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">用户名字，用于在系统中显示，须全局唯一，可由中英文组成</td>
</tr><tr>
<td style="text-align:center;">type</td>
<td style="text-align:center;">Option: ['PERSONAL', 'ENTERPRISE']</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">PERSONAL</td>
<td style="text-align:left;">帐号类型，默认为个人帐号</td>
</tr><tr>
<td style="text-align:center;">company</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">""</td>
<td style="text-align:left;">企业类型帐号对应的公司名称</td>
</tr><tr>
<td style="text-align:center;">tel</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">""</td>
<td style="text-align:left;">企业类型帐号对应的公司联系电话，用于企业认证</td>
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
		"username" : "USERNAME",
		"type" : "PERSONAL",
		"status" : "ACTIVED",
		"creted" : 0,
		"updated" : 0
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

#### 常见错误信息

<table border="0" cellpadding="0" cellspacing="0">
<thead><tr>
<td style="text-align:center; background-color:#f5f5f5;">status</td>
<td style="text-align:center; background-color:#f5f5f5;">message</td>
<td style="text-align:center; background-color:#f5f5f5;">说明</td>
</tr></thead>
<tbody><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">invalid username format</td>
<td style="text-align:left;">无效的用户名格式，表示传入的用户名不是手机号码或电子邮件地址</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">invalid captcha format</td>
<td style="text-align:left;">无效的验证码格式，表示传入的验证码格式不正确</td>
</tr><tr>
<td style="text-align:center;">403</td>
<td style="text-align:left;">captcha verification failed</td>
<td style="text-align:left;">验证码错误，表示传入的验证码与用户名不匹配</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">invalid password format</td>
<td style="text-align:left;">无效的密码格式，表示传入的密码格式无效，正确的密码由数字、大小写英文字母和其他可见的英文字符组成</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">invalid name format</td>
<td style="text-align:left;">无效的名字，表示传入的用户名字无效，正确的名字应该由2至40个字符组成，中英文及特殊字符不限</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">invalid account type</td>
<td style="text-align:left;">无效的帐号类型，表示传入帐号类型错误，不是有效帐号类型中的一种</td>
</tr></tbody>
</table>


## <a name="login">登录 (Login)</a>

> http://api.htaiyun.com/v1/access/login

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
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
<td style="text-align:center;">username</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">用户的登录名，可为手机号码或电子邮件地址，须确保系统级全局唯一</td>
</tr><tr>
<td style="text-align:center;">password</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">用户的登录密码</td>
</tr><tr>
<td style="text-align:center;">enterprise</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">""</td>
<td style="text-align:left;">企业唯一号，用于登录到企业控制台</td>
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
		"username" : "USERNAME",
		"type" : "PERSONAL",
		"status" : "ACTIVED",
		"creted" : 0,
		"updated" : 0
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
</tr><tr>
<td style="text-align:center;">sessionToken</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">用户会话ID</td>
</tr><tr>
<td style="text-align:center;">sessionSecret</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">用户会话密钥</td>
</tr><tr>
<td style="text-align:center;">expired</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">用户会话过期时间戳（以服务器时间为准）</td>
</tr></tbody>
</table>

## <a name="reset-password">重设密码 (Reset Password)</a>

> http://api.htaiyun.com/v1/access/password/reset

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
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
<td style="text-align:center;">username</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">用户的登录名，可为手机号码或电子邮件地址，须确保系统级全局唯一</td>
</tr><tr>
<td style="text-align:center;">captcha</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">手机或电子邮件验证码，为六位数字组成</td>
</tr><tr>
<td style="text-align:center;">password</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">用户的登录密码，指定为6到20位ASCII字符，要求由字母、数字组成</td>
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

## <a name="websocket">建立websocket连接 (websocket)</a>

> http://api.htaiyun.com/services/htaiyun/webSocketServer/sockjs

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-TOKEN</td><td style="color:#999;">当前用户会话ID</td></tr>
	<tr><td style="text-align:left;">IMR-SESSION-SECRET</td><td style="color:#999;">当前用户会话密钥</td></tr>
</table>

#### 浏览器端JS代码示例
	 function connect() {  
		var options = {"server":"userid=1"};
		ws = new SockJS("http://localhost:8080/services/htaiyun/webSocketServer/sockjs",null,options);  
                              
        ws.onopen = function () {  
            log('Info: connection opened.');  
        };  
          
        ws.onmessage = function (event) {  
            log('Received: ' + event.data);  
        };  
          
        ws.onclose = function (event) {  
			log('Info: connection closed.');  
        };  
    }  

    function disconnect() {  
        if (ws != null) {  
            ws.close();  
            ws = null;  
        }  
    }  
         
### 输入参数

### 输出数据
	服务器将每隔5s向在线用户推送未读通知信息。
#### 返回实例

<code>

	"您有2条未读通知"

</code>

#### 数据说明

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

## <a name="update-password">修改密码 (Update Password)</a>

> http://api.htaiyun.com/v1/access/password/update

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
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
<td style="text-align:center;">Long</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">用户ID</td>
</tr><tr>
<td style="text-align:center;">oldpwd</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">旧密码</td>
</tr><tr>
<td style="text-align:center;">newpwd</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">新密码</td>
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
