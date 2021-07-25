成员有王常安、高志成、王旺鑫、王雪瑶、邹广言。\
个人贡献：王常安是组长，主要做到安排分工、拼装小车、训练小车的贡献；高志成是副组长，主要做到安排分工、配置环境、配置树莓派、训练小车的贡献；王旺鑫主要做到拼装小车、训练小车的贡献；王雪瑶书要做到拼装小车、协助训练的贡献；邹广言主要做到配置环境、协助拼装、协助训练的贡献。\
仓库的目录结构：1数据文件夹；2.代码文件夹；3.训练成果文件夹;4、实习日志文档；5、readme. txt文档。\
如何运行？\
1.0 启动\
1.1 DonkeyCar操作\
    用PuTTY连接DonkeyCar的树莓派，输入下列命令：\
    python mycar/manage.py drive\
1.2 PC电脑操作\
    PC上在浏览器输入：192.168.1.31:8887，在Web上控制DonkeyCar。\
2.0 训练自动驾驶\
2.1 收集数据\
    确保收集到的数据质量。\
    在赛道上多练习驾驶几次（不记录数据）；\
    当你确信你可以无误地驾驶10圈时按开始录制；\
    如果碰撞或跑离赛道，请立即按Stop Car停止录制；\
    在收集了10-20圈的良好数据（5-20k图像）之后，可以在小车的ssh会话中使用Ctrl-c停止小车；\
    您收集的数据位于最近的TUB数据文件夹中。\
2.2 将采集的训练数据传输到PC\
    由于Raspberry Pi不是很强大，我们需要将数据传输到PC计算机进行训练。\
    在PC上用FileZilla将raspberry pi中/mycar/data/tub文件发送到PC的/mycar/data/下。\
2.3 训练模型\
    在主机PC上打开一个终端Anaconda prompt，按下列步骤训练模型。\
    d:\
    activate donkey\
    python d:mycar/manage.py train --model mycar/models/mypilot.h5\
2.4 训练模型发送到小车实现自动驾驶\
    现在，再用FileZilla 将你的 model 发送到小车上。\
    现在可以再次启动小车，并将模型传递给自动驾驶仪。\
    python mycar/manage.py drive --model ~/mycar/models/mypilot.h5\
    启动DonkeyCar，选择Local Pilot模式，进行自动驾驶。\
