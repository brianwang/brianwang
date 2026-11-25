### Hi, I'm brianwang

做 AI 应用开发和 agent 工程。喜欢把复杂系统拆成可验证的小块，用能跑的原型代替演示文稿。

**在做的方向**：让 AI agent 真正能操作软件和网页，而不只是聊天。

---

## 代表项目

**[deal-radar](https://github.com/brianwang/deal-radar)** ![CI](https://github.com/brianwang/deal-radar/actions/workflows/ci.yml/badge.svg) — AI 接单助手：聚合多渠道需求、按匹配度打分、生成投标信。半自动，人工审核后发出。**有测试，可本地跑通。**

**[China Web Agent Bench](https://github.com/brianwang/cn-web-agent-bench)** ![CI](https://github.com/brianwang/cn-web-agent-bench/actions/workflows/ci.yml/badge.svg) — 中文互联网平台的 agent 评测集。10 个真实任务，首轮成功率 37%，量化了登录墙、反自动化、动态渲染这些英文基准没有覆盖的障碍。

**[session-keeper](https://github.com/brianwang/session-keeper)** ![CI](https://github.com/brianwang/session-keeper/actions/workflows/ci.yml/badge.svg) — 多平台浏览器登录态管理。持久化 profile、过期检测、headed 重登引导，解决自动化里最长尾的登录失效问题。

**[BIMCraft](https://github.com/brianwang/bimcraft-showcase)** — 用纯 Rust 从零实现的 BIM 工作流，可被 agent 通过 MCP 驱动。自研几何内核、2D/3D 渲染、IFC 读写、族系统、跨平台打包。早期开发，源码私有。

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
```

三个仓库的 CI 都在 GitHub Actions 上真跑，不是摆设。

---

## 在线产品

**[LumaID Studio](https://www.pictool.pro)** — 面向海外的证件照 SaaS。一张照片自动生成合规的签证 / 护照 / 驾照照片：抠图换底、尺寸裁剪、4x6 打印排版。中 / 英 / 日 / 韩 / 西五语言、订阅支付、PWA、公开 API（[文档](https://www.pictool.pro/docs)）。Next.js + Postgres + 阿里云视觉。

---

## 技术栈

`Rust` `Python` `TypeScript` `Next.js` `LLM / RAG / Agent` `MCP` `Playwright` `FastAPI` `Postgres` `IFC` `egui`

---

## 联系

有合作或项目需求，欢迎开 issue 或 GitHub 私信。
