# 跨域

## 怎么是跨越

| URL                                                     | 说明                           | 是否允许通信                           |
| ------------------------------------------------------- | ------------------------------ | -------------------------------------- |
| http://www.a.com/a.js，http://www.a.com/b.js            | 同一域名下                     | 允许                                   |
| http://www.a.com/lab/a.js，http://www.a.com/script/b.js | 同一域名，不同文件夹           | 允许                                   |
| http://www.a.com:8000/a.js，http://www.a.com/b.js       | 同一域名，不同端口             | 不允许                                 |
| http://www.a.com/a.js，https://www.a.com/b.js           | 同一域名，不同协议             | 不允许                                 |
| http://www.a.com/a.js，http://70.32.92.74/b.js          | 域名和域名对应ip               | 不允许                                 |
| http://www.a.com/a.js，http://script.a.com/b.js         | 主域相同，子域不同             | 不允许                                 |
| http://www.a.com/a.js，http://a.com/b.js                | 同一域名，不同二级域名（同上） | 不允许（cookie这种情况下也不允许访问） |
| http://www.cnblogs.com/a.js，http://www.a.com/b.js      | 不同域名                       | 不允许                                 |