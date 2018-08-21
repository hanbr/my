# <a name="users">用户管理 (Users)</a>

## <a name="create-user">创建用户 (Create User)</a>

> http://192.168.96.211/services/user/create

<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
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
<td style="text-align:center;">username</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">用户名，须确保全局唯一存在，在系统中我们建议客户使用手机号码或电子邮件地址作为用户名</td>
</tr><tr>
<td style="text-align:center;">mobile</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">用户手机号码，须确保全局唯一存在</td>
</tr><tr>
<td style="text-align:center;">email</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">用户电子邮件地址，须确保全局唯一存在</td>
</tr><tr>
<td style="text-align:center;">nickname</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">用户昵称</td>
</tr><tr>
<td style="text-align:center;">name</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">用户名称</td>
</tr><tr>
<td style="text-align:center;">gender</td>
<td style="text-align:center;">Options</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">'MALE' : '男性'</td>
<td style="text-align:left;">用户性别，可选参数，须为['MALE', 'FEMALE']中选择一项</td>
</tr><tr>
<td style="text-align:center;">birthday</td>
<td style="text-align:center;">Long</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">0</td>
<td style="text-align:left;">用户出生年月日，此参数可选，应为用户出生年月日的UNIX时间戳</td>
</tr><tr>
<td style="text-align:center;">country</td>
<td style="text-align:center;">Options</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">'CHINA' : '中国'</td>
<td style="text-align:left;">用户国籍</td>
</tr><tr>
<td style="text-align:center;">province</td>
<td style="text-align:center;">Options</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">用户所在省份或地区</td>
</tr><tr>
<td style="text-align:center;">city</td>
<td style="text-align:center;">Options</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">用户所在城市或区域</td>
</tr><tr>
<td style="text-align:center;">groupids</td>
<td style="text-align:center;">Checkbox</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">用户所属组</td>
</tr><tr>
<td style="text-align:center;">desktops</td>
<td style="text-align:center;">int</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">5</td>
<td style="text-align:left;">用户最多可创建的云桌面个数</td>
</tr><tr>
<td style="text-align:center;">applicationids</td>
<td style="text-align:center;">Checkbox</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">用户可以有的云应用列表</td>
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
<td style="text-align:center;">nickname</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">用户昵称</td>
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
<td style="text-align:center;">pinyin</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">用户名字的拼音</td>
</tr><tr>
<td style="text-align:center;">mobile</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">用户手机号码</td>
</tr><tr>
<td style="text-align:center;">email</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">用户电子邮件地址</td>
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
<td style="text-align:center;">birthday</td>
<td style="text-align:center;">Long</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">0</td>
<td style="text-align:left;">用户出生年月日，为用户出生年月日的UNIX时间戳</td>
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
<td style="text-align:center;">groupids</td>
<td style="text-align:center;">Checkbox</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">用户所属组</td>
</tr><tr>
<td style="text-align:center;">desktops</td>
<td style="text-align:center;">int</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">5</td>
<td style="text-align:left;">用户最多可创建的云桌面个数</td>
</tr><tr>
<td style="text-align:center;">applicationids</td>
<td style="text-align:center;">Checkbox</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">用户可以有的云应用列表</td>
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
<td style="text-align:left;">gender must  'MALE'  or  'FEMALE'</td>
<td style="text-align:left;">gender参数值无效，必须是MALE或者FEMALE中的一个</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">username exists</td>
<td style="text-align:left;">用户登录名已经存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">mobile && email at least one is not empty</td>
<td style="text-align:left;">手机号和email至少有一个不为空</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">invalid mobile format</td>
<td style="text-align:left;">手机号码格式错误</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">mobile exists</td>
<td style="text-align:left;">手机号已经存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">invalid email format</td>
<td style="text-align:left;">邮箱地址格式错误</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">email exists</td>
<td style="text-align:left;">邮箱地址已经存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">group not exists</td>
<td style="text-align:left;">所选的用户组不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">application not exists</td>
<td style="text-align:left;">所选的云应用不存在</td>
</tr></tbody>
</table>

---

## <a name="update-user">2.3.2 更新用户信息 (Update User)</a>

> http://192.168.96.211/services/user/{userid}/update

<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
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
<td style="text-align:center;">username</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">用户名，须确保全局唯一存在，在系统中我们建议客户使用手机号码或电子邮件地址作为用户名</td>
</tr><tr>
<td style="text-align:center;">mobile</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">用户手机号码，须确保全局唯一存在</td>
</tr><tr>
<td style="text-align:center;">nickname</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">用户昵称</td>
</tr><tr>
<td style="text-align:center;">email</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">用户电子邮件地址，须确保全局唯一存在</td>
</tr><tr>
<td style="text-align:center;">name</td>
<td style="text-align:center;">String</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">N/A</td>
<td style="text-align:left;">用户名称</td>
</tr><tr>
<td style="text-align:center;">gender</td>
<td style="text-align:center;">Options</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">'MALE' : '男性'</td>
<td style="text-align:left;">用户性别，可选参数，须为['MALE', 'FEMALE']中选择一项</td>
</tr><tr>
<td style="text-align:center;">birthday</td>
<td style="text-align:center;">Long</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">0</td>
<td style="text-align:left;">用户出生年月日，此参数可选，应为用户出生年月日的UNIX时间戳</td>
</tr><tr>
<td style="text-align:center;">country</td>
<td style="text-align:center;">Options</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">'CHINA' : '中国'</td>
<td style="text-align:left;">用户国籍</td>
</tr><tr>
<td style="text-align:center;">province</td>
<td style="text-align:center;">Options</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">用户所在省份或地区</td>
</tr><tr>
<td style="text-align:center;">city</td>
<td style="text-align:center;">Options</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;"></td>
<td style="text-align:left;">用户所在城市或区域</td>
</tr><tr>
<td style="text-align:center;">desktops</td>
<td style="text-align:center;">Checkbox</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">5</td>
<td style="text-align:left;">用户最多可创建的云桌面个数</td>
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
<td style="text-align:left;">user not exists</td>
<td style="text-align:left;">所要修改的用户不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">gender must  'MALE'  or  'FEMALE'</td>
<td style="text-align:left;">gender参数值无效，必须是MALE或者FEMALE中的一个</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">username exists</td>
<td style="text-align:left;">用户登录名已经存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">mobile && email at least one is not empty</td>
<td style="text-align:left;">手机号和email至少有一个不为空</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">invalid mobile format</td>
<td style="text-align:left;">手机号码格式错误</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">mobile exists</td>
<td style="text-align:left;">手机号已经存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">invalid email format</td>
<td style="text-align:left;">邮箱地址格式错误</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">email exists</td>
<td style="text-align:left;">邮箱地址已经存在</td>
</tr></tbody>
</table>

## <a name="enable-user">启用用户 (Enable User)</a>

> http://192.168.96.211/services/user/{userid}/enable

<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
<tr><td style="text-align:left;">Authorization</td><td style="color:#999;">标准HTTP Basic Authentication内容，包括登录用户的sessionToken和sessionSecret</td></tr>
</table>

### 输出数据

#### 返回实例

<code>
{
"status" : 200,
"message" : "OK"
}
</code>

## <a name="enalbe-users">批量启用用户 (Enable Users)</a>

> http://192.168.96.211/services/user/enable

<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td colspan="2" style="text-align:left;">POST</td></tr>
<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
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
<td style="text-align:center;">users</td>
<td style="text-align:center;">JSON Array</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">[]</td>
<td style="text-align:left;">要启用的用户ID列表，例如[1, 2, 4]</td>
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
<td style="text-align:left;">user not exists</td>
<td style="text-align:left;">所要启用的用户不存在</td>
</tr></tbody>
</table>

## <a name="disable-user">停用用户 (Disable User)</a>

> http://192.168.96.211/services/user/{userid}/disable

<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
<tr><td style="text-align:left;">Authorization</td><td style="color:#999;">标准HTTP Basic Authentication内容，包括登录用户的sessionToken和sessionSecret</td></tr>
</table>

### 输出数据
#### 返回实例
<code>
{
"status" : 200,
"message" : "OK"
}
</code>

## <a name="disable-users">批量禁用用户 (Disable Users)</a>

> http://192.168.96.211/services/user/disable

<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td colspan="2" style="text-align:left;">POST</td></tr>
<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
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
<td style="text-align:center;">users</td>
<td style="text-align:center;">JSON Array</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">[]</td>
<td style="text-align:left;">要禁用的用户ID列表，例如[1, 2, 4]</td>
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
<td style="text-align:left;">user not exists</td>
<td style="text-align:left;">所要禁用的用户不存在</td>
</tr></tbody>
</table>

## <a name="list-users">查询用户 (List Users)</a>

> http://192.168.96.211/services/user/list

<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">GET</td><td></td></tr>
<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
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
<td style="text-align:left;">关键词，应用于用户的username、mobile、email和name四个字段上</td>
</tr><tr>
<td style="text-align:center;">status</td>
<td style="text-align:center;">String, Restricted</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">ALL_STATUS</td>
<td style="text-align:left;">查询状态，三个选项：<br><b>ALL_STATUS</b>不限状态；<br><b>ACTIVED</b>可用状态；<br/><b>DISABLED</b>停用状态；</td>
</tr><tr>
<td style="text-align:center;">page</td>
<td style="text-align:center;">Long</td>
<td style="text-align:center;">No</td>
<td style="text-align:center;">1</td>
<td style="text-align:left;">当前页码，从1开始</td>
</tr><tr>
<td style="text-align:center;">offset</td>
<td style="text-align:center;">Long</td>
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
		"hasPrevious" : false,
		"hasNext" : false,
		"total" : 5,
		"entites" : [{
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
<td style="text-align:center;">entites</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">具体用户记录信息</td>
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
<td style="text-align:left;">user not exists</td>
<td style="text-align:left;">所要禁用的用户不存在</td>
</tr></tbody>
</table>

## <a name="list-user-roles">查询用户角色 (List User Roles)</a>

> http://192.168.96.211/services/user/{userid}/role/list

<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">GET</td><td></td></tr>
<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
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
<td style="text-align:left;">关键词，应用于角色的name和displayName两个字段上</td>
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
		"hasPrevious" : false,
		"hasNext" : false,
		"total" : 5,
		"entites" : [{
		"unique" : 1,
		"name" : "administrator",
		"displayName" : "超级管理员"
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
<td style="text-align:center;">entites</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">具体角色记录信息</td>
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

## <a name="add-user-role">添加用户角色 (Add User Role)</a>

> http://192.168.96.211/services/user/{userid}/role/add

<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
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
<td style="text-align:center;">roleid</td>
<td style="text-align:center;">Long</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:left;">角色ID</td>
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
<td style="text-align:left;"> user not exists!</td>
<td style="text-align:left;">所选用户不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">role not found</td>
<td style="text-align:left;">所选角色不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">userRole exists</td>
<td style="text-align:left;">所选用户已经拥有所选角色</td>
</tr></tbody>
</table>

## <a name="update-user-role">修改用户角色 (Update User Role)</a>

> http://192.168.96.211/services/user/{userid}/role/update

<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
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
<td style="text-align:center;">roleid</td>
<td style="text-align:center;">Long</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:left;">角色ID</td>
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
<td style="text-align:left;"> user not exists!</td>
<td style="text-align:left;">所选用户不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">role not found</td>
<td style="text-align:left;">所选角色不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">userRole exists</td>
<td style="text-align:left;">所选用户已经拥有所选角色</td>
</tr></tbody>
</table>

## <a name="delete-user-role">删除用户角色 (Delete User Role)</a>

> http://192.168.96.211/services/user/{userid}/role/delete

<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
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
<td style="text-align:center;">roleid</td>
<td style="text-align:center;">Long</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:left;">角色ID</td>
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
<td style="text-align:left;"> user not exists!</td>
<td style="text-align:left;">所要为之添加角色的用户不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">role not found</td>
<td style="text-align:left;">所选角色不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">userRole not found</td>
<td style="text-align:left;">用户本就没有所选角色</td>
</tr></tbody>
</table>

## <a name="list-user-groups">查询用户群组 (List User Groups)</a>

> http://192.168.96.211/services/user/{userid}/group/list

<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
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
<td style="text-align:left;">关键词，应用于群组的name和displayName两个字段上</td>
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
		"hasPrevious" : false,
		"hasNext" : false,
		"total" : 5,
		"entites" : [{
		"unique" : 1,
		"name" : "group1",
		"displayName" : "群组1"
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
<td style="text-align:center;">entites</td>
<td style="text-align:center;">Integer</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:left;">具体群组记录信息</td>
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

## <a name="add-user-group">添加用户群组 (Add User Group)</a>

> http://192.168.96.211/services/user/{userid}/group/add

<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
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
<td style="text-align:center;">groupid</td>
<td style="text-align:center;">Long</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:left;">群组ID</td>
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
<td style="text-align:left;"> user not exists!</td>
<td style="text-align:left;">所选用户不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">group not exists</td>
<td style="text-align:left;">所选群组不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">user already added</td>
<td style="text-align:left;">用户已经在所选群组中</td>
</tr></tbody>
</table>

## <a name="delete-user-group">删除用户群组 (Delete User Group)</a>

> http://192.168.96.211/services/user/{userid}/group/delete

<table border="0" cellpadding="0" cellspacing="0">
<tr><th style="text-align:right; background-color:#f5f5f5;">Method</th><td style="text-align:left;">POST</td><td></td></tr>
<tr><th style="text-align:right; background-color:#f5f5f5;" rowspan="3">Special Request Header</th><td style="text-align:left;">HT-ACCESS-TOKEN</td><td style="color:#999;">云平台应用接口访问令牌</td></tr>
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
<td style="text-align:center;">groupid</td>
<td style="text-align:center;">Long</td>
<td style="text-align:center;">Yes</td>
<td style="text-align:center;">&lt;Empty&gt;</td>
<td style="text-align:left;">群组ID</td>
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
<td style="text-align:left;"> user not exists!</td>
<td style="text-align:left;">所选用户不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">group not exists</td>
<td style="text-align:left;">所选群组不存在</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">user not exists in group</td>
<td style="text-align:left;">所选用户本就不在所选群组中</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">user is group owner</td>
<td style="text-align:left;">所选用户是群组的拥有者，不能将群组拥有者从群组中删除</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">not group owner</td>
<td style="text-align:left;">当前登录用户不是所选群组的拥有者（如果所选用户是所选群组的管理员，则当前登录用户必须是群组拥有者，才有权限将所选用户从所选群组中删除）</td>
</tr></tbody>
</table>
