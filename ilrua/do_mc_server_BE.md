这篇文章是我20年51节写的，今晚上有空就给搬回来了

所需材料：一个宽带，一个电脑即可

软件需求：Windows系统（最好是win7以上），Sakura frp，MC服务端

### 准备工作：
注册，下载Miao frp内网穿透
官网：https://www.Miaofrp.net

*这里应该有张图*

MC服务端：此处为官方服务端
下载传送门：https://www.minecraft.net/zh-hans/download/server/bedrock/
该链接已炸，把zh-hans改成en-us就能正常下载
![bds](https://i0.hdslb.com/bfs/article/91d9ee48b307556d1019b061e1c86f91d70820d2.png@1320w_702h.webp)

然后把zip包解压到你喜欢的地方
当你这些做完之后，就可以正式开始开服了！

### 第一步是配置端口映射
我们先看看服务器解压出来的东西
![index](https://i0.hdslb.com/bfs/article/fd71a50f0cfc27067198aa7b8d21ba2729f19d17.png@1320w_778h.webp)
找到server.properties，用Windows记事簿打开
server.properties是服务器配置文件，服务器搭建完成后游戏设置的配置都围绕着这个文件进行
![port](https://i0.hdslb.com/bfs/article/bfd5dc8ecc93173a0397a4e7a61bc4b60300feea.png@1320w_1384h.webp)

如上图一样找到server-port这一栏，把数字改成你喜欢的数字（范围是1-65535，但我推荐是1024-65535，因为1-1024是系统端口）
随后打开Miaofrp.net的隧道创建一栏，选择节点创建隧道

本地就填127.0.0.1，端口填你自定义的，远程端口随意

*这里应该有张图*

**注意！注意不要选离你太远或者屏蔽UDP协议的节点！**


随后启动bedrock_server.exe
开启你刚刚整好的隧道
如果没出现报错的话，恭喜你，你的服务器已经可以通过公网来连接了
 ### 配置文件内的翻译：

    server-name=Dedicated
    Server
    # 用作服务器名称
    # 允许值 : 任何字符串

    gamemode=survival
    # 为新玩家设置游戏模式。
    # 允许值 : "survival"(生存), "creative"(创造), 或 "adventure"(冒险)

    difficulty=easy
    # 设定世界的难度。
    # 允许值 : "peaceful"(和平), "easy"(简单), "normal"(普通), 或 "hard"(困难)

    allow-cheats=false
    # 如果设置为"true"，则可以使用类似命令的作弊手段。
    # 允许值 : "true"(是) 或 "false"(否)

    max-players=10
    # 服务端上可以同时在线的最大玩家数。
    # 允许值 : 任意正整数

    online-mode=true
    # 如果设置为"true"，则必须对所有连接的玩家进行Xbox Live身份验证。
    # 无论此设置如何，连接到远程（非本地）服务端的客户端将始终需要Xbox Live身份验证。
    # 如果服务端接受来自互联网的连接，则强烈建议启用联机模式。
    # 允许值 : "true"(是) 或 "false"(否)

    white-list=false
    # 如果为"true"，则必须在"whitelist.json"文件中列出所有连接的玩家。
    # 允许值 : "true"(是) 或 "false"(否)

    server-port=19132
    # 服务端应监听哪个IPv4端口。
    # 允许值 : 1-65535闭区间内的整数 [1, 65535]

    server-portv6=19133
    # 服务端应监听哪个IPv6端口。
    # 允许值 : 1-65535闭区间内的整数 [1, 65535]

    view-distance=32
    # 允许的最大视距（以方块数为单位）。
    # 允许值 : 任意正整数

    tick-distance=4
    # 停止加载区块的距离
    # 允许值 : 4-12闭区间内的整数 [4, 12]

    player-idle-timeout=30
    # 挂机玩家被踢出的时间
    # 允许值 : 任意非负整数

    max-threads=8
    # 服务端使用的最大线程数，如果设置为0，服务端会尽可能多地使用所有线程。
    # 允许值 : 任意非负整数

    level-name=Bedrock level
    # 世界名称以及文件夹名
    # 允许值 : 任何字符串

    level-seed=
    # 为世界定义一个种子
    # 允许值 : 任何字符串

    default-player-permission-level=member
    # 新玩家的游戏模式
    # 允许值 : "visitor"(游客), "member"(会员), "operator"(管理员)

    texturepack-required=false
    # 强制客户端加载服务端资源包
    # 允许值 : "true"(是) 或 "false"(否)

    content-log-file-enabled=false
    # 启用将会使错误内容记录到日志文件中
    # 允许值 : "true"(是) 或 "false"(否)

    compression-threshold=1
    # 要压缩的原始网络有效负载的最小大小
    # 允许值 : 0-65535

    server-authoritative-movement=true
    # 启用服务端权威性移动。 如果为"true"，则服务端将在以下位置重设本地用户输入
    # 客户端的位置与服务端的位置不匹配时，发送服务端更正位置并向下发送至客户端更正。
    # 仅当正确的玩家移动设置为true时，才会进行更正。

    player-movement-score-threshold=20
    # 报告异常行为之前所需的数据不一致的数量。
    # 在 server-authoritative-movement 选项为"false"时失效

    player-movement-distance-threshold=0.3
    # 在检测到异常行为之前，服务端与客户端数值之差。
    # 在 server-authoritative-movement 选项为"false"时失效

    player-movement-duration-threshold-in-ms=500
    # 服务端和客户端位置的时间长度可能不同步 (在 server-authoritative-movement 选项为"false"时失效)
    # 在异常移动计数增加之前。 此值以毫秒为单位定义。
    # 在 server-authoritative-movement 选项为"false"时失效

    correct-player-movement=false
    # 如果为"true"，则移动值超过阈值，客户端的玩家位置将被校正为服务端玩家的位置。
    # 允许值 : "true"(是) 或 "false"(否)

    （来自于MCBBS）

其中：数据压缩（compression-threshold，比代表右边数字大的数据包都压缩）
比较吃CPU，造成性能损失，但是如果最小压缩大小开太大容易费流量。自己权衡。
### 未列出但可选择的配置项目：

    level-type=
    # 世界的类型
    # 可用值DEFAULT，LEGACY，FLAT（无限，有限，超平坦）

* 启动成功后会提示一个域名和端口，这个域名和端口就是你要发给你的小伙伴的
* 然后添加完成后你就可以快乐的玩耍了！
* 常见连接问题：
* 过期的服务端：服务端版本过低，升级服务端或者使用低版本的客户端
* 过期的客户端：客户端版本过低，升级客户端
* 无法连接到外部服务器：网络环境复杂，属正常情况，多试几次就行
* ↑也可能是没关正版验证，去配置文件里把online-mode改成false就行了
* 其他问题请直接私信我（一直显示无法连接到外部服务器也来找我），我会挨个帮忙回答的，如果某个问题出现频次过多的话我会专门写专栏来解答。






>封面：https://img.cncn3.cn/images/pslY.png

>原文章cv号：cv5876332
