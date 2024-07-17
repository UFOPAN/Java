> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [blog.csdn.net](https://blog.csdn.net/qq_43959027/article/details/113528942)

#### 文章目录

*   [1.API](#1API_1)
*   *   [1.1 API 概述 - 帮助文档的使用](#11_API_2)
    *   [1.2 键盘录入字符串](#12__7)
*   [2.String 类](#2String_12)
*   *   [2.1 String 概述](#21_String_13)
    *   [2.2 String 类的构造方法](#22_String_20)
    *   [2.3 创建字符串对象的区别对比](#23__22)
    *   [2.4 字符串的比较](#24__28)
    *   [2.5 String 方法小结](#25__String_35)
*   [3.StringBuilder 类](#3StringBuilder_48)
*   *   [3.1 StringBuilder 类概述](#31_StringBuilder_49)
    *   [3.2 StringBuilder 类和 String 类的区别](#32_StringBuilderString_51)
    *   [3.3 StringBuilder 类的构造方法](#33_StringBuilder_55)
    *   [3.4 StringBuilder 常用的成员方法](#34_StringBuilder_61)
    *   [3.5 StringBuilder 和 String 相互转换](#35_StringBuilderString_67)
*   [4. 常用 API](#4API_74)
*   *   [4.1 Math](#41__Math_75)
    *   [4.2 System](#42__System_93)
    *   [4.3 Object 类的 toString 方法](#43_ObjecttoString_100)
    *   [4.4 Object 类的 equals 方法](#44__Objectequals_112)
    *   [4.5 Objects](#45_Objects_122)
    *   [4.6 BigDecimal](#46_BigDecimal_131)
*   [5. 包装类](#5_166)
*   *   [5.1 基本类型包装类](#51__167)
    *   [5.2 Integer 类](#52_Integer_184)
    *   [5.3 自动拆箱和自动装箱](#53___196)
    *   [5.4 int 和 String 类型的相互转换](#54__intString_202)
*   [6. 时间日期类](#6_212)
*   *   [6.1 Date 类](#61_Date_213)
    *   [6.2 Date 类常用方法](#62_Date_225)
    *   [6.3 SimpleDateFormat 类](#63_SimpleDateFormat_231)
*   [7.JDK8 时间日期类](#7JDK8_248)
*   *   [7.1 JDK8 新增日期类](#71_JDK8_249)
    *   [7.2 LocalDateTime 创建方法](#72__LocalDateTime_254)
    *   [7.3 LocalDateTime 获取方法](#73_LocalDateTime_260)
    *   [7.4 LocalDateTime 转换方法](#74_LocalDateTime_271)
    *   [7.5 LocalDateTime 格式化和解析](#75__LocalDateTime_277)
    *   [7.6 LocalDateTime 增加或者减少时间的方法](#76_LocalDateTime_284)
    *   [7.7 LocalDateTime 修改方法](#77__LocalDateTime_295)
    *   [7.8 Period](#78_Period_306)
    *   [7.9 Duration](#79_Duration_315)

1.API
-----

### 1.1 API 概述 - 帮助文档的使用

*   什么是 API： API (Application Programming Interface) ：应用程序编程接口
*   java 中的 API：指的就是 JDK 中提供的各种功能的 Java 类，这些类将底层的实现封装了起来，我们不需要关心这些类是如何实现的，只需要学习这些类如何使用即可，我们可以通过帮助文档来学习这些 API 如何使用。

### 1.2 键盘录入字符串

**Scanner 类 :**  
next() : 遇到了空格, 就不再录入数据了 , 结束标记: 空格, tab 键  
nextLine() : 可以将数据完整的接收过来 , 结束标记: 回车换行符

2.String 类
----------

### 2.1 String 概述

1.  String 类在 java.lang 包下，所以使用的时候不需要导包
2.  String 类代表字符串，Java 程序中的所有字符串文字（例如 “abc”）都被实现为此类的实例也就是说，Java 程序中所有的双引号字符串，都是 String 类的对象
3.  字符串不可变，它们的值在创建后不能被更改

### 2.2 String 类的构造方法

![](https://img-blog.csdnimg.cn/20210201221718540.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzOTU5MDI3,size_16,color_FFFFFF,t_70)

### 2.3 创建字符串对象的区别对比

**通过构造方法创建**  
通过 new 创建的字符串对象，每一次 new 都会申请一个内存空间，虽然内容相同，但是地址值不同  
**直接赋值方式创建**  
以 “” 方式给出的字符串，只要字符序列相同(顺序和大小写)，无论在程序代码中出现几次，JVM 都只会建立一个 String 对象，并在字符串池中维护

### 2.4 字符串的比较

> == 比较基本数据类型：比较的是具体的值  
> == 比较引用数据类型：比较的是对象地址值

String 类 : public boolean equals(String s) 比较两个字符串内容是否相同、区分大小写

### 2.5 String 方法小结

String 类的常用方法 :
[[]]

*   public boolean equals(Object anObject) 比较字符串的内容，严格区分大小写
*   public boolean equalsIgnoreCase(String anotherString) 比较字符串的内容，忽略大小写
*   public int length() 返回此字符串的长度
*   public char charAt(int index) 返回指定索引处的 char 值
*   public char[] toCharArray() 将字符串拆分为字符数组后返回
*   public String substring(int beginIndex, int endIndex) 根据开始和结束索引进行截取，得到新的字符串（包含头，不包含尾）
*   public String substring(int beginIndex) 从传入的索引处截取，截取到末尾，得到新的字符串
*   public String replace(CharSequence target, CharSequence replacement) 使用新值，将字符串中的旧值替换，得到新的字符串
*   public String[] split(String regex) 根据传入的规则切割字符串，得到字符串数组

3.StringBuilder 类
-----------------

### 3.1 StringBuilder 类概述

概述 : StringBuilder 是一个可变的字符串类，我们可以把它看成是一个容器，这里的可变指的是 StringBuilder 对象中的内容是可变的。

### 3.2 StringBuilder 类和 String 类的区别

String 类：内容是不可变的。  
StringBuilder 类：内容是可变的。

### 3.3 StringBuilder 类的构造方法

<table><thead><tr><th>方法名</th><th>说明</th></tr></thead><tbody><tr><td>public StringBuilder()</td><td>创建一个空白可变字符串对象，不含有任何内容</td></tr><tr><td>public StringBuilder(String str)</td><td>根据字符串的内容，来创建可变字符串对象</td></tr></tbody></table>

### 3.4 StringBuilder 常用的成员方法

<table><thead><tr><th>方法名</th><th>说明</th></tr></thead><tbody><tr><td>public StringBuilder append(任意类型)</td><td>添加数据，并返回对象本身</td></tr><tr><td>public StringBuilder reverse()</td><td>返回相反的字符序列</td></tr></tbody></table>

### 3.5 StringBuilder 和 String 相互转换

StringBuilder 转换为 String  
public String toString()：通过 toString() 就可以实现把 StringBuilder 转换为 String  
String 转换为 StringBuilder  
public StringBuilder(String s)：通过构造方法就可以实现把 String 转换为 StringBuilder

## 4 . 常用 API
---------

### 4.1 Math

1.  Math 类概述  
    Math 包含执行基本数字运算的方法
2.  Math 中方法的调用方式  
    Math 类中无构造方法，但内部的方法都是静态的，则可以通过 类名. 进行调用
3.  Math 类的常用方法

<table><thead><tr><th>方法名</th><th>说明</th></tr></thead><tbody><tr><td>public static int abs(int a)</td><td>返回参数的绝对值</td></tr><tr><td>public static double ceil(double a)</td><td>返回大于或等于参数的最小 double 值，等于一个整数</td></tr><tr><td>public static double floor(double a)</td><td>返回小于或等于参数的最大 double 值，等于一个整数</td></tr><tr><td>public static int round(float a)</td><td>按照四舍五入返回最接近参数的 int</td></tr><tr><td>public static int max(int a,int b)</td><td>返回两个 int 值中的较大值</td></tr><tr><td>public static int min(int a,int b)</td><td>返回两个 int 值中的较小值</td></tr><tr><td>public static double pow (double a,double b)</td><td>返回 a 的 b 次幂的值</td></tr><tr><td>public static double random()</td><td>返回值为 double 的正值，[0.0,1.0)</td></tr></tbody></table>

### 4.2 System

System 类的常用方法

<table><thead><tr><th>方法名</th><th>说明</th></tr></thead><tbody><tr><td>public static void exit(int status)</td><td>终止当前运行的 Java 虚拟机，非零表示异常终止</td></tr><tr><td>public static long currentTimeMillis()</td><td>返回当前时间 (以毫秒为单位)</td></tr></tbody></table>

### 4.3 Object 类的 toString 方法

*   Object 类概述  
    Object 是类层次结构的根，每个类都可以将 Object 作为超类。所有类都直接或者间接的继承自该类，换句话说，该类所具备的方法，所有类都会有一份
*   查看方法源码的方式  
    选中方法，按下 Ctrl + B
*   重写 toString 方法的方式

1.  Alt + Insert 选择 toString
2.  在类的空白区域，右键 -> Generate -> 选择 toString

*   toString 方法的作用：  
    以良好的格式，更方便的展示对象中的属性值

### 4.4 Object 类的 equals 方法

*   equals 方法的作用  
    用于对象之间的比较，返回 true 和 false 的结果  
    举例：s1.equals(s2); s1 和 s2 是两个对象
*   重写 equals 方法的场景  
    不希望比较对象的地址值，想要结合对象属性进行比较的时候。
*   重写 equals 方法的方式

1.  alt + insert 选择 equals() and hashCode()，IntelliJ Default，一路 next，finish 即可
2.  在类的空白区域，右键 -> Generate -> 选择 equals() and hashCode()，后面的同上。

### 4.5 Objects

常用方法

<table><thead><tr><th>方法名</th><th>说明</th></tr></thead><tbody><tr><td>public static String toString(对象)</td><td>返回参数中对象的字符串表示形式。</td></tr><tr><td>public static String toString(对象, 默认字符串)</td><td>返回对象的字符串表示形式。</td></tr><tr><td>public static Boolean isNull(对象)</td><td>判断对象是否为空</td></tr><tr><td>public static Boolean nonNull(对象)</td><td>判断对象是否不为空</td></tr></tbody></table>

### 4.6 BigDecimal

*   作用  
    可以用来进行精确计算
*   构造方法

<table><thead><tr><th>方法名</th><th>说明</th></tr></thead><tbody><tr><td>BigDecimal(double val)</td><td>参数为 double</td></tr><tr><td>BigDecimal(String val)</td><td>参数为 String</td></tr></tbody></table>

*   常用方法

<table><thead><tr><th>方法名</th><th>说明</th></tr></thead><tbody><tr><td>public BigDecimal add(另一个 BigDecimal 对象)</td><td>加法</td></tr><tr><td>public BigDecimal subtract (另一个 BigDecimal 对象)</td><td>减法</td></tr><tr><td>public BigDecimal multiply (另一个 BigDecimal 对象)</td><td>乘法</td></tr><tr><td>public BigDecimal divide (另一个 BigDecimal 对象)</td><td>除法</td></tr><tr><td>public BigDecimal divide (另一个 BigDecimal 对象，精确几位，舍入模式)</td><td>除法</td></tr></tbody></table>

*   总结

1.  BigDecimal 是用来进行精确计算的
2.  创建 BigDecimal 的对象，构造方法使用参数类型为字符串的。
3.  四则运算中的除法，如果除不尽请使用 divide 的三个参数的方法。

> BigDecimal divide = bd1.divide(参与运算的对象, 小数点后精确到多少位, 舍入模式);  
> 参数 1 ，表示参与运算的 BigDecimal 对象。  
> 参数 2 ，表示小数点后面精确到多少位  
> 参数 3 ，舍入模式  
> BigDecimal.ROUND_UP 进一法  
> BigDecimal.ROUND_FLOOR 去尾法  
> BigDecimal.ROUND_HALF_UP 四舍五入

## 5 . 包装类
------

### 5.1 基本类型包装类

*   基本类型包装类的作用  
    将基本数据类型封装成对象的好处在于可以在对象中定义更多的功能方法操作该数据  
    常用的操作之一：用于基本数据类型与字符串之间的转换
*   基本类型对应的包装类

<table><thead><tr><th>基本数据类型</th><th>包装类</th></tr></thead><tbody><tr><td>byte</td><td>Byte</td></tr><tr><td>short</td><td>Short</td></tr><tr><td>int</td><td>Integer</td></tr><tr><td>long</td><td>Long</td></tr><tr><td>float</td><td>Float</td></tr><tr><td>double</td><td>Double</td></tr><tr><td>char</td><td>Character</td></tr><tr><td>boolean</td><td>Boolean</td></tr></tbody></table>

### 5.2 Integer 类

*   Integer 类概述  
    包装一个对象中的原始类型 int 的值
*   Integer 类构造方法

<table><thead><tr><th>方法名</th><th>说明</th></tr></thead><tbody><tr><td>public Integer(int value)</td><td>根据 int 值创建 Integer 对象 (过时)</td></tr><tr><td>public Integer(String s)</td><td>根据 String 值创建 Integer 对象 (过时)</td></tr><tr><td>public static Integer valueOf(int i)</td><td>返回表示指定的 int 值的 Integer 实例</td></tr><tr><td>public static Integer valueOf(String s)</td><td>返回一个保存指定值的 Integer 对象 String</td></tr></tbody></table>

### 5.3 自动拆箱和自动装箱

*   自动装箱  
    把基本数据类型转换为对应的包装类类型
*   自动拆箱  
    把包装类类型转换为对应的基本数据类型

### 5.4 int 和 String 类型的相互转换

**int 转换为 String**  
转换方式  
方式一：直接在数字后加一个空字符串  
方式二：通过 String 类静态方法 valueOf()  
**String 转换为 int**  
转换方式  
方式一：先将字符串数字转成 Integer，再调用 valueOf() 方法  
方式二：通过 Integer 静态方法 parseInt() 进行转换

## 6 . 时间日期类
--------

### 6.1 Date 类

*   计算机中时间原点  
    1970 年 1 月 1 日 00:00:00
*   Date 类概述  
    Date 代表了一个特定的时间，精确到毫秒
*   Date 类构造方法

<table><thead><tr><th>方法名</th><th>说明</th></tr></thead><tbody><tr><td>public Date()</td><td>分配一个 Date 对象，并初始化，以便它代表它被分配的时间，精确到毫秒</td></tr><tr><td>public Date(long date)</td><td>分配一个 Date 对象，并将其初始化为表示从标准基准时间起指定的毫秒数</td></tr></tbody></table>

### 6.2 Date 类常用方法

<table><thead><tr><th>方法名</th><th>说明</th></tr></thead><tbody><tr><td>public long getTime()</td><td>获取的是日期对象从 1970 年 1 月 1 日 00:00:00 到现在的毫秒值</td></tr><tr><td>public void setTime(long time)</td><td>设置时间，给的是毫秒值</td></tr></tbody></table>

### 6.3 SimpleDateFormat 类

*   SimpleDateFormat 类概述  
    SimpleDateFormat 是一个具体的类，用于以区域设置敏感的方式格式化和解析日期。
    
*   SimpleDateFormat 类构造方法
    

<table><thead><tr><th>方法名</th><th>说明</th></tr></thead><tbody><tr><td>public SimpleDateFormat()</td><td>构造一个 SimpleDateFormat，使用默认模式和日期格式</td></tr><tr><td>public SimpleDateFormat(String pattern)</td><td>构造一个 SimpleDateFormat 使用给定的模式和默认的日期格式</td></tr></tbody></table>

*   SimpleDateFormat 类的常用方法

1.  格式化 (从 Date 到 String)  
    public final String format(Date date)：将日期格式化成日期 / 时间字符串
2.  解析 (从 String 到 Date)  
    public Date parse(String source)：从给定字符串的开始解析文本以生成日期

7.JDK8 时间日期类
------------

### 7.1 JDK8 新增日期类

LocalDate 表示日期（年月日）  
LocalTime 表示时间（时分秒）  
LocalDateTime 表示时间 + 日期 （年月日时分秒）

### 7.2 LocalDateTime 创建方法

<table><thead><tr><th>方法名</th><th>说明</th></tr></thead><tbody><tr><td>public static LocalDateTime now()</td><td>获取当前系统时间</td></tr><tr><td>public static LocalDateTime of (年, 月 , 日, 时, 分, 秒)</td><td>使用指定年月日和时分秒初始化一个 LocalDateTime 对象</td></tr></tbody></table>

### 7.3 LocalDateTime 获取方法

<table><thead><tr><th>方法名</th><th>说明</th></tr></thead><tbody><tr><td>public int getYear()</td><td>获取年</td></tr><tr><td>public int getMonthValue()</td><td>获取月份（1-12）</td></tr><tr><td>public int getDayOfMonth()</td><td>获取月份中的第几天（1-31）</td></tr><tr><td>public int getDayOfYear()</td><td>获取一年中的第几天（1-366）</td></tr><tr><td>public DayOfWeek getDayOfWeek()</td><td>获取星期</td></tr><tr><td>public int getMinute()</td><td>获取分钟</td></tr><tr><td>public int getHour()</td><td>获取小时</td></tr></tbody></table>

### 7.4 LocalDateTime 转换方法

<table><thead><tr><th>方法名</th><th>说明</th></tr></thead><tbody><tr><td>public LocalDate toLocalDate ()</td><td>转换成为一个 LocalDate 对象</td></tr><tr><td>public LocalTime toLocalTime ()</td><td>转换成为一个 LocalTime 对象</td></tr></tbody></table>

### 7.5 LocalDateTime 格式化和解析

<table><thead><tr><th>方法名</th><th>说明</th></tr></thead><tbody><tr><td>public String format (指定格式)</td><td>把一个 LocalDateTime 格式化成为一个字符串</td></tr><tr><td>public LocalDateTime parse (准备解析的字符串, 解析格式)</td><td>把一个日期字符串解析成为一个 LocalDateTime 对象</td></tr><tr><td>public static DateTimeFormatter ofPattern(String pattern)</td><td>使用指定的日期模板获取一个日期格式化器 DateTimeFormatter 对象</td></tr></tbody></table>

### 7.6 LocalDateTime 增加或者减少时间的方法

<table><thead><tr><th>方法名</th><th>说明</th></tr></thead><tbody><tr><td>public LocalDateTime plusYears (long years)</td><td>添加或者减去年</td></tr><tr><td>public LocalDateTime plusMonths(long months)</td><td>添加或者减去月</td></tr><tr><td>public LocalDateTime plusDays(long days)</td><td>添加或者减去日</td></tr><tr><td>public LocalDateTime plusHours(long hours)</td><td>添加或者减去时</td></tr><tr><td>public LocalDateTime plusMinutes(long minutes)</td><td>添加或者减去分</td></tr><tr><td>public LocalDateTime plusSeconds(long seconds)</td><td>添加或者减去秒</td></tr><tr><td>public LocalDateTime plusWeeks(long weeks)</td><td>添加或者减去周</td></tr></tbody></table>

### 7.7 LocalDateTime 修改方法

<table><thead><tr><th>方法名</th><th>说明</th></tr></thead><tbody><tr><td>public LocalDateTime withYear(int year)</td><td>直接修改年</td></tr><tr><td>public LocalDateTime withMonth(int month)</td><td>直接修改月</td></tr><tr><td>public LocalDateTime withDayOfMonth(int dayofmonth)</td><td>直接修改日期 (一个月中的第几天)</td></tr><tr><td>public LocalDateTime withDayOfYear(int dayOfYear)</td><td>直接修改日期 (一年中的第几天)</td></tr><tr><td>public LocalDateTime withHour(int hour)</td><td>直接修改小时</td></tr><tr><td>public LocalDateTime withMinute(int minute)</td><td>直接修改分钟</td></tr><tr><td>public LocalDateTime withSecond(int second)</td><td>直接修改秒</td></tr></tbody></table>

### 7.8 Period

<table><thead><tr><th>方法名</th><th>说明</th></tr></thead><tbody><tr><td>public static Period between(开始时间, 结束时间)</td><td>计算两个 “时间 " 的间隔</td></tr><tr><td>public int getYears()</td><td>获得这段时间的年数</td></tr><tr><td>public int getMonths()</td><td>获得此期间的总月数</td></tr><tr><td>public int getDays()</td><td>获得此期间的天数</td></tr><tr><td>public long toTotalMonths()</td><td>获取此期间的总月数</td></tr></tbody></table>

### 7.9 Duration

<table><thead><tr><th>方法名</th><th>说明</th></tr></thead><tbody><tr><td>public static Durationbetween(开始时间, 结束时间)</td><td>计算两个 “时间 " 的间隔</td></tr><tr><td>public long toSeconds()</td><td>获得此时间间隔的秒</td></tr><tr><td>public int toMillis()</td><td>获得此时间间隔的毫秒</td></tr><tr><td>public int toNanos()</td><td>获得此时间间隔的纳秒</td></tr></tbody></table>