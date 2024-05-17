# midjourney
midjourney plugin on chatgpt-on-wechat

## 插件描述

本插件旨在将绘图请求转发至 Midjourney，适用于 chatgpt-on-wechat 项目。通过安装本插件，用户可以在钉钉、微信等通信工具中集成该功能，从而在聊天会话窗口中实现指令绘图。
## 环境要求

请**安装**本插件的依赖包

```
pip3 install apscheduler requests Pillow
```

### midjourney-proxy API docker部署
更多参考到 [midjourney-proxy](https://github.com/novicezk/midjourney-proxy) 开源光光
```bash
docker run -d --name mj6013  -p 6013:8080  \
-e mj.discord.guild-id=discord服务ID  \
-e mj.discord.channel-id=discord服务组ID   \
-e mj.queue.timeout-minutes=6 \
-e mj.api-secret=abc123456 \
-e mj.discord.user-token=**********  \
--restart=always novicezk/midjourney-proxy:2.5.5
```

## 使用说明

请将`config.json.template`复制为`config.json`，并修改其中的参数和规则。

## 支持功能
- [x] midjourney 文生图
- [x] midjourney 垫图+文生图
- [X] midjourney 图变 U1到U4 、 V1到V4、重绘等操作
- [X] midjourney 支持1.5倍变焦 2倍变焦
- [X] midjourney 支持2倍高清 4倍高清
- [X] midjourney 支持左、右、上、下延伸变化
- [X] midjourney 同时支持[midjourney-proxy](https://github.com/novicezk/midjourney-proxy) 接口 和 [midjourney-proxy-plus](https://github.com/litter-coder/midjourney-proxy-plus) 接口
- [X] midjourney 图生文
- [X] 支持midjourney、niji 不同机器人
- [X] midjourney 混图
- [X] midjourney 获取 seed
- [X] midjourney 任务查询


### 帮助

```
Midjourney:这是一个能调用midjourney实现ai绘图的扩展能力。
使用说明:
/imagine 根据给出的提示词绘画;
/img2img 根据提示词+垫图生成图;
/up 任务ID 序号执行动作;
/describe 图片转文字;
/shorten 提示词分析;
/seed 获取任务图片的seed值;
/query 任务ID 查询任务进度;
默认使用🐢 Relax绘图，也可以在提示词末尾使用 --relax 、--fast 参数运行单个作业;
支持图片回复前缀关键字：画。
使用格式：画一棵装饰着金色雪花和金色饰品的圣诞树，周围是地板上的礼物。房间是白色的，有浅色木材的装饰，一侧有一个壁炉，大窗户望向户外花园。一颗星星挂在高约三米的绿色松树顶上。这是一个充满节日庆祝气氛的优雅场景，充满了温暖和欢乐。一张超逼真的照片，以高分辨率2000万像素相机的风格拍摄。
```
