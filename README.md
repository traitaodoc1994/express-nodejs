# Express

# 1. Routing
Routing trong express dùng để xác định xem client truy cập đến URL nào, xử lý request và phản hồi lại cho client. Ví dụ đơn giản về Route:
```javascript
var express = require('express')
var app = express()

// trả về "hello world" khi thực hiện request với phương thức GET với đường dẫn vào thư mục gốc
app.get('/', function (req, res) {
  res.send('hello world')
})
````
+ Route methods

Route method dùng để xác định xem client thực thiện request với phương thức nào và phản hồi lại cho client. Đoạn code dưới đây
cho thấy client cùng truy cập vào đường dẫn thư mục gốc nhưng với các phương thức truy cập khác nhau sẽ đưa ra phản hồi khác nhau:

```javascript
// GET method route
app.get('/', function (req, res) {
  res.send('GET request to the homepage')
})

// POST method route
app.post('/', function (req, res) {
  res.send('POST request to the homepage')
})
```

+ Route parameters

Lấy các thông số truyền qua URL dựa vào vị trí của chúng trên URL. Ví dụ:
```javascript
app.get('/users/:userId/books/:bookId', function (req, res) {
  res.send(req.params)
})
// VD: /users/trung/books/1
// req.params: { "userId": "trung", "bookId": "1" }
```



