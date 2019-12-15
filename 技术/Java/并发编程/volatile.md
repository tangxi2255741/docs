#Volatile

> 为java虚拟机提供**轻量级**的**同步机制**；

## 特性
1、保证可见性；
2、不保证原子性；
3、禁止指令重排序；

## 可见性
> 每个线程对自己内存中的变量的修改，对其他线程可见；



## 为什么不保证原子性

**原子性：** 操作不可被分隔，要么同步成功，要么同时失败；
线程A、B、C同时从主内存获取到当前值1，A++后为2，准备写入主内存时，B也写入主内存，此时主内存原本应该为3,结果还是2；

**怎么解决原子性问题？**
使用AtomicInteger保证原子性；

```java
AtomicInteger atomicInteger = new AtomicInteger();
// ++1；
atomicInteger.getAndIncrement();
```



## 指令重排

> 为了提升性能，编译器和处理器会对指令做重排；

```java
int a = 0;
boolean flag = false;

public void thread1(){
	a = 1;	// 语句1
    flag = true;	// 语句2
}

public void thread2(){
    if(flag){	// 语句3
        a = a + 5;	// 语句4
    }
    sout(a);
}
```

单线程环境没有影响；线程1正常顺序为1 -> 2

多线程时，结果无法预料：线程1重排序，先执行语句2，此时线程2执行了语句3、4，则a = 5；

进行指令重拍的时候需要考虑指令之间的数据依赖性；

### 怎么禁止指令重排序

添加内存屏障；



