## Java里构建字符串的几种方式以及优缺点

字符串连接操作在Java程序很常见，这篇文章将会总结归纳字符串连接的四种方式

+ `+` 连接

+ `String.concat()`

+ `StringBuilder`

+ `StringBuffer`

### 使用`+`号连接

```
class Helloworld {
   public static void main(String[] args) {
    // 现在有两个字符串, Hello与World!, 需要通过程序得到
    // Hello World!
    String str1 = "Hello ";
    String str2 = "World!";
    String str3 = str1 + str2;
    System.out.println(str3);
   }
}
```
**结果：** `Hello World!`

> 优点:

+ 操作简单

> 缺点:

+ 因为每次使用都会新生成一个String对象来负载新的字符串, 所以效率很低

> 适用场景

+ 简单字符串链接


### String.concat

```
public class SringC {
    public static void main(String[] args) {
        String test = "Hello ";
        String test1  = test.concat("World!");
        System.out.println(test1);
    }
}

```
**结果：** `Hello World!`


> 优点:

+ 操作简单

> 缺点:

+ 暂时未发现

> 适用场景

+ 简单字符串链接


### StringBuilder
```
public class StringB {
    public static void main(String[] args) {
        StringBuilder builder = new StringBuilder();
        builder.append("Hello ");
        builder.append("World!");
        System.out.println(builder.toString());
    }
}

```

**结果：** `Hello World!`

> 优点:

+ 无需要每次生成String对象，效率高

> 缺点:

+ 暂时未发现

> 适用场景

+ 比较大的字符串构建，比如从文本里读取



### StringBuffer
```
public class SringF {
    public static void main(String[] args) {
        StringBuffer buffer = new StringBuffer();
        buffer.append("Hello ");
        buffer.append("World!");
        System.out.println(buffer.toString());
    }
}

```
**结果：** `Hello World!`

> 优点:

+ 无需要每次生成String对象，效率高(效率低于`StringBuilder`方式)

> 缺点:

+ 暂时未发现

> 适用场景

+ 比较大的字符串构建，比如从文本里读取

+ 支持多线程创建