# sphinx-jieba


$ cd sphinx-jieba
$ git submodule update --init --recursive
编译（假设安装到/usr/local/sphinx目录，下文同）
$ sudo apt install gcc cmake automake
$ sudo apt install libmysqld-dev
$ ./configure --prefix=/usr/local/sphinx-jieba
--prefix 指定安装路径
--with-mysql 编译mysql支持
--with-pgsql 编译pgsql支持
$ make
$ make install
配置中文支持
修改sphinx.conf索引配置文件
在索引配置项中添加以下两项：

charset_type = utf-8
chinese_dictionary = /usr/local/sphinx/etc/xdict
注意在source部分一定加上如下字段，否则中文分词无法起作用。

sql_query_pre = SET NAMES utf8
