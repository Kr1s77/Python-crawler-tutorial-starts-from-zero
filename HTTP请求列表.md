# HTTP请求头列表
## Host
### 作用
> 请求报头域主要用于指定被请求资源的Internet主机和端口号，它通常从HTTP URL中提取出来的

### 例如
> 我们在浏览器中输入：http://www.hzau.edu.cn
> 
> 浏览器发送的请求消息中，就会包含Host请求报头域，如下：
> 
> Host：www.hzau.edu.cn
> 
> 此处使用缺省端口号80，若指定了端口号，则变成：Host：指定端口号

## Connection
### 作用
> 表Connection表示是否需要持久连接。如果Servlet看到这里的值为“Keep-Alive”，或者看到请求使用的是HTTP 1.1（HTTP 1.1默认进行持久连接），它就可以利用持久连接的优点，当页面包含多个元素时（例如Applet，图片），显著地减少下载所需要的时间。要实现这一点，Servlet需要在应答中发送一个Content-Length头，最简单的实现方法是：先把内容写入ByteArrayOutputStream，然后在正式写出内容之前计算它的大小。

### 例如
> Connection: Keepalive 告诉WEB服务器或者代理服务器，在完成本次请求的响应后，保持连接，等待本次连接的后续请求。
> 
> Connection: Keep-Alive 如果浏览器请求保持连接，则该头部表明希望 WEB 服务器保持连接多长时间（秒），如Keep-Alive：300。
> 
> Connection: close 告诉WEB服务器或者代理服务器，在完成本次请求的响应后，断开连接，不要等待本次连接的后续请求了。
> 
## Upgrade-Insecure-Requests
### 作用
> 则是告诉服务器，自己支持这种操作，也就是我能读懂你服务器发过来的上面这条信息，并且在以后发请求的时候不用http而用https

## User-Agent
### 作用
> 告诉HTTP服务器， 客户端使用的操作系统和浏览器的名称和版本.

> 我们上网登陆论坛的时候，往往会看到一些欢迎信息，其中列出了你的操作系统的名称和版本，你所使用的浏览器的名称和版本，这往往让很多人感到很神奇，实际上，服务器应用程序就是从User-Agent这个请求报头域中获取到这些信息User-Agent请求报头域允许客户端将它的操作系统、浏览器和其它属性告诉服务器。

### 例如
> User-Agent: Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 5.1; Trident/4.0; CIBA; .NET CLR 2.0.50727; .NET CLR 3.0.4506.2152; .NET CLR 3.5.30729; .NET4.0C; InfoPath.2; .NET4.0E)

## Accept
### 作用
> 浏览器端可以接受的媒体类型

### 例如
> Accept: text/html 代表浏览器可以接受服务器回发的类型为 text/html 也就是我们常说的html文档,

> 如果服务器无法返回 text/html 类型的数据,服务器应该返回一个406错误(non acceptable)

> 通配符 * 代表任意类型

> Accept: */* 代表浏览器可以处理所有类型,(一般浏览器发给服务器都是发这个)

## Accept-Encoding
### 作用
> 浏览器申明自己接收的编码方法，通常指定压缩方法，是否支持压缩，支持什么压缩方法（gzip，deflate），（注意：这不是只字符编码）;

### 例如
> Accept-Encoding: zh-CN,zh;q=0.8

## Referer
### 作用
> 当浏览器向web服务器发送请求的时候，一般会带上Referer，告诉服务器我是从哪个页面链接过来的，服务器籍此可以获得一些信息用于处理。比如从我主页上链接到一个朋友那里，他的服务器就能够从HTTP Referer中统计出每天有多少用户点击我主页上的链接访问他的网站。

## Accept-Language
### 作用
> 浏览器申明自己接收的语言。 语言跟字符集的区别：中文是语言，中文有多种字符集，比如big5，gb2312，gbk等等；

### 例如
> Accept-Language: en-us

## Content-Length
### 作用
> 表示请求消息正文的长度。

## Cache-Control
### 作用
> 我们网页的缓存控制是由HTTP头中的“Cache-control”来实现的，常见值有private、no-cache、max-age、must-revalidate等，默认为private。这几种值的作用是根据重新查看某一页面时不同的方式来区分的：
> 
> （1）、打开新窗口
> 
> 值为private、no-cache、must-revalidate，那么打开新窗口访问时都会重新访问服务器。而如果指定了max-age值（单位为秒），那么在此值内的时间里就不会重新访问服务器，例如：
> 
> Cache-control: max-age=5 (表示当访问此网页后的5秒内再次访问不会去服务器)
> 
> （2）、在地址栏回车
> 
> 值为 private 或 must-revalidate 则只有第一次访问时会访问服务器，以后就不再访问。
> 
> 值为 no-cache ，那么每次都会访问。
> 
> 值为 max-age ，则在过期之前不会重复访问。
> 
> （3）、按后退按扭
> 
> 值为 private、must-revalidate、max-age，则不会重访问，
> 
> 值为 no-cache，则每次都重复访问
> 
> （4）、按刷新按扭
> 
> 无论为何值，都会重复访问

## Cookie
### 作用
> Cookie是用来存储一些用户信息以便让服务器辨别用户身份的（大多数需要登录的网站上面会比较常见），比如cookie会存储一些用户的用户名和密码，当用户登录后就会在客户端产生一个cookie来存储相关信息，这样浏览器通过读取cookie的信息去服务器上验证并通过后会判定你是合法用户，从而允许查看相应网页。当然cookie里面的数据不仅仅是上述范围，还有很多信息可以存储是cookie里面，比如sessionid等。

## Content-Type
### 作用
> 表示后面的文档属于什么MIME类型。Servlet默认为text/plain，但通常需要显式地指定为text/html。由于经常要设置Content-Type，因此HttpServletResponse提供了一个专用的方法setContentType。

### 例如
> Content-Type: text/html

## If-Modified-Since
### 作用
> 把浏览器端缓存页面的最后修改时间发送到服务器去，服务器会把这个时间与服务器上实际文件的最后修改时间进行对比。如果时间一致，那么返回304，客户端就直接使用本地缓存文件。如果时间不一致，就会返回200和新的文件内容。客户端接到之后，会丢弃旧文件，把新文件缓存起来，并显示在浏览器中.

### 例如
> If-Modified-Since : Mon, 17 Aug 2015 12:03:33 GMT

## If-None-Match
### 作用
> If-None-Match和ETag一起工作，工作原理是在HTTP Response中添加ETag信息。 当用户再次请求该资源时，将在HTTP Request 中加入If-None-Match信息(ETag的值)。如果服务器验证资源的ETag没有改变（该资源没有更新），将返回一个304状态告诉客户端使用本地缓存文件。否则将返回200状态和新的资源和Etag. 使用这样的机制将提高网站的性能

### 例如
> If-None-Match: W/"3119-1437038474000"

## Authorization
### 作用
> 授权信息，通常出现在对服务器发送的WWW-Authenticate头的应答中。

## Upgrade
### 作用
> 它可以指定另一种可能完全不同的协议，如HTTP/1.1客户端可以向服务器发送一条HTTP/1.0请求，其中包含值为“HTTP/1.1”的Update头部，这样客户端就可以测试一下服务器是否也使用HTTP/1.1了。

## Proxy-Authenticate
### 作用
> 代理服务器响应浏览器，要求其提供代理身份验证信息。

## Proxy-Authorization
### 作用
> 浏览器响应代理服务器的身份验证请求，提供自己的身份信息。

## Range
### 作用
> 浏览器（比如 Flashget 多线程下载时）告诉 WEB 服务器自己想取对象的哪部分。

### 例如
> Range: bytes=1173546