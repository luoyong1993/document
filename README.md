# document
---------------------------------------------------------------idea--------------------------------------------------------------

1：IDEA 打war包</br>
https://blog.csdn.net/qq_34872748/article/details/100390922</br>
2：idea中maven项目bulid时报错</br>
https://www.oschina.net/question/2410767_2138421</br>
3：idea 修改jsp文件不生效问题</br>
https://www.cnblogs.com/yuchencui/p/10937789.html</br>
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
14:idea maven 配置</br>
https://www.cnblogs.com/Silencepeng/p/7444012.html</br>
15：idea 修改访问项目名称</br>
https://blog.csdn.net/weixin_30487317/article/details/98637320</br>
16：idea 修改打war包名称</br>
右键，rename 回车即可
17：ide常用插件
https://juejin.im/post/5eba9a5bf265da7bca50010c

</br>
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
3：备份数据库脚本</br>
mysqldump -u root -p database >database.sql</br>
4：防火墙添加3306端口</br>
　firewall-cmd --zone=public --add-port=3306/tcp --permanent</br>
  查看开放端口：</br>
  firewall-cmd --zone=public --list-ports</br>
  从新载入：</br>
  firewall-cmd --reload</br>
5:自己动手搭建Nexus(maven私服)</br>
https://www.jianshu.com/p/1cfbc1518fce</br>



---------------------------------------------------------------Nginx--------------------------------------------------------------</br>
 Nginx 实战应用</br>
https://www.jianshu.com/p/9fd8533638ad</br>

---------------------------------------------------------------REDIS--------------------------------------------------------------</br>
1:redis基本操作，基本命令</br>
https://www.runoob.com/redis/redis-strings.html</br>
2：redis服务器安装详细步骤</br>
https://www.cnblogs.com/happywish/p/10944253.html</br>

---------------------------------------------------------------GIT--------------------------------------------------------------</br>
1:git 用命令下载代码到本地</br>
https://blog.csdn.net/jxg1473819657/article/details/83656939</br>
2：github上拉取代码执行 npm install报错code：128</br>
https://www.cnblogs.com/minutes/p/11692474.html</br>
3：git拉取代码出现Unpacking objects
https://blog.csdn.net/weixin_39386145/article/details/88905238</br>

---------------------------------------------------------------MYSQL--------------------------------------------------------------</br>
1：根据日期范围显示该范围内的所有日期（统计场景用的多）
select a.assigned_date AS "bizDate",b.id,b.umid,b.gameName,b.logo
		FROM
		(
		select date_format(assigned_date,'%Y-%m-%d') assigned_date
		from
		(select adddate('2011-01-01',t3.i*1000 + t2.i*100 + t1.i*10 + t0.i) assigned_date
		from
		(select 0 i union select 1 union select 2 union select 3 union select 4 union select 5 union select 6 union select 7 union select 8 union select 9) t0,
		(select 0 i union select 1 union select 2 union select 3 union select 4 union select 5 union select 6 union select 7 union select 8 union select 9) t1,
		(select 0 i union select 1 union select 2 union select 3 union select 4 union select 5 union select 6 union select 7 union select 8 union select 9) t2,
		(select 0 i union select 1 union select 2 union select 3 union select 4 union select 5 union select 6 union select 7 union select 8 union select 9) t3
		) c
		where assigned_date between DATE_FORMAT(#{startDate}, '%Y-%m-%d') and DATE_FORMAT(#{endDate}, '%Y-%m-%d')
		)a
		cross join
		(
		select game.id AS "id",game.umid AS "umid",game.name AS "gameName",game.logo AS "logo" FROM ly_biz_game game

		<where>
			AND game.channel_type=#{channelType}
			AND game.del_flag=0
			<if test="gameName != null and gameName != ''">
				AND game.name LIKE
				<if test="dbName == 'oracle'">'%'||#{gameName}||'%'</if>
				<if test="dbName == 'mssql'">'%'+#{gameName}+'%'</if>
				<if test="dbName == 'mysql'">concat('%',#{gameName},'%')</if>
			</if>
		</where>
		)b
		ORDER BY a.assigned_date desc
