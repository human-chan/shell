#!/bin/env bash
#该脚本用于给多个服务器创建一个用户

while read ip pass
do

        /usr/bin/expect <<-END &>/dev/null
        spawn ssh root@$ip
        expect {
                "yes/no" {send "yes\r";exp_continue}
                "password:" {send "$pass\r"}
                }
        expect "#" {send "useradd hdhdhhd;exit\r"}
        expect eof
        END

#ip.txt文件须存有需要创建用户的服务器的ip以及对应的登录密码
done < /root/ip.txt
