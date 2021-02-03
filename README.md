### 小懒猫闲聊SDK

### 这是小懒猫AI推出的闲聊SDK1.0.6版本。这个SDK是pyd文件。

### 使用说明

chat.pyd:

示例：

    -- coding: 'utf-8' --

    from chat import chats

    print("您需要什么帮助")

    while True:

         sel = input()

         q = chats.chat(None,sel,"your-bot-name",age,"x","like")

         print(q)

函数：

1.chats.chat(self,ji,name,age,xibe,like)

self填任何东西都可以，建议填None

ji填问题

name填机器人的名字

age填机器人的年龄

xibe填机器人的性别

like填机器人的爱好

### module.pyd:

以下modulename不包括文件后缀.h6

这个文件可以为用户定制机器人编写语料库，如编写客服机器人，聊天机器人

预训练模型在module-tool中

chat.h6：

这个模型包含623条语料（预训练模型）（通用）

chat.txt:

chat.h6对应文件数据集，自己编写数据集请参考

chat-1.h6:

内容与chat.h6部分相同（女），101条语料

语料库来源： 1.chatterbot库语料库

2.腾讯智能闲聊

3.网上图片

4.自编

数据集编写规范：

--问题--(空一格) --答案--(空一格) --相似度--(如1，0.9，0.8，0.7，0.33)（不超过1）

函数

训练函数

module.train(self,filename,modulename)

self不填

filename填数据集文件名(是txt文件)

modulename是模型名

模型使用函数：

module.chat(self,q,modulename)

modulename是模型名 Best:

module.Best_train(self,filename,modulename)

self填None

filename填数据集名

modulename填模型名

Best数据集：

问题（空一格） 答案

module.Best_chat（self,q,modulename):

(其实module_tool中的预训练模型也可以用这个函数使用）

self不填

q填问题

modulename填模型名

q指问题

示例：

    from module import module as chat

    chat.train(None,'chat','chat')

    while True:

        s = input()

        d = chat.chat(None,s,'chat')

        print(d)

compare.pyd:

这是一个chat.pyd的依赖项

函数：

compare(str1,str2)

str1，str2填对比的文本

### pyd文件：

pyd文件采用cython在windows编译的二进制文件，是无法进行反编译。

### 要求：

1.Python3.8.6rc1(必须要下载这个版本)

2.chat.pyd需要requests==2.24(查天气）

下载地址：https://www.python.org/downloads/release/python-386rc1/

2.requests2.24

### 源代码：

本SDK的代码禁止个人获取，只提供服务。

使用方法：

1.下载SDK之后解压，建议下载zip文件（git下载可跳过）

2.把解压的文件改为您的项目名

3.编写py文件，导入参考示例

4.运行

### 用户使用协议：

希望各位用户遵守以下条款：

1.不将SDK发布到CSDN平台(CSDN平台下载很麻烦）

2.在fork此储存库同时，不能更改README.md文件

                          小懒猫AI
联系邮箱：earuil@outlook.com

gitee地址：https://gitee.com/Zhou-Chengy/pychatbot

gitee地址2：https://gitee.com/Lazy-cat-Xiao

一般是github先更新
