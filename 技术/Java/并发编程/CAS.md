CAS：compare and swap 比较交换；

```java
// 判断当前值是否是5，如果是则更新为2019
AtomicInteger.compareAndSet(5,2019);
```



## CAS底层原理

1、unsafe保证CAS执行CPU语句是原子性的，compareAndSwapInt等方法是native修饰的；

2、通过do while自旋去获取最新的值；

```java
// 1.主内存atomicInteger = 5 线程1工作内存 atomicInteger = 5，线程2工作内存 atomicInteger = 5；
AtomicInteger atomicInteger = new AtomicInteger(5);

// unsafe.getAndAddInt 方法：
// var1 修改的对象，var2 内存地址偏移量，var4 修改的值
public final int getAndAddInt(Object var1,long var2,int var4){
    int var5;
    do{
        // 2. 线程1、2 先后执行，都取到var5 = 5;
        // 5. 线程1 再次循环，获取到var5 = 6;
        var5 = this.getIntVolatile(var1,var2);
        // 3. 线程2 先执行比较更新 var5 = 6；
        // 4. 线程1 执行比较更新，重新获取到的var5 = 6，与自己的var5 不一致，执行失败；
        // 6. 线程1 执行比较更新成功；var5 = 7；
    }while(!this.compareAndSwapInt(var1,var2,var5,var5 + var4));
    return var5;
}
```



## CAS的缺点

1、循环开销大：自旋；

2、只能保证一个 共享变量的操作；

3、引出ABA问题；

### ABA问题

1、线程1、线程2从主内存取到值都为A

2、线程1执行之前，线程2更新成B了，然后线程又更新回A了；

3、对于线程1来说，值都为A，所以能更新成功，但实际上中间是有其他操作的；



### 解决ABA问题

加版本号（类似时间戳）

## 原子引用AtomicReference

```java
AtomicReference<User> atomicReference = new AtomicReference();
```





