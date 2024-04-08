### 主要使用场景：
同步中国大陆转发IP。一些中转商家提供的域名在境内会被dns污染，直接cname的话会将错误IP一同解析，  
所以可以部署此脚本在境外服务器定时检测域名解析的变化。
- 2024年观察发现自己的域名会连带污染，感觉没啥用了放在这里存个档。

### 用法
```
wget https://github.com/MJJSUN/cf-ddns-cname/blob/main/cf-ddns-cname.sh
```
修改API信息和目标域名
`crontab定时执行即可`
