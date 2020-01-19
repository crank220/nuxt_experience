## pm2

### windows
> pm2 delete wx233book

> cd C:\wwwroot\book_233_com

> pm2 start --watch -n wx233book ./node_modules/nuxt/bin/nuxt.js -- start

### mac
> pm2 start npm --name "bookstore-render" -- run start

### other
npm run build
pm2 start ./node_modules/nuxt/bin/nuxt-start

### defin
> pm2是一个进程管理工具,可以用它来管理你的node进程，并查看node进程的状态，当然也支持性能监控，进程守护，负载均衡等功能

### command
1. pm2需要全局安装 npm install -g pm2

2. 进入项目根目录 cd

3. 启动进程/应用 pm2 start bin/www 或 pm2 start app.js

4. 重命名进程/应用 pm2 start app.js --name wb123

5. 添加进程/应用 watch pm2 start bin/www --watch

6. 结束进程/应用 pm2 stop www

7. 结束所有进程/应用 pm2 stop all

8. 删除进程/应用 pm2 delete www

9. 删除所有进程/应用 pm2 delete all

10. 列出所有进程/应用 pm2 list

11. 查看某个进程/应用具体情况 pm2 describe www

12. 查看进程/应用的资源消耗情况 pm2 monit

13. 查看pm2的日志 pm2 logs

14. 若要查看某个进程/应用的日志,使用 pm2 logs www

15. 重新启动进程/应用 pm2 restart www

16. 重新启动所有进程/应用 pm2 restart all
