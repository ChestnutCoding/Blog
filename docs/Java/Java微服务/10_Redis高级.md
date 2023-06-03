# Redis高级
## Redis事务
> Redis事务是基于**队列**实现的，创建一个事务队列，然后将事务操作都放入队列中，最后依次执行

### Redis事务命令
```redis
  multi 开启事务
  exec 执行事务
  discard 取消事务
```
### Redis事务问题
1. 语法错误
2. 执行错误
### SpringBoot整合Redis事务
1. 开启事务
```java
  redisTemplate.setEnableTransactionSupport(true);
```
2. 执行事务
```java
    //开启事务
    redisTemplate.multi();
    try{
        redisTemplate.opsForValue().set("lesson","java");
        redisTemplate.opsForSet().add("lesson","eureka","feign","gateway");
        redisTemplate.opsForValue().set("lesson","redis");
        System.out.println(redisTemplate.opsForValue().get("lesson"));
    }catch (Exception e){
        //回滚
        System.out.println("出现异常");
        redisTemplate.discard();
    }finally {
        redisTemplate.exec();
    }
```
## Redis持久化
### RDB持久化
> RDB持久化是将当前数据保存到一个dump.rdb文件中，当Redis重启时，会将dump.rdb文件中的数据加载到内存中

#### RDB触发机制
>save、bgsave

区别:save是同步阻塞的，bgsave是异步非阻塞的
默认使用的是 bgsave 来保存快照数据
执行流程:
```flow
st=>start: bgsave
op1=>operation: 创建子进程
cond=>condition: 是否存在
执行save
或bgsave
的子线程
op2=>operation: 直接返回
op3=>operation: 阻塞式创建子线程
op4=>operation: 取消阻塞可以响应其他命令
生成RDB文件
st->cond
cond(yes)->op2
cond(no)->op3->op4
```



#### RDB持久化配置
```redis
  save 
```
#### RDB持久化优缺点

### AOF持久化
> AOF持久化是将每一条命令写入到appendonly.aof文件中，当Redis重启时，会将appendonly.aof文件中的命令重新执行一遍
