阻塞队列

```java
// 大小为3
new ArrayBlockingQueue(3);

// 同步队列
BlockingQueue synchronousQueue = new SynchronousQueue<>();
synchronousQueue.put("1");
// 释放一个才能put进去
synchronousQueue.put("2");

```



老				新

synchronize	lock

wait	await

notify	signal



synchronized 和lock的区别

1. synchronized是关键字属于jvm层面，lock是api层面；
2.  synchronized不需要手动释放锁，lock需要手动释放；
3.  lock可以中断；
4. synchronized 默认非公平锁，lock可以自己选择；
5. lock可以实现精确唤醒；



基于volatile queue的生产消费实例；