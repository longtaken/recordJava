# recordJava
### Ⅰ 环境
* 安装JDK
* 配置环境变量 <br>
  1. JAVA_HOME 配置JDK安装路径 系统变量C:\Java\jdk1.x<br>
  2. PATH 配置JDK命令文件的位置 系统变量C:\Java\jdk1.x\bin;<br>
  3. CLASSPATH 配置类库文件的位置 系统变量.:C:\Java\jdk1.x\lib<br>
* 记事本编辑java<br>
  1. 创建file.java<br>
  2. 【编译器】javac file.java <br>
  3. 【解释器】java file (不能跟后缀名.class)<br> 
* Eclipse
  1. 创建java项目 -->Java Project<br>
  2. 创建程序包 便于源代码管理，避免重名 -->Package [name]=com.projectName<br> 
  3. 编写java源程序 com.projectName --> Class<br>
  4. 运行java程序 Run As <br>
### Ⅱ 语法
  变量命名规则跟JS一样~<br>
      main 方法中定义的变量必须先赋值，然后才能输出 ```String str;System.out.println(str);//报错 ```<br>
  -------------------------------------------<br>
  java是强类型语言，有两种数据类型<br>
      基本数据类型<br>
          数值型<br>
              整数类型(byte、short、int、long)<br>
              浮点类型(float、double)<br>
          字符型(char)<br>
          布尔型(boolean)<br>
      引用数据类型<br>
          类 (class) <br>
          接口 (interface) <br>
          数组 <br>
  -------------------------------------------<br>
  java类型转换<br>
      自动类型转换<br>
          解释：int 型变量 num1 可以直接为 double 型变量 num2 完成赋值操作 <br>
          代码：<pre><code>int num1=10;double num2=num1;System.out.println(num2);//10.0</code></pre>
          解释：目标类型能与源类型兼容，如 double 型兼容 int 型，但是 char 型不能兼容 int 型<br>
          代码：<pre><code>int age=18;char sex='man';char result=age+sex;//报错，int类型不能自动转换为char类型</code></pre>
          解释：目标类型大于源类型，如 double 为 8 字节， int 为 4 字节，因此 double 类型的变量里直接可以存放 int 类型的数据，但反过来就不可以了<br>
          代码：<pre><code>double num1=33.3;int num2=num1;//报错,double类型不能自动转换为int类型</code></pre>
      强制类型转换<br>
          解释： int 型的存储范围比 double 型的小,需要通过强制类型转换。数值上并未进行四舍五入，而是直接将小数位截断<br>
          代码：<pre><code> double num1=176.2;	int num2=(int)num1;	System.out.println(num1);	System.out.println(num2);</code></pre>
  -------------------------------------------<br>
  java常量<br>
     语法：final 常量名 = 值;<br>
  -------------------------------------------<br>
  java注释<br>        
     java注释比JS多一种文档注释 以/** 开头 以 */ 结尾
     
     使用文档注释时还可以使用 javadoc 标记，生成更详细的文档信息：
       @author 标明开发该类模块的作者，
       @version 标明该类模块的版本，
       @see 参考转向，也就是相关主题，
       @param 对方法中某参数的说明，
       @return 对方法返回值的说明，
       @exception 对方法可能抛出的异常进行说明<br>
  -------------------------------------------<br>
  java运算符<br>
       跟JS类似。<br>
       没有全等===<br>
       多了异或。有且只能有一个正确。true^false -> true;<br>
       有三目运算符 ?:<br>
       运算符优先级 http://img.mukewang.com/5360ffb90001b4f002620224.jpg<br>
  -------------------------------------------<br>
  java条件语句<br>
       跟JS类似。<br>
  -------------------------------------------<br>
  java数组<br>
      声明数组语法：数据类型[] 数组名； ||  数据类型 数组名[]；<br>
      int[] scores;<br>
      分配空间:（指定数组中最多可存储多少个元素）语法： 数组名 = new  数据类型 [ 数组长度 ];<br>
      int[] scores; scores=new int[5]; || int[] scores=new int[5]<br>
      赋值：分配空间后就可以向数组中放数据<br>
      scores[0]=1;<br>
      直接创建：<br>
      int[] scores = { 1,2,3,4 };scores[1]//2<br>
      double height[] = {5,6,7};height[1]//6.0<br>
      int[] scores=new int[]{1,2,3,4}<br>
  -------------------------------------------<br>
  java中Arrays类<br>
  Arrays 类是 Java 中提供的一个工具类，在 java.util 包中//import java.util.Arrays;<br>
      1、 排序<br>
      语法：  Arrays.sort(数组名);<br>
      2、 将数组转换为字符串<br>
      语法：  Arrays.toString(数组名);<br>
  -------------------------------------------<br>
  foreach 操作数组<br>
  语法：for(元素类型 元素变量：遍历对象){ 执行代码 }<br>
  foreach 并不是 Java 中的关键字，是 for 语句的特殊简化版本，在遍历数组、集合时， foreach 更简单便捷<br>
  -------------------------------------------<br>
  java 中的二维数组<br>
		声明数组并分配空间<br>
		数据类型[][] 数组名 = new 数据类型[行的个数][列的个数];<br>
		数据类型[][] 数组名; 数组名=new 数据类型[行的个数][列的个数];<br>
		赋值<br>
		数组名[行的索引][列的索引]=值;//num[0][0]=1;第一行第一列的元素赋值<br>
		数据类型[][] 数组名={{值1,值2..},{值1,值2..}};<br>
  -------------------------------------------<br>
  定义一个方法的语法<br>
  访问修饰符 返回值类型 方法名(参数列表){方法体}<br>
  1、 访问修饰符：方法允许被访问的权限范围， 可以是 public、protected、private 甚至可以省略 ，其中 public 表示该方法可以被其他任何代码调用<br>
  2、 返回值类型：方法返回值的类型，如果方法不返回任何值，则返回值类型指定为 void ；如果方法具有返回值，则需要指定返回值的类型，并且在方法体中使用 return 语句返回值<br>
  3、 方法名：定义的方法的名字，必须使用合法的标识符<br>
  4、 参数列表：传递给方法的参数列表，参数可以有多个，多个参数间以逗号隔开，每个参数由参数类型和参数名组成，以空格隔开 <br>
  根据方法是否带参、是否带返回值，可将方法分为四类：无参无返回值方法、无参带返回值方法、带参无返回值方法、带参带返回值方法<br>
  <pre><code>public class HelloWorld {
    //定义了一个方法名为 print 的方法，实现输出信息功能
    public void print() { System.out.println("Hello World"); }
    //在 main 方法中调用 print 方法
    public static void main(String[] args){ HelloWorld test=new HelloWorld(); test.print(); } 
  }</code></pre>
  -------------------------------------------<br>
  Java 中无参无返回值方法的使用<br>
  方法不包含参数，且没有返回值<br>
  <pre><code>public void showMyLove() { System.out.println("我爱慕课网!"); }</code></pre><br>
  -------------------------------------------<br>
  Java 中无参带返回值方法的使用<br>
  方法不包含参数，但有返回值<br>
      1、 如果方法的返回类型为 void ，则方法中不能使用 return 返回值！<br>
      2、 方法的返回值最多只能有一个，不能返回多个值<br>
      3、 方法返回值的类型必须兼容，例如，如果返回值类型为 int ，则不能返回 String 型值<br>
  <pre><code>public double calcAvg() {	double java = 92.5; return java; }</code></pre><br>
  -------------------------------------------<br>  
  Java 中带参无返回值方法的使用<br>
  对象名.方法名(实参1，实参2...)<br>
  <pre><code>public int calc(int num1,int num2){ int num3=num1+num2; System.out.println(num3) }</code></pre><br>
  -------------------------------------------<br> 
  Java 中带参带返回值方法的使用<br>
  <pre><code>public int sort(int[] scores){
	Arrays.sort(scores);
	System.out.println(Arrays.toString(scores));
        return scores.length;//返回数组中元素的个数
  }</code></pre><br>
  -------------------------------------------<br>
  Java 中方法的重载<br>
  如果同一个类中包含了两个或两个以上方法名相同、方法参数的个数、顺序或类型不同的方法，则称为方法的重载，也可称该方法被重载了。<br>
  当调用被重载的方法时， Java 会根据参数的个数和类型来判断应该调用哪个重载方法，参数完全匹配的方法将被执行。<br>
  跟JS函数会被覆盖不同，java会保留。如果有一样的函数会报错。<br>
  <pre><code>
  public void print() { System.out.println("无参的print方法"); } 
  public void print(String name,int age) { System.out.println("无参的print方法"+name); System.out.println(age); }
  </code></pre>
  -------------------------------------------<br> 
  Math.random()跟JS一样
  ````
  public int[] getArray(int length) {
        int[] nums = new int[length]; 
	for (int i=0;i<nums.length;i++) { 
	    nums[i]=(int)(Math.random()*100); 
	}  
	return nums;
  }
  ````
  -------------------------------------------<br> 
### Ⅲ Java 面向对象编程
  所有java程序都以类class为组织单元<br>
  类时模子，确定对象将会拥有的特征（属性）和行为（方法）<br>
  类的组成：属性和方法<br>
  定义一个类的步骤<br>
	1，定义类名<br>
	2，编写类的属性<br>
	3，编写类的方法<br>
  <pre><code>
  public class 类名{
	//定义属性部分（成员变量）
	属性1的类型 属性1;
	属性2的类型 属性2;
	//定义方法部分
	方法1;
	方法2;	
  }
  package com.mypackage;
  public class Telphone{
	//属性
	float screen;
	float cpu;
	float mem;
	//方法
	void call(){
		System.out.println('call');
	}
	void sendMsg(){
		System.out.println('msg');
	}
  }
  </code></pre>	
