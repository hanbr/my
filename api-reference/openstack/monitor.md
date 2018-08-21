# <a name="charge-system">虚拟机监控</a>

## <a name="login">登录 (Login)</a>

> http://192.168.95.121:8086/wsgi_app.py

### 输入参数

|名称|类型|是否必须|默认值|说明|
|:--:|:--:|:----:|:---:|:--:|
|user_name|String|是|N/A|用户名|
|password|String|是|N/A|密码|
|method|String|否|N/A|请求的方法|

### 使用说明
{"data": {"user_name": "admin","password": "123456"},"method": 458753}

### 输出数据

#### 返回实例

<code>
{
    "status_code": 1, 
	"message": "'User authenticated sucessfully...'", 
	"method": 458753, 
	"session_id": "9afdb1ec-d396-4ba3-af7a-1e38fd8751ca", 
	"message_id": ""
}
</code>

#### 数据说明

|名称|说明|
|:--:|:--:|
|status_code|状态码（1.创建2.成功3.失败4.超时）|
|message|成功或失败信息|
|session_id|有效的Token|
|method|请求的方法|

#### 错误说明

## <a name="get-vmMonitoringProcData">获取虚拟机进程数据 (getVMMonitoringProcData)</a>

> http://192.168.95.121:8086/wsgi_app.py

### 输入参数

|名称|类型|是否必须|默认值|说明|
|:--:|:--:|:----:|:---:|:--:|
|instance_id|String|是|N/A|虚拟机ID|
|session_id|String|是|N/A|有效的Token|
|method|String|否|N/A|请求的方法|

### 使用说明
{"method":611711,"data":{"instance_id":"6abf5a1e-b85c-4e5f-ba02-f96e22cbd02e;"}, "session_id": "9afdb1ec-d396-4ba3-af7a-1e38fd8751ca", "limit": 4}

### 输出数据

#### 返回实例

<code>
{
   "status_code":1,
   "session_id":"9afdb1ec-d396-4ba3-af7a-1e38fd8751ca",
   "message_id":"",
   "message": "'success query proc information'",
   "data":[
      "{u'net_incoming':0.6,
        u'shutdown_time':None,
        u'mem':0.1,
        u'net_outgoing':5.7,
        u'cmd':u'systemd-udevd',
        u'pid':489,
        u'instance_id':u'6abf5a1e-b85c-4e5f-ba02-f96e22cbd0e,
        u'disk_write': 0.0, 
        u'disk_read': 0.0, 
        u'create_date': u'2017-01-01T21:37:59.001065', 
        u'_id': ObjectId('58690637594c10403e25b048'),
        u'cpu_util':0.0,u'running_time':1482236516.07
      }",
      "{u'net_incoming':0.6,
        u'shutdown_time':None,
        u'mem':0.2,
        u'net_outgoing':5.7,
        u'cmd':u'lvmetad',
        u'pid':479,	
		u'instance_id':u'6abf5a1e-b85c-4e5f-ba02-f96e22cbd02e,	
		u'disk_write':0.0,u'disk_read':0.0,u'create_date':u'2017-1-01T21:37:58.999841',
        u'_id':ObjectId('58690637594c10403e25b047'),
        u'cpu_util':0.0,u'running_time': 1482236515.63
       }", 
      "{u'net_incoming': 0.6, u'shutdown_time': None, 
        u'mem': 0.4, u'net_outgoing': 5.7, 
        u'cmd': u'dhclient', u'pid': 975, 
        u'instance_id':u'6abf5a1e-b85c-4e5f-ba02-f96e22cbd0e, 
        u'disk_write': 0.0, u'disk_read': 0.0, 
        u'create_date':u'2017-01-01T21:37:58.998690',
        u'_id':ObjectId('58690636594c10403e25b046'),
        u'cpu_util':0., 
		u'running_time': 1482236528.23
      }", 
      "{u'net_incoming': 0.6,
	    u'shutdown_time': None, 
        u'mem': 0.1, u'net_outgoing': 5.7, 
	    u'cmd': u'systemd-journald',u'pid': 461, 
	    u'instance_id':u'6abf5a1e-b85c-4e5f-ba02-f96e22cbd02e', 
	    u'disk_write': 0.0, u'disk_read': 2.2, 
	    u'create_date': u'2017-01-01T21:37:58.996452', 
	    u'_id': ObjectId('58690636594c10403e25b045'), 
	    u'cpu_util': 0.0, u'running_time': 1482236514.85
       }"
   ], 
   "method": 611711
}

</code>

#### 数据说明

|名称|说明|
|:--:|:--:|
|net_incoming|下行流量|
|shutdown_time|进程关闭时间|
|net_outgoing|上行流量|
|cmd|请求的方法|
|disk_write|磁盘写速率|
|disk_read|磁盘读速率|
|create_date|记录上报时间|
|cpu_util|cpu使用率|
|running_time|进程开启时间|

#### 错误说明

## <a name="get-vmMonitoringData">获取虚拟机数据 (getVMMonitoringData)</a>

> http://192.168.95.121:8086/wsgi_app.py

### 输入参数

|名称|类型|是否必须|默认值|说明|
|:--:|:--:|:----:|:---:|:--:|
|instance_id|String|是|N/A|虚拟机ID|
|session_id|String|是|N/A|有效的Token|
|method|String|否|N/A|请求的方法|

### 使用说明
{"method":611611,"data":{"instance_id":"6abf5a1e-b85c-4e5f-ba02-f96e22cbd02e;"}, "session_id": "768a07b5-2206-4952-b445-21162571a19a", "limit": 1}

### 输出数据

#### 返回实例

<code>
{
  "status_code": 1, 
  "session_id": "768a07b5-2206-4952-b445-21162571a19a", 
  "message_id": "", 
  "message": "'success query vm information'", 
  "data": [
    "{u'net_incoming': 0.6, 
      u'disk_write': 128.8, 
      u'mem': 8.6, u'net_outgoing': 5.7, 
      u'instance_id': u'6abf5a1e-b85c-4e5f-ba02-f96e22cbd02e', 
      u'cpu_util': 0.0, 
      u'disk_read': 0.0, 
      u'create_date': u'2017-01-01T21:37:59.680873', 
      u'_id': ObjectId('58690637594c10403e25b049'), 
      u'proc': 95}"
   ], 
  "method": 611611
}

</code>

#### 数据说明

|名称|说明|
|:--:|:--:|
|net_incoming|下行流量|
|net_outgoing|上行流量|
|mem|内存使用率（%）|
|disk_write|磁盘写速率|
|disk_read|磁盘读速率|
|create_date|记录上报时间|
|cpu_util|cpu使用率|
|instance_id|虚拟机ID|
|proc|进程数|

#### 错误说明

## <a name="get-vmMonitoringProcByNameData">根据虚拟机名称获取进程数据 (getVMMonitoringProcByNameData)</a>

> http://192.168.95.121:8086/wsgi_app.py

### 输入参数

|名称|类型|是否必须|默认值|说明|
|:--:|:--:|:----:|:---:|:--:|
|instance_id|String|是|N/A|虚拟机ID|
|session_id|String|是|N/A|有效的Token|
|method|String|否|N/A|请求的方法|
|proc_name|String|否|N/A|进程名称|

### 使用说明
{"method":611712,"data":{"instance_id":"6abf5a1e-b85c-4e5f-ba02-f96e22cbd02e;"}, "session_id": "768a07b5-2206-4952-b445-21162571a19a", "limit": 4, "proc_name": "vballoon"}

### 输出数据

#### 返回实例

<code>
{
   "status_code": 1, 
   "session_id": "768a07b5-2206-4952-b445-21162571a19a", 
   "message_id": "", 
   "message": "'success query proc information'", 
   "data": [
    "{u'net_incoming': 0.6, 
	  u'shutdown_time': None, 
	  u'mem': 0.0, u'net_outgoing': 5.7, 
	  u'cmd': u'vballoon', u'pid': 512, 
	  u'instance_id': u'6abf5a1e-b85c-4e5f-ba02-f96e22cbd02e', 
	  u'disk_write': 0.0, u'disk_read': 0.0, 
	  u'create_date': u'2017-01-01T21:37:58.871895', 
	  u'_id': ObjectId('58690636594c10403e25afea'),
	  u'cpu_util': 0.0, u'running_time': 1482236517.03
	 }", 
	 "{u'net_incoming': 0.5, 
	    u'shutdown_time': None, 
		u'mem': 0.0, u'net_outgoing': 5.6, 
		u'cmd': u'vballoon', u'pid': 512, 
		u'instance_id': u'6abf5a1e-b85c-4e5f-ba02-f96e22cbd02e', 
		u'disk_write': 0.0, u'disk_read': 0.0, 
		u'create_date': u'2017-01-01T20:37:56.853789', 
		u'_id': ObjectId('5868f824594c10403e25af89'),
		u'cpu_util': 0.0, u'running_time': 1482236517.03}", 
	 "{u'net_incoming': 0.5,
	   u'shutdown_time': None, u'mem': 0.0, 
	   u'net_outgoing': 5.6, u'cmd': u'vballoon', 
	   u'pid': 512, 
	   u'instance_id': u'6abf5a1e-b85c-4e5f-ba02-f96e22cbd02e', 
	   u'disk_write': 0.0, u'disk_read': 0.0, 
	   u'create_date': u'2017-01-01T19:37:55.258726', 
	   u'_id': ObjectId('5868ea13594c10403e25af29'), 
	   u'cpu_util': 0.0, u'running_time': 1482236517.03
	 }", 
	 "{u'net_incoming': 0.6, u'shutdown_time': None, 
	   u'mem': 0.0, u'net_outgoing': 5.7, 
	   u'cmd': u'vballoon', u'pid': 512, 
	   u'instance_id': u'6abf5a1e-b85c-4e5f-ba02-f96e22cbd02e', 
	   u'disk_write': 0.0, u'disk_read': 0.0, u'create_date': 
	   u'2017-01-01T18:37:53.736660', 
	   u'_id': ObjectId('5868dc01594c10403e25aec9'),
	   u'cpu_util': 0.0, u'running_time': 1482236517.03
	  }"
	], 
	"method": 611712
}

</code>

#### 数据说明

|名称|说明|
|:--:|:--:|
|net_incoming|下行流量|
|shutdown_time|进程关闭时间|
|net_outgoing|上行流量|
|cmd|进程名|
|disk_write|磁盘写速率|
|disk_read|磁盘读速率|
|create_date|记录上报时间|
|cpu_util|cpu使用率|
|running_time|进程开启时间|

#### 错误说明

## <a name="startmonitor">启动虚拟机 (startmonitor)</a>

> http://192.168.95.121:8086/wsgi_app.py

### 输入参数

|名称|类型|是否必须|默认值|说明|
|:--:|:--:|:----:|:---:|:--:|
|instance_id|String|是|N/A|虚拟机ID|
|session_id|String|是|N/A|有效的Token|
|method|String|否|N/A|请求的方法|

### 使用说明
{"method":32523,"data":{"instance_id":"6abf5a1e-b85c-4e5f-ba02-f96e22cbd02;"},"session_id":"9afdb1ec-d396-4ba3-af7a-1e38fd8751ca"}

### 输出数据

#### 返回实例

<code>
{
   "status_code": 1, 
   "session_id": "768a07b5-2206-4952-b445-21162571a19a", 
   "message_id": "", 
   "message": "''", 
   "data": null, 
   "method": 32523
}
</code>

#### 数据说明

|名称|说明|
|:--:|:--:|
|status_code|状态码（1.创建2.成功3.失败4.超时）|
|session_id|有效的Token|
|method|请求的方法|

#### 错误说明
