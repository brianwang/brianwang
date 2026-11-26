### Hi, I'm brianwang

**我做的事只有一件：把 AI 真正跑起来，跑在真实业务里。**

不写 PPT 方案，不做演示 Demo。下面每一条都是已经在跑、或者你 clone 下来就能跑的东西。

### 我能交付什么

- **能跑的系统** —— 仓库带测试和 CI，不是截图。你 `git clone` 之后直接 `pytest` 就知道真假。
- **线上产品** —— [LumaID Studio](https://www.pictool.pro)：多语言 SaaS，付费订阅、PWA、公开 API，在线上运营。
- **每天在跑的自动化** —— 拼多多订单/商品/消息巡检、闲鱼上架与自动回复、知乎内容发布、20+ 个定时任务，都是生产环境里跑着的，不是玩具脚本。
- **可衡量的效果** —— 用 `rag-eval-kit` 把"改完不知道好坏"变成数字，用 `cron-guard` 保证自动化不会悄悄死掉。

---

## 代表项目

**[deal-radar](https://github.com/brianwang/deal-radar)** ![CI](https://github.com/brianwang/deal-radar/actions/workflows/ci.yml/badge.svg) — AI 接单助手：聚合多渠道需求、按匹配度打分、生成投标信。半自动，人工审核后发出。**有测试，可本地跑通。**

**[China Web Agent Bench](https://github.com/brianwang/cn-web-agent-bench)** ![CI](https://github.com/brianwang/cn-web-agent-bench/actions/workflows/ci.yml/badge.svg) — 中文互联网平台的 agent 评测集。10 个真实任务，首轮成功率 37%，量化了登录墙、反自动化、动态渲染这些英文基准没有覆盖的障碍。

**[rag-eval-kit](https://github.com/brianwang/rag-eval-kit)** ![CI](https://github.com/brianwang/rag-eval-kit/actions/workflows/ci.yml/badge.svg) — RAG 检索评测：recall@k、MRR、命中率。把「改完不知道是好是坏」变成数字。零依赖，可打 HTTP 接口也可当库用。

**[cron-guard](https://github.com/brianwang/cron-guard)** ![CI](https://github.com/brianwang/cron-guard/actions/workflows/ci.yml/badge.svg) — 用心跳文件发现「静默死亡」的定时任务。跑过 20+ 个 cron 之后写的：cron 最危险的失败不是报错，是根本不跑。

**[session-keeper](https://github.com/brianwang/session-keeper)** ![CI](https://github.com/brianwang/session-keeper/actions/workflows/ci.yml/badge.svg) — 多平台浏览器登录态管理。持久化 profile、过期检测、headed 重登引导，解决自动化里最长尾的登录失效问题。


---

## 自己验证

不要求你相信描述，直接跑：

```bash
# 1) deal-radar —— 需求聚合 / 打分 / 投标信
git clone https://github.com/brianwang/deal-radar && cd deal-radar
uv sync --group dev && uv run pytest -q   # 5 passed
uv run ruff check .                       # All checks passed

# 2) cn-web-agent-bench —— 评测集本身的一致性
git clone https://github.com/brianwang/cn-web-agent-bench && cd cn-web-agent-bench
pip install pytest pyyaml && pytest -q    # 22 passed（10 个任务定义全部校验）

# 3) session-keeper —— 登录态管理
git clone https://github.com/brianwang/session-keeper && cd session-keeper
pip install -e . pytest && pytest -q      # 3 passed
python cli.py --help

# 4) rag-eval-kit —— RAG 检索评测
git clone https://github.com/brianwang/rag-eval-kit && cd rag-eval-kit
pip install -e . pytest && pytest -q      # 9 passed

# 5) cron-guard —— 定时任务静默失败检测
git clone https://github.com/brianwang/cron-guard && cd cron-guard
pip install -e . pytest && pytest -q      # 7 passed
```

五个仓库的 CI 都在 GitHub Actions 上真跑，不是摆设。

---

## 在线产品

**[LumaID Studio](https://www.pictool.pro)** — 面向海外的证件照 SaaS。一张照片自动生成合规的签证 / 护照 / 驾照照片：抠图换底、尺寸裁剪、4x6 打印排版。中 / 英 / 日 / 韩 / 西五语言、订阅支付、PWA、公开 API（[文档](https://www.pictool.pro/docs)）。Next.js + Postgres + 阿里云视觉。

---

## 技术栈

`Rust` `Python` `TypeScript` `Next.js` `LLM / RAG / Agent` `MCP` `Playwright` `FastAPI` `Postgres` `IFC` `egui`

---

## 技术轨迹（2012 → 现在）

十四年，一条线：**从写框架，到做数据，到调度硬件，到落地 AI。**

| 年份 | 在做什么 | 仓库 |
|---|---|---|
| 2012–2015 | PHP / 前端轮子时代：框架、脚手架、早年开源导入 | `ts-php`(2012) `blueplan`(2014) `geekedu` `agb` `luckysign` `jqlite`(2015) |
| 2014–2017 | 数据采集：Scrapy 爬虫、社交平台接口对接 | `amazone_comments_crawler`(2014) `suanming`(2016) `tumblr_mediaspider`(2017) |
| 2019–2022 | 行业应用与算法：Webhook 对接、AGV 调度、教育平台 | `fb-webhook`(2019) `agvalgorithrim`(2021) `veduonline`(2022) `trueworld`(2022) |
| 2025 | AI 应用起步：学习规划、长期项目实验 | `aiedu`(2025-07) `communistplan4mankind`(2025-10) |
| 2026 | **AI 落地**：检索评测、自动化监控、agent 评测、产品化 | `rag-eval-kit` `cron-guard` `session-keeper` `cn-web-agent-bench` `deal-radar` `autocar` |

技术栈换了五六轮，不变的是**只做能跑的东西**——上面每一行都能点进去看代码。

---

## 联系

有合作或项目需求，欢迎开 issue 或 GitHub 私信。

---
