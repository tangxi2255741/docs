# 栅栏-CyclicBarrier
> 控制同时执行线程的总数
> 它允许一组线程互相等待，直到到达某个公共屏障点，然后释放这些线程，重置屏障点继续等待，直到所有要执行的线程都执行完毕;
> 举例：100个人坐电梯，电梯只能做10个人（屏障点），下了以后，又去载剩余的人；



## CyclicBarrier两个重要的方法：

```java
//让线程进入屏障被挂起，直到满足珊栏的条件
public int await() 
//挂起后，到达传入的时间才会执行；
public int await(long timeout, TimeUnit unit) 
```



## CyclicBarrier实战

```java
public static void main(String[] args) {
        ExecutorService executorService = Executors.newCachedThreadPool();
        final int parties = 6;
        // 设置屏障拦截的线程数量
        CyclicBarrier cyclicBarrier = new CyclicBarrier(parties);
        for (int i = 1; i <= 20; i++) {
            executorService.execute(new Runnable() {
                @Override
                public void run() {
                    System.out.println(Thread.currentThread().getName() + "等待其他线程集合");
                    try {
                        // 线程进入屏障通过CyclicBarrier的await()方法
                        cyclicBarrier.await();
                        System.out.println(Thread.currentThread().getName() + "开始执行业务逻辑，耗时0.5秒，当前屏障内线程数为：" + cyclicBarrier.getParties());
                        // 工作线程开始处理，这里用Thread.sleep()来模拟业务处理
                        Thread.sleep(500);
                        System.out.println(Thread.currentThread().getName() + "业务逻辑执行完毕");
                    } catch (InterruptedException e) {
                        e.printStackTrace();
                    } catch (BrokenBarrierException e) {
                        e.printStackTrace();
                    }
                }
            });
        }
        executorService.shutdown();
}

pool-1-thread-2等待其他线程集合
pool-1-thread-3等待其他线程集合
pool-1-thread-1等待其他线程集合
pool-1-thread-4等待其他线程集合
pool-1-thread-5等待其他线程集合
pool-1-thread-9等待其他线程集合
pool-1-thread-9开始执行业务逻辑，耗时0.5秒，当前屏障内线程数为：6
pool-1-thread-6等待其他线程集合
pool-1-thread-11等待其他线程集合
pool-1-thread-2开始执行业务逻辑，耗时0.5秒，当前屏障内线程数为：6
pool-1-thread-7等待其他线程集合
pool-1-thread-3开始执行业务逻辑，耗时0.5秒，当前屏障内线程数为：6
pool-1-thread-1开始执行业务逻辑，耗时0.5秒，当前屏障内线程数为：6
pool-1-thread-5开始执行业务逻辑，耗时0.5秒，当前屏障内线程数为：6
pool-1-thread-12等待其他线程集合
pool-1-thread-8等待其他线程集合
pool-1-thread-4开始执行业务逻辑，耗时0.5秒，当前屏障内线程数为：6
pool-1-thread-10等待其他线程集合
pool-1-thread-10开始执行业务逻辑，耗时0.5秒，当前屏障内线程数为：6
pool-1-thread-13等待其他线程集合
pool-1-thread-6开始执行业务逻辑，耗时0.5秒，当前屏障内线程数为：6
pool-1-thread-7开始执行业务逻辑，耗时0.5秒，当前屏障内线程数为：6
pool-1-thread-11开始执行业务逻辑，耗时0.5秒，当前屏障内线程数为：6
pool-1-thread-14等待其他线程集合
pool-1-thread-8开始执行业务逻辑，耗时0.5秒，当前屏障内线程数为：6
pool-1-thread-12开始执行业务逻辑，耗时0.5秒，当前屏障内线程数为：6
pool-1-thread-15等待其他线程集合
pool-1-thread-20等待其他线程集合
pool-1-thread-17等待其他线程集合
pool-1-thread-18等待其他线程集合
pool-1-thread-18开始执行业务逻辑，耗时0.5秒，当前屏障内线程数为：6
pool-1-thread-13开始执行业务逻辑，耗时0.5秒，当前屏障内线程数为：6
pool-1-thread-17开始执行业务逻辑，耗时0.5秒，当前屏障内线程数为：6
pool-1-thread-19等待其他线程集合
pool-1-thread-20开始执行业务逻辑，耗时0.5秒，当前屏障内线程数为：6
pool-1-thread-15开始执行业务逻辑，耗时0.5秒，当前屏障内线程数为：6
pool-1-thread-14开始执行业务逻辑，耗时0.5秒，当前屏障内线程数为：6
pool-1-thread-16等待其他线程集合
pool-1-thread-4业务逻辑执行完毕
pool-1-thread-9业务逻辑执行完毕
pool-1-thread-3业务逻辑执行完毕
pool-1-thread-5业务逻辑执行完毕
pool-1-thread-2业务逻辑执行完毕
pool-1-thread-1业务逻辑执行完毕
pool-1-thread-7业务逻辑执行完毕
pool-1-thread-6业务逻辑执行完毕
pool-1-thread-10业务逻辑执行完毕
pool-1-thread-14业务逻辑执行完毕
pool-1-thread-18业务逻辑执行完毕
pool-1-thread-13业务逻辑执行完毕
pool-1-thread-12业务逻辑执行完毕
pool-1-thread-8业务逻辑执行完毕
pool-1-thread-11业务逻辑执行完毕
pool-1-thread-20业务逻辑执行完毕
pool-1-thread-15业务逻辑执行完毕
pool-1-thread-17业务逻辑执行完毕
```



## 源码解析

### dowait
```java
private int dowait(boolean timed, long nanos) throws InterruptedException, BrokenBarrierException,TimeoutException {
        final ReentrantLock lock = this.lock;
        lock.lock();
        try {
            //标志着每一个线程，当一个线程到来就生成一个新生代
            final Generation g = generation;
            //当计数器被破坏，抛出BrokenBarrierException异常
            if (g.broken)
                throw new BrokenBarrierException();
            //当线程被中断。抛出中断异常
            if (Thread.interrupted()) {
                breakBarrier();
                throw new InterruptedException();
            }
            //当一个线程到来时count减1，直到count为0则计数完成
            int index = --count;
            if (index == 0) {  // tripped
                boolean ranAction = false;
                try {
                    final Runnable command = barrierCommand;
                    if (command != null)
                        command.run();
                    ranAction = true;
                    //更新标志，唤醒所有等待线程
                    nextGeneration();
                    return 0;
                } finally {
                    //如果计数完成，唤醒所有等待的线程，计数器重新开始工作
                    if (!ranAction)
                        breakBarrier();
                }
            }

            // 一直循环等待
            for (;;) {
                try {
                    //如果当前线程没有超时则继续等待
                    if (!timed)
                        trip.await();
                        //如果调用超时，调用awaitNanos方法等待
                    else if (nanos > 0L)
                        nanos = trip.awaitNanos(nanos);
                } catch (InterruptedException ie) {
                    //如果所有线程都已经到达或者被中断则计数完成，进入下一次循环
                    if (g == generation && ! g.broken) {
                        breakBarrier();
                        throw ie;
                    } else {
                        // We're about to finish waiting even if we had not
                        // been interrupted, so this interrupt is deemed to
                        // "belong" to subsequent execution.
                        Thread.currentThread().interrupt();
                    }
                }

                if (g.broken)
                    throw new BrokenBarrierException();
                //如果不是同一个线程，则返回index
                if (g != generation)
                    return index;

                if (timed && nanos <= 0L) {
                    breakBarrier();
                    throw new TimeoutException();
                }
            }
        } finally {
            //释放锁
            lock.unlock();
        }
}
```



**参考链接**

https://www.baidu.com/link?url=R4D5tJyakYGca4NAIPV6q3E1VtQYVXsaqFB4y_HxOwG7_Nz9nlORVB4-7VRMxf5nQ6cpp4uhb3bYbx__Sr3CXFo20xCBlfUxJ-fBCx-7OSm&wd=&eqid=c3f7a40100063e2a000000035de871c4

http://www.manongjc.com/article/28441.html

