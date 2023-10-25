# serv00-vless [注册serv00](https://www.serv00.com/)

## 使用方法：

1. 在WWW Websites处将原来的php删除（注意Delete DNS zone if it exists不要勾选），然后新建一个nodejs（域名填入原来php分配的域名）

2. 在Port reservation处，随机开通一个tcp端口,然后再开通另一个tcp端口(随机分配端口+1)

3. 在index.js中修改UUID和端口（改为上面提到的所创建的第二个端口号）

4. 把文件上传到分配的域名的文件夹内

5. 在 ssh 中进入文件所在的文件夹，输入以下命令：

 `cd domains/XXXX你的域名 `

6. 安装依赖项

 `npm install -r package.json `

7.在终端中执行以下命令以创建一个新的 screen 会话：

 `screen -S mysession `

8. 在 screen 会话中，运行应用程序：

 `node index.js `

9.按下 Ctrl + A，然后按下 D 键将 screen 会话分离,即可关闭终端保活。

10. 下次需要重新连接到 screen 会话时，可以使用以下命令：
 `screen -r mysession `

***建议去CF设回源；其中XXXXX，换成你自己的。***
--------------------------------------------------------------
查看进程
 `top `
退出top
 `Ctrl + C `
结束pid为xxxx的进程
 `kill -9 xxxx `
清除缓存
 `npm cache clean --force `
