# 1.提取最外层()里的内容：
	var data_regx = /(?<=\().*(?=\))/;   "((need))"
	text.match(data_regx)[0]
## 1.2 提取最前边的一组（）
	/(?<=\().*?(?=\))/;  "(need)(not)"
	宽断言	
	(?=exp)	匹配exp前面的位置
	(?<=exp)	匹配exp后面的位置
	(?!exp)	匹配后面跟的不是exp的位置
	(?<!exp)	匹配前面不是exp的位置
# 2.mysql中Unicode "\" 被过滤问题：
	
	
# 3、[node解析yaml ](https://blog.csdn.net/lym152898/article/details/78278947)

# 4、[axios](https://github.com/axios/axios)

# 5： 提取最外层()
	var data_regx = /(?<=\().*(?=\))/;
	/(?<=\().*(?=\))/
# 6、python中sql % 模糊查询
```
"SELECT fileid 
	FROM files 
	WHERE description LIKE '%%%s%%' 
		OR filename LIKE '%%%s%%' 
		OR uploader LIKE '%%%s%%' 
		ORDER BY fileid DESC" % (search, search, search)  
```		
# 7、资料 银河统计室

# 8、text转DOM元素
```javascript
try //Firefox, Mozilla, Opera, etc.
            {
                parser=new DOMParser();
                xmlDoc=parser.parseFromString(txt,"text/xml");
             //alert('FMO');
                return(xmlDoc);
            }
```
# 9、[好书贴](http://bestcbooks.com/B008AK5YJO/)

# 田要自己耕， 儿要自己养；

# 要想小儿安， 三分饥与寒；

# [python linux安装](https://blog.csdn.net/lovefengruoqing/article/details/79284573)
wget https://www.python.org/ftp/python/2.7.13/Python-2.7.13.tar.xz
####解压
xz -d Python-3.6.4.tar.xz
tar -xf Python-3.6.4.tar

unzip xxx.zip -d /aim

##### 压缩
	压c：tar -zcvf new.tzr.gz xxx.js xxx.py xxx
	解压x：到目标路径下 tar -zxvf path/new.tzr.gz
	

####进入解压后的目录，依次执行下面命令进行手动编译
./configure prefix=/usr/local/python3
make && make install


# 11 [MySQLdb ImportError: libmysqlclient.so.18解决方法](https://www.jb51.net/article/54120.htm)
[参考](https://www.cnblogs.com/python-life/articles/4626622.html)
>File "MySQLdb/__init__.py", line 19, in <module>
    import _mysql
  File "build/bdist.linux-x86_64/egg/_mysql.py", line 7, in <module>
  File "build/bdist.linux-x86_64/egg/_mysql.py", line 6, in __bootstrap__
ImportError: libmysqlclient.so.18: cannot open shared object file: No such file or directory
根据最后提示，应该是找不着一个叫：libmysqlclient.so.18的文件，于是到mysql安装目录里找到这个文件并且做一个软连接到/usr/lib
复制代码 代码如下:

ln -s /usr/local/mysql/lib/libmysqlclient.so.18 /usr/lib/libmysqlclient.so.18

如果是64系统则：
复制代码 代码如下:

ln -s /usr/local/mysql/lib/libmysqlclient.so.18 /usr/lib64/libmysqlclient.so.18

# 12 [Npp使用教程](http://ju.outofmemory.cn/entry/337149)
	[个性化Notepad++](https://www.cnblogs.com/coding-my-life/p/3676665.html)
	
# 13 [Node.js中常用的异常处理方式](https://segmentfault.com/a/1190000009651765)
	[Node异常处理 和守护进程](https://www.cnblogs.com/cnxkey/articles/7442203.html)
	
# 14 [node内存溢出解决](https://blog.csdn.net/allan_shore_ma/article/details/78434698)

# 15 [npm之 ](https://www.npmjs.com/search?q=redux&ranking=quality)
optimal 		最佳
popularity		流行
quality			质量
maintenance		维护频率

# 16 [chrome 扩展集](https://blog.csdn.net/lgd_guangdong/article/details/80062649)

# 17 [实用软件集合](https://blog.csdn.net/qq_35318273/article/details/80302118)

# 18 回调函数传参
```javascript
function fn (yourArgs){
    console.log("===", yourArgs)
 return (heArg) => {
     console.log(heArg)
     return heArg
 }
}
```

# 19 [nodejs mysql交互](https://zhidao.baidu.com/question/811790948480479452.html)
```javascript
// 实现与MySQL交互
var mysql = require('mysql');
var $conf = require('../cfg/cfg');
// var $util = require('../util/util');
var $sql = require('./articleSql');
 
// 使用连接池，提升性能
// var pool  = mysql.createPool($util.extend({}, $conf.mysql));
var pool  = mysql.createPool($conf.mysql);
 
 
 
module.exports = {
  add: function (req, res, next,data,fn) {
    pool.getConnection(function(err, connection) {
      // 'INSERT INTO user(id, name, age) VALUES(0,?,?)',
      connection.query($sql.insert, data, function(err, result) {
        // 以json形式，把操作结果返回给前台页面
        if(err)console.log(err);
         
        if(fn)fn(req,res,next);
        // 释放连接 
        connection.release();
      });
    });
  }
  })
 };
  
 //cfg.js
 module.exports = {
    mysql : {
        host : '127.0.0.1',
        user : 'root',
        password : 'root',
        database : 'test',
        port : 3306
    }
};
 
//各个第三方都不一样吧。
```

# 20 [nodejs获取函数名称操作](https://www.cnblogs.com/huizong/p/6068677.html)

# 21 [module.exports与exports，export与export default之间的关系和区别](https://www.cnblogs.com/fayin/p/6831071.html)

# 22 [定时任务Corn表达式](https://blog.csdn.net/fanrenxiang/article/details/80361582)

# 23 [Nodejs发邮件](https://blog.csdn.net/newborn2012/article/details/19116939)

	中文 Settings->Startup->Environment 添加 记得上行尾加;
		set LANG=zh_CN.UTF-8;
		set LC_ALL=zh_CN.utf8

	cmder的快捷键和浏览器的很相近，如果要用爽cmder一定记住常用快捷键
	双击Tab, 可以路径补全
	可以用Ctrl+T新建Tab页
	利用Ctrl-W关闭当前Tab页
	使用Ctrl-n来切换到第n个Tab页
	Alt+Enter切换到全屏
	Alt+Shift+n开启你的settings->Tab下的terminals
	Ctrl-r反向搜索历史命令
	Win+Alt+p打开设置窗口
	Ctrl-u 删除文字到行首
	Ctrl-A 移动光标到行首
	Ctrl-E 移动光标到行尾	
	
	解决文字重叠问题
	Win + Ait + P 唤出设置界面 > mian > font > monospce 的勾勾去掉(点两下)
	"ctrl + shift + e"水平分屏；
	按住"ctrl + shift + o"垂直分屏
	
# 24 [Node内存治理](https://segmentfault.com/a/1190000004934938)
	node --max-nex-space-size=1024 app.js // 单位为KB
	node --max-old-space-size=2000 app.js // 单位为MB
	node --max-nex-space-size=1024 --max-old-space-size=4335 app.js // 单位为KB
	node --max-old-space-size=2000 app.js // 单位为MB
	
# 25 [python2 与 python3]
	py -2 pip2  
	py -3 pip3
	
# 26 [bpython安装](http://www.bubuko.com/infodetail-2274259.html)
	启动 bpython-curses
	
	
# 27 如何销毁node的let const定义的变量
	pass
	
# 28 puppeteer修改元素样式
	await page.evaluate(bid_btn => {
                bid_btn.style.display = 'block';
                bid_btn.parentElement.style.display = "block";
                }, bid_btn).catch(e=>e.message);
	
# 29 [关于dataset()方法](https://blog.csdn.net/jx950915/article/details/78931509)
	//data-前缀属性可以在JS中通过dataset取值，更加方便
console.log(getId.dataset.id);//112
//data-vice-id连接取值使用驼峰命名法取值 
console.log(getId.dataset.viceId);//11

//赋值
getId.dataset.id = "113";//113
getId.dataset.viceId--;//10

//新增data属性
getId.dataset.id2 = "100";//100

//删除，设置成null，或者delete
getId.dataset.id2 = null;//null
delete getId.dataset.id2;//undefind

# 30 [npm使用命令](https://blog.csdn.net/houyanhua1/article/details/79439726/)

//npm install md5-node  //安装第三方模块包
//npm install md5-node --save  或者  npm install md5-node --save-dev  //注意：以后安装模块的时候我们要把这个模块写入到package.json这个配置文件
//npm install md5-node --save       写入到package.json 里面的  dependencies
//npm install md5-node --save-dev   写入到package.json 里面的  devDependencies
 
//npm install  表示安装package.json 里面的依赖（先进入项目目录）
//有时候的话 npm install 模块    下载不下来  或者很慢
//安装淘宝镜像 cmd----npm install -g cnpm --registry=https://registry.npm.taobao.org
//如果安装完成淘宝镜像就可以用 cnpm命令安装
//npm install 模块名  ==>  cnpm install 模块名     （先进入项目目录


# 31[cat 操作](https://blog.csdn.net/weixin_41585557/article/details/81252763)

# 32 Gtk-WARNING **: cannot open display: :0解决方法
通常是因为程序运行需要图形化界面导致
## 1不打开图形化界面：
	例如 puppeteer设置了headless为false 所致， 设置为headless:true（不打开图形化界面即可）
## 2， 申请root权限打开图形化界面， 或者在VNC桌面下打开
	Xserver默认情况下不允许别的用户的图形程序的图形显示在当前屏幕上

所以解决方法是：命令行退出root后，[用当前账户执行命令](https://blog.csdn.net/iceprincess_1968/article/details/79941540)

> xhost +

xhost + 是使所有用户都能访问Xserver 
xhost + ip 是使所有ip用户都能访问Xserver

执行完以后再在命令行内登录root，就能用eog打开图片了

# 33 [m3u8文件解析](https://blog.csdn.net/Ronadlo7/article/details/81029229)
----
MPEG-1音频标准定义了三种不同的压缩层次，即MPEG Audio Layer-1、MPEG Audio Layer-2、MPEG Audio Layer-3，分别简称MP1、MP2和MP3。层次越高压缩性能越好，但是编码的开销和译码的复杂度也随之增加。MP2均衡了性能和复杂度，它能在192～256Kbps的速率下实现CD级的音质。
MPEG音频文件——.MP1/.MP2/.MP3
MPEG是运动图像专家组(Moving Picture Experts Group)的英文缩写，代表MPEG运动图像压缩标准，这里的音频文件格式指的是MPEG标准中的音频部分，即MPEG音频层(MPEG Audio Layer)。MPEG音频文件的压缩是一种有损压缩，根据压缩质量和编码复杂程度的不同可分为三层(MPEG Audio Layer 1/2/3)，分别对应MP1、MP2和MP3这三种声音文件。MPEG音频编码具有很高的压缩率，MP1和MP2的压缩率分别为4∶1和6∶1～8∶1，而MP3的压缩率则高达10∶1～12∶1，也就是说一分钟CD音质的音乐，未经压缩需要10MB存储空间，而经过MP3压缩编码后只有1MB左右，同时其音质基本保持不失真，因此，目前使用最多的是MP3文件格式。
-------
 动态影像专家压缩标准音频层面3  MEPG3
Moving Picture Experts Group Audio Layer III  -- mp3
M3U（Moving Picture Experts Group Audio Layer 3 Uniform Resource Locator）这种文件格式，本质上说不是音频文件，它并不能在脱机模式下读取网络资源音频，它是音频文件的列表文件，是纯文本文件。
M3U8文件是指UTF-8编码格式的M3U文件。M3U文件是记录了一个索引纯文本文件，打开它时播放软件并不是播放它，而是根据它的索引找到对应的音视频文件的网络地址进行在线播放。


# 34 Solr安装
 [下载 solr](https://mirrors.tuna.tsinghua.edu.cn/apache/lucene/solr/7.5.0/)
 
## 1、启动与停止
> 直接到解压缩的solr/bin目录运行solr start即可。
会看到：
> Provider chain: env;sysprop
Waiting up to 30 to see Solr running on port 8983
Started Solr server on port 8983. Happy searching!
然后浏览器访问： http://localhost:8983
## 1.2启动多个  
> solr start -p 8084  
 solr start -p 8085
## 1.3停止指定  
 solr stop -p 8083  
 solr stop -p 8084  
### 1.4停止全部 solr stop -all  

## 2、搭建简单的solr  
 1、在 `D:\Program Files\solr-7.5.0\server\solr` 下创建文件夹 `test_core` 然后将 `D:\Program Files\solr-7.5.0\server\solr\configsets\_default` 下的文件复制过来  
 2、在http://localhost:8983 下 点击“ No cores available” 到 http://localhost:8983/solr/#/~cores  
 在Add Core对话框中的 `name`和`instanceDir` 两栏均填入刚才创建的文件夹名 如`test_core`  
 3、点击`Add Core` 按钮即可看到test_core 搭建成功  
 
 
# 35 zip(https://www.cnblogs.com/zdz8207/p/3765604.html)
zip -r xxx.zip ./*

tar cvf xxx.tar  /

# 36 puppeteer设置全屏截图
	await page.screenshot({ path: 'screen.png',fullPage: true,});
	
# 37 [pylint配置和使用](https://www.cnblogs.com/gaowengang/p/7892661.html)
[pylint在项目中的使用](https://www.cnblogs.com/zhangningyang/p/8652941.html)
	pylint --persistent=n --generate-rcfile > pylint.conf

# 38 flake8 配置和使用
	pip2 install flake8
	设置路径：File | Settings | Tools | External Tools
	
	Program: $PyInterpreterDirectory$/python    insert Macros 中选 PyInterpreterDirectory  或者 $JDKPath$
	Arguments: -m flake8 --show-source --statistics $FilePath$   
		insert Macros 中选 ProjectFileDir 表示运行flake8时检测整个项目， FilePath 表示检查当前文件
	Working directory: $ProjectFileDir$
	Output Filter: (留空就可以了, pycharm能自动识别路径.)
	
	当然可以设置快接键
	
	[配置扩展图等](https://baijiahao.baidu.com/s?id=1568428923336669&wfr=spider&for=pc)
	
	py -2 -m flake8 --show-source --statistics E:\projects\transcodeV2\transcode-master\ctrl\LocalTreeCtrl_te
xt.py | flake8chart --chart-type=BAR --chart-output=test——shadow.svg


# 39 [FFmpeg常用命令及参数](https://www.jianshu.com/p/11b6c4eb9e49)

# 40 [批处理获取绝对路径](https://jingyan.baidu.com/article/870c6fc32fba8fb03fe4beb8.html)
 @echo off & setlocal EnableDelayedExpansion

for /f "delims=" %%i in ('"dir /a/s/b/on tmp_ts\*.ts"') do (

set file=%%~fi

set file=!file:/=/!

echo file '!file!' >> filelist.txt

)

 tmp_ts\ 表示获取当前路径下 tmp_ts文件夹下的
 !file! 是文件的完整绝对路径
 
 evaluateOnNewDocument

 
# 41[博客园吧](https://www.cnblogs.com/cnsevennight/)


# 42 [软件关注](http://mai.apprcn.com)

# 43 SQL replace
例：把表table中的name字段中的aa替换为bb 
update table set name=replace(name,'aa','bb');


# 44 [win kill]
	D:\Program Files\cmder>netstat -ano | findstr "8082"
    TCP    0.0.0.0:8082           0.0.0.0:0              LISTENING       172204
	taskkill /f /t /im 172204
	
# 45 vncserver 重启
切换到 vncuser1
whoami 确认用户
vncserver

# 46 [正则集合](https://blog.csdn.net/angel_w/article/details/79787351)

# 47 [crontab](http://www.cnblogs.com/peida/archive/2013/01/08/2850483.html)
http://www.cnblogs.com/peida/archive/2013/01/08/2850483.html

# 48[talkPython] mxh~2019