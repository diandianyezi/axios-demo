# axios

基于Promise的HTTP库，可以用在浏览器和nodejs中

**https://github.com/axios/axios**



## 特性

* 从浏览器中创建xhr
* 从nodejs中创建http请求
* 支持Promise API
* 拦截请求和响应
* 转换请求数据和响应数据
* 取消请求
* 自动转换JSON数据
* 客户端支持防御XSRF（TODO）

## 使用

可执行多个并发请求

```javascript
function getUserAccount() {
  return axios.get('/user/12345');
}

function getUserPermissions() {
  return axios.get('/user/12345/permissions');
}

axios.all([getUserAccount(), getUserPermissions()])
  .then(axios.spread(function (acct, perms) {
    // 两个请求现在都执行完成
  }));
 
```

### axios API

axios(config)：可通过传递相关配置来创建请求

axios(url[,config])

```javascript
// 发送 GET 请求（默认的方法）
axios('/user/12345');
```

### 请求方法别名

##### axios.request(config)

##### axios.get(url[, config])

##### axios.delete(url[, config])

##### axios.head(url[, config])

##### axios.options(url[, config])

##### axios.post(url[, data[, config]])

##### axios.put(url[, data[, config]])

##### axios.patch(url[, data[, config]])

###### 注意

在使用别名方法时， `url`、`method`、`data` 这些属性都不必在配置中指定。

### 并发

处理并发请求的助理函数有：

##### axios.all(iterable)

##### axios.spread(callback)

### 创建实例

可以使用自定义配置新建一个axios实例

##### axios.create([config])

```javascript
const instance = axios.create({
  baseURL: 'https://some-domain.com/api/',
  timeout: 1000,
  headers: {'X-Custom-Header': 'foobar'}
});
```

### 实例方法

##### axios#request(config)

##### axios#get(url[, config])

##### axios#delete(url[, config])

##### axios#head(url[, config])

##### axios#options(url[, config])

##### axios#post(url[, data[, config]])

##### axios#put(url[, data[, config]])

##### axios#patch(url[, data[, config]])



### 请求配置

只有url是必需的，默认为get请求

http://www.axios-js.com/zh-cn/docs/#%E8%AF%B7%E6%B1%82%E9%85%8D%E7%BD%AE



### 配置默认值

指定将被用在各个请求的配置默认值

#### 全局axios的默认值

```javascript
axios.defaults.baseURL = 'https://api.example.com';
axios.defaults.headers.common['Authorization'] = AUTH_TOKEN;
axios.defaults.headers.post['Content-Type'] = 'application/x-www-form-urlencoded';

```

#### 自定义实例默认值

```javascript
// Set config defaults when creating the instance
const instance = axios.create({
  baseURL: 'https://api.example.com'
});

// Alter defaults after instance has been created
instance.defaults.headers.common['Authorization'] = AUTH_TOKEN;

```

### 拦截器



### 错误处理



### 取消

使用cancel token

TODO

 

