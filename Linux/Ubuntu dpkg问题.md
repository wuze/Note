# Ubuntu dpkg问题

*2017.7.23*


```

juntaran@ubuntu:~$ sudo apt-get install mongodb
[sudo] password for juntaran: 
E: Could not get lock /var/lib/dpkg/lock - open (11: Resource temporarily unavailable)
E: Unable to lock the administration directory (/var/lib/dpkg/), is another process using it?
juntaran@ubuntu:~$ sudo dpkg --configure -a
dpkg: error: dpkg status database is locked by another process

juntaran@ubuntu:~$ sudo rm /var/cache/apt/archives/lock
juntaran@ubuntu:~$ sudo rm /var/lib/dpkg/lock

juntaran@ubuntu:~$ sudo apt-get install mongodb
Reading package lists... Done
Building dependency tree       
Reading state information... Done

```

当 dpkg 被另一个进程锁定时，而且你确定并没有在另一个终端执行  

执行以下命令

``` bash
juntaran@ubuntu:~$ sudo rm /var/cache/apt/archives/lock
juntaran@ubuntu:~$ sudo rm /var/lib/dpkg/lock
```
