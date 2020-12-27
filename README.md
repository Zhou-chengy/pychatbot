这是小懒猫AI推出的闲聊SDK1.0.1版本。这个SDK是pyc文件,

示例：

-- coding: 'utf-8' --

from chat import chats

print("您需要什么帮助")

while True:

    sel = input()
    
    q = chats.chat(None,sel,"your-bot-name",age,"x","like")
    
    print(q)

compare.pyc:

这是一个chat.pyc的依赖项
