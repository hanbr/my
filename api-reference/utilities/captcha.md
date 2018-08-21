# <a name="captcha">验证码</a>

## <a name="captcha-sms">获取短信验证码 (SMS Captcha)</a>

<http://api.htaiyun.com/services/utilities/captcha/sms>

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
</table>

该接口限制调用频率，同一个手机号码每60秒才能够调用一次；否则会返回406错误。

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
<td style="text-align:center;">mobile</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">用户手机号码</td>
</tr><tr>
<td style="text-align:center;">type</td>
<td style="text-align:center;">Option: ['REGISTER_CODE', 'RANDOM_PASSWORD', 'NO_VERIFICATION']</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">RANDOM_PASSWORD</td>
<td style="text-align:left;">短信验证码类型，<br/>REGISTER_CODE: 注册用验证码，系统会验证改手机号是否存在，如存在将返回错误；<br/>RANDOM_PASSWORD: 随机密码，系统会验证手机号是否存在，如不存在将返回错误；<br/>NO_VERIFICATION: 不需要验证，无论手机号是否在系统注册过，都会发送验证码；</td>
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

###错误信息

|status|message|description|
|:----:|:-----:|:---------:|
|406|mobile-has-exists|在type为REGISTER_CODE的情况下可能返回，指的是该手机号码已经存在|
|406|mobile-not-exists|在type为RANDOM_PASSWORD的情况下可能返回，指的是该手机号码不存在|
|406|call-frequency-too-fast|当同一手机号码的两次调用时间差小于1分钟时返回|


## <a name="captcha-email">获取邮件验证码 (Email Captcha)</a>

<http://api.htaiyun.com/services/utilities/captcha/email>

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
</table>

该接口限制调用频率，同一个电子邮件地址每300秒才能够调用一次；否则会返回406错误。

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
<td style="text-align:center;">email</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">用户电子邮件地址</td>
</tr><tr>
<td style="text-align:center;">type</td>
<td style="text-align:center;">Option: ['REGISTER_CODE', 'RANDOM_PASSWORD', 'NO_VERIFICATION']</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">RANDOM_PASSWORD</td>
<td style="text-align:left;">短信验证码类型，<br/>REGISTER_CODE: 注册用验证码，系统会验证邮件地址是否存在，如存在将返回错误；<br/>RANDOM_PASSWORD: 随机密码，系统会验证邮件地址是否存在，如不存在将返回错误；<br/>NO_VERIFICATION: 不需要验证，无论邮件地址是否在系统注册过，都会发送验证码；</td>
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

### 错误信息

|status|message|description|
|:----:|:-----:|:---------:|
|406|email-has-exists|在type为REGISTER_CODE时返回,指的是email已经存在|
|406|email-not-exists|在type为RANDOM_PASSWORD时返回，指的时email不存在|
|406|call-frequency-too-fast|当同一邮箱的两次调用时间差小于5分钟时返回|

## <a name="captcha-graphic-link">获取图形验证码链接 (Graphic Captcha)</a>

<http://api.htaiyun.com/services/utilities/captcha/graphic>

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
</table>

### 输入参数

### 输出数据
<code>
{
	"status" : 200,
	"message" : "OK",
	"url" : "http://api.htaiyun.com/services/utilities/captcha/graphic?unique=1",
	"unique" : "1"
}
</code>

### 返回数据说明
|field|description|
|:----:|:-----:|
|url|用来获取验证码图形的链接|
|unique|此验证码的唯一标示符，在验证验证码时使用|

## <a name="captcha-graphic-verification">校验图形验证码 (Graphic Captcha Verification)</a>

<http://api.htaiyun.com/v1/utilities/captcha/graphic/verification>

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
<td style="text-align:center;">unique</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">获取图形验证码链接时返回的验证码的唯一标示符</td>
</tr><tr>
<td style="text-align:center;">captcha</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">验证码，由六位数字组成</td>
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

### 错误信息

|status|message|description|
|:----:|:-----:|:---------:|
|406|captcha-format-invalid|验证码中含有非法字符|
|406|captcha-not-find|该unique代表的验证码不存在|
|406|captcha-has-expired|验证码已经过期，有效期为15分钟|
|406|captcha-is-wrong|验证码错误|
