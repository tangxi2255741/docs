## Collections.synchronizedList
```java
// 将 ArrayList 转换成线程安全的容器
List<Object> list = Collections.synchronizedList(new ArrayList<Object>);
```



## synchronized

> 相当于单线程，比较耗性能，但没有额外内存消耗；

```java
synchronized(list.get()) {
	list.get().add(model);
}
```



## CopyOnWriteArrayList

> 使用线程安全的CopyOnWriteArrayList,如果不是写少读多的场景，使用 CopyOnWriteArrayList 开销比较大，因为每次对其更新操作（add/set/remove）都会做一次数组拷贝；

` List<Object> list1 = new CopyOnWriteArrayList<Object>(); `



## 使用ThreadLocal

> 使用ThreadLocal变量确保线程封闭性(封闭线程往往是比较安全的， 但由于使用ThreadLocal封装变量，相当于把变量丢进执行线程中去，每new一个新的线程，变量也会new一次，一定程度上会造成性能[内存]损耗，但其执行完毕就销毁的机制使得ThreadLocal变成比较优化的并发解决方案）

```java
ThreadLocal<List<Object>> threadList = new ThreadLocal<List<Object>>() {
    @Override
    protected List<Object> initialValue() {
   	 	return new ArrayList<Object>();
    }
 };
```



**参考链接：**

https://www.baidu.com/link?url=8au5xnkoO-gCVcMG5Wl5ROiozwdf9o6Nrqslgg38CtT-PpbRuwmGO0gVjdTixUtqF6zN16qNWxy7o3PnzZXTnK&wd=&eqid=afda67700009651d000000035de871ac

https://www.baidu.com/link?url=IFtbMt6l6m6OyOvR38A3pRVB0kOaxPEr6UbEynlW42aoOvl3FTg-l1wdD25eoX-c&wd=&eqid=afda67700009651d000000035de871ac