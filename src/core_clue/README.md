# 逆向核心思路

TODO：

【未解决】Android的YouTube逆向：研究request请求api和protobuf相关部分代码

---

此处介绍安卓逆向的核心思路：

* 找核心代码的入口点
  * 对于Android来说，往往是`java`中相关的`基础的类`，`内置的类`
  * 比如
    * `网络请求`类
    * `url`相关的类
      * 比如
        * `new URL`
    * `字符串`相关的类
      * 可能会用到URL拼接，其内部涉及到`字符串`的拼接
      * 比如
        * `append`
        * `getBytes`
        * `String builder`
* 再去写hook代码，加过滤条件，用工具调试
  * `Xposed`：用`hook`框架去写hook代码
  * `frida`：调试逻辑
* 期间配合抓包
  * 先要`抓包`找相关`url`
    * 后续才知道要过滤哪些url

## Java基础的内置的类

### URL

```java
URL myURL = new URL("http://example.com/pages/");
URL page1URL = new URL(myURL, "page1.html");
URL page2URL = new URL(myURL, "page2.html");
```

或：

```java
new URL("http", "example.com", "/pages/page1.html");
```

或：

```java
//URLDemo.java
import java.net.*;

public class URLDemo {

  public static void main(String[] args) {
    try {
      URL url = new URL("http://www.javatpoint.com/java-tutorial");

      System.out.println("Protocol: " + url.getProtocol());
      System.out.println("Host Name: " + url.getHost());
      System.out.println("Port Number: " + url.getPort());
      System.out.println("File Name: " + url.getFile());
    } catch (Exception e) {
      System.out.println(e);
    }
  }
}
```

或：

```java
import java.net.*;

URL url = new URL("/a-guide-to-java-sockets");

URL home = new URL("http://baeldung.com");
URL url = new URL(home, "a-guide-to-java-sockets");
```

或：

```java
@Test
public void givenBaseUrl_whenCreatesRelativeUrl_thenCorrect() {
    URL baseUrl = new URL("http://baeldung.com");
    URL relativeUrl = new URL(baseUrl, "a-guide-to-java-sockets");
    
    assertEquals("http://baeldung.com/a-guide-to-java-sockets", 
      relativeUrl.toString());
}
```

或：

```java
URL url = new URL(yourUrl, "/api/v1/status.xml");
```

或：

```java
URL domain = new URL("http://example.com");
URL url = new URL(domain + "/files/resource.xml");
```
