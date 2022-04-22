EN | [CN](readme.md)


build and deploy your cloud hypervisor/desktop/disk with onekeystoke diskdumping(demo pics attached)
=====

onekeydevdesk is a system which embeds a "hypervisor engine+function engine achived transparent virtual/fuction enviroment and dev/deploy stack" as integrated basic Soc in its minmal core, then bundles multiple OSes/containers based around the core, plus scripts/uilities/managetools related，finally the composed implentmented OS towards the "all in one onekeystoke devdesk" theories.    

 * as the part of onekeydevdesk installation and build script, 1keydd can extends to multiple target models  and customiablity, can be self hosted and packaged into a repo even a "ddhub",for each of your target host/target image combination,for later dd restoring  
 * as the part of onekeydevdesk os-bundle core,based on pve,onekeydevdesk implements a transparent ve: it supports single integrated gpu switch freely between host/subos within a host,and "local experience of file sharing and syncing mechanism just as if they are hypermanager pervioned vms" arcoss mateable internet vps os and local vps os entries

> onekeydevdesk is also referred as：1keydd,1keydiskdump,1keydeepindsm,1keydebiandesk,1keydevdeploy,1keydebugdemo,1key desk dock,1key datacenter and desk,1key dir disk,etc ..

project repo url: https://github.com/minlearn/onekeydevdesk 

demo
-----

1keydd installation support dd progress bar inside debian installer（ demo video：https://www.bilibili.com/video/BV1ug411N7tn/ ）  
supports machine models including: [az](_pages/ddexpandcicustom/az/en/),[servarica](_pages/ddexpandcicustom/sr/en/),[oracle,oracle arm](_pages/ddexpandcicustom/orc/en/),[ksle](_pages/ddexpandcicustom/ks/en/),[bwg10g512m](_pages/ddexpandcicustom/bwglowres/en/)
![](_pages/intro/1keydd.png)

as one of onekeydevdesk's sub qemu vm OSes,the same windows image can be installed both on uefi/bios vps/bearmetal machines, without any difference and extra processing needed  
![](_pages/intro/1keydevdeskwin.png)

as one of onekeydevdesk's sub qemu vm OSes,dsm can be installed on vps, with no kvm-nested required upon host  
![](_pages/intro/1keydevdeskdsm.jpg)

as one of onekeydevdesk's sub qemu vm OSes,osx uses standard full set kvm virtio drivers and bios model， should be installed on a 2c2g vps with kvm-nested (with 1c1.5g/2c2g give to osx, with 2c2g/3c3g give to osx the best),win11 is also supported,cloudosx+cloudwin11=local matedesk  
![](_pages/intro/1keydevdeskosx.png)

as part of onekeydevdesk uilities,1keydirdisk supports netdisk in dir-listing manner just inside file explorer
![](_pages/intro/1keydirdisk.png)

getting-started
-----

below are tested under vnc of an Debian and Debian flow Linux vps or local host,centos not recommended  
for amd64,all commands below are avaliable,for arm64,limited command set are avaliable  

基本用法:  

 * 简单前端交互模式  
`wget -qO- 1keydd.com/inst.sh | bash`   

 * 安装其它目标os镜像：deb是纯净debian10,自定义镜像是你的raw系统硬盘格式经过gzip打包后托管的http/https地址  
`wget -qO- 1keydd.com/inst.sh | bash -s - -t deb或自定gz镜像`  

更多用法:  

 * 指定静态网络配置  
`wget -qO- 1keydd.com/inst.sh | bash -s - -n IPV4:youripv4,MASK:yourmask,GATE:yourgateway -t deb或自定gz镜像`  

 * 进入nc+dd模式：提供port:blkdevname参数形式将作为服务器接收端，提供blkdevname:ip:port参数形式将作为客户发送端  
`wget -qO- 1keydd.com/inst.sh | bash -s - -t port:blkdevname或blkdevname:ip:port`  

 * 进入救援模式,ip:5900 vnc访问，无须-t  
`wget -qO- 1keydd.com/inst.sh | bash -s - -d`  


安装后，/run/initramfs/usr/bin/growpart /dev/vda(sda) 2,resize2fs /dev/vda(sda) 2扩展磁盘空间,root密码1keydd，https://xxx:8006为pve口，pve用户名root密码1keydd，vnc客户端连接你机器的ip:8059，密码为1keydd，二个lxc box的端口情况在各自的summary页有写，默认密码都是root/1keydd，如果是云主机建议开放8000-8100这些端口  

onekeydevdesk lxc os镜像在pve的storage->ct templates页可找到，github或github，不做说明的情况下，qemu版osx和dsm镜像并不提供开放托管和安装。  

more docs and demos
-----

更多请看项目文档库[《更多特点介绍和自助安装使用文档》](_pages/docs/en/)部分和hub部分


服务
-----

免费
 * 只提供inst.sh，可一站式解决你DD中大部分问题，去上面仓库，一键DD即可  
`注：仅拥有inst.sh dd能力`  

收费  
 * 项目1：获取osx或win11的系统镜像和安装服务一次（100元,usdt 15）  
 * 项目2：加入付费dd群获取ci.sh脚本源码和1G资源享免费咨询技术支持1年（100元,usdt 15）  
 * 项目1+2：获取一份镜像并同时加入收费群获取源码ci.sh (150元,usdt 25)  
`注：拥有ci.sh扩展驱动/机型能力和自托管能力`  
`加如下作者个人TG：简单说明需求或说明来意即可`     

[minlearn_1keydd](https://t.me/minlearn_1keydd)

捐助
 * 打赏我虚拟币：TRX/USDT/BTC/ETH: [TZ6YPtsojLCJEifNpwm38mmiq7T2gkhGKj](https://trx.tokenview.com/cn/address/TZ6YPtsojLCJEifNpwm38mmiq7T2gkhGKj)    
`怎么捐助: 用支持tron链的钱包APP扫描下列二维码`  

![](_pages/intro/donate.png)

-----


此项目关联 https://github.com/minlearn/minlearnprogramming/tree/master/p/onekeydevdeskopen/ ，它是为配合我在《minlearnprogramming》最小编程/统一开发的想法的一个支持项目。  
本项目长期保存

![](_pages/intro/logo123zd15sz150.png)
