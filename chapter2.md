# 第二篇：BEncoding

**BEncoding** 是一种用于组织、描述数据的简洁编码格式，它支持 4 种数据类型：字节串（Byte String）、整数（Integer）、列表（List, 线性表）、字典（Dictionary）。

**BEncoding** 使用不同的格式描述上述类型，下面逐一介绍：

> 为了方便表述，在本文中，每一个使用 **BEncoding** 编码的数据称为 **BE量**，而 **BEncoding** 则简称 **BE**。

-   字节串（Byte String）

    字节串的格式为 `字节串长度:内容`，其中 `字节串长度` 是 ASCII 编码格式的整数字符串，单位为字节，例如：

    ```
    4:abcd
    ```

    表示4个字节的串 `"abcd"`

    ```
    0:
    ```

    表示0个字节的串 `""`

-   整数（Integer）

    整数的格式为 `i整数e`，其中 `整数` 是 ASCII 编码格式的整数字符串，例如

    ```
    i1234e
    ```

    表示整数 `1234`

    ```
    i-1e
    ```

    表示整数 `-1`

    > 注意：

    > 1. `i-0e` 是无效编码；
    > 2. 除了 `i0e` 之外，一切以0开头的整数如 `i03e`, `i011e` 都是无效的编码；
    > 3. 虽然并未规定整数类型的最大值，但是 64位 整数的支持是强制的、必不可少的，以支持超过 4GB 大小的文件。

-   列表（List, 线性表）

    列表的格式为 `l不限数量个BE量e`（小写L开头），例如：

    ```
    l4:spam4:eggse
    ```

    表示 `[ "spam", "eggs" ]`

    ```
    li123e5:helloi111ee
    ```

    表示 `[ 123, "hello", 111 ]`

    ```
    le
    ```

    表示 [] 空列表

-   字典（Dictionary）

    字典的格式为 `d不限数量个BE数据对e`（小写D开头）。**BE数据对**是指一种 **key-value** 结构，其中 **key**是一个BE字节串，一个数据对的格式为 **一个BE字节串+一个BE量**
    
    例如：

    ```
    d3:cow3:moo4:spam4:eggse
    ```

    表示 `{ "cow" => "moo", "spam" => "eggs" }`

    ```
    d4:name5:Angus3:agei23ee
    ```

    表示 `{ "name" => "Angus", "age" => 23 }`

    ```
    d4:spaml1:a1:bee
    ```

    表示 `{ "spam" => [ "a", "b" ] }`

    ```
    d9:publisher3:bob17:publisher-webpage15:www.example.com18:publisher.location4:homee
    ```

    表示 `{ "publisher" => "bob", "publisher-webpage" => "www.example.com", "publisher.location" => "home" }`

    ```
    de
    ```

    表示一个空字典 `{}`

    > 注意：








