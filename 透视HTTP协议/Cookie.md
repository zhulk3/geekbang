Cookie技术涉及到HTTP中的两个字段，Set-Cookie和Cookie，当用户通过浏览器第一次访问服务器时，服务器会在响应报文中加入Set-Cookie字段，当浏览器收到响应报文以后，会将Set-Cookie字段的值保存，下一次再访问这个服务器，将这个值放入Cookie字段一起发送给服务器，服务器就可以根据Cookie的值判断用户之前的访问信息了，然后提供个性化服务。

服务器可以在响应报文中加入多个Set-Cookie字段，客户端的请求报文只有一个Cookie字段，可以有多个值，逗号分隔。

Cookie的有效期可以使用Max-Age设置，是相对时间，单位是秒，浏览器用收到报文的时间加上Max-Age就得到了过期时间，也可以使用Expires，直接设置过期时间。

Domain”和“Path”指定了 Cookie 所属的域名和路径，浏览器在发送 Cookie 前会从 URI 中提取出 host 和 path 部分，对比 Cookie 的属性。如果不满足条件，就不会在请求头里发送 Cookie。

属性“HttpOnly”会告诉浏览器，此 Cookie 只能通过浏览器 HTTP 协议传输，禁止其他方式访问，浏览器的 JS 引擎就会禁用 document.cookie 等一切相关的 API，脚本攻击也就无从谈起了。