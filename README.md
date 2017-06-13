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
      
      
      
