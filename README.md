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
  java类型转换<br>
      自动类型转换<br>
          解释：int 型变量 num1 可以直接为 double 型变量 num2 完成赋值操作<br>
          代码：<pre><code>int num1=10;double num2=num1;System.out.println(num2);//10.0</code></pre>
          解释：目标类型能与源类型兼容，如 double 型兼容 int 型，但是 char 型不能兼容 int 型<br>
          代码：<pre><code>int age=18;char sex='man';char result=age+sex;//报错，int类型不能自动转换为char类型</code></pre>
          解释：目标类型大于源类型，如 double 为 8 字节， int 为 4 字节，因此 double 类型的变量里直接可以存放 int 类型的数据，但反过来就不可以了<br>
          代码：<pre><code>double num1=33.3;int num2=num1;//报错,double类型不能自动转换为int类型</code></pre>
          
