# Map



## HashMap

HashMap根据键的hashCode值存储数据，大多数情况下可以直接定位到它的值，因而具有很快的访问速度，但遍历顺序却是不确定的。

HashMap最多只允许一个记录的键为null,允许多条记录的值为null。

`HashMap非线程安全，即任一时刻可以有多个线程同时写HashMap,可能会导致数据的不一致，如果需要满足线程安全，可以用Collections的synchronizedMap方法使HashMap具有线程安全的能力，或使用CocurrentHashMap。`

### Java 1.7实现

![image-20200427111219905](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20200427111219905.png)

HashMap是由数组+链表组成的，HashMap 里面是一个数组，然后数组中每个元素是一个单向链表。上图中，每个绿色
的实体是嵌套类 Entry 的实例， Entry 包含四个属性： key, value, hash 值和用于单向链表的 next  。

1. capacity:当前叔祖容量，始终保存2^n，可以扩容，扩容后数组大小为当前的2倍
2. loadFactor:负载因子，默认为0.75
3. threshold:扩容的阈值，等于capacoty*loadFactor

HashMap的put操作：

`是从头节点插入`



### Java 1.8实现

![image-20200427114657727](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20200427114657727.png)

HashMap是由数组+链表+红黑树组成。

在Java1.7时，查找一个元素，需要顺着链表一个个比较下去能找到我们需要的，时间复杂度取决于链表的长度，为O(n)。在Java1.8中，当链表中的元素超过8个以后，会将链表转换为红黑树，时间复杂度为O(logN)

## ConcurrentHashMap

- Segment段

ConcurrentHashMap支持并发操作，是由一个个Segment组成。ConcurrentHashMap是一个Segment数组，Segment通过继承ReentrantLock来进行加锁，所以每次需要加锁的操作锁住的是一个segment，可以保证每个Segment是线程安全，也实现了全局的线程安全。

- concurrencyLevel(并行度)

默认是16(ConcurrentHashMap有16个Segments),最多可以同时支持16个线程并发写，只要它们的操作分别分布在不同的Segment上。这个值可以在初始化的时设置为其他值，但是一旦初始化以后，它是不可以扩容的。  

### Java 1.7实现

![image-20200427161711066](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20200427161711066.png)

### Java 1.8实现

![image-20200427161742871](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20200427161742871.png)

## HashTable(线程安全)

Hashtable 是遗留类，很多映射的常用功能与 HashMap 类似，不同的是它承自 Dictionary 类，
并且是线程安全的，任一时间只有一个线程能写 Hashtable，并发性不如 ConcurrentHashMap，
因为 ConcurrentHashMap 引入了分段锁。 Hashtable 不建议在新代码中使用，不需要线程安全
的场合可以用 HashMap 替换，需要线程安全的场合可以用 ConcurrentHashMap 替换。  

## TreeMap(可排序)

TreeMap 实现 SortedMap 接口，能够把它保存的记录根据键排序，默认是按键值的升序排序，也可以指定排序的比较器，当用 Iterator 遍历 TreeMap 时，得到的记录是排过序的。如果使用排序的映射，建议使用 TreeMap。在使用 TreeMap 时， key 必须实现 Comparable 接口或者在构造 TreeMap 传入自定义的Comparator，否则会在运行时抛出java.lang.ClassCastException 类型的异常  

## LinkHashMap(记录插入顺序)

LinkedHashMap 是 HashMap 的一个子类，保存了记录的插入顺序，在用 Iterator 遍历
LinkedHashMap 时，先得到的记录肯定是先插入的，也可以在构造时带参数，按照访问次序排序  