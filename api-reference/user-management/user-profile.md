# <a name="user-profile">个人资料 (User Profile)</a>

## <a name="read-user-profile">读取个人资料 (Read User Profile)</a>

> http://api.htaiyun.com/v1/user/profile/<userid>/read

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">HT-SESSION-TOKEN</td><td style="color:#999;">当前用户会话ID</td></tr>
	<tr><td style="text-align:left;">HT-SESSION-SECRET</td><td style="color:#999;">当前用户会话密钥</td></tr>
</table>

### 输出数据

#### 返回实例

<code>
{ 
	"status" : 200, 
	"message" : "OK",
	"result" : {
		"unique" : 1,
		"name" : "张三",
		"gender" : "MALE",
		"age" : 28,
		"enterprises" : ["894320483","483920843"],
		"mobile" : "...",
		"email" : "...",
		"country" : "CHINA",
		"province" : "BEIJING",
		"city" : "HAIDIAN",
		"address" : "",
		"avatarUrl" : "http://...",
		"signature" : "..."
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

## <a name="update-user-profile">更新个人资料 (Update User Profile)</a>

> http://api.htaiyun.com/v1/user/profile/<userid>/update

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">HT-SESSION-TOKEN</td><td style="color:#999;">当前用户会话ID</td></tr>
	<tr><td style="text-align:left;">HT-SESSION-SECRET</td><td style="color:#999;">当前用户会话密钥</td></tr>
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
<td style="text-align:left;">用户名字</td>
</tr><tr>
<td style="text-align:center;">gender</td>
<td style="text-align:center;">Options: ['MALE','FEMALE']</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">MALE</td>
<td style="text-align:left;">用户性别</td>
</tr><tr>
<td style="text-align:center;">birthday</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">0</td>
<td style="text-align:left;">用户出生年月日</td>
</tr><tr>
<td style="text-align:center;">country</td>
<td style="text-align:center;">String, Restricted</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">CHINA</td>
<td style="text-align:left;">用户所属国家，提交内容受到限制，必须为国籍数据列表中的项目</td>
</tr><tr>
<td style="text-align:center;">province</td>
<td style="text-align:center;">String, Restricted</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">""</td>
<td style="text-align:left;">用户所在省份、地区或州，提交内容受到限制，必须为国籍对应的数据列表中的项目</td>
</tr><tr>
<td style="text-align:center;">city</td>
<td style="text-align:center;">String, Restricted</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">""</td>
<td style="text-align:left;">用户所在城市、区、县，提交内容受到限制，必须为省份、地区或州队赢的数据列表中的项目</td>
</tr><tr>
<td style="text-align:center;">address</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">""</td>
<td style="text-align:left;">用户的通信地址</td>
</tr><tr>
<td style="text-align:center;">avatar</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">""</td>
<td style="text-align:left;">用户的头像URL地址</td>
</tr><tr>
<td style="text-align:center;">signature</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">""</td>
<td style="text-align:left;">用户的个性化签名</td>
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

## <a name="update-user-profile-single">更新个人资料单项 (Update User Profile - Single Item)</a>

> http://api.htaiyun.com/v1/user/profile/<userid>/update/name
> 
> http://api.htaiyun.com/v1/user/profile/<userid>/update/gender
> 
> http://api.htaiyun.com/v1/user/profile/<userid>/update/birthday
> 
> http://api.htaiyun.com/v1/user/profile/<userid>/update/location
> 
> http://api.htaiyun.com/v1/user/profile/<userid>/update/address
> 
> http://api.htaiyun.com/v1/user/profile/<userid>/update/avatar
> 
> http://api.htaiyun.com/v1/user/profile/<userid>/update/signature

<table border="0" cellpadding="0" cellspacing="0">
	<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
	<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
	<tr><td style="text-align:left;">HT-SESSION-TOKEN</td><td style="color:#999;">当前用户会话ID</td></tr>
	<tr><td style="text-align:left;">HT-SESSION-SECRET</td><td style="color:#999;">当前用户会话密钥</td></tr>
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
<td style="text-align:left;">用户名字</td>
</tr><tr>
<td style="text-align:center;">email</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">NO</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">用户邮箱</td>
</tr><tr>
<td style="text-align:center;">mobile</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">NO</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">用户电话</td>
</tr><tr>
<td style="text-align:center;">gender</td>
<td style="text-align:center;">Options: ['MALE','FEMALE']</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">MALE</td>
<td style="text-align:left;">用户性别</td>
</tr><tr>
<td style="text-align:center;">birthday</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">0</td>
<td style="text-align:left;">用户出生年月日</td>
</tr><tr>
<td style="text-align:center;">country</td>
<td style="text-align:center;">String, Restricted</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">CHINA</td>
<td style="text-align:left;">用户所属国家，提交内容受到限制，必须为国籍数据列表中的项目</td>
</tr><tr>
<td style="text-align:center;">province</td>
<td style="text-align:center;">String, Restricted</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">""</td>
<td style="text-align:left;">用户所在省份、地区或州，提交内容受到限制，必须为国籍对应的数据列表中的项目</td>
</tr><tr>
<td style="text-align:center;">city</td>
<td style="text-align:center;">String, Restricted</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">""</td>
<td style="text-align:left;">用户所在城市、区、县，提交内容受到限制，必须为省份、地区或州队赢的数据列表中的项目</td>
</tr><tr>
<td style="text-align:center;">address</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">""</td>
<td style="text-align:left;">用户的通信地址</td>
</tr><tr>
<td style="text-align:center;">avatar</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">""</td>
<td style="text-align:left;">用户的头像URL地址</td>
</tr><tr>
<td style="text-align:center;">signature</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">""</td>
<td style="text-align:left;">用户的个性化签名</td>
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