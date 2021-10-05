# Ajax

> 更多Ajax方法参考https://www.runoob.com/jquery/jquery-ref-ajax.html

## load()

load() 方法从服务器加载数据，并把返回的数据放入被选元素中。

- `$(selector).load(URL,data,callback);`
  - 必需的 *URL* 参数规定您希望加载的 URL。
  - 可选的 *data* 参数规定与请求一同发送的查询字符串键/值对集合。
  - 可选的 *callback* 参数是 load() 方法完成后所执行的函数名称。

**简单示例；**

```javascript

        let url = "serverttext.txt";
        $("#log").load(url);	//把内容加载到选择的元素内。
```



**对应HTTP；**

```http
GET /star_web/test/serverttext.txt HTTP/1.1
Host: localhost:63342
Connection: keep-alive
Accept: text/html, */*; q=0.01
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/81.0.4044.138 Safari/537.36 Edg/81.0.416.77
X-Requested-With: XMLHttpRequest
Sec-Fetch-Site: same-origin
Sec-Fetch-Mode: cors
Sec-Fetch-Dest: empty
Referer: http://localhost:63342/star_web/test/jquery_ajax.html?_ijt=o33qnm0ni0jvtv16i2bouc7pa8
Accept-Encoding: gzip, deflate, br
Accept-Language: zh-CN,zh;q=0.9,en;q=0.8,en-GB;q=0.7,en-US;q=0.6
Cookie: Webstorm-f94e6e3a=84b60da9-de36-4551-80b0-7c71e08560d8
If-Modified-Since: Wed, 20 May 2020 12:23:45 GMT
```

- $(selector).load(URL+selector,data,callback); 仅把请求文件中 id="p1" 的元素的内容，加载到指定的 元素中。如果没有这个元素就加载文件中的全部内容。

```javascript
let url = "serverttext.txt";
$("#log").load(url+" #p2");		//加载请求文件中id位p2的元素选择器和url中间使用空格分割
```

### load()方法callback参数

- 可选的 callback 参数规定当 load() 方法完成后所要允许的回调函数。回调函数可以设置不同的参数：
  - *responseTxt* - 包含调用成功时的结果内容
  - *statusTXT* - 包含调用的状态 
    - success 成功值
    - error 失败值
  - *xhr* - 包含 XMLHttpRequest 对象

```javascript
		let url = "serverttext.txt";
		//指定回调函数
        $("#log").load(url,function (responseTxt,statusTxt,xhr) {
            if (statusTxt == "success")
                alert("调用成功");
            if (statusTxt == "error")
                alert("调用失败");
        });
```



## GET请求

### get()

- `$.get(*URL*,*callback*);`
  - 必需的 *URL* 参数规定您希望请求的 URL。
  - 可选的 *callback* 参数是请求成功后所执行的函数名。

#### get()方法callback参数

回调函数参数；

- data  服务器返回的数据

- status  请求的状态。success 成功值 error 失败值

**示例；**

```javascript
		let url = "serverttext.txt";
        $.get(url,function (data,status) {
            $("#log").val(data+"\r\n状态"+status);	//展示数据
            
        });
```

**对应HTTP；**

```http
GET /star_web/test/serverttext.txt HTTP/1.1
Host: localhost:63342
Connection: keep-alive
Accept: */*
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/81.0.4044.138 Safari/537.36 Edg/81.0.416.77
X-Requested-With: XMLHttpRequest
Sec-Fetch-Site: same-origin
Sec-Fetch-Mode: cors
Sec-Fetch-Dest: empty
Referer: http://localhost:63342/star_web/test/jquery_ajax.html?_ijt=o33qnm0ni0jvtv16i2bouc7pa8
Accept-Encoding: gzip, deflate, br
Accept-Language: zh-CN,zh;q=0.9,en;q=0.8,en-GB;q=0.7,en-US;q=0.6
Cookie: Webstorm-f94e6e3a=84b60da9-de36-4551-80b0-7c71e08560d8
If-Modified-Since: Wed, 20 May 2020 12:23:45 GMT
```



## POST请求

### post() 

- `$.post(*URL,data,callback*);` 
  - 必需的 *URL* 参数规定您希望请求的 URL。
  - 可选的 *data* 参数规定连同请求发送的数据。
  - 可选的 *callback* 参数是请求成功后所执行的函数名。回调函数参数见[get()方法callback参数](#get()方法callback参数)

**示例；**

```javascript
		let url = "serverttext.txt";
        $.post(url,{
            //请求体 以key：value形式
            name:"娜可露露",
            age:"18"
        },function (data,status) {
            $("#log").val(data+"\n状态码"+status);
        });
```



**对应HTTP；**

```http
POST /star_web/test/serverttext.txt HTTP/1.1
Host: localhost:63342
Connection: keep-alive
Content-Length: 48
Accept: */*
X-Requested-With: XMLHttpRequest
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/81.0.4044.138 Safari/537.36 Edg/81.0.416.77
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
Origin: http://localhost:63342
Sec-Fetch-Site: same-origin
Sec-Fetch-Mode: cors
Sec-Fetch-Dest: empty
Referer: http://localhost:63342/star_web/test/jquery_ajax.html?_ijt=o33qnm0ni0jvtv16i2bouc7pa8
Accept-Encoding: gzip, deflate, br
Accept-Language: zh-CN,zh;q=0.9,en;q=0.8,en-GB;q=0.7,en-US;q=0.6
Cookie: Webstorm-f94e6e3a=84b60da9-de36-4551-80b0-7c71e08560d8

name=%E5%A8%9C%E5%8F%AF%E9%9C%B2%E9%9C%B2&age=18	//请求体
```



## Ajax()跨越请求

ajax() 方法用于执行 AJAX（异步 HTTP）请求。

所有的 jQuery AJAX 方法都使用 ajax() 方法。该方法通常用于其他方法不能完成的请求。

- `$.ajax(*{name:value, name:value, ... }*)`

  - 该参数规定 AJAX 请求的一个或多个名称/值对。

  | 名称                         |                           值/描述                            |
  | ---------------------------- | :----------------------------------------------------------: |
  | async                        |         布尔值，表示请求是否异步处理。默认是 true。          |
  | beforeSend(*xhr*)            |                    发送请求前运行的函数。                    |
  | cache                        |     布尔值，表示浏览器是否缓存被请求页面。默认是 true。      |
  | complete(*xhr,status*)       | 请求完成时运行的函数（在请求成功或失败之后均调用，即在 success 和 error 函数之后）。 |
  | contentType                  | 发送数据到服务器时所使用的内容类型。默认是："application/x-www-form-urlencoded"。 |
  | context                      |          为所有 AJAX 相关的回调函数规定 "this" 值。          |
  | data                         |                  规定要发送到服务器的数据。                  |
  | dataFilter(*data*,*type*)    |         用于处理 XMLHttpRequest 原始响应数据的函数。         |
  | dataType                     |                 预期的服务器响应的数据类型。                 |
  | error(*xhr,status,error*)    |                  如果请求失败要运行的函数。                  |
  | global                       | 布尔值，规定是否为请求触发全局 AJAX 事件处理程序。默认是 true。 |
  | ifModified                   | 布尔值，规定是否仅在最后一次请求以来响应发生改变时才请求成功。默认是 false。 |
  | jsonp                        |            在一个 jsonp 中重写回调函数的字符串。             |
  | jsonpCallback                |             在一个 jsonp 中规定回调函数的名称。              |
  | password                     |            规定在 HTTP 访问认证请求中使用的密码。            |
  | processData                  | 布尔值，规定通过请求发送的数据是否转换为查询字符串。默认是 true。 |
  | scriptCharset                |                      规定请求的字符集。                      |
  | success(*result,status,xhr*) |                   当请求成功时运行的函数。                   |
  | timeout                      |             设置本地的请求超时时间（以毫秒计）。             |
  | traditional                  |          布尔值，规定是否使用参数序列化的传统样式。          |
  | type                         |               规定请求的类型（GET 或 POST）。                |
  | url                          |             规定发送请求的 URL。默认是当前页面。             |
  | username                     |           规定在 HTTP 访问认证请求中使用的用户名。           |
  | xhr                          |             用于创建 XMLHttpRequest 对象的函数。             |

**示例；**

```javascript
$.ajax({
            type: "get",
            url: "https://api.zhuolin.wang/api.php?types=search&count=5&source=kugou&pages=1&name=%E8%8D%B7%E5%A1%98%E6%9C%88%E8%89%B2&_=1589614714594",
            dataType: "jsonp",		///指定以jsonp方式執行，实现跨越请求
            success: function (res) {	//成功回调函数
                $("#log").val(JSON.stringify(res));	//显示服务器返回结果。
            },
            error: function () {	//失败回调函数
                alert("请求失败");
            }
        })
```

**对应HTTP；**

- jQuery331016287123643987855_1589990068276,字段就是返回json数据的对象名称。

```http
GET /api.php?types=search&count=5&source=kugou&pages=1&name=%E8%8D%B7%E5%A1%98%E6%9C%88%E8%89%B2&&callback=jQuery331016287123643987855_1589990068276&_=1589990068277 HTTP/1.1
Host: api.zhuolin.wang
Connection: keep-alive
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/81.0.4044.138 Safari/537.36 Edg/81.0.416.77
Accept: */*
Sec-Fetch-Site: cross-site
Sec-Fetch-Mode: no-cors
Sec-Fetch-Dest: script
Referer: http://localhost:63342/star_web/test/jquery_ajax%E8%B7%A8%E8%B6%8A%E8%AF%B7%E6%B1%82.html?_ijt=ifd1ekqou4rc2u9d7ks6n7rl3o
Accept-Encoding: gzip, deflate, br
Accept-Language: zh-CN,zh;q=0.9,en;q=0.8,en-GB;q=0.7,en-US;q=0.6
Cookie: UM_distinctid=17222f9516e19a-06440222c9b524-70657c6b-100200-17222f9516f214
```