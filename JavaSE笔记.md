

### 正则表达式:

![image-20221102172405867](C:\Users\孟祥龙\AppData\Roaming\Typora\typora-user-images\image-20221102172405867.png)

- ```Java
  System.out.println(checkQQ("1742813261"));    
  
  public static boolean cheakQQ(String qq){     \\判断QQ是否为6-20位的纯数字， \\\d 表示全数字，{6，20}6-20位
  	return qq != null && qq.matches("\\d{6,20}")
  }
  ```

  - ###### \d :  一个数字：0-9

  - ###### \D:   非数字

  - ###### \s:    一个空白字符

  - ###### \w：数字,英文,下划线
  
    



### Collection集合体系



<img src="C:\Users\孟祥龙\AppData\Roaming\Typora\typora-user-images\image-20221103001508879.png" alt="image-20221103001508879" style="zoom: 80%;" />



```java
Collection<String> list1 = new ArrayList<>();	//运用了多态， 泛型为String  有序 可重复 有索引

Collettion<Integer> list2 = new HashSet<>();	//无序 不充分 无索引

/**
	list2.add(12);
	list2.add(14);
	list2.add(15);
	list2.add(12);
	list2.add(14);
	
	System.out.println(list);					//无序 不充分 无索引
	输出值为：[12，14，15]
*/

```

<img src="C:\Users\孟祥龙\AppData\Roaming\Typora\typora-user-images\image-20221103002406076.png" alt="image-20221103002406076" style="zoom:80%;" />

### Arrays

```java
//1 toString:(输出数组元素值)
	int[]arr = {23,22,54,21,54,32,5,67,43};
	System.out.println(Arrays.toString(arr));
	
//2 sort：自动排序
	Arrays.sort(arr);
	System.out.println(Arrays.toString(arr));
	
//3 二分查找：BinarySerch(数组名，查找内容)
	int index = Arrays.binarySearch(arr,54);	//返回索引值
	System.out.println(index);		

/**
	4 被排序的数组 必须是引用类型的元素，
*/
```

![image-20221104001334043](C:\Users\孟祥龙\AppData\Roaming\Typora\typora-user-images\image-20221104001334043.png)

```java
Student[] students = new Student[3];
students[0] = new Students("张三"，14，164);
students[1] = new Students("李四"，15，181);
students[2] = new Students("王五"，11，172);

return o2.getAge() - o1.getAge();	//直接用对象的成员变量相减
```



![image-20221104003243593](C:\Users\孟祥龙\Desktop\image-20221104003243593.png)



```java
//正常匿名内部类
    Arrays.sort(ages1,new Comparator<Integer>(){
        @Override
        public int compare(Integer o1,Integer 02){
            return o2-o1;//降序
        }
    });

//Lambda表达式简化
    Arrays.sort(ages1,(Integer o1,Integer 02)->{
    	return o2-o1;//降序
    });

//再简化
	Arrays.sort(ages1,o1,o2)->{
		return o2-o1;//降序
    })；
        
//再再简化
	Arrays.sort(ages1, ( o1, o2) -> o2 - o1);

//当比较的数据为小数时：
	return Double.compare(o2.getHeight(),o1.getHeight());	//调用此API时，两个参数中用逗号隔开

```

### 匿名内部类

```java
/**
	1、匿名内部类是一个没有名字的内部类
	2、匿名内部类写出来就会产生一个匿名内部类的对象
	3、匿名内部类的对象类型相当于是当前new的那个的类型的子类类型
*/

public class InnerClass {

    public static void main(String[] args) {
        Animal tiger = new Animal(){		//用抽象类new对象，直接重写抽象类中的方法
            @Override
            public void run() {
                System.out.println("老虎跑的很快");
            }
        };
        tiger.run();
    }
}
    abstract class Animal{
        public abstract void run();
    }
```

##### 对象回调：

<img src="C:\Users\孟祥龙\AppData\Roaming\Typora\typora-user-images\image-20221104112055385.png" alt="image-20221104112055385" style="zoom:67%;" />

### Lambda表达式

```java
/**
	作用：简化匿名内部类的代码写法
	注意：Lambda表达式只能简化函数式接口的匿名内部类的写法形式
	
		（函数接口：必须是接口，接口中有且只能有一个抽象方法的形式）
		通常我们回在接口上加一个@FunctionalInterface注解，标记该接口必须是满足函数式接口。
 */

	//匿名内部类形式
	Swimming People = new Swimming() {
		@Override
		public void run() {
			System.out.println("姚明在游泳");
		}
        People.Swimming();
	};
        
	//Lambda表达式简化内部类
	Swimming People1  = () -> System.out.println("姚明在游泳");
	People.run();

	//Lambda表达式进一步简化
	Swimming (() ->
       System.out.println("姚明在游泳")});
    )
	
	//Lambda表达式进进进一步简化
        Swimming (() -> System.out.println("姚明在游泳"));

	//游泳的接口
	interface Swimming{
        void run();
    }

=================================================================================================================================================================================================================
    
    
    
//正常匿名内部类
    Arrays.sort(ages1,new Comparator<Integer>(){
        @Override
        public int compare(Integer o1,Integer 02){
            return o2-o1;//降序
        }
    });

//Lambda表达式简化
    Arrays.sort(ages1,(Integer o1,Integer 02)->{
    	return o2-o1;//降序
    });

//再简化
	Arrays.sort(ages1,o1,o2)->{
		return o2-o1;//降序
    })；
        
//再再简化!!!!!!!!!!!
	Arrays.sort(ages1, ( o1, o2) -> o2 - o1);

```

<img src="C:\Users\孟祥龙\AppData\Roaming\Typora\typora-user-images\image-20221105001359633.png" alt="image-20221105001359633" style="zoom: 67%;" />



总结

- 作用：简化函数式接口的匿名内部类的写法
- 使用前提：必须是接口的匿名内部类，接口中只能有一个抽象方法





### Collection集合体系

- 集合分为Collection集合和Map集合
- ​     Collection单列集合每个元素（数据）只包含一个值
- ​     Map双列集合，每个元素包含两个值（键值对）



<img src="C:\Users\孟祥龙\AppData\Roaming\Typora\typora-user-images\image-20221103001508879.png" alt="image-20221103001508879" style="zoom: 67%;" />



```java
Collection<String> list1 = new ArrayList<>();	//运用了多态， 泛型为String  有序 可重复 有索引
	// 1 添加元素
	list1.add("Java");
	list1.add("C++");
    list1.add("HTML");
    list1.add("Python");
    list1.add("Go");

​	// 2 清空集合的元素
​		list1.clear();

​	// 3 判断集合是否为空 ， 是空返回true ， 反之
​		System.out.println(list1.isEmpty());

​	// 4 获取集合大小
​		System.out.println(list1.size());

​	// 5 判断集合中是否包含某个元素
​		System.out.println(list1.contains("Java"));	//true
​		System.out.println(list1.contains("asf")));	//false

​	// 6 删除某个元素：如果有多个重复元素默认删除前面第一个
​		System.out.println(list1.lis1.remove("Java");	//true
​                           
​	// 7 把集合转换为数组：
​		Object[] arrs = list.toArray();
​		System.out.println("数组：" + Arrays.toString(arrs));

​	// 8 addAll把list2集合元素全部导入到list1中
​		list1.addAll(list2);
================================================================================================================================================================================================================== 	   // 1 迭代器 1得到当前集合的迭代器对象
​		Iterator<String> it = list1.iterator();

​	// 2 定义while循环
​		while(it.hasNext){
​            String ele = it.next();
​            System.out.println(ele);	//遍历集合中的数据
​        }
​                           
​	// 3 增强循环
​		for(String ele : list1){		//元素数据类型  变量名 ： 数组或Collection集合
​            System.out.println(ele);
​        }
	/**
	4.1 foreach增强循环
 		list1.forEach(s -> {
             System.out.println(s);
         });

	4.2 foreach增强循环	
 		list1.forEach(s -> System.out.println(s));

	4.3 foreach增强循环	
​		list1.forEach(System.out::println );
​     */
​                           
	list<String> list = new ArrayList<>();
		list.add("黑马");
         list.add("java");                           
         list.add("李四");                           
         list.add("黑马");     
		System.out.println(list);		//[黑马，java，李四，黑马]
//迭代循环遍历删除
	Iterator<String> it = list.iterator();
	while(it.hasNext()){
        String ele = it.next();
        if("java".equals(ele)){
            //list.remove("java");
            it.remove();	//删除当前所在元素，并且不会后移
        }
    }
    System.out.println(list);
                           
```

### 数据结构

#### 一、数组

数组是一种**查询快，增删慢**的模型

特点：1、**查询速度快**：通过地址值和索引定位。

​			2、**删除效率高**：删除数据的同时后面每个数据前移。

​			3、**添加效率极低**：添加数据的同时每个数据后移在添加元素



#### 二、链表

特点：1、链表中过的元素是游离存储的，每个元素节点包含数据值和下一个元素的地址。

​			2、链表查询慢。无论查询那个都要从头开始找。

​			3、链表增删速度快

链表分为**单向链表**和**双向链表**







```java
Collettion<Integer> list2 = new HashSet<>();	//无序 不重复  无索引

​        /**
​            list2.add(12);
​            list2.add(14);
​            list2.add(15);
​            list2.add(12);
​            list2.add(14);

​            System.out.println(list);					//无序 不充分 无索引
​            输出值为：[12，14，15]
​        */
​           
/**
​	集合和泛型不支持基本类型，只支持引用数据类型
*/
```

### set集合

![image-20221108144431936](C:\Users\孟祥龙\AppData\Roaming\Typora\typora-user-images\image-20221108144431936.png)

```java
//集合自带比较器比较
	apples.add(new Apple("红萍果","红色","9.9","500"))；
	apples.add(new Apple("红萍果","红色","9.9","500"))；
	apples.add(new Apple("红萍果","红色","9.9","500"))；
	apples.add(new Apple("红萍果","红色","9.9","500"))；
        System.out.println(apples);
```





- 元素重复，有索引，查询快：									ArrayList集合，基于数组（用的最多）

- 元素重复，有索引，增删首尾快： 						   LinkedList集合，基于链表

  

- 增删改查都快，元素不重复、**无序**、无索引：        HashSet集合，基于哈希表

- 增删改查都快，元素不重复、**有序**、无索引：        LinledHashSet集合，基于哈希表和双链表

- 对对象进行排序：														TreeSet集合，基于红黑树，后续也可以用List集合实现排序



**shift + F6 批量修改变量名**

```java
List<String> names = new ArrayaList<>();
    names.add("张三");
    names.add("李四");
    names.add("王五");
// 1 给集合对象批量添加元素
	Collections.addAll(names,"张三","李四","王五")；
// 2 打乱集合顺序
    Collections.shuffle(names);
```

### Map



```java
Map<String,Integer> maps = new HashMap<>();
maps.put("娃娃",30);
maps.put("Iphone",10);
maps.put("HUAWEI",20);
maps.put("手表",100);
maps.put("生活用品",23);
System.out.println(maps);	//maps = {娃娃=100,Iphone=10,HUAWEI=20,手表=100,生活用品=23};

//用lamdba表达式遍历集合
maps.forEach((k, v) -> System.out.println(k + "--->" + v));
```

​				正常的遍历：

<img src="C:\Users\孟祥龙\AppData\Roaming\Typora\typora-user-images\image-20221109150632224.png" alt="image-20221109150632224" style="zoom:80%;" />



​				Lambda遍历：

![image-20221109151051211](C:\Users\孟祥龙\AppData\Roaming\Typora\typora-user-images\image-20221109151051211.png)



### 	Stream流

```java
List<String> names = new ArrayaList<>();
	names.add("张三");
	names.add("张三疯");
	names.add("王立森");
	names.add("李立辰");
	names.add("白晨曦");
```

过滤出数据为张开头，长度为三的数据：

```java
names.stream.filter(s -> s.startsWith("张")).
    filter(s -> s.length() == 3).
    forEach(s -> System.out.println(s));
```

##### Stream流的作用及技术：

​	**简化集合、数组操作的API ，结合了Lambda表达式。**



获取Stream流：

```java
//Collection集合获取流：
Collection<String> list = new ArrayList<>();
Stream<String> s = list.stream();

//Map集合获取流：
Map<String, Integer> maps = new HashMap<>();
	//键流
	Stream<String> keyStream = maps.keySet().stream();		
	//值流
	Stream<Integer> valuesStream = maps.values().stream()	
     //键值对流（拿整体）   
	Stream<Map.Entry<String,Integer>> keyAndValuesStream = maps.entrySet().stream(); 

//数组获取流：
String[] names = {"张三","李四","王五","小刘","琪亚娜","玛尔扎哈",}；
	Stream<String> nameStream = Array.Stream(names);
	//或
	Stream<String> nameStream2 = Stream.of(names);

//map加工方法：第一个参数原料 -> 第二个参数是加工后的结果。
	//给集合元素前面都加上一个：帅气的：
	list.stream().map(s -> "帅气的" + s).forEach(s -> System.out.println(s));

//需求：把所欲的名称都加工成一个学生对象。
	list.stream().map(s -> new Student(s)).forEach(s -> System.out.println(s));
								||	//再次简化
	list.stream().map(Student::new).forEach(System.out::println);
```

##### 合并流：

<img src="C:\Users\孟祥龙\AppData\Roaming\Typora\typora-user-images\image-20221111001956051.png" alt="image-20221111001956051" style="zoom:80%;" />

**收集器：**



```java
//用Stream流筛选完数据保存到新的集合：
Stream<String> s1 = list.stream().filter(s -> s.startsWith("张"));
//List
List<String> zhangList = s1.collect(Collectors.toList());
System.out.println(zhangList));

//					！ ！ ！ ！ ！   流只能使用一次   ！ ！ ！ ！ ！
Stream<String> s2 = list.stream().filter(s -> s.startsWith("张"));
//Set:
Set<String> zhangSet = s2.collect(Collectors.toSet());
System.out.println(zhangSet));


public static void main(String[] args) {
        List<String> s1 = new ArrayList<>();
        s1.add("张三");
        s1.add("张三丰");
        s1.add("张丽");
        s1.add("王强");
        s1.add("李刚");

        Stream<String> list = s1.stream().filter(s -> s.startsWith("张"));
        List<String> list2 = list.toList();
        System.out.println(list2);

    }
```

