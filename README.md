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

源代码：

本SDK的代码禁止个人获取，只提供服务。

使用方法：

1.下载SDK之后解压，建议下载zip文件（git下载可跳过）

2.把解压的文件改为您的项目名

3.编写py文件，导入参考示例

4.运行

gitee地址：https://gitee.com/Zhou-Chengy/pychatbot

gitee地址2：https://gitee.com/Lazy-cat-Xiao

