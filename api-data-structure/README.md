# 恒泰艾普云平台应用接口的数据结构说明 (API Data Structure)

本文以说明、解释恒泰艾普云平台应用接口中使用的数据结构为目的。文中所提及的数据结构均采用JSON封装。

## 云平台接口的HTTP Request

云平台大多数接口均是通过HTTP协议调用，部分接口通过WebSocket提供长连接访问。对于采用HTTP协议调用的接口，对于HTTP Request，有以下一些约定：

1. 对于不同的接口须采用不同的请求方法，我们支持的请求方法包括：GET, POST，具体接口调用时采用的方法，请参考API Reference文档；
2. 关于参数提交，采用GET方法调用时，参数须通过URL QueryString提交，对于包含有特殊字符的参数，请通过encodeURI处理；采用POST方法调用时，大多数方法通过表单方式提交（x-www-form-urlencoded），部分接口通过JSON方式提交，具体请参考API Reference文档；
3. 所有的请求均采用UTF-8编码；
4. 在请求头中，应该以下内容是必须包含的：IMR-ACCESS-TOKEN，这个头传入应用的访问令牌，在API系统开发过程中，请暂时传入0000-0000-0000-0000；

## 云平台接口的HTTP Response

当调用一个云平台接口，系统将通过HTTP Response返回调用结果。一个标准的云平台调用结果为JSON数据格式（Content-Type: application/json），采用UTF-8编码。标准结构如下：

<code>
{
	"status" : 200,
	"message" : "OK",
	"result" : { ... }
}
</code>

status代表调用结果代码，message代表调用结果描述，result为调用结果（可选，某些调用可能不返回结果，类似函数定义中的void返回）。

常用的status包括：

<table border="0" cellpadding="0" cellspacing="0">
<thead><tr>
<td style="text-align:center; background-color:#f5f5f5;">status</td>
<td style="text-align:center; background-color:#f5f5f5;">说明</td>
</tr></thead>
<tbody><tr>
<td style="text-align:center;">200</td>
<td style="text-align:left;">调用成功</td>
</tr><tr>
<td style="text-align:center;">400</td>
<td style="text-align:left;">调用参数不合法</td>
</tr><tr>
<td style="text-align:center;">403</td>
<td style="text-align:left;">方法需要授权后才能调用，即需要在HTTP Request中传入IMR-SESSION-TOKEN和IMR-SESSION_SECRET头，且这两个参数代表的帐号拥有访问接口的权限</td>
</tr><tr>
<td style="text-align:center;">406</td>
<td style="text-align:left;">调用过程出错，详细错误请参考message字段</td>
</tr></tbody>
</table>

## 云平台接口数据结构说明

在返回的HTTP Response中，可能存在result字段，这个字段即为返回结果。在云平台接口中，这个返回结果可能包括：

1. 用户系统

	1.1 [认证会话 (Authenticated Session)](authenticated-session.md)

	1.2 [简单用户对象 (Simple User Object)](simple-user-object.md)

	1.3 [详细用户对象 (User Object)](user-object.md)

