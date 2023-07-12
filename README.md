# sehuapush
sehua堂的新帖推送

本人py能力一般，代码只能说凑合用
反正能跑，也不收钱

如遇到bug，请直接提issue
欢迎欢迎欢迎提pr
issue只接受bug和建议，其他勿扰


update:

2023-07-12:不再使用selenium，改为playwright,只能说安装简单了不少, 大概一段时间内不会再有什么大的更新

2023-6-8 :  这两天发现多了很多权限贴，我就弄了下登陆，发现98堂登陆之后页面的xpath居然会变，无语
            理论上登陆应该有个验证是否登陆成功的，不过我也懒得弄了，凑合着用吧,反正其实也用处不大

2023-5-13 : 新增自动获取免翻地址
2023 未知日期 :新增了持久化，存到sqlite3，有需要的下载根目录下的sehua.db自行查看


推荐使用Ubuntu20，因为我用的是ubuntu20，我个人使用是没有问题的

warning ！！！！
1. 本脚本需要一定的计算机/服务器基础才可用，而非懒人一键脚本

2. 强烈建议使用外国服务器，国内服务器需配置代理以使用tg的推送

3. 使用本脚本需要掌握打开网址、输入文字、点击搜索等高端技术

如果已经放弃：这个是我自己搭的，https://t.me/sehuazonghe 不过只有综合区和原创区，如果对其他区有兴趣可以试试自己搭，
其他区参考参考进阶2


以下是配置环境
安装环境，需要python3

1. python3 使用服务器自带或者装个3.6以上应该都可，安装方式自行百度

2. 如果服务器已经有pip，直接pip install -r requirements.txt 
    如果没有，请先百度/谷歌 “服务器名称+如何安装pip”

3.  安装完毕之后，在命令行输入 `playwright install` 
    用以安装playwright环境

4. 脚本需要在后台运行，所以需要使用screen 或者nohup
    墙裂推荐使用screen，安装、使用方法百度/谷歌，一般都是一行代码
    ubuntu安装是apt install screen 

以下是使用教程
1. 点击https://t.me/BotFather 创建一个机器人，获取机器人token （创建完会自动发你）

2. 创建一个频道，把刚才创建的机器人拉进群并设为管理员

3. 打开频道信息，有个id，复制这个id，前面加上-100 就是推送id

4. 分别把token和频道id放到98.json中

5. （可选）填写times和timed，如20和40，脚本会在20到40秒之内检查一次更新，请勿填过小的数字
    不填默认为20 40

6. python 98push.py

进阶 
warning2 ！！！
以下不推荐使用

1. 国内搭建：需要使用代理，需要使用代理，需要使用代理
    首先把98push.py的proxies中填入你的代理，
    然后把url1改为国内可访问的镜像地址

2. 获取其他区的新帖：更改代码底部的url_sehua即可,
    其他区本人未测试，如有错误，请自行修改
    
    获取链接方法：
    进入分区之后，查看当前页面的地址,找到其中的fid
    修改替换底部url_sehua的fid即可

3. 可使用selenium操作浏览器登陆账号，以预览权限贴
    在98.json中配置账号密码即可
    注意不同的镜像站的格式和官方可能有出入，所以登陆之后我的代码或许就会不可用
    所以慎重登陆，另外建议不要使用这种方式签到

4. 我使用的是MarkdownV2格式推送，如果你想用html等其他格式，也可自行更改
