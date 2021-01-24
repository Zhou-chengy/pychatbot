这是小懒猫AI推出的闲聊SDK1.0.1版本。这个SDK是pyd文件。

示例：

-- coding: 'utf-8' --

from chat import chats

print("您需要什么帮助")

while True:

    sel = input()
    
    q = chats.chat(None,sel,"your-bot-name",age,"x","like")
    
    print(q)

compare.pyd:

这是一个chat.pyd的依赖项

pyd文件：

pyd文件采用cython在windows编译的二进制文件，是无法进行反编译。

函数：

1.chats.chat(self,ji,name,age,xibe,like)

self填任何东西都可以，建议填None

ji填问题

name填机器人的名字

联系邮箱：earuil@outlook.com

age填机器人的年龄

xibe填机器人的性别

like填机器人的爱好

2.compare(str1,str2)

str1，str2填对比的文本

要求：

1.Python3.8.6rc1(必须要下载这个版本)

下载地址：https://www.python.org/downloads/release/python-386rc1/

2.requests2.24

源代码：

本SDK的代码禁止个人获取，只提供服务。

使用方法：

1.下载SDK之后解压，建议下载zip文件（git下载可跳过）

2.把解压的文件改为您的项目名

3.编写py文件，导入参考示例

4.运行

module.pyd:

这个文件可以为用户定制机器人编写语料库，如编写客服机器人，聊天机器人

预训练模型在module-tool中

chat.pkl：

这个模型包含193条语料（预训练模型）

chat.txt:

chat.pkl对应文件数据集，自己编写数据集请参考

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

q指问题

modulename是模型名

gitee地址：https://gitee.com/Zhou-Chengy/pychatbot

gitee地址2：https://gitee.com/Lazy-cat-Xiao

