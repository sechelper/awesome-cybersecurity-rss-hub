# 网络安全RSS订阅中心

🤩仓库地址：https://github.com/sechelper/awesome-cybersecurity-rss-hub

打造全球网络安全学习资料最丰富的`RSS`订阅中心。

先给坤哥贡献一个`star`在继续看，`star`的是这个仓库吗？这是在`star`全球网络安全学习资料库。

👉配合[ 坤哥网安学习法](https://github.com/sechelper/kunge-cybersecurity-learning)效果更佳。

其它行业想要打造同样的`RSS`订阅中心，加坤哥`vx：aptepoch`，备注：“RSS订阅交流”

## 💥初衷

🙈业内公认学习网络安全入门太难，客观原因很多，其中最大的原因不外乎没有学习方向，看不到前辈们是如何学习的，想要借鉴却无从下手。

那么这个项目可以说**打破**找学习资料难现状，订阅**100+**网络安全学习网站，包括应急、打靶、渗透、代码审计、免杀、CTF、PWN和逆向等技术一网打尽。

每天看着各国大佬的骚操作，能坚持半年小伙伴们挖掘`SRC`、涨薪和突破瓶颈统统不是梦。

## ❤️贡献RSS

期待大家提交自己喜欢的`RSS`（仅限安全行业），在仓库直接提交`PR`或者联系坤哥都可以。

## 🤔如何使用

⭐老规矩`三连+关注`，使用方法 👉 [订阅100+安全干货网站，学习不怕没资料](https://www.bilibili.com/video/BV18k4y1s7Ag)

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

支持全平台订阅，这里推荐几个好用的客户端：

|   平台   |                            客户端                            |
| :------: | :----------------------------------------------------------: |
|   安卓   |     [miniflutt](https://github.com/DocMarty84/miniflutt)     |
| 苹果手机 | [Reading](https://apps.apple.com/cn/app/reading-for-rss/id1611939852) |
|   Mac    | [Fluent Reader](https://github.com/yang991178/fluent-reader) |
| Windows  | [Fluent Reader](https://github.com/yang991178/fluent-reader) |
