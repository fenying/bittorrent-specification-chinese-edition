# 第四篇：Tracker 协议

Tracker 是一个基于 HTTP(S) 的服务器，通过 HTTP GET 的方法提供服务。**BT客户端**通过 HTTP GET 请求，发送上传、下载相关的信息到 Tracker，以助于 Tracker 统计**种子**的数据信息。请求的返回数据中，包括当前参与该种子上传、下载的**伙伴**信息列表。

Tracker 的 URL 被包含在种子文件中，即 announce 字段，而请求携带的参数则添加到 URL 的 queryString 中。

> 注意：二进制参数必须转义为 URL 标准编码格式。这意味着除 `[-0-9A-Za-z\._~]` 之外的字符都将被转义为 `%nn` 十六进制格式。参考 [RFC1738](http://www.faqs.org/rfcs/rfc1738.html)。




