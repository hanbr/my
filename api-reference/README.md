# 恒泰艾普云平台应用接口说明 (API Reference)

本文以说明、解释恒泰艾普云平台应用接口为目的，相关的文档还包括：

[1] 关于文档中所涉及接口的调用方法，请参考[《恒泰艾普云平台应用接口的调用方法说明》](.api-quick-start.md)；

[2] 关于文档中所提及的数据结构，请参考[《恒泰艾普云平台应用接口的数据结构说明》](.api-data-structure/README.md)；

--

## 应用接口目录

1. [工具 (Utilities)](utilities/README.md)

	1.1 [验证码 (Captcha)](utilities/captcha.md)

	> 1.1.1 [获取短信验证码 (SMS Captcha)](utilities/captcha.md#captcha-sms)

	> 1.1.2 [获取邮件验证码 (Email Captcha)](utilities/captcha.md#captcha-email)

	> 1.1.3 [获取图形验证码链接 (Graphic Captcha link)](utilities/captcha.md#captcha-graphic-link)

	> 1.1.4 [获取图形验证码 (Graphic Captcha)](utilities/captcha.md#captcha-graphic)

	> 1.1.5 [校验图形验证码 (Graphic Captcha Verification)](utilities/captcha.md#captcha-graphic-verification)

2. [用户管理 (User Management)](user-management/README.md)

	2.1 [访问控制 (Access Control)](user-management/access-control.md)

	> 2.1.1 [注册 (Register)](user-management/access-control.md#register)

	> 2.1.2 [登录 (Login)](user-management/access-control.md#login)

	> 2.1.3 [重设密码 (Reset Password)](user-management/access-control.md#reset-password)

	2.2 [个人资料管理 (User Profile)](user-management/user-profile.md)
	
	> 2.2.1 [读取个人资料 (Read User Profile)](user-management/user-profile.md#read-user-profile)

	> 2.2.2 [更新个人资料 (Update User Profile)](user-management/user-profile.md#update-user-profile)

	> 2.2.3 [更新个人资料 - 单项 (Update User Profile - Single Item)](user-management/user-profile.md#update-user-profile-single)
	
	2.3 [用户管理 (Users)](user-management/users.md)
	
	> 2.3.1 [创建用户(Create User)](user-management/users.md#create-user)
	
	> 2.3.2 [更新用户资料(Update User)](user-management/users.md#update-user)
	
	> 2.3.3 [禁用用户(Disable User)](user-management/users.md#disable-user)

	> 2.3.4 [启用用户(Enable User)](user-management/users.md#enable-user)
	
	> 2.3.5 [查询用户(List Users)](user-management/users.md#list-users)
	
	> 2.3.6 [查询用户角色(List User Roles)](user-management/users.md#list-user-roles)
	
	> 2.3.7 [添加用户角色(Add User Role)](user-management/users.md#add-user-role)
	
	> 2.3.8 [删除用户角色(Delete User Role)](user-management/users.md#delete-user-role)
	
	> 2.3.9 [查询用户群组(List User Groups)](user-management/users.md#list-user-groups)
	
	> 2.3.10 [添加用户群组(Add User Group)](user-management/users.md#add-user-group)
		
	> 2.3.11 [删除用户群组(Delete User Group)](user-management/users.md#delete-user-group)
		
	2.4 [角色管理 (Roles)](user-management/roles.md)
	
	> 2.4.1 [创建角色(Create Role)](user-management/roles.md#create-role)
	
	> 2.4.2 [更新角色信息(Update Role)](user-management/roles.md#update-role)
	
	> 2.4.3 [禁用角色(Disable Role)](user-management/roles.md#disable-role)

	> 2.4.4 [启用角色(Enable Role)](user-management/roles.md#enable-role)
	
	> 2.4.5 [查询角色(List Roles)](user-management/roles.md#list-roles)

	> 2.4.6 [查询角色用户(List Role Users)](user-management/roles.md#list-role-users)
	
	> 2.4.7 [添加角色用户(Add Role User)](user-management/roles.md#add-role-user)
	
	> 2.4.8 [删除角色用户(Delete Role User)](user-management/roles.md#delete-role-user)

	2.5 [群组管理 (Groups)](user-management/groups.md)
	
	> 2.5.1 [创建群组(Create Group)](user-management/groups.md#create-group)

	> 2.5.2 [更新群组信息(Update Group)](user-management/groups.md#update-group)
	
	> 2.5.3 [禁用群组(Disable Group)](user-management/groups.md#disable-group)

	> 2.5.4 [启用群组(Enable Group)](user-management/groups.md#enable-group)
	
	> 2.5.5 [查询群组(List Groups)](user-management/groups.md#list-groups)

	> 2.5.6 [查询群组用户(List Group Users)](user-management/groups.md#list-group-users)
	
	> 2.5.7 [添加群组用户(Add Group User)](user-management/groups.md#add-group-user)
	
	> 2.5.8 [删除群组用户(Delete Group User)](user-management/groups.md#delete-group-user)
	
	2.6 [申请管理 (Request Management)](user-management/requests.md)
	
	> 2.6.1 [创建申请(Create Request)](user-management/requests.md#create-request)

	> 2.6.2 [更新申请(Update Request)](user-management/requests.md#update-request)
	
	> 2.6.3 [删除申请(Delete Request)](user-management/requests.md#delete-request)

	> 2.6.4 [取消申请(Cancel Request)](user-management/requests.md#cancel-request)
	
	> 2.6.5 [拒绝申请(Reject Request)](user-management/requests.md#reject-request)

	> 2.6.6 [批准申请(Approval Request)](user-management/requests.md#approval-request)
	
	> 2.6.7 [查询申请(List Requests)](user-management/requests.md#list-requests)
	
	> 2.6.8 [获取申请(Get Request)](user-management/requests.md#get-request)	
	
3. [云管理 (Cloud Management)](openstack/README.md)

	3.1 [云应用管理 (Application Management)](openstack/applications.md)
	
	> 3.1.1 [创建云应用 (Create Application)](openstack/applications.md#create-application)
	
	> 3.1.2 [更新云应用 (Update Application)](openstack/applications.md#update-application)
	
	> 3.1.3 [删除云应用 (Delete Application)](openstack/applications.md#delete-application)
	
	> 3.1.4 [禁用云应用 (Disable Application)](openstack/applications.md#disable-application)
	
	> 3.1.5 [启用云应用 (Enable Application)](openstack/applications.md#enable-application)

	> 3.1.6 [查询云应用 (List Applications)](openstack/applications.md#list-applications)
	
	> 3.1.7 [读取云应用 (Get Application)](openstack/applications.md#get-applications)

	> 3.1.8 [查询云应用用户 (List Application Users)](openstack/applications.md#list-application-usres)
	
	> 3.1.9 [添加云应用用户 (Add Application User)](openstack/applications.md#add-application-user)	

	> 3.1.10 [删除云应用用户 (Delete Application User)](openstack/applications.md#delete-application-user)

	3.2 [主机类型管理 (Flavor Management)](openstack/flavors.md)
	
	> 3.2.1 [创建主机类型 (Create Flavor)](openstack/flavors.md#create-flavor)
	
	> 3.2.2 [更新主机类型 (Update Flavor)](openstack/flavors.md#update-flavor)
	
	> 3.2.3 [删除主机类型 (Delete Flavor)](openstack/flavors.md#delete-flavor)
	
	> 3.2.6 [查询主机类型 (List Flavor)](openstack/flavors.md#list-flavor)
	
	> 3.2.7 [获得主机类型 (Get Flavor)](openstack/flavors.md#get-flavor)

	3.3 [镜像管理 (Image Management)](openstack/images.md)
	
	> 3.3.1 [创建镜像 (Create Image)](openstack/images.md#create-image)
	
	> 3.3.2 [更新镜像 (Update Image)](openstack/images.md#update-image)
	
	> 3.3.3 [删除镜像 (Delete Image)](openstack/images.md#delete-image)
	
	> 3.3.4 [查询镜像 (List Image)](openstack/images.md#list-image)
	
	> 3.3.5 [获得镜像 (Get Image)](openstack/images.md#get-image)
	
	3.4 [网络管理 (Network Management)](openstack/networks.md)
	
	> 3.4.1 [创建网络 (Create Network)](openstack/networks.md#create-network)
	
	> 3.4.2 [更新网络 (Update Network)](openstack/networks.md#update-network)
	
	> 3.4.3 [删除网络 (Delete Network)](openstack/networks.md#delete-network)
	
	> 3.4.6 [查询网络 (List Networks)](openstack/networks.md#list-networks)
	
	> 3.4.7 [获得网络 (Get Network)](openstack/networks.md#get-network)

	> 3.4.8 [创建子网络 (Create Sub Network)](openstack/networks.md#create-sub-network)
	
	> 3.4.9 [更新子网络 (Update Sub Network)](openstack/networks.md#update-sub-network)
	
	> 3.4.10 [删除子网络 (Delete Sub Network)](openstack/networks.md#delete-sub-network)	
	
	> 3.4.11 [查询子网络 (List Sub Networks)](openstack/networks.md#list-sub-networks)
	
	> 3.4.12 [获得子网络 (Get Sub Network)](openstack/networks.md#get-sub-network)
	
	> 3.4.13 [创建路由器 (Create Router)](openstack/networks.md#create-router)
	
	> 3.4.14 [更新路由器 (Update Router)](openstack/networks.md#update-router)
	
	> 3.4.15 [删除路由器 (Delete Router)](openstack/networks.md#delete-router)
	
	> 3.4.16 [设置路由器WAN端口 (Set Router Port)](openstack/networks.md#set-router-port)
	
	> 3.4.17 [添加路由器子网 (Add Router Network)](openstack/networks.md#add-router-network)
	
	> 3.4.18 [查询路由器 (List Routers)](openstack/networks.md#list-routers)
	
	> 3.4.19 [获得路由器 (Get Router)](openstack/networks.md#get-router)
	
	> 3.4.20 [创建浮动IP (Create Floating IP)](openstack/networks.md#create-floating-ip)
	
	> 3.4.21 [删除浮动IP (Delete Floating IP)](openstack/networks.md#delete-floating-ip)
	
	> 3.4.22 [查询浮动IP (List Floating IP)](openstack/networks.md#list-floating-ip)

	3.5 [云磁盘管理 (Cloud Disk Management)](openstack/volumes.md)
	
	> 3.5.1 [创建云磁盘 (Create Cloud Disk)](openstack/volumes.md#create-cloud-disk)
	
	> 3.5.2 [更新云磁盘信息 (Update Cloud Disk)](openstack/volumes.md#update-cloud-disk)
	
	> 3.5.3 [删除云磁盘 (Delete Cloud Disk)](openstack/volumes.md#delete-cloud-disk)
	
	> 3.5.6 [查询云磁盘 (List Cloud Disks)](openstack/volumes.md#list-cloud-disks)

	> 3.5.6 [获取云磁盘 (Get Cloud Disk)](openstack/volumes.md#get-cloud-disk)
	
	> 3.5.7 [查询云磁盘状态 (Get Cloud Disk Status)](openstack/volumes.md#get-cloud-disk-status)

	3.6 [主机管理 (Server Management)](openstack/servers.md)
	
	> 3.6.1 [创建主机 (Create Server)](openstack/servers.md#create-server)
	
	> 3.6.2 [更新主机信息 (Update Server)](openstack/servers.md#update-server)
	
	> 3.6.3 [删除主机 (Delete Server)](openstack/servers.md#delete-server)

	> 3.6.4 [关闭主机 (Shutdown Server)](openstack/servers.md#shutdown-server)
	
	> 3.6.5 [重启主机 (Resstart Server)](openstack/servers.md#restart-server)
	
	> 3.6.6 [查询主机 (List Servers)](openstack/servers.md#list-servers)
	
	> 3.6.7 [获得主机 (Get Server)](openstack/servers.md#get-server)
	
	> 3.6.8 [查询云磁盘 (List Cloud Disks)](openstack/servers.md#list-cloud-disks)
	
	> 3.6.9 [挂接云磁盘 (Mount Cloud Disk)](openstack/servers.md#mount-cloud-disk)
	
	> 3.6.10 [断开云磁盘 (Unmount Cloud Disk)](openstack/servers.md#unmount-cloud-disk)
	
	> 3.6.11 [创建连接会话 (Open Connection)](openstack/servers.md#open-connection)