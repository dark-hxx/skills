# 公益中转站猎人 · Relay Station Hunter

> 查找、验证、推荐可用的 AI API 公益中转站（免费/注册送额度）。

## 何时使用

- 用户说"查公益站"、"免费中转站"、"免费API"、"白嫖模型"
- 用户想找免费 Claude/GPT/DeepSeek API
- 用户现有中转站挂了，需要替代

**不要用于：** 推荐官方付费API（那是另一回事）；保证某个站长期可用（公益站会挂）

---

## 信息源（多源交叉验证）

| 来源 | 地址 | 说明 |
|------|------|------|
| CSDN实测文 | `blog.csdn.net/2303_79726025/article/details/164029506` | 2026-08 实测7站 |
| GitHub整理 | `gist.github.com/haha0510/ff8da8d08a7a8bac6518f775749ebcd4` | 带注册链接 |
| 公益集盒导航 | `missmihu.github.io/gongyijihe/` | 持续更新的清单 |
| awesome-ai-api | `claws-zh.github.io/awesome-ai-api/zh/` | 排行榜+在线率 |
| GitHub导航 | `github.com/1sh1ro/ai-api-zhongzhuan` | 入口清单 |
| 核验日期 | 每次搜索记录 | 公益站变化快 |

## 搜索关键词模板

```
公益AI API中转站 {当前年月} 免费
AI免费API {当前年月} 实测
Claude/Codex 免费中转 {当前年月}
公益站导航 2026 {当前年月}
```

搜索引擎：DuckDuckGo Lite / Sogou / Bing 轮询（百度有验证码）

## 验证流程（关键）

每个站必须实测，不能只看文章推荐：

```bash
# 1. 检查站点是否在线 + 识别面板类型
curl -sL "https://站点地址" -H "User-Agent: Mozilla/5.0" | grep -oP '<title>[^<]+'
# New API / one-api 面板 → 大概率是真中转
# 无法访问 / 标题异常 → 标记不可用

# 2. 提取注册链接（gist/文章里的 href）
```

**面板识别：**
- `New API` / `one-api` → 主流中转面板 ✅
- `Agent Router` / 自研面板 → 公益网关 ✅
- 直接跳转广告/下载页 → ❌ 假站

## 输出格式

```markdown
## 🆓 公益中转站清单（{核验日期}）

| # | 站点 | 地址 | 适合 | 状态 |
|:-:|:-----|:-----|:-----|:----:|
| 1 | Agent Router | https://agentrouter.org | AI编程 | ✅ 在线 |
...

### 🥇 推荐
（按用户场景推荐1-2个，如AI编程→Agent Router/DoCode）

### ⚠️ 提醒
- 公益站生存周期短，别当生产依赖
- 注册用独立测试Key，设最低额度
- 以注册页实际到账为准
```

## 已知站点库（必须重新验证，不复用）

| 站点 | 地址 | 备注 |
|------|------|------|
| Agent Router | https://agentrouter.org | AI编程，注册送~$100 |
| DoCode | https://docode.cc | AI编程文档全 |
| 肖恩AI | https://free.supxh.xin | 新人额度直观 |
| 芙卡卡の小食堂 | https://api.fuka.win | 桌面客户端友好 |
| GoRouter | https://gorouter.app | Claude路由 |
| 北织 | https://beizhi.sylu.cc | New API面板 |
| (未知) | https://api456.me | New API面板 |

## 用户偏好（马爷）

- 用 GPT 模型做代码开发 → 优先推荐 AI Coding 向站点
- 只相信实测验证，不信文章吹嘘
- 每个站给出**干净地址**（去邀请码）

## 常见坑

1. **邀请码污染** — gist/文章里的链接带 `?aff=` 或 `?code=`，给用户地址时**必去掉**
2. **假站** — 无法访问、标题异常、跳广告的站直接标记
3. **额度变化快** — 页面数字≠承诺，以实际到账为准
4. **生存周期短** — 上次能用这次可能就挂了，每次都要重新核验
5. **国内访问** — 部分站国内直连慢或打不开，需要代理