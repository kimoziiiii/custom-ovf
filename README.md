# 环境
1. Ubuntu22.04.3LTS
2. VMware
   
# 依赖
1. open-vm-tools  # 用于获取变量
```
vmtoolsd --cmd "info-get guestinfo.ovfEnv"
```

# 工具
1. ovftool
```
ovf /path/to/file.ovf /path/to/file.ova  # ovf转换成ova
ovf --noSSLVerify vi:/exsi_ip # 提示路径
ovf --noSSLVerify vi/exsi_ip/path/<vm_name> <output_directory>
```

# 整体流程

VMWare虚拟机配置vApp属性，开启vApp环境变量，使用VM Tools进行传输变量，使用rc.local获取VM Tools传输的变量，提取变量进行系统配置。


# 说明
目前只支持主机名和IP预定义，其他例如用户名已进行了标准化配置（密钥登录），CPU和内存默认1C2G，这个在虚拟机管理页面中自行修改。听说是可以预定义，就这样吧。