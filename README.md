这是小懒猫AI推出的闲聊SDK1.0.1版本。这个SDK是pyd文件,

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
pyd文件不可反编译
