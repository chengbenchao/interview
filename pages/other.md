##### 1、mongodb基本指令

```
mongo     								          进入mongodb命令行	
show dbs    							            显示数据库列表
use dbname    							          切换/创建dbname数据库，大小写敏感
show collections    					            显示数据库中的集合
db.createCollection(‘users’)    		            创建users集合
db.users.drop()或db.runCommand({"drop","users"})    删除集合
usersdb.runCommand({"dropDatabase": 1})    	     删除当前数据库
db.users.save({"name":"lecaf"})      	           创建了名为users的集合，并新增了一条{"name":"lecaf"}的数据
db.users.insert({"name":"ghost", "age":10})         在users集合中插入一条新数据，，如果没有users这个集合，mongodb会自动创建
db.users.remove()                                   删除users集合下所有数据
db.users.remove({"name": "lecaf"})                  删除users集合下name=lecaf的数据
db.users.find()                                     查找users集合中所有数据
db.users.find({“name”:”feng”})                      查找users集合中name=feng的所有数据
db.users.findOne()                                  查找users集合中的第一条数据
db.users.find({“name”:”feng”})                      查找users集合中name=feng的数据集合中的第一条数据

```

##### 2、yarn、npm、cnpm区别

```
cnpm是npm在国内的复制，很多功能不能实现
yarn是类似于npm 的另一款软件，目的在于解决npm由于语义版本控制而导致的npm安装的不确定性问题

```

##### 3、typescript什么叫接口

```
除了可用于对类的一部分行为进行抽象以外，也常用于对「对象的形状（Shape）」进行描述。 

```

##### 4、css预处理技术

```
1. Sass（SCSS）
2. LESS
3. Stylus
4. Turbine
5. Swithch CSS
6. CSS Cacheer
7. DT CSS

```

##### 5、git切换、合并分支  （git merge和git rebase区别）

```
checkout: 切换分支
marge   ：自动创建一个新的commit 
rebase	：会合并之前的commit历史 
如果你想要一个干净的，没有merge commit的线性历史树，那么你应该选择git rebase
如果你想保留完整的历史记录，并且想要避免重写commit history的风险，你应该选择使用git merge

```

##### 6、webpack的核心概念

```
一切文件如：JavaScript 、CSS 、 SASS 、 IMG/PNG等，在 Webpack 眼中都是一个个模块，通过对 Webpack 进行配置，对模块进行组合和打包。经过 Webpack 的处理，最终会输出浏览器能使用的静态资源。

```

##### 7、.gitignore文件的作用

```
在里面写的文件名，不会包含在Git上传的文件里

```

##### 8、什么是jdk、sdk、npm

```
jdk：针对Java开发人员发布的免费软件开发工具包 
sdk：可用于开发面向特定平台的软件应用程序的工具包 
npm：node包管理器，主要功能就是管理node包，包括：安装、卸载、更新、查看、搜索、发布等 

```

##### 9、使用过的接口管理平台有哪些

```
YApi、EasyAPI、Postman、CrapApi、Swagger

```

##### 10、跨平台方案

```
国内：
	weex			阿里				vue
	taro			京东				react
	hippy		   腾讯				vue/react
国外：
	react-native	   facebook		    react
	flutter			google			  dart
	ionic			  几个屌丝写的		 angular/react/vue
```

﻿