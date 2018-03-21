# restful接口约定

## 相关约定

1. 尽可能少使用动词,如`/getAllGoods,/createNewGoods`,***但是有一些行为需要使用动词,比如登录***
2. 使用名词的复数形式,如`/cars,/users,/goods`
3. 为关系使用子资源.
	
		GET /goods/711/price/ 返回商品id为711的价格列表
		GET /goods/711/price/4 返回商品id为711且价格id为4的信息

4. 版本化你的API.

		/api/v1		

5. 字段名使用小驼峰,如`goodsType,goodsTags`.
6. 字段名见名知义,如`goodsName,goodsPrice`.
7. 判断条件字段命名为is_xxx,如(is_yellow_vip).
8. 所有API请求和响应内的日期格式都为yyyy-MM-dd HH:mm:ss.
9. 返回的字段列表，字段之间用‘,’分割.

## 举例说明

1. 首先我们选择一个名词复数,比如商品

## get方法

1. 获取所有的XXX

 比如`...../goods` 代表获取所有的产品

因为分页,后面会加上queryBulid ?page=1&limit=50

约定: 所有的名词复数,都会返回`list`,且list每个对象都有字段为`id`的唯一id.

返回json

	{
		"status": "success",
    	"data": [
				{"id":"唯一id","其他很多字段":""},
				{"id":"唯一id","其他很多字段":""}
			],	
	}
2. 获取某个具体XXX

比如`……/goods/{id}`,代表获取某个具体商品

3. 某个具体的商品还包含一个list,如该商品推荐列表,则:

如`……/goods/{id}/recommendations`

4. 某个具体的商品包含的不是list,而是对象,如商品佣金信息,则:

如`……/goods/{id}/commission`

***这里判断名词复数判断是对象还是list***

## post 方法

新增一条XXX

比如	`..../goods`则代表新增一条商品

入参json:

	{
		"name":"名称",
	    "price":价格,
	    "pic":[一组图片],
	    等等还有很多
	}


## put 方法

新增某条XXX记录

比如` ……/goods/111111`

入参json:

	{
		"name":"名称",
	    "price":价格,
	    "pic":[一组图片],
	    等等还有很多
	}

表示增加一条 111111id的记录

## patch方法

更新局部XXX产品YYY信息

入参是post方法时入参的子集,所有支持更新的参数会说明，并不是支持所有变量

比如`……/goods/{id}`

	{
		"name":"商品名称",
	    "price":100,
	    部分变量
	}

## delete方法

删除XXX记录

删除1111产品