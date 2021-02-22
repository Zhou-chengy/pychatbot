# 小懒猫闲聊SDK

![pypi](https://img.shields.io/pypi/v/pychatbots?color=gold&label=pychatbot&logo=pychatbot&logoColor=grey&style=plastic)  [![MIT Licence](https://badges.frapsoft.com/os/mit/mit.svg?v=103)](https://opensource.org/licenses/mit-license.php) [![unstable](http://badges.github.io/stability-badges/dist/unstable.svg)](http://github.com/badges/stability-badges) [![experimental](http://badges.github.io/stability-badges/dist/experimental.svg)](http://github.com/badges/stability-badges) [![deprecated](http://badges.github.io/stability-badges/dist/deprecated.svg)](http://github.com/badges/stability-badges) [![Gitter](https://badges.gitter.im/Pychatbot/community.svg)](https://gitter.im/Pychatbot/community?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)

## 这是小懒猫AI推出的闲聊SDK1.1.3版本。这个SDK是pyd文件。

### 下载方式
```

pip install pychatbots

python -m pip install pychatbots

```

### 注意：1.采用pip下载不支持chat.pyd 2.使用module.pyd请先下载数据集


### 使用说明

#### chat.pyd:

##### 示例：

```Python

-- coding: 'utf-8' --

 from chat import chats

 print("您需要什么帮助")

 while True:

     sel = input()

     q = chats.chat(None,sel,"your-bot-name",age,"x","like")

     print(q)
   
```

##### 函数：

1.chats.chat(self,ji,name,age,xibe,like)

self填任何东西都可以，建议填None

ji填问题

name填机器人的名字

age填机器人的年龄

xibe填机器人的性别

like填机器人的爱好

#### module.pyd:

##### module:

以下modulename不包括文件后缀.h6

这个文件可以为用户定制机器人编写语料库，如编写客服机器人，聊天机器人

预训练模型在module-tool中

###### chat.h6：

这个模型包含404条语料（预训练模型）（通用）

###### hat.txt:

chat.h6对应文件数据集，自己编写数据集请参考

###### chat-1.h6:

内容与chat.h6部分相同（女），101条语料

##### 语料库来源：

1.chatterbot库语料库

2.腾讯智能闲聊

3.网上图片

4.自编

##### 数据集编写规范：

--问题--(分割符，可自定义，但chat.txt,chat-1.txt必须是空格) --答案1#答案2--(分割符，可自定义，但chat.txt,chat-1.txt必须是空格) --相似度--(如1，0.9，0.8，0.7，0.33)（不超过1）

函数

训练函数

module.train(self,g,filename,modulename,encoding)

self填None

g填分割符

filename填数据集文件名(是txt文件)

modulename是模型名

encoding填编码（如gbk,utf-8)

##### 模型使用函数：

module.chat(self,q,modulename)

self填None

q填问题

modulename填模型名(不包括.h6)

modulename是模型名 

##### Best:

module.Best_train(self,g,filename,modulename，encoding)

self填None

g是分割符

filename填数据集名

modulename填模型名

encoding填编码（如gbk,utf-8)

###### Best数据集：

问题（分割符，可自定义，但chat.txt,chat-1.txt必须是空格） 答案

module.Best_chat（self,g,q,modulename):

(其实module_tool中的预训练模型也可以用这个函数使用）

self不填

q填问题

modulename填模型名

q指问题

示例：

```Python

from pychatbots.module import module as chat

chat.train(None,' ','module-tool\chat','module-tool\chat')

while True:

    s = input()

    d = chat.chat(None,s,' ','module-tool\chat')#d = chat.Best_chat(None,s,' ','module-tool\chat

    print(d)
    
```        
        
效果：

``` 

1次/##########/100%
    
......
    
    
你好吗
    
你好

```

##### bot:

这是一个基于module的扩展,可以让聊天机器人不那么傻

示例1：

```Python

from pychatbots.module import bot
    
from pychatbots.module import compare
    
from pychatbots.module import module
    
module.train(None,' ','module-tool\chat','module-tool\chat','utf-8')
    
Zhou = bot('Zhou')
    
Zhou.reset()
    
while True:
    
    s = input()
        
    a = Zhou.bot(s,'小智不能理解','module-tool\chat',',你烦不烦,None)
        
    print(a)
        
```

效果：

```

1次/##########/100%

......

你好

你好

你好

看到你好我都不知道要回什么那就回你好吧，你烦不烦

```

示例2(使用tihuan)：

```Python

from pychatbots.module import bot
    
from module import compare
    
from module import module
    
module.train(None,' ','module-tool\chat','module-tool\chat','utf-8')
    
Zhou = bot('Zhou')
    
Zhou.reset()
    
while True:
    
    s = input()
        
    a = Zhou.bot(s,'，小智','小智不能理解','module-tool\chat',None,['你烦不烦','到底你是机器人还是我是机器人'])
        
    print(a)
```
效果：
```

1次/##########/100%

......

你好(问)

你好(答)

你好(问)

你烦不烦(答)

你好(问)

到底你是机器人还是我是机器人(答)

```


这里的XXX可以自定义

XXX = bot(botname)

这个函数可以创建一个机器人，并生成XXX.bot文件

botname指生成XXX.bot的文件名，不包括.bot。

XX.bot(self,q,chu,Nonesay,modulename,again,tihuan)

self填None

q填问题

chu填对一些没用的词，系统会把这些词去掉。(chu参数可为列表(list)或字符串(str))

Nonesay是当调用Best_chat函数的返回结果是None时，返回的语句。(Nonesay参数可为列表(list)或字符串(str))

modulename指模型名（module)

again填再次问一个问题的后缀，不用可填None或False

tihuan填再次问一个问题的替换句，即可为列表(list)或字符串（不用可填None或False(注意：again和tihuan必须使用其中一项）

XXX.reset()

重置机器人

### compare.pyd:

这是一个chat.pyd的依赖项

函数：

compare(str1,str2)

str1，str2填对比的文本

### pyd文件：

pyd文件采用cython在windows编译的二进制文件，是无法进行反编译。

### 要求：

1.Python3.8.6rc1(必须要下载这个版本)

下载地址：[Python](https://www.python.org/downloads/release/python-386rc1/)

2.chat.pyd需要requests==2.24(查天气）

### 源代码：

本SDK的代码禁止个人获取，只提供服务。

### 使用方法：

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

gitee地址：[gitee](https://gitee.com/Zhou-Chengy/pychatbot)

一般是github先更新
