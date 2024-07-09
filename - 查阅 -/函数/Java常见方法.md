## 1.[Java中数字的四舍五入和取整](https://blog.csdn.net/lxh_worldpeace/article/details/106839012)
---
Java中对数字进行四舍五入或取整处理经常使用`Math`库中的三个方法：

- `ceil`
- `floor`
- `round`

## 2.[Java中double过大，怎么避免使用科学计数法展示](https://blog.csdn.net/Tomwildboar/article/details/103876558)
---

>[【Java】如何使double类型数据位数过长时不以科学计数法的方式输出-CSDN博客](https://blog.csdn.net/u011453342/article/details/138392806)

```java
public static void main(String[] args) {
	double j = 10000000.1;
	System.out.println(j);

	// 方法一
	NumberFormat nf = NumberFormat.getInstance();
	nf.setGroupingUsed(false);
	System.out.println(nf.format(j));
	
	//方法二
	System.out.println(new BigDecimal(j + "").toString());
}

```
## 3.[Java中控制输出小数位数](https://blog.csdn.net/z_xindong/article/details/82428803)
---
```java
import java.math.BigDecimal;
import java.text.DecimalFormat;
import java.text.NumberFormat;
import java.util.Scanner;
 
public class Main {
	public static void main(String[] args) {
	Scanner sc = new Scanner(System.in);
	// 第一种
	DecimalFormat df = new DecimalFormat("#0.00");
	float data;
	data = sc.nextFloat();
	System.out.println(df.format(data));
	 
	// 第二种,模仿c语言的输出方式
	System.out.printf("%.2f\n", data);
	 
	// 第三种
	System.out.println(String.format("%.2f", data));
	}
}
```

注意和c/c++不同的是double对应的数据类型是 %f，而非%lf；
## 4.交换数值
---
```java
a = a + b - (b=a)
```