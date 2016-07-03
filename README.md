# mongo

background属性 高效修改/创建索引
在项目运行中，如果我们直接采用前面的方法创建索引或者修改索引，那么数据库会阻塞建立索引期间的所有请求。mongodb提供了background属性做后台处理。

> db.taobao_item.ensureIndex({"modified":1,"is_man_delisting":1},{background:true})

我们知道如果哦阻塞所有请求，建立索引就会很快，但是使用系统的用户就需要等待，影响了数据库的操作，因此可以更具具体情况来选择使用background属性