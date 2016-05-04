# 第一篇：基本概念


## 定义

`BitTorrent` 是一个由 Bram Cohen 设计的`对等的(Peer-To-Peer)`文件传输协议，其官方网站是 [http://www.bittorrent.com]( http://www.bittorrent.com)。
`BitTorrent` 被设计于帮助在`伙伴(Peer)`之间，通过不可靠网络传输文件。

## 目的

编纂本文档的目的在于详细地描述 BitTorrent v1.0 协议的内容——Bram的那一篇[《BitTorrent协议规范》](http://bittorrent.org/beps/bep_0003.html)使用通俗的语言描述了协议的规范，却未描述关于行为上的细节规则。本文档致力于使用清晰、明确的文字描述协议，以成为 BitTorrent v1.0 协议的正式规范文档，以便将来作为扩展、升级协议的参考基础。

## 范畴

本文档仅适用于 BitTorrent v1.0 协议本身，目前包括`种子文件结构`、`伙伴通信协议`以及`Tracker HTTP(S) 协议`等规范。如果有更新的版本，应当在另一番专门的文档里对其进行描述，而非本文档内。

## 相关文献

