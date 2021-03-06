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
   
  public int[] getArray(int length) { int[] nums = new int[length]; for (int i=0;i<nums.length;i++) { nums[i]=(int)(Math.random()*100); }  	return nums; }
 
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
  -------------------------------------------<br> 
  局部变量跟JS类似<br>  
  变量<br>
  1.成员变量<br>
  在类中定义，用来描述对象将要有什么<br>
  作用域在整个类的内部都是可见<br>
  会给变量一个初始值<br><br>

  2.局部变量<br>
  在类的方法中定义，在方法中临时保存数据<br>
  作用域仅限于定义它的方法<br>
  不会给变量初始值<br>
  在同一个方法中不允许有同名局部变量，不同方法中可以。<br>
  局部变量高于全局变量<br>

  -------------------------------------------<br> 
  构造方法<br>
  1.使用new+构造方法创建一个新的对象<br>
  2.构造方法是定义在java类中的一个用来初始化对象的方法，构造方法与类同名且没有返回值<br>

  构造方法的语句格式<br>
  没有返回值类型  与类名相同  可以指定参数<br>
  public 构造方法名(){ }<br>

  当没有指定构造方法时，系统会自动添加无参的构造方法<br>
  当有指定构造方法，无论是有参、无参的构造方法，都不会自动添加无参的构造方法<br>
  构造方法的重载：方法名相同，但参数不同的多个方法，调用时会自动根据不同的参数选择相应的方法<br>
  构造方法不但可以给对象的属性赋值，还可以保证给对象的属性赋一个合理的值<br>

  -------------------------------------------<br>
  静态变量<br>
  Java 中被 static 修饰的成员称为静态成员或类成员。<br>
  它属于整个类所有，而不是某个对象所有，即被类的所有对象所共享。<br> 
  静态成员可以使用类名直接访问，也可以使用对象名进行访问。推荐用类名访问<br>
  使用 static 可以修饰变量、方法和代码块。<br>
  <pre><code>
  // 定义静态变量
  static String className = "a123";
  //访问静态变量	
  public static void main(String[] args) { System.out.println(HelloWorld.className); }
  </code></pre>
  -------------------------------------------<br>
  
  用static修饰方法称为静态方法或类方法<br>
  main方法就是静态方法<br>

  //使用static关键字声明静态方法<br>
  <pre><code>
  public static void print(){}
  public static void main(String[] args){
	//直接使用类名调用静态方法
	HelloWorld.print();
	
	//通过对象名调用
	HelloWorld demo = new HelloWorld();
	demo.print();
  }
  </code></pre>
  注意：<br>
  1，静态方法中可以直接调用同类中的静态成员，但不能直接调用非静态成员。<br>
  <pre><code>
  String str1 = "global";
  static String str2 = "static global";
  public static void print(){
	System.out.print(str1);//报错，不能直接调用非静态变量 str1
	System.out.print(str2);//可以直接调用静态变量 str2
  }
  </code></pre>
  如果希望在静态方法中调用非静态变量，可以通过创建类的对象，然后通过对象来访问非静态变量
  <pre><code>
  public static void print(){
	HelloWorld wrap = new HelloWorld();
	System.out.print(wrap.str1);
  }
  </code></pre>
  2，在普通成员方法中，则可以直接访问同类的非静态变量和静态变量
  <pre><code>
  public void show(){
	System.out.print(str1);//可以访问
	System.out.print(str2);//可以访问
  }
  </code></pre>
  3、 静态方法中不能直接调用非静态方法，需要通过对象来访问非静态方法
  //普通成员方法
  <pre><code>
  public void show(){
	System.out.print("hello");
  }
  //静态方法
  public static void print(){
	System.out.print("welcome");
  }
  public static void main(String[] args){
	HelloWorld hello=new HelloWorld();
	hello.show();//普通成员方法需要通过对象调用
	print();//可以直接调用静态方法
  }
  </code></pre>
  静态方法是属于类的，内存必须为它分配内存空间，这个空间一直由静态方法占用，内存管理器不会由于静态方法没有被调用而将静态方法的存储空间收回，这样如果将所有的方法都声明为静态方法，就会占用大量的内存空间，最后是系统变慢。而普通的成员方法是由对象调用的，内存并不会一直为起分配内存，只有调用的时候才为其分配存储空间，而当其没有被调用时，存储空间就会被内存管理其收回，释放没有用的空间，提高的系统的运行速率！

-------------------------------------------<br>
  Java 中可以通过初始化块进行数据赋值
  <pre><code>
  public class Hello{
	String name;//定义一个成员变量
	{ //通过初始化块为成员变量赋值
		name='h';
	}	
  }
  </code></pre>
  在类的声明中，可以包含多个初始化块，当创建类的实例时，就会依次执行这些代码块。如果使用 static 修饰初始化块，就称为静态初始化块。

  静态初始化块只在类加载时执行，且只会执行一次，同时静态初始化块只能给静态变量赋值，不能初始化普通的成员变量。

  <pre><code>
  public class Hi{
	int n1;
	int n2;
	static int n3;
	public Hi(){//构造方法
		n1=888;
		System.out.print('aaa');
	}
	{//初始化块
		n2=666;
		System.out.print('bbb');
	}
	static {//静态初始化块
		n3=999;
		System.out.print('ccc');
	}
	public static void main(String[] args){
		Hi hi= new Hi();
		System.out.print(hi.n1);
		System.out.print(hi.n2);
		System.out.print(n3);
		Hi hi2=new Hi();
	}
  }
  /*ccc
  bbb
  aaa
  hi.n1
  hi.n2
  n3
  bbb
  aaa*/ 
  </code></pre>
  程序运行时静态初始化块最先被执行，然后执行普通初始化块，最后才执行构造方法。由于静态初始化块只在类加载时执行一次，所以当再次创建对象 hello2 时并未执行静态初始化块。
-------------------------------------------<br>
面向对象三大特性
封装、继承、多态

封装
1、概念
将类的某些信息隐藏在类的内部，不允许外部程序直接访问，而是通过该类提供的方法来实现对隐藏信息的操作和访问

2、好处
a.只能通过规定的方法访问数据
b.隐藏类的实例细节，方便修改和实现

3、封装的实现步骤
修改属性的可见性 （设为private）
创建getter/setter方法 （用于属性的读写）
在getter/setter方法中加入属性控制语句 （对属性值的合法性进行判断）

属性设置为private，用一个方法去调用修改，方法不是private，用public
-------------------------------------------<br>

java中的包
1、包的作用
管理java文件
解决同名文件冲突

2、定义包：package包名
必须放在java源程序的第一行包名间可以使用"."号隔开 （eg:com.im.myclass）

3、系统中的包
java.(功能).(类)
java.lang.(类)包含java语言基础的类
java.util.(类)包含java语言中各种工具类
java.io.(类)包含输入、输出相关功能的类

4、包的使用
a.可以通过import关键字，在某个文件使用其他文件的类 (import com.im.myclass)
b.java中，包的命名规范是全小写字母拼写
c.使用的时候不但可以加载某个包下的所有文件
eg:com.im.*
也可以加载某个具体子包下的所有文件
eg:com.im.m.*

-------------------------------------------<br>
访问修饰符--可以修饰属性和方法的访问范围
访问修饰符  本类   同包   子类   其他
private	     √
默认         √     √
protected    √     √     √
public       √     √     √     √
-------------------------------------------<br>

java中的this关键字
1，this关键字代表当前对象
this.属性 操作当前对象的属性
this.方法 调用当前对象的方法
2，封装对象的属性的时候，经常使用this

this关键字其实相当于帮你创建当下类的一个具体对象，如果不用this的话就得自己实例化一下

-------------------------------------------<br>
java中的内部类
内部类（ Inner Class ）就是定义在另外一个类里面的类。与之对应，包含内部类的类被称为外部类。

内部类的主要作用如下：
1. 内部类提供了更好的封装，可以把内部类隐藏在外部类之内，不允许同一个包中的其他类访问该类
2. 内部类的方法可以直接访问外部类的所有数据，包括私有的数据
3. 内部类所实现的功能使用外部类同样可以实现，只是有时使用内部类更方便

内部类可分为以下几种：
成员内部类
静态内部类
方法内部类
匿名内部类
<pre><code>
//外部类Hello
public class Hello {
	// 内部类Inner，类Inner在类Hello的内部
	public class Inner {
		// 内部类的方法
		public void show() {	
			System.out.println("welcome");
		}
	}
	public static void main(String[] args) {
		// 创建外部类对象
		Hello ni = new Hello();
		// 创建内部类对象
		Inner i = ni.new Inner();
		// 调用内部类对象的方法
		i.show();
	}
}
</code></pre>
  
  -------------------------------------------<br>
  equals方法
比较的是对象的引用是否指向同一块内存地址
a.equals(b);返回布尔值

getClass 获取类对象

默认继承 Object 的 toString( ) 方法，输出对象地址

-------------------------------------------<br>
多态
对象的多种形态
继承时多态的基础，一定要用继承
1.引用多态
父类的引用可以指向本类的对象
父类的引用可以指向子类的对象
2.方法多态
创建本类对象时，调用的方法为本类方法
创建子类对象时，调用的方法为子类重写的方法或者继承的方法
3.instanceof 运算符来解决引用对象的类型，避免类型转换的安全性问题

引用类型转换
1.向上类型转换(隐式／自动类型转换)，是小类型刀大类型的转换。无风险
2.向下类型转换(强制类型转换)，是大类型到小类型。有风险

-------------------------------------------<br>
抽象类
1.语义定义：
抽象类前使用abstract关键字修饰，则该类为抽象类

2.应用场景：
A、在某些情况下，某个父类只是知道其子类应该包含怎样的方法，但无法准确知道这些子类如何实现这些方法
B、从多个具有相同特征的类中抽象出一个抽象类，以这个抽象类作为子类的模板，从而避免了子类设计的随意性

3.作用：
限制规定子类必须实现某些方法，但不关注实现细节

4.使用规则
a、abstract定义抽象类
B、abstract定义抽象方法，只有声明，不需要实现
C、包含抽象方法的类是抽象类
D、抽象类中可以包含普通的方法，也可以没有抽象方法
E、抽象类不能直接创建，可以定义引用变量
-------------------------------------------<br>
接口
1.接口概念
接口可以理解为一种特殊的类，由全局敞亮和公共的抽象方法所组成
类是一种具体实现体，而接口定义了某一批所需要遵守的规范，接口不关心这些类的内部数据，也不关心这些类里方法的实现细节，它只规定这些类里必须提供某些方法
2.接口定义
和类定义不同，定义接口不再适用class关键字，而是使用interface关键字

接口定义的基本语法：
[修饰符] interface 接口名 [extends 父接口1，父接口2]
{
  零个到多个常量定义
  零个到多个抽象方法的定义
}
接口就是用来被继承、被实现的，修饰符一般建议用public
注意：不能使用private和protected修饰接口

3.接口定义
常量：
接口中的属性是常量，即使定义时不添加public static final修饰符，系统也会自动加上

方法：
接口中的方法只能是抽象方法，总是使用，即使定义时不添加public abstract修饰符，系统也会自动加上

4.使用接口
一个类可以实现一个或多个接口，实现接口使用implements关键字。java中一个类只能继承一个父类，是不够灵活的，通过实现多个接口可以做补充。

继承父类实现接口的语法为：
[修饰符] class 类型 extends 父类 implements 接口1，接口2...
{
  类体部分／／如果继承了抽象类，需要实现继承的抽象方法；要实现接口中的抽象方法
}
如果要继承父类，继承父类必须在实现接口之前

使用接口：
接口在使用过程当中，还经常与匿名内部类配合使用
匿名内部类就是没有名字的内部类，多用于关注实现而不关注实现类的名称
语法格式：
Interface I = new Interface(){
  public void method(){
	System.out.println(“匿名内部类实现接口的方式”);
  }
};
-------------------------------------------<br>

1.Java中的所有不正常类都继承于Throwable类。Throwable主要包括两个大类，一个是Error类，另一个是Exception类；

2.其中Error类中包括虚拟机错误和线程死锁，一旦Error出现了，程序就彻底的挂了，被称为程序终结者；

3.Exception类主要指编码、环境、用户操作输入出现问题，Exception主要包括两大类，非检查异常（RuntimeException）和检查异常（其他的一些异常）

4.RuntimeException异常主要包括以下四种异常：
空指针异常
String str=null;System.out.println(str.length());

数组下标越界异常
int[] ary={1,2,3};
for(int i=0;i<=3;i++){ System.out.println(ary[i]); }

类型转换异常
A a1=(B)b1;

算术异常
System.out.println(12/0)


try{
}catch(InputMismatchException e){
}catch(ArithmeticException e){
}catch(Excetion e){
}
多重catch，先捕获子类，最后到父类的错误

finally中有return用finally.return代替，顺序为“try语句  ->  catch  ->  finally  ->  finally.return  ->  catch.return  ->  try.return”，没有相应的阶段请忽略该阶段，任何阶段的return被执行，则整个语句块结束。

throw 将产生的异常抛出
throws 声明将要抛出何种类型的异常

public void divide(int one, int two) throws Exception{
	if(two==0){
		throw new Exception("xx");
	}else{
		System.out.print(one/two);
	}
}


class 自定义异常类 extends 异常类型{ }

-------------------------------------------<br>
异常链
public void t1() throws DrunkException{
	throw new DrunkException("错误1");
}
public void t2(){
	try{
		t1();
	}catch(DrunkException e){
		RuntimeException newExc=new RuntimeException("错误了");
		newExc.initCause(e);
		throw newExc;
	}
}
public static void main(String[] args){
	ChainT ct=new ChainT();
	try{
		ct.t2();
	}catch(Exception e){
		e.printStackTrace();
	}
}


1.自定义异常: 
class 异常类名 extends Exception { 
    public 异常类名(String msg) { 
        super(msg); 
    } 
} 
 
2.标识可能抛出的异常: 
throws 异常类名1,异常类名2 

3.捕获异常: 
try{} 
catch(异常类名 y){} 
catch(异常类名 y){} 

4.方法解释 
getMessage() //输出异常的信息 
printStackTrace() //输出导致异常更为详细的信息

-------------------------------------------<br>
在 Java 中，字符串被作为 String 类型的对象处理。 
String 类位于 java.lang 包中。默认情况下，该包被自动导入所有的程序
创建 String 对象的方法:
String s1="str";
String s2=new String();//空字符串
String s3=new String("str");

String 对象创建后则不能被修改，是不可变的，所谓的修改其实是创建了新的对象，所指向的内存空间不同。
String i="str";
String j="str";
String k=new String("str");
String l=new String("str");
s1==s2;//true
s1==s3;//false
s3==s4;//false
s1="new"+s1;//字符串s1被修改，指向新的内存空间

通过 String s1="爱慕课"; 声明了一个字符串对象， s1 存放了到字符串对象的引用
然后通过 s1="欢迎来到："+s1; 改变了字符串 s1 ，其实质是创建了新的字符串对象，变量 s1 指向了新创建的字符串对象
一旦一个字符串在内存中创建，则这个字符串将不可改变。如果需要一个可以改变的字符串，我们可以使用StringBuffer或者StringBuilder
 每次 new 一个字符串就是产生一个新的对象，即便两个字符串的内容相同，使用 ”==” 比较时也为 ”false” ,如果只需比较内容是否相同，应使用 ”equals()” 方法

  
String 类提供了许多用来处理字符串的方法，例如，获取字符串长度、对字符串进行截取、将字符串转换为大写或小写、字符串分割等（大部分与js类似）
int length() 返回当前字符串的长度
byte[] getBytes() 将该字符串转换为byte数组
o.equals("str");  比较存储在两个字符串对象中的内容是否一致

在Java中，除了可以使用 String 类来存储字符串，还可以使用 StringBuilder 类或 StringBuffer 类存储字符串
StringBuilder 和StringBuffer ，它们基本相似，不同之处，StringBuffer 是线程安全的，而 StringBuilder 则没有实现线

程安全功能，所以性能略高。因此一般情况下，如果需要创建一个内容可变的字符串对象，应优先考虑使用 StringBuilder 类

StringBuilder append(args) 追加内容到当前StringBuilder对象的末尾
StringBuilder insert(位置，参数) 将内容插入StringBuilder对象的指定位置
String toString() 将StringBuilder对象转换为String对象
int length() 获取字符串长度

// 创建一个空的StringBuilder对象
		
StringBuilder str=new StringBuilder();
  
      
		
// 追加字符串
		
str.append("jaewkjldfxmopzdm");
	
	
        
// 从后往前每隔三位插入逗号
        
for(int i = str.length()-3;i>0;i=i-3){
            str.insert(i,',');
        }
  
      
       
// 将StringBuilder对象转换为String对象并输出
		
System.out.print(str.toString());



基本类型		对应的包装类
byte			Byte
short			Short
int 			Interger
long			Long
float			Float
double			Double
char			Character
boolean			Boolean
包装类主要提供了两大类方法：
1. 将本类型和其他基本类型进行转换的方法
2. 将字符串和本类型及包装类互相转换的方法

Integer(int value) 创建一个Integer对象，表示指定的int值
Integer(String s) 创建一个Integer对象，表示String参数所指示的int值

// 定义int类型变量，值为86

int score1 = 86; 
        
		
// 创建Integer包装类对象，表示变量score1的值
		
Integer score2=new Integer(score1);
        
		
// 将Integer包装类转换为double类型
		
double score3=score2.doubleValue();
        
		
// 将Integer包装类转换为float类型
		
float score4=score2.floatValue();
        
		
// 将Integer包装类转换为int类型
		
int score5 =score2.intValue();

		

Integer包装类：86
double类型：86.0
float类型：86.0
int类型：86

Java 中基本类型和包装类之间的转换
基本类型和包装类之间经常需要互相转换
Integer a=new Integer(3);//定义Integer包装类对象，值为3
int b=a+5;

装箱：把基本类型转换成包装类，使其具有对象的性质，又可分为手动装箱和自动装箱
int i=10;//定义一个int基本类型值
Integer x=new Integer(i);//手动装箱
Integer y=i;//自动装箱

拆箱：和装箱相反，把包装类对象转换成基本类型的值，又可分为手动拆箱和自动拆箱
Integer j=new Integer(8);//定义一个Integer包装对象，值为8
int m=j.intValue();//手动插箱int类型
int n=j;//自动拆箱为int类型

// 定义double类型变量
		
double a = 91.5;
        
         
// 手动装箱
		
Double b = new Double(a);
        
        
// 自动装箱
		
Double c = a;

        
System.out.println("装箱后的结果为：" + b + "和" + c);
        
        

// 定义一个Double包装类对象，值为8
		
Double d = new Double(87.0);
        
        
// 手动拆箱
		
double e =  d.doubleValue() ;
        
        
// 自动拆箱
		
double f =  d;
        
         
System.out.println("拆箱后的结果为：" + e + "和" + f);


Java 中基本类型和字符串之间的转换
基本类型转换为字符串有三种方法：
1. 使用包装类的 toString() 方法
2. 使用String类的 valueOf() 方法
3. 用一个空字符串加上基本类型，得到的就是基本类型数据对应的字符串

//将基本类型装换为字符串
int c=10;
String str1=Integer.toString(c);
String str2=String.valueOf(c);
String str3=c+"";


将字符串转换成基本类型有两种方法：
1. 调用包装类的 parseXxx 静态方法
2. 调用包装类的 valueOf() 方法转换为基本类型的包装类，会自动拆箱
//将字符串转为基本类型
String str="8";
int d=Integer.parseInt(str);
int e=Integer.valueOf(str);


使用 Date 和 SimpleDateFormat 类表示时间
经常需要处理日期和时间的相关数据，此时我们可以使用 java.util 包中的 Date 类。这个类最主要的作用就是获取当前时间
Date d=new Date();//使用默认的构造方法创建Date对象

使用 Date 类的默认无参构造方法创建出的对象就代表当前时间，我们可以直接输出 Date 对象显示当前的时间

java.text 包中的 SimpleDateFormat
对日期时间进行格式化，如可以将日期转换为指定格式的文本，也可将文本转换为日期。
1. 使用 format() 方法将日期转换为指定格式的文本
Date d=new Date();
SimpleDateFormat sdf=new SimpleDateFormat("yyyy-MM-dd HH:mm:ss");
String today=sdf.format(d);
System.out.println(today);//2014-06-11  09:55:48

2. 使用 parse() 方法将文本转换为日期
String day="2017年02月14日 10:02:23;
SimpleDateFormat df=new SimpleDateFormat("yyyy年MM月dd日 HH:mm:ss");
Date date=df.parse(day);
System.out.println(date);//Fri Feb 14 10:02:23 CST 2017

1、 调用 SimpleDateFormat 对象的 parse() 方法时可能会出现转换异常，即 ParseException ，因此需要进行异常处理
2、 使用 Date 类时需要导入 java.util 包，使用 SimpleDateFormat 时需要导入 java.text 包


Calendar 类的应用
Date 类最主要的作用就是获得当前时间，同时这个类里面也具有设置时间以及一些其他的功能，但是由于本身设计的问题，这

些方法却遭到众多批评，不建议使用，更推荐使用 Calendar 类进行时间和日期的处理。

java.util.Calendar 类是一个抽象类，可以通过调用 getInstance() 静态方法获取一个 Calendar 对象，此对象已由当前日期

时间初始化，即默认代表当前时间，如 Calendar c = Calendar.getInstance();

Calendar c=Calendar.getInstance();
int year=c.get(Calendar.YEAR);
int month=c.get(Calendar.MONTH)+1;
int day=c.get(Calendar.DAY_OF_MONTH);
int hour=c.get(Calendar.HOUR_OF_DAY);
int minute=c.get(Calendar.MINUTE);
int second=c.get(Calendar.SECOND);

Date date=c.getTime();//将Calendar对象转换为Date对象
Long time=c.getTimeInMillis();//获取当前毫秒数


使用 Math 类操作数据
Math 类位于 java.lang 包中，包含用于执行基本数学运算的方法， Math 类的所有方法都是静态方法，所以使用该类中的方法

时，可以直接使用类名.方法名，如： Math.round();
返回值	  方法名	解释
long	  round()	返回四舍五入后的整数
double    floor()	返回小于参数的最大整数
double    ceil()	返回大于参数的最小整数
double    random()	返回[0,1)之间的随机数浮点数

  
  
java中的集合类：是一种工具类，储存任意数量的具有共同属性的对象
集合的作用
在类的内部，对数据进行组织
简单而快速的搜索大数量的条目
有的集合接口，提供了一系列排列有序的元素，并且可以在序列中间快递的插入或者删除有关元素
有的集合接口，提供了映射关系，可以通过关键字（key）去快速查找对应的唯一对象，而这个关键字可以是任意类型

与数组的对比
数组的长度固定，集合长度可变
数组只能通过下标访问元素，类型固定，而有的集合可以通过任意类型查找所映射的具体对象

java集合框架
Collection
List	ArrayList
Queue   LinkedList
Set     HashSet

Map  Entry键值对
HashMap



Collection接口

是List、Set和Queue接口的父接口

定义了可用于操作List、Set、Queue的方法-增删改查


List接口及其实现类ArrayList
List是元素有序并且可以重复的集合，被称为序列
List可以精确控制每个元素的插入位置，或删除某个位置元素
ArrayList是一个数组序列，是List接口的一个重要实现类
ArrayList的底层是由数组来实现的

构造器的作用:
           1):创建对象,凡是必须和 new 一起使用.
           2):完成对象的初始化操作.
构造器的特点:
          1):构造器的名称和当前所在类的名称相同.
                  如果构造器名称叫XXX,  new  XXX();你看出来创建的是什么类型的对象吗?
          2):禁止定义返回类型,千万不要使用void作为返回类型. void  Student(){}这是普通方法.
                     假设需要写返回类型,也应该这样写:Student   Student(); 既然所有的返回类型都和所在类名相同,何必再写.
          3):在构造器中,不需要使用return语句.
                  其实构造器是有返回值的,返回的是当前创建对象的引用.
---------------------------------------------------------------------------------
编译器创建的默认构造器的特点:
         1):符合构造器特点.
         2):无参数的.
         3):无方法体.
         4):如果类A没有使用public修饰,则编译器创建的构造器也没有public修饰.
  
  
  
  
