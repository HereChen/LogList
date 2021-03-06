# Linux

* `dig` 域名解析，可用于查看域名对应的 IP：`dig www.baidu.com`。
* `awk`
* 压缩: `zip -r myzip.zip ./*`
* 解压: `unzip myzip.zip -d myzip`
* 压缩: `tar -czvf xxx.tar.gz folder`
* 解压缩: `tar -xzvf xxx.tar.gz`
* 复制当前文件夹下所有文件: `cp -r * ../folder`
* 复制文件内内容: `xclip -sel c < file`
* 列出一级文件，并作排除：`tree -L 1 -I "draft|README.md"`

## Bash On Ubuntu On Windows 升级

1. 查看当前版本(Bash): `lsb_release -a`
2. 卸载(CMD): `lxrun /uninstall`
3. 安装(CMD): `lxrun /install`
4. 升级(Bash): `sudo do-release-upgrade`

## 运维

* 查看本机端口: `netstat -lntu`, `netstat -tulpn | grep LISTEN`.
* 查看是32位还是64位: `file /sbin/init`
* 查看端口是否可用: `nc -zv 127.0.0.1 80 8080`, `nc -z 127.0.0.1 8080`
* 查看进程: `ps -ef | grep tomcat_8103`, `ps aux | grep tomcat_8103`
* 杀进程: `kill -9 8111`
* rpm 包依赖检测: `rpm -qpR tcpdump-4.9.0-7.1.x86_64.rpm`
* docker 安装: `curl -sSL https://get.docker.com/ | sh`
* 查看当前系统 IP: `ifconfig -a`
* 安装 ifconfig(CentOS): `sudo yum install net-tools`
* SSH 登录, `.ssh` 下有多个 rsa 情况下用后者: `ssh root@host`, `ssh -o PubkeyAuthentication=no root@host`

## 禁止 ping 响应 (禁止 ICMP 协议响应)

```bash
sudo vim /etc/sysctl.conf

## disable
# net.ipv4.icmp_echo_ignore_all=1
## enable
# net.ipv4.icmp_echo_ignore_all=0

sudo sysctl -p
```
