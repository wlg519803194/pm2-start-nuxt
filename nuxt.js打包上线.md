### nuxt.js打包上线 ###

1.到local磁盘下

	cd /usr/local


2.安装nodejs

	
	wget https://nodejs.org/dist/v8.9.1/node-v8.9.1-linux-x64.tar.gz

3.解压


	tar -zxvf node-v8.9.1-linux-x64.tar.gz -C /usr/local

4.更换名字

	mv /usr/local/node-v8.9.1-linux-x64/ /usr/local/node8.9.1

5.软链接指向到node npm

	ln -s /usr/local/node8.9.1/bin/node  /usr/local/bin/node


	ln -s /usr/local/node8.9.1/bin/npm  /usr/local/bin/npm 

6.查看软链是否成功


	ls -al /usr/local/bin

7.安装vue


	npm install -g vue-cli


8.安装淘宝景象，因为在国内使用npm特别慢


	npm install -g cnpm --registry=https://registry.npm.taobao.org


9.cnpm 软链

	ln -s /usr/local/node8.9.1/bin/cnpm  /usr/local/bin/cnpm

10.安装pm2 node进程管理器


	cnpm install -g pm2 

11.建立软连接


	ln -s /usr/local/node8.9.1/bin/pm2  /usr/local/bin/pm2


12.切换到项目目录下，安装vue相关组件

	cnpm install


13.把nuxt自带的nuxt命令放到项目目录下


	ln -s 项目路径/node_modules/nuxt/bin/nuxt 项目路径/nuxt

14.nuxt服务端打包

	cnpm run build


15.使用pm2启动项目（线程保护型==后台启动）

	pm2 start cnpm --name "自定义名字" -- run start

16.关闭项目

	pm2 delete 0（这里可以是名字，也可以是ip）






> 'curl 线上ip + 端口 '可以测试是否能连接此地址


> 'netstat -aano' 可以查看某个端口是否启动


