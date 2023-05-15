
<h1 align="center">GetBilibiliUserInfo</h1>
<div align="center">
<a href="https://github.com/GaiZhenBiao/ChuanhuChatGPT">
<img src="logo.png" alt="Logo" height="300">
</a>

<p align="center">
<h3>一个基于Python3.7开发的全自动bilibili用户信息爬取工具</h3>
<p align="center">
<a href="http://qm.qq.com/cgi-bin/qm/qr?_wv=1027&k=SQ2EDC77_dObl8QOdmwMVxw39H8Ur1Ax&authKey=OD1jf7NyaNkZu0HpXuhjnFPTA9hWdxcmiU72rteVclsIWSziS1bjThC8OJaK36sV&noverify=0&group_code=893018099">
<img alt="加入QQ交流群" src="https://img.shields.io/badge/QQGroup-893018099-blue" />
</a>
<p>
自动爬取 / 词云生成 / 保存结果 / 数据文件生成(供GPT) <br />
大会员信息查询 / 实时硬币数量查询 / 实时等级信息查询 / 注册时间查询 / 直播间浏览查询 / 直播间发言查询...　<br />
<br />
示例文件，数据来源UID2
<br />
<a href="https://github.com/cwuom/GetBilibiliUserInfo/blob/main/datas/%E7%A2%A7%E8%AF%97_2.txt"><strong>主要数据文件</</a> | 
<a href="https://github.com/cwuom/GetBilibiliUserInfo/blob/main/gpt_datas/gpt_2_%E7%A2%A7%E8%AF%97.txt"><strong>GPT数据文件</</a> |
<a href="https://github.com/cwuom/GetBilibiliUserInfo/blob/main/wordcloud_data/WordCloud_%E7%A2%A7%E8%AF%97_2.png"><strong>词云展示文件</</a>
</p>
</p>
</p>
</div>



# 快速上手此项目🔨
### 克隆源码🪄

```cmd
git clone https://github.com/cwuom/GetBilibiliUserInfo.git
cd GetBilibiliUserInfo
pip install -r requirements.txt
python main.py
```

### 直接上手👨‍💻

若你在克隆源码时遇到困难，那么您可以直接运行我们提供的[打包版本](https://github.com/cwuom/GetBilibiliUserInfo/releases "exe版本")，此版本更新速度随缘，**建议直接克隆源码**
> 注意: 使用此方式部署体积较大(300M)，更新速度慢

------------
  
# 使用方式
- 初次使用需提交您的B站cookies，此项目依靠cookies爬取更多信息。
- 当cookies校验通过，后续只需要提供用户mid(uid)就可以爬取所有信息。
- 每当爬取完部分数据需要您回车确认后再进行下一步，在生成词云前您可以输入n取消生成。GPT数据同理


------------

# 数据收集🕵️

## 您需要提供的数据📃
1. 您的**bilibil cookies**
2. 您需要爬取的用户mid(uid)


## 程序返回给您的数据📃

<details>
<summary>点击展开</summary>

#### 注: 括号内的详细数据来源自UID2，部分其他来源会标注在末尾

### 主页数据
1. 昵称
2. 性别
3. rank
4. 头像链接
5. 硬币数量
6. DisplayRank
7. 注册时间 (2009-06-24 14:16:45)
8. 生日
9. 个性签名
10. 粉丝数量 (精确到个位)
11. 关注数
12. 关注他的知名UP

### 经验/等级数据
1. 当前经验数量 (226644exp)
2. 当前等级
3. 下一级所需经验数量
4. 当前等级所需经验数量
5. 升级进度 
> 低于LV6: 还差6666exp可升级，当前进度为76.85416666666667% (来自UID102570170)
> 高于LV6: 此人等级已经爆表！超出LV6 197844exp

### 视频/专栏数据
1. 视频总浏览量 (精确到个位)
2. 文章总浏览量 (精确到个位)
3. 总浏览量 (视频浏览量 + 专栏浏览量)
4. 总被赞数
5. 被赞率 (总被赞数 / 总播放量)

### 大会员信息 
1. 会员状态 (有/无)
2. 会员类型 (年度及以上大会员 / 月大会员/ 无)
3. 到期时间 (2094-07-31 00:00:00) 
4. 电视大会员状态 (开通电视大会员 / 未开通电视大会员)
5. 大会员角色 (月度大会员  / 年度大会员  /十年大会员  / 百年大会员)

 
### 直播间数据
1. 是否有房间 (有/无)
2. 开播状态 (未开播 / 直播中)
3. 直播间URL (https://live.bilibili.com/1024?broadcast_type=0&is_room_feed=0)
4. 直播间标题 (试图恰鸡)
5. 直播间封面(http://i0.hdslb.com/bfs/live/new_room_cover/96ee5bfd0279a0f18b190340334f43f473038288.jpg)
6. 直播间ID (1024)
7. 是否轮播 (未轮播 / 轮播)

----


### 访问直播间数据
 1. 观看主播数量 (共观看了74名主播)
 3. 观看直播次数 (280次)
3. 访问排行
```
========================================
UID:434334701 - name:七海Nana7mi - 观看49次
========================================
UID:463999 - name:波喵喵喵 - 观看36次
========================================
UID:6189069 - name:小糖发财 - 观看29次
========================================
UID:370687588 - name:花留Karu - 观看21次
========================================
UID:867152 - name:蕾蕾大表哥 - 观看17次
========================================
UID:28278455 - name:香菇滑鸡_ - 观看15次
========================================
UID:548076 - name:樱群 - 观看5次
========================================
...

```

4. 自监听以来所有进入直播间进入事件
```
========================================
访问主播ID: 樱群 - 548076
进入直播间日期: 2023-05-13 14:34:08
========================================
访问主播ID: 小糖发财 - 6189069
进入直播间日期: 2023-05-12 11:45:30
...
========================================
访问主播ID: 波喵喵喵 - 463999
进入直播间日期: 2022-06-26 01:52:11
========================================
访问主播ID: 波喵喵喵 - 463999
进入直播间日期: 2022-06-19 18:33:13
```
5. 最后一次访问事件
```
访问主播ID: 樱群 - 548076
进入直播间日期: 2023-05-13 14:34:08
```
6. 自统计最早访问数据
```
访问主播ID: 波喵喵喵 - 463999
进入直播间日期: 2022-06-19 18:33:13
```


 ----


 ### 发言数据
  1. 发言次数 (共发言258次)
  2. 发言排行
```
========================================
在花留Karu - 370687588 - 发言了113次
========================================
在七海Nana7mi - 434334701 - 发言了55次
========================================
在波喵喵喵 - 463999 - 发言了25次
========================================
在蕾蕾大表哥 - 867152 - 发言了14次
========================================
在琉绮Ruki - 420249427 - 发言了11次
========================================
在小糖发财 - 6189069 - 发言了10次
========================================
...
========================================
在狐洛洛子 - 44820 - 发言了2次
========================================
```
 3. 自监听以来所有进入直播间发言事件
 ```
========================================
发言: 14岁！
发送到樱群 - 548076
发言时间: 2023-05-13 14:34:48
========================================
发言: 永远14岁哈
发送到樱群 - 548076
发言时间: 2023-05-13 14:34:57
========================================
发言: 下午好w
发送到樱群 - 548076
发言时间: 2023-05-13 14:35:23
========================================
发言: [抱抱]
发送到樱群 - 548076
发言时间: 2023-05-13 14:35:54
========================================
发言: 你个分奴~
发送到蕾蕾大表哥 - 867152
发言时间: 2023-05-11 21:20:27
========================================
发言: 刑天你好呀
发送到桃核叫我桃道长 - 837470
发言时间: 2023-04-22 14:56:56
========================================
.....
========================================
发言: 给老二次元发小奖金
发送到七海Nana7mi - 434334701
发言时间: 2020-05-31 01:48:04
 ```


### 直播间送礼数据
1. 送礼数量 (共送出879个礼物)
2. 送礼排行
```
========================================
送给七海Nana7mi - 434334701 - 送出361次
========================================
送给花留Karu - 370687588 - 送出270次
========================================
送给波喵喵喵 - 463999 - 送出162次
========================================
送给小糖发财 - 6189069 - 送出48次
========================================
送给琉绮Ruki - 420249427 - 送出19次
========================================
送给樱群 - 548076 - 送出10次
========================================
送给艾因Eine - 421267475 - 送出8次
========================================
送给=咬人猫= - 116683 - 送出1次
========================================
```
3. 自监听以来所有直播间打赏事件
```
========================================
主播ID樱群 - 548076
送礼日期: 2023-05-13 14:34:31
礼物内容: 小花花
========================================
主播ID=咬人猫= - 116683
送礼日期: 2023-01-14 21:49:52
礼物内容: 小花花 x1
========================================
主播ID波喵喵喵 - 463999
送礼日期: 2022-10-25 00:35:08
礼物内容: 爱心抱枕 x1 [¥16]
========================================
...
========================================
主播ID花留Karu - 370687588
送礼日期: 2020-06-13 23:12:47
礼物内容: 小电视飞船 x10 [¥6660]

```

### 可视化数据
1. 通过所有直播间发言数据制作一张词云图
```python
 wordcloud = WordCloud(background_color="white",
                              width=4000,
                              height=3000,
                              max_words=20000,
                              max_font_size=200,
                              contour_width=4,
                              contour_color='steelblue',
                              font_path="PingFang-Bold_0.ttf"
                              ).generate(result)
wordcloud.to_file(f'wordcloud_data\\WordCloud_{name}_{mid}.png')
```

![词云图](https://raw.githubusercontent.com/cwuom/GetBilibiliUserInfo/main/wordcloud_data/WordCloud_%E7%A2%A7%E8%AF%97_2.png)

### GPT数据
1. 昵称
2. 简介
3. 粉丝数量
4. 关注数
5. 直播间发言 (随机抽取250条)
6. 前五观看主播排行
7. 视频信息，包含简介以及标题
![GPT演示1](https://github.com/cwuom/GetBilibiliUserInfo/blob/main/GPT_1.jpg?raw=true)
![GPT演示2](https://github.com/cwuom/GetBilibiliUserInfo/blob/main/GPT_2.jpg?raw=true)
![GPT演示3](https://github.com/cwuom/GetBilibiliUserInfo/blob/main/GPT_3.png?raw=true)
注: 以上演示图非程序本身提供，需要您把程序给的数据文件投喂给ChatGPT才能达到如上效果! 


</details>

# 注意事项👀

### 数据爬取慢
- 软件本身不需要代理，但是如果你需要爬取很多数据，请打开您的代理再使用本软件。
### 无法访问
- 请检查代理配置或网络设置，若使用代理请将系统代理模式(System Proxy)关闭


# 声明
- 本人只负责整理数据并没有自己的数据库，所有数据大多也是在公开透明的基础上的
- GetBilibiliUserInfo是一个免费的脚本，不会对任何人采取强制收费措施
- 由于项目的特殊性，开发者也许会在未来随时停更或删除此项目
- 请勿滥用，本项目仅用于学习和测试


# 鸣谢❤️
###  灵感来源 
1. [LAPLACE](https://laplace.live/)

### 数据/文档/API 来源
1. [LAPLACE](https://laplace.live/)
2. [SocialSisterYi/bilibili-API-collect: 哔哩哔哩-API收集整理【不断更新中....】](https://github.com/SocialSisterYi/bilibili-API-collect)
3. [ukamnads](https://ukamnads.icu/)
4. [自己 (很多都是自己爬的)](https://space.bilibili.com/473400804)

### 以及被我测试的工具人(doge)

