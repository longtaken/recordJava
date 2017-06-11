# recordJava
## 记录学习java之路
### Ⅰ 环境
* 安装JDK
* 配置环境变量
  * JAVA_HOME 配置JDK安装路径 系统变量C:\Java\jdk1.x
  * PATH 配置JDK命令文件的位置 系统变量C:\Java\jdk1.x\bin;
  * CLASSPATH 配置类库文件的位置 系统变量.:C:\Java\jdk1.x\lib
* 记事本编辑java
  * 创建file.java
  * 【编译器】javac file.java 
  * 【解释器】java file (不能跟后缀名.class) 
* Eclipse
  * 创建java项目 -->Java Project
  * 创建程序包 便于源代码管理，避免重名 -->Package [name]=com.projectName 
  * 编写java源程序 com.projectName --> Class
  * 运行java程序 Run As 
### Ⅱ 语法
  * 变量命名规则跟JS一样~
  * java是强类型语言，有两种数据类型
    * 基本数据类型
      * 数值型
        * 整数类型（byte、short、int、long）
        * 浮点类型（float、double）
      * 字符型（char）
      * 布尔型（boolean）
    * 引用数据类型
        * 类（class）
        * 接口（interface）
        * 数组
