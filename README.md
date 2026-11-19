# 抖音数据接口（Douyin API）：视频、评论、用户、热榜、星图、巨量算数

**抖音数据 API · 抖音评论采集 · 抖音视频数据接口 · 抖音用户主页 · 抖音热搜榜 · 星图达人数据 · 巨量算数指数。**

这个仓库是 [okdata](https://okdata.online/zh/?src=gh-douyin-api) 的抖音接口示例：38 个接口在线可用，一个 API Key 调用，按次计费（$0.002 起），不用订阅。不用登录平台账号，不用 Cookie，不开浏览器，所以也不存在账号被风控的问题。

[免费注册拿 Key（送 $0.1 试用额度）](https://okdata.online/zh/signup/?src=gh-douyin-api) · [全部接口文档](https://okdata.online/zh/apis/?src=gh-douyin-api) · [接入 AI（MCP）](https://okdata.online/zh/mcp/?src=gh-douyin-api)

## 接口清单

| 接口 | 说明 | 价格 | 路径 |
|---|---|---|---|
| [抖音视频搜索](https://okdata.online/zh/apis/douyin/videos/search/) | 按关键词搜视频，带点赞、评论、转发和作者。 | $0.02 / 次 | `GET /v1/douyin/videos/search` |
| [抖音视频详情](https://okdata.online/zh/apis/douyin/videos/get/) | 按 ID 或分享链接取一个视频：文案、数据、作者、音乐和话题。 | $0.002 / 次 | `GET /v1/douyin/videos/get` |
| [抖音视频评论](https://okdata.online/zh/apis/douyin/videos/comments/list/) | 视频的一级评论，按最热排序（平台自己的顺序）。 | $0.002 / 次 | `GET /v1/douyin/videos/comments/list` |
| [抖音账号信息](https://okdata.online/zh/apis/douyin/users/get/) | 账号的粉丝数、获赞数、作品数、简介和认证。 | $0.002 / 次 | `GET /v1/douyin/users/get` |
| [抖音账号作品列表](https://okdata.online/zh/apis/douyin/users/videos/list/) | 账号发布的视频，从新到旧，带数据。 | $0.002 / 次 | `GET /v1/douyin/users/videos/list` |
| [抖音热搜榜](https://okdata.online/zh/apis/douyin/trends/list/) | 当前热搜榜，带排名和热度。 | $0.002 / 次 | `GET /v1/douyin/trends/list` |
| [抖音星图达人搜索](https://okdata.online/zh/apis/douyin/xingtu/creators/search/) | 在抖音官方达人广场「星图」按内容或昵称找达人，可按粉丝数、近期互动率和性别筛选。返回粉丝数、近 30 天互动率和播放中位数、内容类目，以及植入视频和定制视频的报价（元）。 | $0.004 / 次 | `GET /v1/douyin/xingtu/creators/search` |
| [抖音星图达人报价](https://okdata.online/zh/apis/douyin/xingtu/creators/rates/get/) | 达人在星图上每种合作方式（植入视频、定制视频等）的报价（元）、是否开放接单和结算方式。 | $0.04 / 次 | `GET /v1/douyin/xingtu/creators/rates/get` |
| [抖音评论回复](https://okdata.online/zh/apis/douyin/comments/replies/list/) | 按一级评论 ID 和所在视频 ID 取评论下的回复，一页一页取：内容、回复者、点赞、发布时间和 IP 属地。评论不存在时和没有回复一样，返回空结果，不报 404。 | $0.002 / 次 | `GET /v1/douyin/comments/replies/list` |
| [抖音话题视频](https://okdata.online/zh/apis/douyin/hashtags/videos/list/) | 按话题 ID 取带这个话题的视频，可按抖音综合排序、最多点赞或最新发布：文案、作者、点赞、评论、分享、收藏和发布时间。 | $0.002 / 次 | `GET /v1/douyin/hashtags/videos/list` |
| [抖音账号搜索](https://okdata.online/zh/apis/douyin/users/search/) | 按关键词找抖音账号，每页约 30 个：账号 ID（douyin.users.get 用的 sec_uid）、名称、头像、粉丝数、作品数和获赞总数。这里没有简介和认证，账号信息接口里有。 | $0.002 / 次 | `GET /v1/douyin/users/search` |
| [抖音视频播放量](https://okdata.online/zh/apis/douyin/videos/metrics/) | 按 ID 或链接取一条视频此刻的数字：播放、点赞和分享。播放数是抖音多数接口不给的。不返回视频的其他信息；published_at 由视频 ID 推出（误差在一分钟内）。 | $0.002 / 次 | `GET /v1/douyin/videos/metrics` |
| [抖音相关视频](https://okdata.online/zh/apis/douyin/videos/related/) | 按视频 ID 取抖音在这条视频旁推荐的相关视频，一次约 10 条：文案、作者、点赞、评论、分享和收藏。推荐每次可能不同；不存在的视频 ID 也会得到一批无关的推荐。 | $0.002 / 次 | `GET /v1/douyin/videos/related` |
| [抖音视频榜](https://okdata.online/zh/apis/douyin/videos/trending/) | 抖音近 24 小时的视频榜之一：低粉爆款、高点赞率、高完播率或高涨粉率。每条带文案、播放、点赞、作者名称和粉丝数，以及这条视频带来的新粉丝。 | $0.002 / 次 | `GET /v1/douyin/videos/trending` |
| [抖音搜索框联想词](https://okdata.online/zh/apis/douyin/keywords/related/) | 在抖音搜索框输入一个词时下拉给出的联想词（自动补全），按抖音列出的顺序，一次约 10 个。只有词和名次，没有指数。没有联想词时返回空列表。 | $0.02 / 次 | `GET /v1/douyin/keywords/related` |
| [抖音巨量算数品牌指数趋势](https://okdata.online/zh/apis/douyin/index/brands/history/) | 按品牌名和起止日期取品牌在抖音上逐日的搜索指数、内容指数和传播指数（巨量算数），带品牌所属行业。指数是平台算出的分，不是次数。日期是中国时间的自然日。 | $0.002 / 次 | `GET /v1/douyin/index/brands/history` |
| [抖音巨量算数品牌指数对比](https://okdata.online/zh/apis/douyin/index/brands/metrics/) | 按品牌名和起止日期取品牌在抖音上搜索、内容、传播指数的日均值（巨量算数），并带同行业全部品牌和前 3、5、10、15、30 名品牌的均值作对照。指数是平台算出的分，不是次数。 | $0.002 / 次 | `GET /v1/douyin/index/brands/metrics` |
| [抖音巨量算数达人热门视频](https://okdata.online/zh/apis/douyin/index/creators/videos/list/) | 按抖音账号的数字 ID 和起止日期（最多 30 天）取巨量算数给的这个账号的热门视频，最多 20 条，按点赞从高到低：文案、链接、发布日期、点赞、评论、分享和带来的新粉丝。工具多从时间段最后一两天发布的视频里挑，要看哪天就把截止日期设到那天。只有一页，没有播放数。 | $0.002 / 次 | `GET /v1/douyin/index/creators/videos/list` |
| [抖音巨量算数达人粉丝画像](https://okdata.online/zh/apis/douyin/index/creators/audience/get/) | 按抖音账号的数字 ID 取巨量算数给的粉丝画像：性别、年龄、省份、城市（全部城市）、城市等级、手机品牌和兴趣各段的占比。不限星图达人，粉丝够多的账号都有；只给占比，不给人数。 | $0.002 / 次 | `GET /v1/douyin/index/creators/audience/get` |
| [抖音巨量算数达人核心指标](https://okdata.online/zh/apis/douyin/index/creators/metrics/) | 按抖音账号的数字 ID 取巨量算数给的近一周和近一个月日均新增点赞、分享、评论和关注，以及各自和上一周期相比的变化。关注数是平台口径，比粉丝净增大。平台没有数据的账号返回“不存在”。 | $0.002 / 次 | `GET /v1/douyin/index/creators/metrics` |
| [抖音巨量算数关键词人群画像](https://okdata.online/zh/apis/douyin/index/keywords/audience/get/) | 按关键词和起止日期取抖音上关注这个词的人群画像（巨量算数）：年龄、性别、省份、城市、城市等级和兴趣各段的占比和 TGI。 | $0.002 / 次 | `GET /v1/douyin/index/keywords/audience/get` |
| [抖音巨量算数关键词热度趋势](https://okdata.online/zh/apis/douyin/index/keywords/history/) | 按一个关键词或一次最多 5 个关键词加起止日期，取每个词在抖音上逐日的搜索指数和综合指数（巨量算数，即抖音指数），带本期、上期和去年同期的日均值。指数是平台算出的分，不是次数。每个有数的词返回一条，平台没收录的词不在返回里。 | $0.006 / 次 | `GET /v1/douyin/index/keywords/history` |
| [抖音巨量算数关联词](https://okdata.online/zh/apis/douyin/index/keywords/related/) | 按关键词取它在抖音上某一周的关联词（巨量算数）：一起被搜索的词和视频里一起出现的词，各带相关度、相关度名次、搜索指数和综合指数。指数是平台算出的分，不是次数。 | $0.002 / 次 | `GET /v1/douyin/index/keywords/related` |
| [抖音巨量算数实时热点](https://okdata.online/zh/apis/douyin/index/trends/list/) | 巨量算数的实时热点榜或飙升热点榜，各约 30 条：名次、热点和热点指数（热度）。热点指数是平台算出的分，不是次数。 | $0.002 / 次 | `GET /v1/douyin/index/trends/list` |
| [抖音巨量算数关键词热门视频](https://okdata.online/zh/apis/douyin/index/videos/search/) | 按关键词取巨量算数给出的视频指数最高的 20 条视频：文案、链接、作者昵称、头像和粉丝数、点赞、视频指数和发布时间。只有一页；没有作者 ID（douyin.videos.get 里有）。 | $0.002 / 次 | `GET /v1/douyin/index/videos/search` |
| [抖音达人互动与粉丝趋势](https://okdata.online/zh/apis/douyin/users/history/) | 按抖音账号的数字 ID 取最近 7 天或 30 天的变化（巨量算数）：净增粉丝、新增点赞、评论、分享和作品数，各自和上一周期相比的变化，以及现在的总数。一次最多 5 个账号（其中一个不存在，整批都取不到）。给的是一个周期的合计，不是逐日序列。 | $0.002 / 次 | `GET /v1/douyin/users/history` |
| [抖音星图达人资料](https://okdata.online/zh/apis/douyin/xingtu/creators/get/) | 按星图达人 ID 取这位抖音达人在星图上的资料：昵称、头像、所在地、性别、粉丝数和内容类目。取一个时带抖音账号 ID（sec_uid）、抖音号、签约机构和内容标签；一次取多个（最多 50 个）时改为带植入和定制视频报价、预期 CPM（元）和预估播放量。 | $0.004 / 次 | `GET /v1/douyin/xingtu/creators/get` |
| [抖音星图达人粉丝画像](https://okdata.online/zh/apis/douyin/xingtu/creators/audience/get/) | 按星图达人 ID 取这位抖音达人的粉丝画像：性别、年龄、省份、城市（前十）、城市等级、兴趣、手机品牌、八大人群、消费品类和客单价各段的人数和占比，以及星图最近一次统计的时间。占比是这一段的人数除以所列各段的合计。 | $0.004 / 次 | `GET /v1/douyin/xingtu/creators/audience/get` |
| [抖音星图达人传播数据](https://okdata.online/zh/apis/douyin/xingtu/creators/metrics/) | 按星图达人 ID 取这位抖音达人近 30 天或 90 天视频的传播数据：视频数、播放中位数、平均点赞评论分享、互动率和完播率及其排名，以及预期千次播放成本和单次互动成本（元）。数据算的是全部视频，星图不单给商单视频的数。 | $0.004 / 次 | `GET /v1/douyin/xingtu/creators/metrics` |
| [抖音星图达人作品表现](https://okdata.online/zh/apis/douyin/xingtu/creators/videos/list/) | 按星图达人 ID 取这位抖音达人的视频，从新到旧，每页 20 条，带星图给的数据：播放、点赞、评论、完播率、互动率和时长。商单和日常视频混在一起，不做标注。达人不存在时和没有作品一样，返回空结果。 | $0.004 / 次 | `GET /v1/douyin/xingtu/creators/videos/list` |
| [抖音星图达人内容热词](https://okdata.online/zh/apis/douyin/xingtu/creators/keywords/get/) | 按星图达人 ID 取星图从这位抖音达人少量近期视频里提出的词，最多约 20 个，每个带出现次数（通常是个位数）。这些词常只来自一两条视频，可能是商单，不代表达人的整体内容；看内容方向请用内容分布接口。 | $0.002 / 次 | `GET /v1/douyin/xingtu/creators/keywords/get` |
| [抖音星图达人星图指数](https://okdata.online/zh/apis/douyin/xingtu/creators/scores/get/) | 按星图达人 ID 取星图给这位抖音达人的六项指数：星图指数（综合）和传播、种草、转化、合作、性价比五个分项，每项带得分、同类达人平均分、名次和名次所在的前百分比。 | $0.008 / 次 | `GET /v1/douyin/xingtu/creators/scores/get` |
| [抖音星图达人内容分布](https://okdata.online/zh/apis/douyin/xingtu/creators/content_mix/get/) | 按星图达人 ID 取这位抖音达人近期视频的内容分类：每一类的视频数和占比，用来看达人的内容是否集中在某个品类。 | $0.004 / 次 | `GET /v1/douyin/xingtu/creators/content_mix/get` |
| [抖音星图达人转化能力](https://okdata.online/zh/apis/douyin/xingtu/creators/conversion/get/) | 按星图达人 ID 取这位抖音达人带货视频的转化数据：相关视频数和播放中位数、推荐商品数，以及销售额、千次播放成交额、商品价格、点击成本、组件点击次数和点击率所在的区间。区间是星图给的文字，不是精确值；很多达人（包括带货多的）没有区间，完全没有带货数据的达人返回“不存在”。 | $0.004 / 次 | `GET /v1/douyin/xingtu/creators/conversion/get` |
| [抖音星图营销活动日历](https://okdata.online/zh/apis/douyin/xingtu/campaigns/list/) | 取星图营销日历上和一段时间有交集的活动：平台大事件、电商节点、情绪节点、创意营销和行业活动，每个带名称、介绍、类型、阶段、招商期和活动期。一次给全。 | $0.004 / 次 | `GET /v1/douyin/xingtu/campaigns/list` |
| [抖音星图视频数据报告](https://okdata.online/zh/apis/douyin/xingtu/videos/get/) | 按视频 ID 或链接取星图对一条抖音视频的数据报告：播放、点赞、评论、分享和收藏，加上完播率、互动率、时长、作者粉丝数和作者的星图达人 ID（可接着查达人数据）。只有星图收录的视频才有，多是星图达人的视频。 | $0.004 / 次 | `GET /v1/douyin/xingtu/videos/get` |
| [抖音用户视频（备用版）](https://okdata.online/zh/apis/douyin/backup/users/videos/list/) | 抖音用户视频（douyin.users.videos.list）的备用版，原接口取不到时改调：账号发布的视频，从新到旧，每页 20 条，价格略高。文案、作者、点赞、评论、分享、收藏和发布时间。账号不存在时和没有视频一样，返回空结果，不报 404。 | $0.0025 / 次 | `GET /v1/douyin/backup/users/videos/list` |
| [抖音视频搜索（备用版）](https://okdata.online/zh/apis/douyin/backup/videos/search/) | 抖音视频搜索（douyin.videos.search）的备用版，原接口取不到时改调：按关键词搜视频，可按综合、最新或最多点赞排，可只要最近一天、一周或半年内的。文案、作者、点赞、评论、分享、收藏和发布时间。 | $0.03 / 次 | `GET /v1/douyin/backup/videos/search` |

## 快速开始

1. 在 [okdata 控制台](https://okdata.online/zh/signup/?src=gh-douyin-api) 用邮箱注册，拿到 `okd_` 开头的 Key。
2. 调一次接口：

```bash
export OKDATA_API_KEY=okd_...
curl -G "https://api.okdata.online/v1/douyin/videos/search" \
  -H "Authorization: Bearer $OKDATA_API_KEY" \
  --data-urlencode 'query=露营装备'
```

Python 版在 [examples/quickstart.py](examples/quickstart.py)（只用标准库，会顺带演示翻页）：`python3 examples/quickstart.py`。

返回统一的结构：列表在 `data.items`，下一页用 `page.next_cursor` 传回 `cursor`，这次扣了多少钱在 `meta.billing.amount`，平台不提供的字段为 null 并在 `meta.unavailable` 里写明原因。

## 让 AI 直接用（MCP）

Claude Code：

```bash
claude mcp add --transport http --scope user okdata https://api.okdata.online/mcp --header "Authorization: Bearer $OKDATA_API_KEY"
```

Cursor、Cherry Studio、WorkBuddy 等支持远程 MCP 的客户端：

```json
{
  "mcpServers": {
    "okdata": {
      "url": "https://api.okdata.online/mcp",
      "headers": {
        "Authorization": "Bearer okd_..."
      }
    }
  }
}
```

接好以后直接用中文说需求，比如「抖音视频搜索：露营装备」。AI 会先用免费的 `find`、`describe` 找接口和看价格，再用 `call` 取数据。

## 常见问题

**要登录平台账号吗？** 不用。数据是公开内容，okdata 在服务端获取，你的账号完全不参与。

**怎么收费？** 每个接口单独定价，表里写的就是一次调用的价格；按条计费的接口按实际返回条数算。新账号送 $0.1 试用额度，之后 $10 起充，余额不过期，没有订阅。价格页：https://okdata.online/zh/pricing/ ，计费说明：https://okdata.online/zh/docs/billing/

**和官方开放平台有什么区别？** 官方开放平台只能读授权给你的账号自己的数据，而且要企业资质和审核；这里是平台上任何人都能看到的公开数据，比如搜索结果、别人的笔记或视频、评论、热榜。

**能翻页吗？** 列表接口每页一次调用，把 `page.next_cursor` 原样传回 `cursor` 就是下一页，24 小时内有效。

**出错了怎么办？** 每个错误都有固定的 `code`、中文说明 `message_zh`，以及会不会扣费（`charged`）和要不要重试（`retry`）。全部错误码：https://okdata.online/zh/docs/errors/

## English

Examples for the okdata Douyin API: 38 live endpoints behind one API key, pay per call from $0.002, no platform login or cookies. Sign up at https://okdata.online/signup/?src=gh-douyin-api, docs at https://okdata.online/apis/, MCP at https://okdata.online/mcp/.

## License

MIT. The data comes from the okdata API; its terms apply to API use.
