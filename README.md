# Redis命令大全
## 导航

### [Strings](#Strings)
[get](#StringsGet) 
[set](#StringsSet) 
[del](#StringsDel)
### [Lists](#Lists)
[rpush](#ListsRPush) 
[lrange](#ListsLRange) 
[lindex](#ListsLIndex) 
[lpop](#ListsLPop)
### [Sets](#Sets)
[sadd](#Setssadd) 
[smembers](#Setssmembers) 
[sismember](#Setssismember) 
[srem ](#Setssrem)
### [Hashes](#Hashes)
[hset](#Hasheshset)
[hget](#Hasheshget)
[hgetall](#Hasheshgetall)
[hdel](#Hasheshdel)
### [Sorted sets](#SortedSets)
[zadd](#SortedSetszadd)
[zrange](#SortedSetszrange)
[zrangebyscore](#SortedSetszrangebyscore)
[szrem](#SortedSetszrem)
[zrevrank](#SortedSetszrevrank)
[zrevrange](#SortedSetszrevrange)

## <label id="Strings">字符串(Strings)</label>

* <label id="StringsGet">Get key-name</label>
获取存储在给定键中的值

* <label id="StringsSet">Set key-name</label>
获取存储在给定键中的值

* <label id="StringsDel">Del key-name</label>
删除存储在给定键中的值（适用于所有类型）

## <label id="Lists">列表(Lists)</label>

* <label id="ListsRPush">RPush list-key item</label>
将给定值推入列表的右端

* <label id="ListsLRange">LRange list-key start stop</label>
获取列表在给定范围上的所有值

* <label id="ListsLIndex">LIndex list-key index</label>
获取列表在给定位置上的单个元素

* <label id="ListsLPop">LPop list-key</label>
从列表的左端pop出一个值，并返回该值

## <label id="Sets">集合(Sets)</label>

* <label id="Setssadd">sadd set-key item</label>
将给定元素item添加到集合（返回0表示元素已存在于集合中，1表示添加成功）

* <label id="Setssmembers">smembers set-key</label>
返回集合中的所有元素

* <label id="Setssismember">sismember set-key item</label>
检查给定元素item是否存在于集合中

* <label id="Setssrem">srem set-key item</label>
如果item存在于集合中，移除该元素（返回移除元素的数量）

## <label id="Hashes">散列(Hashes)</label>

* <label id="Hasheshset">hset hash-key sub-key value</label>
在散列中设置给定的键值对

* <label id="Hasheshget">hget hash-key sub-key</label>
在散列中获取指定键的值
* <label id="Hasheshgetall">hgetall hash-key</label>
获取散列中所有的键值对
* <label id="Hasheshdel">hdel hash-key sub-key</label>
移除散列中的给定键（存在返回1，不存在返回0）

## <label id="SortedSets">有序集合(Sorted Sets)</label>

* <label id="SortedSetszadd">zadd zset-key score member</label>
将一个带有给定分值的成员添加到有序集合中

* <label id="SortedSetszrange">zrange zset-key start stop [withscores]</label>
根据元素在有序集合中所处的位置，从有序集合里面获取多个元素

* <label id="SortedSetszrangebyscore">zrangebyscore zset-key start stop [withscores]</label>
获取有序集合在给定分值范围内的所有元素

* <label id="SortedSetszrem">zrem zset-key member </label>
在有序集合中移除给定成员（存在返回1，不存在返回0）

* <label id="SortedSetszrevrank">zrevrank zset-key member </label>
返回有序集合成员 member的排名，成员按照分值从大到小排列

* <label id="SortedSetszrevrange">zrevrange zset-key start stop [withscores]</label>
返回有序集合给定排名范围内的成员，成员按照分值从大到小排列
