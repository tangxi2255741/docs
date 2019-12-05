Lock
java.util.concurrent.locks.AbstractOwnableSynchronizer              抽象类：
java.util.concurrent.locks.AbstractQueuedLongSynchronizer        AbstractQueuedSynchronize的64位实现，完全一致。
java.util.concurrent.locks.AbstractQueuedSynchronizer                参考：AbstractQueuedSynchronizer源码解析
java.util.concurrent.locks.Condition                                                接口，参考：ConditionObject源码
java.util.concurrent.locks.Lock                                                        接口：
java.util.concurrent.locks.LockSupport                                           参考：Java线程阻塞原语-LockSupport
java.util.concurrent.locks.ReadWriteLock                                       接口：
java.util.concurrent.locks.ReentrantLock                                        参考：ReentrantLock源码
java.util.concurrent.locks.ReentrantReadWriteLock                       参考：ReentrantReadWriteLock源码解析
java.util.concurrent.locks.StampedLock                                        



原子操作类：
java.util.concurrent.atomic.AtomicBoolean.class                  参考： 深入解析Java AtomicInteger 原子类型
java.util.concurrent.atomic.AtomicInteger                             参考： 深入解析Java AtomicInteger 原子类型 
java.util.concurrent.atomic.AtomicIntegerArray                    参考：AtomicIntegerArray类详解
java.util.concurrent.atomic.AtomicIntegerFieldUpdater        参考：AtomicIntegerFieldUpdater字段原子更新类
java.util.concurrent.atomic.AtomicLong                                参考： 深入解析Java AtomicInteger 原子类型
java.util.concurrent.atomic.AtomicLongArray                       参考：AtomicIntegerArray类详解
java.util.concurrent.atomic.AtomicLongFieldUpdater           参考：AtomicIntegerFieldUpdater字段原子更新类
java.util.concurrent.atomic.AtomicMarkableReference        参考： AtomicStampedReference实现
java.util.concurrent.atomic.AtomicReference                       参考： AtomicStampedReference实现
java.util.concurrent.atomic.AtomicReferenceArray              参考：AtomicIntegerArray类详解
java.util.concurrent.atomic.AtomicReferenceFieldUpdater  参考：AtomicIntegerFieldUpdater字段原子更新类
java.util.concurrent.atomic.AtomicStampedReference        参考： AtomicStampedReference实现
java.util.concurrent.atomic.DoubleAccumulator
java.util.concurrent.atomic.DoubleAdder
java.util.concurrent.atomic.LongAccumulator
java.util.concurrent.atomic.LongAdder
java.util.concurrent.atomic.Striped64

阻塞队列                                              参考：Java并发包--阻塞队列（BlockingQueue）
java.util.concurrent.ArrayBlockingQueue
java.util.concurrent.BlockingDeque                                    接口：
java.util.concurrent.BlockingQueue                                    接口：
java.util.concurrent.LinkedBlockingDeque
java.util.concurrent.LinkedBlockingQueue
java.util.concurrent.LinkedTransferQueue
java.util.concurrent.SynchronousQueue      
java.util.concurrent.PriorityBlockingQueue
java.util.concurrent.Delayed
java.util.concurrent.DelayQueue                                          

线程池                                                      参考：JavaThreadPoolExecutor解析
java.util.concurrent.ThreadFactory
java.util.concurrent.ThreadPoolExecutor
java.util.concurrent.ScheduledExecutorService
java.util.concurrent.ScheduledFuture
java.util.concurrent.ScheduledThreadPoolExecutor
java.util.concurrent.Executor
java.util.concurrent.ExecutorCompletionService
java.util.concurrent.Executors
java.util.concurrent.ExecutorService
java.util.concurrent.AbstractExecutorService
java.util.concurrent.RejectedExecutionException
java.util.concurrent.RejectedExecutionHandler

 

信号量
java.util.concurrent.Semaphore                                                 参考： Semaphore应用及原理
java.util.concurrent.CyclicBarrier                                               参考：CyclicBarrier详解
java.util.concurrent.CountDownLatch                                        参考：CountDownLatch应用及原理

线程安全类

java.util.concurrent.ConcurrentHashMap
java.util.concurrent.ConcurrentLinkedDeque
java.util.concurrent.ConcurrentLinkedQueue
java.util.concurrent.ConcurrentMap
java.util.concurrent.ConcurrentNavigableMap
java.util.concurrent.ConcurrentSkipListMap
java.util.concurrent.ConcurrentSkipListSet
java.util.concurrent.CopyOnWriteArrayList
java.util.concurrent.CopyOnWriteArraySet
java.util.concurrent.CountedCompleter

框架类
java.util.concurrent.BrokenBarrierException
java.util.concurrent.Callable
java.util.concurrent.CancellationException
java.util.concurrent.CompletableFuture
java.util.concurrent.CompletionException
java.util.concurrent.CompletionService
java.util.concurrent.CompletionStage
java.util.concurrent.Exchanger
java.util.concurrent.ExecutionException
java.util.concurrent.ForkJoinPool
java.util.concurrent.ForkJoinTask
java.util.concurrent.ForkJoinWorkerThread
java.util.concurrent.Future                                                                   参考：FutureTask源码
java.util.concurrent.FutureTask                                                            参考：FutureTask源码
java.util.concurrent.Phaser
java.util.concurrent.RecursiveAction
java.util.concurrent.RecursiveTask
java.util.concurrent.RunnableFuture                                                    参考：FutureTask源码
java.util.concurrent.RunnableScheduledFuture
java.util.concurrent.ThreadLocalRandom
java.util.concurrent.TimeoutException
java.util.concurrent.TimeUnit
java.util.concurrent.TransferQueue



原文链接：https://blog.csdn.net/demon7552003/article/details/90548735