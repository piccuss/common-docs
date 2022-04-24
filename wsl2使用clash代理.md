# wsl2使用clash代理

1. clash启用allow-Lan
2. wsl2下，在~/.bashrc添加以下内容，配置代理
    
```   
export hostip=$(cat /etc/resolv.conf |grep -oP '(?<=nameserver\ ).*');
export https_proxy="http://${hostip}:7890";
export http_proxy="http://${hostip}:7890";
export all_proxy="socks5://${hostip}:7891";
```   
3. 使用source命令更新即可
