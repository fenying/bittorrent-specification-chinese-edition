# 第四篇：Tracker 协议

Tracker 是一个基于 HTTP(S) 的服务器，通过 HTTP GET 的方法提供服务。**BT客户端**通过 HTTP GET 请求，发送上传、下载相关的信息到 Tracker，以助于 Tracker 统计**种子**的数据信息。请求的返回数据中，包括当前参与该种子上传、下载的**伙伴**信息列表。

是