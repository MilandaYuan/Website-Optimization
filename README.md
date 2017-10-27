## 网站性能优化项目

### Part 1: 优化 index.html 的 PageSpeed Insights 得分

####运行步骤

1. 运行一个本地服务器nginx
   具体做法：
   step1、下载nginx
   step2、把下载的nginx.conf替换为代码库中的该文件
   step3、将nginx.conf中http的root修改为本地代码库中dist目录所在的绝对路径
   step4、双击nginx.exe以启动程序
2.给本地服务器一个公网地址，使其能够被远程访问
   具体做法：
   step1、下载ngrok
   step2、进入ngrok所下载的目录，执行命令：./ngrok http 8080
   step3、复制返回的公网地址到pagespeed，测试分数
####优化概述
1.在nginx服务器启用了gzip压缩功能
2.在nginx服务器设置了图片、js、css缓存功能
3.缩小了图片pizzeria.jpg的大小
4.使用html-minify、clean-css-cli、uglify-js分别压缩html、css、js文件
5.使用@font-face把web字体调整到style.css里
6.在两个link标签里，使用了媒体查询
7.在引用谷歌分析的script标签里，添加了asyc属性


###Part 2: 优化 pizza.html 的 FPS（每秒帧数）

1.简化了遍历披萨元素并改变宽度的过程
2.将造成强制同步布局的代码移除循环体