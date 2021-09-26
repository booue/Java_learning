## Java中ArrayList

+++++++++++++++++

```JAva
Date:2021.9.26
Author:lqy
```

+ #### ArrayList简介：

  1. Java中<font color = Red>数组长度不可变</font>，但集合ArrayList提供<font color = Green>**存储空间可变**的存储模型，大小可变</font>
  2. ArrayList<E>:
     + 可以调整大小的数组实现
     + <E>表征一种<font color = Blue>特殊的数据结构(泛型)</font>，可借指任意引用数据类型

+ ArrayList构造函数：

  ```Java
  ArrayList<String> arr = new ArrayList<>();
  ```

  标明泛型具体数据类型，借助于无参构造方法进行ArrayList的构造
  
+ ArrayList常用函数：

  1. 添加add()命令：

     返回boolean类型变量，表明添加元素是否成功

     ```Java
     ArrayList<String> arr = new ArrayList<>();
     // 返回boolean数据类型，表示添加是否成功
     arr.add("hello world");  
     arr.add(" liqiyan");
     System.out.println(arr);  // output->["hello world","liiqyan"]
     
     /*ArrayList同样提供add方法，支持在特定位置插入指定元素*/
     arr.add(0,"linxuan");  // output->["linxuan","hello world","liqiyan"]
     ```

  2. 移除remove()命令：

     ```Java
     /*Java中remove提供两种移除元素方法：
     1. 按照指定元素进行移除("liqiyan"为ArrayList中的元素)
     2. 按照索引进行移除(去除索引为多少的元素)
     */
     arr.remove("liqiyan");
     arr.remove(0);
     ```
     
  3. 替换set()命令：
  
     ```Java
     /*将指定索引位置处的元素替换为特定元素*/
     /*set(intdex,object)*/
     arr.set(0,"linxuan");
     ```
  
  4. 清空clear()命令：
  
     ```Java
     /*清空ArrayList中的所有元素*/
     arr.clear();
     ```
  
  5. 集合大小size()，元素获取get()函数：
  
     ```Java
     /*集合遍历操作*/
     public static void PrintArr(ArrayList arr)
     {
     	for(int i = 0;i<arr.size();i++)
          /*size函数获取	ArrayList大小*/
     	{
     		System.out.println(arr.get(i));
             /*根据索引位置获取对应元素*/
     	}
     	System.out.println("---------");
     }
     ```
  
     
  
+ #### ArrayList中泛型<E>

  <E>不仅仅为String类型，可以为**任意引用数据类型**，包括自定义数据类型class

  ```java
  /*Student为自定义数据类型class，以此构建ArrayList*/
  ArrayList<Student> arr = new ArrayList<> ();
  ```

+ #### ArrayList不指定类型：

  ArrayList也可以不指定数据类型，用于**存储任意数据类型的数据**

  ```Java
  ArrayList arr = new ArrayList();
  arr.add("liqiyan");
  arr.add(10);
  System.out.println(arr);
  ```

  
