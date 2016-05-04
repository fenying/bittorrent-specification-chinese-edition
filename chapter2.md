# 第二篇：Bencoding

**Bencoding** 是一种用于组织、描述数据的简洁编码格式，它支持 4 种数据类型：字节串（Byte String）、整数（Integer）、列表（List, 线性表）、字典（Dictionary）。

**Bencoding** 使用不同的格式描述上述类型，下面逐一介绍：

-   字节串（Byte String）

    字节串的格式为 `字节串长度:内容`，其中 `长度` 是 ASCII 编码格式的整数，单位为字节，例如：

    ```
    4:abcd
    ```

    表示4个字节的串 "abcd"

    ```
    0:
    ```

    表示0个字节的串 ""

-   整数（Integer）

    
