### Hi, I'm brianwang

**从模型到落地，全链路能自己走完。** 后端服务、浏览器自动化、检索评测、产品化上线——每一层都有能跑、能验证的东西。

**在做的方向**：让 AI agent 真正能操作软件和网页，而不只是聊天。

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

## 联系

有合作或项目需求，欢迎开 issue 或 GitHub 私信。

---

## 技术轨迹（2012 → 现在）

十四年，一条线：**从写框架，到做数据，到调度硬件，到落地 AI。**

| 年份 | 在做什么 | 留下的东西 |
|---|---|---|
| 2012–2015 | PHP / 前端轮子时代：框架、脚手架、开源导入项目 | `ts-php`、`jqlite`、`ogame-opensource` |
| 2014–2017 | 数据采集：Scrapy 爬虫、社交媒体接口对接 | `amazone_comments_crawler`、`tumblr_mediaspider`、`fb-webhook` |
| 2019–2022 | 行业软件与算法：AGV 调度、教育平台 | `agvalgorithrim`、`autocar`、`veduonline` |
| 2025 | AI 应用起步：学习规划、需求匹配 | `aiedu`、`deal-radar` |
| 2026 | **AI 落地**：检索评测、浏览器自动化、agent 评测、产品化 | `rag-eval-kit`、`cron-guard`、`session-keeper`、`cn-web-agent-bench`、`pictool.pro` |

每一段都不是收藏，是当时真在做的项目。技术栈换了四五轮，不变的是**只做能跑的东西**。

