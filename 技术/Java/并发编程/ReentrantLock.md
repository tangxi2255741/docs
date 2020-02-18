## 重入锁
可以反复得到相同的一把锁，它有一个与锁相关的获取计数器，如果拥有锁的某个线程再次得到锁，那么获取计数器就加1，锁释放则-1，计数器为0时才是真正的释放完成；


## Synchronized和ReentrantLock的区别

### 相同点
1、都是独占锁；
2、都是可重入锁；

### 不同点
- ReentrantLock在功能上更加丰富，它具有可重入、可中断、可限时、公平锁等特点；
- ReentrantLock必须在finally中进行解锁操作，可能出现异常导致锁没有释放，Synchronized是由JVM来释放锁；
- ReentrantLock提供的lockInterruptibly()方法可以在遇到中断时，优先响应中断，不再继续获取锁，而Synchronized会一直去获取锁；
- JDK 5.0 ReentrantLock 性能 >> synchronized
- JDK 6.0 ReentrantLock ~= Synchronized



### 常用方法：

- lock()：获得锁，如果锁被占用，进入等待。
- lockInterruptibly()：获得锁，但优先响应中断。
- tryLock()：尝试获得锁，如果成功，立即放回 true，反之失败返回 false。该方法不会进行等待，立即返回。
- tryLock(long time, TimeUnit unit)：在给定的时间内尝试获得锁。
- unLock()：释放锁。


## 公平锁
> 所有线程按等待时间顺序获取锁，公平锁能防止饥饿；

```java
// 创建公平锁
ReentrantLock lock = new ReentrantLock(true);
```

## 非公平锁
> 线程随机获取锁,Synchronized和ReentrantLock默认是非公平锁，**非公平锁性能更好**