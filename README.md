# serv00-vless [注册serv00](https://www.serv00.com/)
## 使用方法：

1. 在WWW Websites处将原来的php删除（注意Delete DNS zone if it exists不要勾选），然后新建一个nodejs（域名填入原来php分配的域名）

2. 在Port reservation处，随机开通一个tcp端口,然后再开通另一个tcp端口(随机分配端口+1)

3. 在app.js中修改UUID和端口（改为上面提到的所创建的第二个端口号）

4. 把文件上传到迷个文件夹 public-nodejs

5. 在 ssh 中进入30行文件所在的文件夹，输入以下命令：

   `cd /usr/home/XXXXX/domains/XXXXX.serv00.net/public_nodejs`

6. 运行 npm install 来安装依赖项

7. 运行 npm start 启动您的 Node.js 应用程序。

8. 在WWW Websites处的Manage处，点击重启restart。

***建议去CF设回源；其中的两处XXXXX，换成你自己的。***

## 关闭命令窗口保持运行方法：

<font color="red">如果关闭命令窗口任然保持运行，可忽略以下方法。</font>

1. 使用 screen 命令：
    ```
   ​	①在终端中执行以下命令以创建一个新的 screen 会话：
   ```
   screen -S mysession
   ```
      ②定位到public_nodejs所在目录（XXXXX为用户名）输入以下命令：
    ```
   `cd /usr/home/XXXXX/domains/XXXXX.serv00.net/public_nodejs`
    ```
   ​	③在 screen 会话中，运行应用程序：
   ```
   node app.js
   ```
   ​	④按下 Ctrl + A，然后按下 D 键将 screen 会话分离。
    ```
   ​	⑤关闭终端窗口后，应用程序将继续在后台运行。下次需要重新连接到 screen 会话时，可以使用以下命令：
   ```
   screen -r mysession
   ```

3. 使用 tmux 命令：

   ​	①首先，确保已安装 tmux（如果尚未安装）：

   ```
   	sudo apt-get update
   	sudo apt-get install tmux
   ```

   ​	②然后，在终端中执行以下命令以创建一个新的 tmux 会话：
   ​	

   ```
   tmux new-session -s mysession
   ```

   ​	③在 tmux 会话中，运行应用程序
   ​	

   ```
   node app.js
   ```

   ​	④按下 Ctrl + B，然后按下 D 键将 tmux 会话分离。
   ​	⑤关闭终端窗口后，应用程序将继续在后台运行。下次需要重新连接到 tmux 会话时，可以使用以下命令：

   ```
   	tmux attach -t mysession
   ```
