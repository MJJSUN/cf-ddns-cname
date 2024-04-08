### 主要使用场景：
通过Cloudflare API实现DDNS更新中国大陆转发IP。一些中转商家提供的域名在境内会被dns污染，直接cname的话会将错误IP一同解析，  
所以可以部署此脚本在境外服务器定时检测域名解析的变化。
- 2024年观察发现自己的域名会连带污染，感觉没啥用了放在这里存个档。

### 用法
```
wget https://github.com/MJJSUN/cf-ddns-cname/blob/main/cf-ddns-cname.sh && chmod +x cf-ddns-cname.sh
```
修改API信息和目标域名 
```
nano cf-ddns-cname.sh
```
然后设置定时任务
```
crontab -e
```
每分钟执行(按需要自行修改)
```
*/1 * * * * /path to script/cf-ddns-cname.sh >/dev/null 2>&1
```
带log的写法
```
*/1 * * * * /path to script/cf-ddns-cname.sh >> /var/log/cf-ddns.log 2>&1
```

### 参考项目
[teIegraph/cloudflare-api-v4-ddns](https://github.com/teIegraph/cloudflare-api-v4-ddns/blob/master/new-cloudflare.sh)
