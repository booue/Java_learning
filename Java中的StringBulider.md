## Java中的StringBulider

++++++++++++++++++

```C++
Date:2021.9.25
Author:lqy
```

+ #### StringBulider简介：

  StringBulider是一个<font color = Red>**可变的字符串类**</font>，可以视作一个容器，容器中的内容是可以发生改变的

  StringBulider与String相比，StringBulider是可以发生改变的，而String是无法发生改变的

+ #### 拼接字符串区别-String和StringBulider

  + String：

    ```Java
    String s = "hello";
    s += "world";
    System.out.println(s);  // output->"hello world"
    
    /*常量池中会出现三个字符串常量：hello,world,hello world*/
    ```

    ALL:String借用此种方式拼接字符串会造成内存冗余，<font color = Blue>浪费时间和空间</font>

  + StringBulider:

    ```Java
    StringBulider sb = new StringBulider();
    sb.append("hello world");
    ```

    ALL:由于StringBulider的可变特性，因此可以通过append方法直接添加、改变元素

+ #### StringBulider构造方法：

  1. 无参构造
  2. 带参构造

  ```JAVA
  /*借助于new无参构造*/
  StringBuilder sb1 = new StringBuilder();
  System.out.println(sb1);
  /*通过String类型的变量构造StringBulider*/
  String s = "hello world";
  StringBuilder sb2 = new StringBuilder(s);  
  ```

+ #### StringBulider常用函数：

  1. append函数：

     ```Java
     StringBuilder sb = new StringBuilder();
     StringBuilder sb2 = sb.append("hello world");
     /*比较sb和sb2的地址*/
     System.out.println(sb==sb2);  //output->true
     ```

     ALL:append函数返回对象本身，sb和sb2地址相同

     **append函数链式编程：**

     ```java
     sb.append("Java").append("hello").append("world")
     ```

  2. reverse函数：

     ```java
     StringBuilder sb = new StringBuilder();
     sb.append("hello world");
     sb.reverse();   // 对象本身的序列反转
     System.out.println(sb);   // output->"dlrow olleh"
     ```

  3. length和charAt函数

     ```Java
     StringBuilder sb = new StringBuilder();
     sb.append("hello");
     sb.append("world");
     for (int i = 0;i < sb.length();i++)  //获取容器长度
     {
         /*根据索引获取容器中对应的元素*/
         System.out.println(sb.charAt(i));
     }
     ```

  4. insert函数：

     ```Java
     String s = "liqiyan";
     StringBuilder sb = new StringBuilder(s);
     /*在特定索引位置添加String类型变量*/
     sb.insert(0, "linxuan "); 
     System.out.println(sb);
     ```

  5. setCharAt函数：

     ```Java
     String s = "liqiyan";
     StringBuilder sb = new StringBuilder(s);
     /*将特定索引位置的元素替换为目标元素*/ /*替换字符型变量使用单引号修饰*/
     sb.setCharAt(7, '-');      
     System.out.println(sb);
     ```

  6. delete和replace函数：

     ```Java
     String s = "liqiyan";
     StringBuilder sb = new StringBuilder(s);
     /*删除特定区间的元素*/
     sb.delete(0, 7);  
     System.out.println(sb);  
     /*指定区间替换为String类型*/
     sb.replace(0, 1, "linxuan ");  
     System.out.println(sb);//
     ```

+ #### StringBulider和String类型相互转换：

  前文提到，String为不可变类型，StringBuilder为可变类型，在日常生活中，为使用方便，经常需要二者进行相互转换：

  + ### String->StringBulider

    ```Java
    /*借助于构造方法进行转换*/
    String s = "hello world";
    StringBuilder sb = new StringBuilder(s);
    ```

  + ### StringBuilder->String

    ```Java
    /*借助于toString方法进行转换*/
    StringBuilder sb = new StringBuilder();
    sb.append("hello world");
    String s = sb.toString();
    ```

+ #### StringBuilder常见用法：

  ```Java
  /*String字符串反转*/
  public static String myReverse(String s)
  {
      StringBuilder sb = new StringBuilder(s);
      sb.reverse();
      String sAfter = sb.toString();
      return sAfter;
  
      /*一行代码实现*/
      //return new StringBuilder(s).reverse().toString();
  }
  ```

  
