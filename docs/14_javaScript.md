## 跨域
#### 同源策略
对于URL路径只要协议/域名/端口其中一个不一样，就是非同源域。异步请求是不能跨域的，这是基于安全的考虑。
但是当需要跨域请求时怎么处理呢？
1. CORS(cross origin resource sharing)

2. JSONP。jsonp的方式原理是利用 `script` 标签具有跨域的能力，也就是说script标签能加载不同域的文件。具体做法：
    - 本地定义数据处理函数（回调）。
    - 动态创建 `script` 标签，src属性为跨域请求地址，并带上回调函数名作为参数。
    - 后端将所请求数据以参数的形式传入回调函数（其实就是字符串拼接），然后返回一个javaScript文件。
    - 前端加载文件后会立即执行文件内容，这样就调用了本地的数据处理函数。至此达到跨域请求的目。

另外如果使用 `jquery` 则可以使用封装好的jspnp机制：
 ```javaScript
     $.ajax({
         async : true,
         url : "https://api.douban.com/v2/book/search",
         type : "GET",
         dataType : "jsonp", // 返回的数据类型，设置为JSONP方式
         jsonp : 'callback', //指定一个查询参数名称来覆盖默认的 jsonp 回调参数名 callback
         jsonpCallback: 'handleResponse', //设置回调函数名
         data : {
             q : "javascript",
             count : 1
         },
         success: function(response, status, xhr){
             console.log('状态为：' + status + ',状态是：' + xhr.statusText);
             console.log(response);
         }
     });

 ```
 jquery的方式看起来像ajax请求，但本质还是jsonp


