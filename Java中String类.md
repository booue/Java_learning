## Java中String类

+++++++

```C++
Date:2021.9.24
Author:lqy
```

+ #### String简介：

  1. String实际上为一个类，所有<font color = Red>双引号引起的字符串变量均为String类的实例化对象</font>
  2. String类实例化的字符串为<font color = Green>不可变的变量，值一旦创建，不可以发生修改</font>
  3. String类实例化的字符串本质上为**字符数组**，即表明可以通过索引的方式获取特定元素

+ #### String类构造方法：

  1. 无参构造方法
  2. 字符数组传入
  3. 字节数组传入
  4. 直接赋值方法

  ```Java
  //String构造方法
  String s1 = new String();  // 无参构造方法
  
  char[] chs = {'a','b','c'};
  String s2 = new String(chs);  // 字符数组
  
  byte[] chs1 = {97,98,99};
  String s3 = new String(chs1); // 字节数组
  
  String s4 = "abc";  //直接赋值
  ```

+ #### 字符串比较：

  + String对象特点：

    ```Java
    /*
    * 1.通过new创建的字符串对象，每一次new都会申请新的内存空间，虽然内容相同，但是地址值不同
    * 2.以""方式给出的字符串对象，只要字符串序列相同（顺序和大小写），无论在代码中出现几次，都只会创建一个对象，在字符串池(string pool)中维护
    */
    ```

  + String对象比较：

    1. 等号"=="比较：<font color = Yellow>1.基本数据类型：比较数据值是否相同 2.引用数据类型：比较地址值是否相同</font>

       ```Java
       /*常量池中进行维护->地址相同，不再创建新对象*/
       String s1 = "liqiyan";
       String s2 = "liqiyan";
       System.out.println(s1==s2);   // output->true
       
       /*参照的字符数组相同，但每次创建都会开辟新的内存空间，地址不相同*/
       char[] chs = {'a','b','c'};
       String s3 = new String(chs);
       String s4 = new String(chs);
       System.out.println(s3==s4);  // output->false
       ```

    2. "equals"方法比较字符串内容是否相同：

       ```Java
       // 比较字符串内容是否相同
       String s1 = "liqiyan";
       String s2 = "linxuan";
       System.out.println(s1.equals(s2));  // output->false  
       ```

    3. "compareTo"方法比较字符串内容AscII码值：

       ```Java
       String s1 = "liqiyan";
       String s2 = "linxuan";
       System.out.println(s1.compareTo(s2));   // output->3
       ```

    <font color = Green>**总结**：</font>

    ```Java
    System.out.println((s.equals(s2)));  // 判断两个String是否相等,返回boolean类型值
    System.out.println(s.compareTo(s2)); // 返回数值->比较AscII码值
    System.out.println((s == s2));       // 判断两个对象的地址是否相同，返回的boolean类型值
    ```

  + #### String常用函数：

    + 比较函数：equals

    + 查找函数：charAt

      ```Java
      String s = "liqiyan";
      ch = s.charAt(0);   // output->l
      ```

    + 长度函数：length

      ```Java
      String s = "liqiyan";
      len = s.length();   // output->7
      ```

  + #### String常见案例：

    + 字符串遍历：

      ```Java
      // 遍历字符串
      Scanner sc = new Scanner(System.in);
      System.out.println("请输入字符串：");
      String s = sc.nextLine();
      for(int i = 0;i<s.length();i++)   // 字符串长度获取->s.length()
      {
      	System.out.println(s.charAt(i));  // charAt方法获取字符串中的每一个字符
      }
      ```

    + 统计字符次数：

      ```Java
      // 统计字符次数
      System.out.println("请输入字符串：");
      Scanner sc = new Scanner(System.in);
      String s = sc.nextLine();
      
      int numCaps = 0;
      int numLitt = 0;
      int number = 0;
      for(int i = 0;i<s.length();i++)
      {
      	if(s.charAt(i)>0&&s.charAt(i)<9)
      	{
      		number++;
      	}else if(s.charAt(i)>'a'&&s.charAt(i)<'z'){
      		numLitt++;
      	}else{
      		numCaps++;
      	}
      }
      
      System.out.println("大写字母：" + numCaps + " " + "小写字母：" + numLitt + " " + "数字：" + number);
      
      ```

    + 字符串拼接：

      ```Java
      // 字符串拼接案例：
      public static String arrayTolist(int[] arr) {
      	String s = "";
      
      	s += "[";
      	for (int i = 0; i < arr.length; i++) {
      		if (i == arr.length - 1) {
      			s += arr[i];
      		} else {
      			s += arr[i];
      			s += ",";
      		}
      	}
      	
      	s += "]";
      	return s;
      }
      ```

    + 字符串反转：

      ```java
      // 字符串反转案例
      public static String stringReverse(String s) {
      	String ObjectString = "";
      	ObjectString += "[";
      	for (int i = s.length() - 1; i >= 0; i--) {
      		if (i == 0) {
      			ObjectString += s.charAt(i);
      		} else {
      			ObjectString += s.charAt(i);
      			ObjectString += ",";
      		}
      	}
      	ObjectString += "]";
      	return ObjectString;
      }
      ```

      

