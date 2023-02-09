#### string
```
127.0.0.1:6379> SET name John
OK
127.0.0.1:6379> GET name
"John"
127.0.0.1:6379> EXISTS name
(integer) 1
127.0.0.1:6379> SET age 12
OK
127.0.0.1:6379> DEL name age
(integer) 2
127.0.0.1:6379> SET name ABCDEF
OK
127.0.0.1:6379> STRLEN name
(integer) 6
127.0.0.1:6379> GET name
"ABCDEF"
127.0.0.1:6379>
```
#### limit time 
```
127.0.0.1:6379> EXPIRE name 10
(integer) 1
127.0.0.1:6379> TTL name
(integer) 6
127.0.0.1:6379> TTL name
(integer) 3
127.0.0.1:6379> TTL name
(integer) 1
127.0.0.1:6379> TTL name
(integer) -2
127.0.0.1:6379> EXISTS name
(integer) 0
```
#### SETRANGE (Thay the)
```
127.0.0.1:6379> SET myname "Hello World"
OK
127.0.0.1:6379> SETRANGE myname 6 Redis
(integer) 11
127.0.0.1:6379> GET myname
"Hello Redis"
```
##### INCREASE vs DECREASE
```
127.0.0.1:6379> SET number 10
OK
127.0.0.1:6379> INCR number
(integer) 11
127.0.0.1:6379> INCR number
(integer) 12
127.0.0.1:6379> INCRBY number 5
(integer) 17
127.0.0.1:6379> DECR number
(integer) 16
127.0.0.1:6379> DECRBY number 6
(integer) 10
```
#### LIST(STRING) - RPUSH(Cuối mảng) - LPUSH(đầu mảng)
```
127.0.0.1:6379> RPUSH myList A
(integer) 1
127.0.0.1:6379> RPUSH myList B
(integer) 2
127.0.0.1:6379> LPUSH myList C
(integer) 3
127.0.0.1:6379> LRANGE myList 0 -1
1) "C"
2) "A"
3) "B"
127.0.0.1:6379> LPOP myList
"C"
127.0.0.1:6379> RPOP myList
"B"
127.0.0.1:6379> LRANGE myList 0 -1
1) "A"
```
#### HASH
```
127.0.0.1:6379> HSET user username MinhNguyen
(integer) 1
127.0.0.1:6379> HMSET user birth 2001 sex male age 23
OK
127.0.0.1:6379> HGET user username
"MinhNguyen"
127.0.0.1:6379> HMGET user username birth sex
1) "MinhNguyen"
2) "2001"
3) "male"
127.0.0.1:6379> HMGETALL user
1) "MinhNguyen"
2) "2001"
3) "male"
4) "23"
127.0.0.1:6379> HINCRBY user age 5
(integer) 28
```
#### List all key
```
127.0.0.1:6379> KEYS *
```
#### Delete all key
```
127.0.0.1:6379> flushall
```
