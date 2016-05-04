# 第一篇：基本概念


## 定义

`BitTorrent` 是一个由 Bram Cohen 设计的`对等的(Peer-To-Peer)`文件传输协议，其官方网站是 [http://www.bittorrent.com]( http://www.bittorrent.com)。
`BitTorrent` 被设计于帮助在`伙伴(Peer)`之间，通过不可靠网络传输文件。

## 目的

编纂本文档的目的在于详细地描述 BitTorrent v1.0 协议的内容——Bram的那一篇[《BitTorrent 协议官方规范》](http://bittorrent.org/beps/bep_0003.html)使用通俗的语言描述了协议的规范，却未描述关于行为上的细节规则。本文档致力于使用清晰、明确的文字描述协议，以成为 BitTorrent v1.0 协议的正式规范文档，以便将来作为扩展、升级协议的参考基础。

## 范畴

本文档仅适用于 BitTorrent v1.0 协议本身，目前包括`种子文件结构`、`伙伴通信协议`以及`Tracker HTTP(S) 协议`等规范。如果有更新的版本，应当在另一番专门的文档里对其进行描述，而非本文档内。

## 相关文献

- [BitTorrent 协议官方文档](http://bittorrent.org/beps/bep_0003.html)
- [开发者和用户的心愿单](https://wiki.theory.org/BitTorrentWishList)
- [Tracker协议扩展功能](https://wiki.theory.org/BitTorrentTrackerExtensions)

## 本文约定

为了清晰、明确地表述，本文档中使用了一定量的术语，如下：

*BitTorrent*: 指 BitTorrent 协议，下面简称 *BT*。

*伙伴(Peer)*与*BT客户端(Client)*: 本文档中，*同伴*是指一切参与下载（上传）活动的*BT客户端*。因此您的*BT客户端(Client)*也是一个*伙伴(Peer)*，只不过它是运行在您的本地计算机上面的。您可以认为

peer v/s client: In this document, a peer is any BitTorrent client participating in a download. The client is also a peer, however it is the BitTorrent client that is running on the local machine. Readers of this specification may choose to think of themselves as the client which connects to numerous peers.
piece v/s block: In this document, a piece refers to a portion of the downloaded data that is described in the metainfo file, which can be verified by a SHA1 hash. A block is a portion of data that a client may request from a peer. Two or more blocks make up a whole piece, which may then be verified.
defacto standard: Large blocks of text in italics indicates a practice so common in various client implementations of BitTorrent that it is considered a defacto standard.
In order to help others find recent changes that have been made to this document, please fill out the change log (last section). This should contain a brief (i.e. one-line) entry for each major change that you've made to the document.


