# opensshupdate

自动升级openssl openssh，Centos7,openeuler使用 **update_c7.sh**  ; Ubuntu18,20,22使用 **update_ub.sh**  ; Kylin-Server-V10使用  **update_KV10.sh**  。自行先配置好yum源 apt源，把脚本文件放到 **/home/update** 下执行，可以提前将脚本3，4行对应版本的升级文件放到同目录下，省去下载的步骤。 Ubuntu下请先保证可用ssh连接服务器再升级。若升级完后出现ssh服务无法启动，将文件夹下ssh文件复制到/etc/init.d下重试，或者将/usr/lib/systemd/system/sshd.service里的Type=notify改成Type=simple后重试。PS：openssl官方把下载地址改成github后可能会经常下载失败，需要重复尝试。新版本OPENSSL编译时间有点长。。

以Ubuntu22为例操作:

cd /home/update

wget https://gitee.com/darkcp/opensshupdate/raw/master/ubuntu/update_ub.sh --no-check-certificate

chmod +x update_ub.sh

./update_ub.sh