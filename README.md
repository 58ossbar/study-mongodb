# study-mongodb
mongodb入门到实战

# Mongodb是什么
　MongoDB并非芒果的意思，而是源于 Humongous（巨大）一词。中文叫盲狗db

MongoDB是面向文档的数据库，不是关系型数据库。它将原来**‘行’（row）的概念换成了更加灵活的‘文档’（document）模型**。面向文档的方式可以将文档和数组内嵌进来，所以用一条记录就可以表示很复杂的层次关系。 MongoDB没有模式，文档的键不会事先定义也不会固定不变。

Mongodb主要由文档（Document）、集合（Collection）、数据库（Database）三部分组成。

一个MongoDB实例，由多个数据库（Database）组成；一个数据库，由多个集合（Collection）组成；一个集合，又由多个文档组成。注意Mongodb单个文档大小上限为16MB，确保不会使用过多的内存RAM或在传输过程中占用过多的带宽。为了存储更大的文档，Mongodb提供了GridFS。
![开源吧](https://www.budaos.com/bds/uploads/cbeditor-image/2021-09-02/c0792515f214442bb1b9d910595998b9.png)

## 程序员注重对象，您的数据库也是。

MongoDB 是一个文档数据库，即在类似 JSON 的文档内存储数据。我们认为面对数据，这种方法非常自然，比传统的排/列模型更加直观和强大。

## 丰富的 JSON 文档

自然、高效的数据处理方法。

支持将数组和嵌套对象存储为值。

支持灵活、动态结构。

## 强大的查询语言

查询语言丰富和直观，支持通过任何字段进行筛选和排序，而不受其在文档内的嵌套方式影响。

支持聚合和其他现代使用案例，如基于地理的搜索、图搜索和文本搜索。

查询本身是 JSON 格式，因此很容易进行组合。无需串联字符串即可动态生成 SQL 查询。

## Mogodb特性

　MongoDB的3大技术特色如下所示：

除了上图所示的还支持：

二级索引、动态查询、全文搜索 、聚合框架、MapReduce、GridFS、地理位置索引、内存引擎 、地理分布等一系列的强大功能。

但是其也有些许的缺点，例如：

　多表关联： 仅仅支持Left Outer Join

　SQL 语句支持： 查询为主，部分支持

　多表原子事务： 不支持

　多文档原子事务：不支持

　16MB 文档大小限制，不支持中文排序 ，服务端 Javascript 性能欠佳
 
 ## 关系数据库与Mongodb区别
 
存储方式对比

在传统的关系型数据库中，存储方式是以表的形式存放，而在MongoDB中，以文档的形式存在。

 数据库中的对应关系，及存储形式的说明

MongoDB与SQL的结构对比详解

![开源吧](https://www.budaos.com/bds//uploads/cbeditor-image/2021-09-02/db4220a58b1648648daca3eea4d9a70b.png)

# MongoDB的安装和配置

## 安装前的准备

### 1.芒果数据库官网地址：https://www.mongodb.com/
备用下载链接：http://dl.mongodb.org/dl/win32/x86_64
### 2.选择合适的Mongodb社区版或企业版
下载可以选择 zip 格式或者 msi 格式，msi 格式就是下一步、下一步安装。我们讲解 zip格式。
### 3.解压缩这个文件夹，建议不要有中文路径

## 安装说明

### 1. 文件配置

进入解压后的文件夹，新建data和log文件夹，并在log文件夹下，新建mongod.log空文件

新建mongod.conf文件与bin文件夹同级

mongod.conf写入以下内容
![image](https://user-images.githubusercontent.com/110378589/194069719-e2f369a5-f2c7-4c27-b922-9ba7e2cdfd37.png)

注：dbpath和logpath根据自己的具体路径进行修改

### 2. 安装

特点注意：不同的操作系统

从bin文件夹下进入命令行执行,如果是windows7操作系统，不需要 加./

./mongod --config D:\mongodb-win32-x86_64-windows-5.0.11\mongod.conf--install --serviceName  mongodb

注：在cmd操作下执行一定要以管理员身份运行，否则可能造成安装失败

windows10以上操作系统，在开始---右键-----windows终端（管理员）运行，或开始---运行--cmd （ctrl+shift+Enter）调出

正常情况下执行后窗口没有任何反应，其实是正常在生成data下默认的几个数据库文件，可以查看是否已经在data目录下生成初始化文件。

### 3. 查看服务及启动服务 
启动/停止mongodb：
net start/stop mongodb



