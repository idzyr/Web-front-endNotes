# http请求

## XMLHttpRequest

> https://developer.mozilla.org/zh-CN/docs/Web/API/XMLHttpRequest

**属性；**

- `readyState` 存有 XMLHttpRequest的预备状态。从 0 到 4 发生变化。
  - 0: 请求未初始化
  - 1: 服务器连接已建立
  - 2: 请求已接收
  - 3: 请求处理中
  - 4: 请求已完成，且响应已就绪
- status 响应状态
  - 200: "OK" 404: 未找到页面
- `response` 返回一个 ArrayBuffer、Blob、Document，或 DOMString，具体是哪种类型取决于 XMLHttpRequest.responseType 的值。其中包含整个响应体（response body）。
- `responseText` 返回一个 DOMString，该 DOMString 包含对请求的响应，如果请求未成功或尚未发送，则返回 null。
- responseType 一个用于定义响应类型的枚举值（enumerated value）。
  - 枚举值见；https://developer.mozilla.org/zh-CN/docs/Web/API/XMLHttpRequest/responseType

**方法；**

- `open(*method*,*url*,*async*)` 规定请求的类型、URL 以及是否异步处理请求。
  - *method*：请求的类型；GET 或 POST
  - *url*：文件在服务器上的位置
  - *async*：true（异步）或 false（同步）
- `send(string)` 将请求发送到服务器。
  - *string*：仅用于 POST 请求使用
- `setRequestHeader(*header,value*)` 向请求添加 HTTP 头。
  - *header*: 规定头的名称
  - *value*: 规定头的值

**事件；**

- `onreadystatechange` 存储函数（或函数名），每当 readyState 属性改变时，就会调用该函数。
  - **注意：** onreadystatechange 事件被触发 4 次（0 - 4）, 分别是： 0-1、1-2、2-3、3-4，对应着 readyState 的每个变化。

## 发送请求

### GET方式

**示例；**

```javascript
        let httpRequest = new XMLHttpRequest();  //创建http请求对象
        let url = "./serverttext.txt";    //请求地址
        httpRequest.open("GET", url, true);     //指定请求类型，地址，是否异步。
        /*———————————配置请求头——————————————————*/
        httpRequest.setRequestHeader("Accept", "/");
        httpRequest.setRequestHeader("Accept-Language", "zh-CN");
        httpRequest.setRequestHeader("Content-Type", "text/plain");
        httpRequest.send();     //发送请求
        /*——————监听请求状态并获取返回响应内容———————————*/
        httpRequest.onreadystatechange = function () {
            //当状态是4时，请求码我200时进行操作
            if (httpRequest.readyState == 4 && httpRequest.status == 200) {
                log.value = httpRequest.responseText;
            }
        }
```

**对应HTTP；**

```http
GET /star_web/test/serverttext.txt HTTP/1.1
Host: localhost:63342
Connection: keep-alive
Accept: /
Accept-Language: zh-CN
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/81.0.4044.138 Safari/537.36 Edg/81.0.416.77
Content-Type: text/plain
Sec-Fetch-Site: same-origin
Sec-Fetch-Mode: cors
Sec-Fetch-Dest: empty
Referer: http://localhost:63342/star_web/test/ajax.html?_ijt=eg4ocvqmk6sudkoj98noosidig
Accept-Encoding: gzip, deflate, br
Cookie: Webstorm-f94e6e3a=84b60da9-de36-4551-80b0-7c71e08560d8
```

### POST方式

**示例；**

```javascript
        let httpRequest = new XMLHttpRequest();  //创建http请求对象
        let url = "./serverttext.txt";
        httpRequest.open("POST", url, true);     //指定请求模式和地址等
        /*———————————配置请求头——————————————————*/
        httpRequest.setRequestHeader("Accept", "/");
        httpRequest.setRequestHeader("Accept-Language", "zh-CN");
        httpRequest.setRequestHeader("Content-Type", "text/plain");
        let request_body = "name=娜可露露&age=18";  //表单内容可以这样拼接
        httpRequest.send(request_body);     //发送post请求，附带请求体。
        /*——————监听请求状态并获取返回响应内容———————————*/
        httpRequest.onreadystatechange = function () {
            //当状态是4时，请求码我200时进行操作
            if (httpRequest.readyState == 4 && httpRequest.status == 200) {
                log.value = httpRequest.responseText;
            }
        }
```

**对应HTTP；**

```http
POST http://localhost:63342/star_web/test/serverttext.txt HTTP/1.1
Host: localhost:63342
Connection: keep-alive
Content-Length: 24
Accept: /
Accept-Language: zh-CN
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/81.0.4044.138 Safari/537.36 Edg/81.0.416.77
Content-Type: text/plain
Origin: http://localhost:63342
Sec-Fetch-Site: same-origin
Sec-Fetch-Mode: cors
Sec-Fetch-Dest: empty
Referer: http://localhost:63342/star_web/test/ajax.html?_ijt=eg4ocvqmk6sudkoj98noosidig
Accept-Encoding: gzip, deflate, br
Cookie: Webstorm-f94e6e3a=84b60da9-de36-4551-80b0-7c71e08560d8

name=娜可露露&age=18        //请求体
```