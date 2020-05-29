# document
---------------------------------------------------------------idea--------------------------------------------------------------

1：IDEA 打war包</br>
https://blog.csdn.net/qq_34872748/article/details/100390922</br>
2：idea中maven项目bulid时报错</br>
https://www.oschina.net/question/2410767_2138421</br>
3：idea 修改jsp文件不生效问题</br>
https://blog.csdn.net/lihefei_coder/article/details/86625324</br>
4：git clone下载速度很慢的解决方法</br>
https://blog.csdn.net/MENGHUANBEIKE/article/details/74001756?depth_1-utm_source=distribute.pc_relevant.none-task-blog-BlogCommendFromBaidu-1&utm_source=distribute.pc_relevant.none-task-blog-BlogCommendFromBaidu-1</br>
5：使用git将项目上传到github（最简单方法）</br>
https://www.cnblogs.com/cxk1995/p/5800196.html</br>
6：idea tomcat配置</br>
https://www.cnblogs.com/yayazi/p/7920257.html</br>
7：Intellij IDEA 部署Web项目，解决 404 错误</br>
https://blog.csdn.net/eaphyy/article/details/72513914</br>
8：IDEA git导入maven项目</br>
https://blog.csdn.net/liubin5620/article/details/80364634  </br>
9：idea登录github账户报错</br>
https://blog.csdn.net/qq_40202111/article/details/104828365  </br>
10：IDEA 不编译</br>
https://blog.csdn.net/baidu_38116275/article/details/79889936 </br>
11：IDEA部署项目到tomcat时artifact中没有项目</br>
https://jingyan.baidu.com/article/0aa2237511ba0088cc0d64de.html</br>
12：idea激活</br>
https://shimo.im/docs/WgCXhcrkWy8HVCVG</br>
14:idea maven 配置
https://www.cnblogs.com/Silencepeng/p/7444012.html
---------------------------------------------------------------linux--------------------------------------------------------------</br>
1：创建用户并授数据库权限等操作
//新建用户 admin 密码为123456</br>
create user admin identified by '123456';</br>
//查看用户权限</br>
show grants for admin;</br>
//创建数据库</br>
create database if not exists dbname;</br>
//给test数据库权限赋给admin用户</br>
GRANT SELECT, INSERT, UPDATE, DELETE, CREATE, DROP ON `test`.* TO 'admin'@'%'</br>
————————————————</br>
2：用具体ip登录mysql数据库
mysql -P 3306 -h ipname -u username -p
ipname 为具体的ip名称
username为具体的登录用户名称
3：备份数据库脚本
mysqldump -u root -p database >database.sql
4：防火墙添加3306端口
　firewall-cmd --zone=public --add-port=3306/tcp --permanent
  查看开放端口：
  firewall-cmd --zone=public --list-ports



---------------------------------------------------------------Nginx--------------------------------------------------------------</br>
 Nginx 实战应用</br>
https://www.jianshu.com/p/9fd8533638ad</br>

---------------------------------------------------------------REDIS--------------------------------------------------------------</br>
1:redis基本操作，基本命令
https://www.runoob.com/redis/redis-strings.html
2：redis服务器安装详细步骤
https://www.cnblogs.com/happywish/p/10944253.html


