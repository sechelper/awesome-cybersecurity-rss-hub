# awesome-cybersecurity-rss-hub

打造全网最丰富的网络安全学习资料`RSS`订阅中心。

先给坤哥贡献一个`Star`在继续看，`Star`是给这个仓库吗？这是在`Star`了全球网络安全行业。

👉配合[ 坤哥网安学习法](https://github.com/sechelper/kunge-cybersecurity-learning)效果更佳。

## 💥初衷

🙈业内公认学习网络安全入门太难，客观原因很多，其中最大的原因不外乎没有学习方向，看不到前辈们是如何学习的，想要借鉴却无从下手。

那么这个项目可以说**打破**找学习资料难现状，订阅坤哥整理的**100+**网络安全学习网站。

每天看着各国大佬的骚操作，能坚持半年小伙伴们挖掘`SRC`、涨薪和突破瓶颈统统不是梦。

## 🤔如何使用

⭐老规矩`三连+关注`，使用方法 👉 [B站视频占坑，录制完成补上](https://space.bilibili.com/1233892570)

坤哥将文章划分成几个大的分类，随着不断更新会调整，及时关注b站动态，。

- **安全自媒体**，国内安全自媒体，分享有技术、新闻和商业宣传等
- **技术博客**，国内技术博客，存粹交流分享技术的博客
- **国外-安全自媒体**，国外安全自媒体，分享有技术、新闻和商业宣传等
- **国外-技术博客**，国外技术博客，存粹交流分享技术的博客
- **Exploit**，跟踪漏洞Exploit最新情报
- **漏洞披露**，跟踪`0Day`、`1day`和`Nday`，漏洞爆出第一手资料
- **讨论**，订阅一些站点的讨论帖
- **靶场**，漏洞靶场

这里说下为什么中文版区订阅源区分了国内外，这是由于一些小伙伴英语不扎实，看不懂英文网站，这样的分类方式能快速将英文订阅源屏蔽或者删除。

### 服务器搭建

坤哥使用[miniflux](https://github.com/miniflux/v2)搭建的订阅管理平台，安装的docker-compose配置如下（根据自己实际情况调整，密码记得要修改）：

```yml
services:
  miniflux:
    image: miniflux/miniflux:latest
    ports:
      - "9001:8080"
    depends_on:
      db:
        condition: service_healthy
    environment:
      - DATABASE_URL=postgres://miniflux:secret@db/miniflux?sslmode=disable
      - RUN_MIGRATIONS=1
      - CREATE_ADMIN=1
      - ADMIN_USERNAME=admin
      - ADMIN_PASSWORD=admin.012
  db:
    image: postgres:15
    environment:
      - POSTGRES_USER=miniflux
      - POSTGRES_PASSWORD=secret
    volumes:
      - /opt/miniflux/miniflux-db:/var/lib/postgresql/data
    healthcheck:
      test: ["CMD", "pg_isready", "-U", "miniflux"]
      interval: 10s
      start_period: 30s
volumes:
  miniflux-db:
```

### 客户端

全平台都有对应客户端，这里推荐几个使用：

|   平台   |                            客户端                            |
| :------: | :----------------------------------------------------------: |
|   安卓   |     [miniflutt](https://github.com/DocMarty84/miniflutt)     |
| 苹果手机 | [Reading](https://apps.apple.com/cn/app/reading-for-rss/id1611939852) |
|   Mac    | [Fluent Reader](https://github.com/yang991178/fluent-reader) |
| Windows  | [Fluent Reader](https://github.com/yang991178/fluent-reader) |

## 💰 付费订阅

本项目完全**开源免费**，任何人都可以订阅分享项目内的网站和文章，标明出处即可。

订阅付费是坤哥搭建的服务器，不想自己搭建RSS订阅服务的小伙伴，可以付费订阅。不提供任何安全解答，只是保障小伙伴们正常使用此服务器订阅知识。

👍坤哥也会对付费用户优化文章阅读列表。付费标准（人数上升会调高，维护成本会增加）：

- **免费试用半个月**
- **5元/月**
- **50元/年**

## 💘支持一下

📓其它资料领取和交流，点击下方链接：

- [b站，点赞、收藏、投币三连支持坤哥继续创作](https://space.bilibili.com/1233892570)每周三、周五晚8点准时直播，心里默念三遍，不要错过。
- [关注公众号](https://paper.static.secself.com/img/qrcode/mp_qrcode2.png)
- [交流群01](https://paper.static.secself.com/img/qrcode/qrcode-group-01.png)
- [交流群02](https://paper.static.secself.com/img/qrcode/qrcode-group-01.png)
- [交流群03](https://paper.static.secself.com/img/qrcode/qrcode-group-01.png)

### 💰守护坤哥发际线

<center> <img style="height 400px; width: 400px;" src="https://paper.static.secself.com/img/qrcode/appreciatio-%20code2.jpg"></center>

