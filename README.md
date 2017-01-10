# Redis命令大全
## 导航

### [Strings](#Strings)
> [Get](#StringsGet) 
[Set](#StringsSet) 
[Del](#StringsDel)
### [Lists](#Lists)
> [RPush](#ListsRPush) 
[LRange](#ListsLRange) 
[LIndex](#ListsLIndex) 
[LPop](#ListsLPop)
### [Sets](#Sets)
> [sadd](#Setssadd) 
[smembers](#Setssmembers) 
[sismember](#Setssismember) 
[srem ](#Setssrem)
### [Hashes](#Hashes)
> [hset](#Hasheshset)
[hget](#Hasheshget)
[hgetall](#Hasheshgetall)
[hdel](#Hasheshdel)
### [Sorted sets](#SortedSets)
> [zadd](#SortedSetszadd)
[zrange](#SortedSetszrange)
[zrangebyscore](#SortedSetszrangebyscore)
[szrem](#SortedSetszrem)
[zrevrank](#SortedSetszrevrank)
[zrevrange](#SortedSetszrevrange)

## 字符串(<label id="Strings">Strings</label>)

* <label id="StringsGet">Get</label> key-name
获取存储在给定键中的值

* <label id="StringsSet">Set</label> key-name
获取存储在给定键中的值

* <label id="StringsDel">Del</label> key-name
删除存储在给定键中的值（适用于所有类型）

## 列表(<label id="Lists">Lists</label>)

* <label id="ListsRPush">RPush</label> list-key item
将给定值推入列表的右端

* <label id="ListsLRange">LRange</label> list-key start stop
获取列表在给定范围上的所有值

* <label id="ListsLIndex">LIndex</label> list-key index
获取列表在给定位置上的单个元素

* <label id="ListsLPop">LPop</label> list-key
从列表的左端pop出一个值，并返回该值

## 集合(<label id="Sets">Sets</label>)

* <label id="Setssadd">sadd</label> set-key item
将给定元素item添加到集合（返回0表示元素已存在于集合中，1表示添加成功）

* <label id="Setssmembers">smembers</label> set-key
返回集合中的所有元素

* <label id="Setssismember">sismember</label> set-key item
检查给定元素item是否存在于集合中

* <label id="Setssrem">srem</label> set-key item
如果item存在于集合中，移除该元素（返回移除元素的数量）

## 散列(<label id="Hashes">Hashes</label>)

* <label id="Hasheshset">hset</label> hash-key sub-key value
在散列中设置给定的键值对

* <label id="Hasheshget">hget</label> hash-key sub-key
在散列中获取指定键的值
* <label id="Hasheshgetall">hgetall</label> hash-key
获取散列中所有的键值对
* <label id="Hasheshdel">hdel</label> hash-key sub-key
移除散列中的给定键（存在返回1，不存在返回0）

## 有序集合(<label id="SortedSets">Sorted Sets</label>)

* <label id="SortedSetszadd">zadd</label> zset-key score member
讲一个带有给定分值的成员添加到有序集合中

* <label id="SortedSetszrange">zrange</label> zset-key start stop [withscores]
根据元素在有序集合中所处的位置，从有序集合里面获取多个元素

* <label id="SortedSetszrangebyscore">zrangebyscore</label> zset-key start stop [withscores]
获取有序集合在给定分值范围内的所有元素

* <label id="SortedSetszrem">zrem</label> zset-key member 
在有序集合中移除给定成员（存在返回1，不存在返回0）

* <label id="SortedSetszrevrank">zrevrank</label> zset-key member 
返回有序集合成员 member的排名，成员按照分值从大到小排列

* <label id="SortedSetszrevrange">zrevrange</label> zset-key start stop [withscores]
返回有序集合给定排名范围内的成员，成员按照分值从大到小排列
