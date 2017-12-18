# Redis命令大全

## 导航

### [Strings](#Strings)
   [get](#StringsGet) | [set](#StringsSet) | [del](#StringsDel) 
### [Lists](#Lists)
   [rpush](#ListsRPush) | [lrange](#ListsLRange) | [lindex](#ListsLIndex) | [lpop](#ListsLPop)
### [Sets](#Sets)
   [sadd](#Setssadd) | [smembers](#Setssmembers) | [sismember](#Setssismember) | [srem ](#Setssrem) | [SCARD ](#SetScard) 
### [Hashes](#Hashes)
   [hset](#Hasheshset) | [hget](#Hasheshget) | [hgetall](#Hasheshgetall) | [hdel](#Hasheshdel)
### [Sorted sets](#SortedSets)
   [zadd](#SortedSetszadd) | [zrange](#SortedSetszrange) | [zrangebyscore](#SortedSetszrangebyscore) |
   [szrem](#SortedSetszrem) | [zrevrank](#SortedSetszrevrank) | [zrevrange](#SortedSetszrevrange) 
### [Other Commands](#OtherCommands)
[sort](#sort)
#### [publish/subscribe](#pubsub)
[subscribe](#subscribe) | [unsubscribe](#unsubscribe) | [publish](#publish) |
[psubscribe](#psubscribesort) | [punsubscribe](#punsubscribe) 
#### [expiring keys](#expiring)
[persist](#persist) | [ttl](#ttl) | [expire](#expire) | [expireat](#expireat) | 
[pttl](#pttl) | [pexpire](#pexpire) | [pexpireat](#pexpireat) 

<h2 id="Strings">字符串(Strings)</h2>

* <p id="StringsGet">Get key-name - 获取存储在给定键中的值</p>
* <p id="StringsSet">Set key-name - 获取存储在给定键中的值</p>
* <p id="StringsDel">Del key-name - 删除存储在给定键中的值（适用于所有类型）</p>

<h2 id="Lists">列表(Lists)</h2>

* <p id="ListsRPush">RPush list-key item - 将给定值推入列表的右端</p>
* <p id="ListsLRange">LRange list-key start stop - 获取列表在给定范围上的所有值</p>
* <p id="ListsLIndex">LIndex list-key index - 获取列表在给定位置上的单个元素</p>
* <p id="ListsLPop">LPop list-key - 从列表的左端pop出一个值，并返回该值</p>

<h2 id="Sets">集合(Sets)</h2>

* <p id="Setssadd">sadd set-key item - 将给定元素item添加到集合（返回0表示元素已存在于集合中，1表示添加成功）</p>
* <p id="Setssmembers">smembers set-key - 返回集合中的所有元素</p>
* <p id="Setssismember">sismember set-key item - 检查给定元素item是否存在于集合中</p>
* <p id="Setssrem">srem set-key item - 如果item存在于集合中，移除该元素（返回移除元素的数量）</p>
* <p id="SetScard">SCARD set-key - 获取集合的成员数</p>

<h2 id="Hashes">散列(Hashes)</h2>

* <p id="Hasheshset">hset hash-key sub-key value - 在散列中设置给定的键值对</p>
* <p id="Hasheshget">hget hash-key sub-key - 在散列中获取指定键的值</p>
* <p id="Hasheshgetall">hgetall hash-key - 获取散列中所有的键值对</p>
* <p id="Hasheshdel">hdel hash-key sub-key - 移除散列中的给定键（存在返回1，不存在返回0）</p>

<h2 id="SortedSets">有序集合(Sorted Sets)</h2>

* <p id="SortedSetszadd">zadd zset-key score member - 将一个带有给定分值的成员添加到有序集合中</p>
* <p id="SortedSetszrange">zrange zset-key start stop [withscores] - 根据元素在有序集合中所处的位置，从有序集合里面获取多个元素</p>
* <p id="SortedSetszrangebyscore">zrangebyscore zset-key start stop [withscores] - 获取有序集合在给定分值范围内的所有元素</p>
* <p id="SortedSetszrem">zrem zset-key member - 在有序集合中移除给定成员（存在返回1，不存在返回0）</p>
* <p id="SortedSetszrevrank">zrevrank zset-key member - 返回有序集合成员 member的排名，成员按照分值从大到小排列</p>
* <p id="SortedSetszrevrange">zrevrange zset-key start stop [withscores] - 返回有序集合给定排名范围内的成员，成员按照分值从大到小排列</p>

<h2 id="OtherCommands">其他命令(Other Commands)</h2>
* <p id="sort">sort source-key [BY pattern] [Limit offset count] [Get pattern [Get pattern ...]] [Asc|Desc] [Alpha] [Store dest-key] - 根据给定的选项，对输入的列表、集合或者有序集合进行排序，返回或存储排序的结果</p>
<h3 id="pubsub">发布/订阅(publish/subscribe)</h3>
* <p id="subscribe">subscribe channel [channel ...] - 订阅给定的频道（一个或多个）</p>
* <p id="unsubscribe">unsubscribe [channel [channel ...]] - 退订给定的频道，如果没有给定频道，将退订所有频道</p>
* <p id="publish">publish channel message - 向给定频道发送消息</p>
* <p id="psubscribe">psubscribe pattern [pattern ...] - 订阅给定模式匹配的频道</p>
* <p id="punsubscribe">punsubscribe [pattern [pattern ...]] - 退订给定pattern匹配的所有模式，如果没有给定模式，将退订所有模式</p>
<h3 id="expiring">过期时间(expiring keys)</h3>
* <p id="persist">persist key-name - 移除键的过期时间</p>
* <p id="ttl">ttl key-name - 查看给定键距离过期还有多少秒</p>
* <p id="expire">expire key-name seconds - 让指定键在给定秒数后过期</p>
* <p id="expireat">expireat key-name timestamp - 将给定的过期时间设置为给定的Unix时间戳</p>
* <p id="pttl">pttl key-name - 查看给定键距离过期还有多少毫秒(version >= 2.6)</p>
* <p id="pexpire">pexpire key-name milliseconds - 让指定键在给定毫秒数后过期(version >= 2.6)</p>
* <p id="pexpireat">pexpireat key-name timestamp-milliseconds - 将给定的过期时间设置为给定的毫秒级精度的Unix时间戳(version >= 2.6)</p>
