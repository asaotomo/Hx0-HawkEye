# 🦅 Hx0 鹰眼（Hx0 HawkEye）：全栈式轻量抓包、拦截重放与 MCP / AI Agent 安全审计扩展

【[English](./README_EN.md) / 中文】

<!-- 这是一张图片，ocr 内容为： -->
![](https://img.shields.io/badge/网络-无需系统代理-success)<!-- 这是一张图片，ocr 内容为： -->
![](https://img.shields.io/badge/形态-侧栏一体化-5865F2)<!-- 这是一张图片，ocr 内容为： -->
![](https://img.shields.io/badge/会话-同源_XHR_Fetch_WS-00A86B)<!-- 这是一张图片，ocr 内容为： -->
![](https://img.shields.io/badge/能力-抓包_拦截-4285F4)<!-- 这是一张图片，ocr 内容为： -->
![](https://img.shields.io/badge/能力-流量重放-blue)<!-- 这是一张图片，ocr 内容为： -->
![](https://img.shields.io/badge/能力-微型_Fuzz-8B5CF6)<!-- 这是一张图片，ocr 内容为： -->
![](https://img.shields.io/badge/能力-敏感信息检测-FF69B4)<!-- 这是一张图片，ocr 内容为： -->
![](https://img.shields.io/badge/能力-暗链检测-333333)<!-- 这是一张图片，ocr 内容为： -->
![](https://img.shields.io/badge/AI-BYOK_可选-orange)
![](https://img.shields.io/badge/Version-1.0.6-6D28D9) ![](https://img.shields.io/badge/PRO-安全专版_MCP-7C3AED) ![](https://img.shields.io/badge/Agent-浏览器级-2563EB) ![](https://img.shields.io/badge/Release-ZIP_only-0F766E)

<img width="1672" height="941" alt="1.0.6" src="https://github.com/user-attachments/assets/d1e65fd3-66de-4f0d-8ce4-9f2ec8b438a7" />


## v1.0.6 重点更新

> **0920版本更新：** MCP Server 更新至 1.0.12，Chrome / Firefox 共用同一份 MJS，支持双浏览器连接待命；改善工具 schema 兼容与分页，保留 51 个工具，修复端口占用不退出、stdio 结束后残留进程、Firefox 导航取消信号错位及原生输入回执问题。browser_read_text 正文与结构化 value 同步返回，缺失正文显式报错；点击、输入、选择、按键和等待默认返回精简回执，保留状态变化与输入证据，include_elements 可按需附带页面详情；evaluate 默认省略控制台日志（include_logs 可开启），导航默认提供带 ref 的精简预览（include_snapshot 可获取完整观察），大结果使用 next_page_token 续读。修复 SPA 换页 ref 复用、标题误判及查找上下文重复。代理分流修复默认端口校验、无效地址误应用和浏览器代理读取，Firefox 改用原生请求分流；Chrome 未命中规则直连，Firefox 保留浏览器默认路径。页面脚本修复刷新漏注入、保存失败仍执行旧代码、重复注入、禁用脚本被执行及目标偏移，串行化注册并校验保存回执。Agent 截断决策修复请求增加输出预算、关闭该次思考，持续耗尽时明确提示暂停和恢复方式。升级请替换扩展并重新加载，同时替换 MJS、重启 MCP 服务。

> **0906版本更新：** 本次重点优化 Agent 长任务执行与稳定性：修复切换标签页后仍操作旧页、关闭任务页面异常退出、文件发现误触发下载和检查点超限阻断新任务；完善目标/计划进度保留、中断恢复与防重复提交，优化历史同步，并将标题与记忆整理移至后台；增强联网搜索、页面数值证据与 Firefox 输入可靠性，新增 Ctrl+H 抓包界面快捷键，同时同步中英文用户手册与 Chrome/Firefox 发行包。

> **0904版本更新：** 本次重点优化 Agent 多模型兼容性与交互体验：新增按会话保存的深度思考开关，完善 DeepSeek、GLM-5.3-Flash 及本地/自定义模型适配，修复工具调用缺参和长文本溢出并统一 HawkEye Agent 标识；补齐 OpenSSL/CryptoJS AES 口令密文本地解密，修正未知动作误报成功，增强 DeepSeek 空响应重试、诊断及基于真实工具结果的兜底总结，同时同步中英文用户手册与 Chrome/Firefox 发行包。

> **0902 维护更新：** 完善主流模型兼容层，新增智谱 GLM、小米 MiMo、硅基流动预设与 Base URL 套餐端点自动识别，修复智谱/小米历史配置串号并补强请求错误回显；上下文窗口统一为 token 下拉/自定义，已知视觉模型自动开启图片输入；同时修复侧栏未打开时后台广播产生的 `Receiving end does not exist` 错误，并同步中英文用户手册。

> **0830 更新包：** 在不降低抓包与拦截覆盖率的前提下，补强 Firefox 抓包监听初始化、请求头/请求体保留、智能 Web 编解码、Chrome/Firefox 可信输入及截图证据落盘；同步更新中英文用户手册、MCP/Agent 安装说明和主流 Browser MCP 对比。

- **鹰眼浏览器自动化 MCP（PRO）**：定位类似面向安全专版的 Playwright MCP。Codex、Cursor、LM Studio 等 Agent Host 接入 `hx0-hawkeye` 后，可让 Host 中的模型自动调用浏览器与鹰眼工具控制真实标签页完成任务；支持 stdio、Streamable HTTP 和 legacy SSE，独立于扩展内 AI 任务台。
- **浏览器级 Agent（PRO）**：直接在用户真实标签页与登录态中自主规划、多轮执行导航、复杂控件 / iframe 交互、抓包研判、重放验证、联网研究与原生下载，不是普通聊天或单次 AI 报告；Agent 模式仅在有效试用或专业版授权下可用。
- **1.0.6 社区版能力开放**：相比 1.0.5，智能代理分流器、全量深度搜索、内置 / 自定义敏感信息匹配与关键词库已向社区版开放。
- **Firefox 与 Chrome 性能重构**：DOM 快照改为单次线性遍历与有界输出，视口外元素早过滤；Firefox `webRequest` 监听器按状态动态注册 / 卸载；Agent / MCP 传输紧凑化、通知批处理、观察器复用、大结果支持 `next_cursor` 续读，不牺牲任务证据完整性。
- **可信输入与证据落盘**：Chrome 优先使用 CDP `Input.dispatchKeyEvent` / `Input.dispatchMouseEvent`，Firefox 使用原生输入中继与聚焦回退；`browser_screenshot` 可在显式传入 `save_to_file: true` 时把图片保存到本地，默认仍只返回图片、不写磁盘。
- **Skills 双重显式授权**：内置渗透 / CTF 知识库更新至 v1.0.6；Agent 新会话默认不启用 Skills。用户须先在「高级设置」启用允许的 Skill / 子模块，再点击当前 Agent 会话的 `Skills`；Agent 只能在该允许列表内按目标适时调用。

<img width="1800" height="1382" alt="Codex、Cursor、LM Studio 等 Agent Host 通过 HawkEye MCP 自动控制浏览器" src="https://github.com/user-attachments/assets/ff0c2671-6559-4f38-b6f5-2a6a50c5375a" />

<img width="1500" height="900" alt="v1.0.6 浏览器级 Agent" src="https://github.com/user-attachments/assets/26994329-4e55-42c4-b48d-9a60153ae146" />

## 一、它是什么
**告别繁琐代理，真正开箱即用。** Hx0 鹰眼是一款面向 Chrome、Firefox 和主流 Chromium 浏览器的轻量级安全工作台。它在用户真实标签页与登录态中统一提供**抓包与拦截改包（含 WebSocket）、流量重放、微型 Fuzz、敏感信息 / 暗链检测、AI 安全审计、HawkEye MCP 与浏览器级 Agent（PRO）**，让人工分析、外部 Agent Host 和扩展内自动化共享同一套浏览器证据与安全工具。

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774273422290-60039442-71ed-433c-847f-0f7d0bd25a30.png)

#### ⚡ 核心优势：为什么不用传统代理？
+ **零环境依赖**：无需打开 Burp Suite，不必改系统代理，无需信任根证书或配置 Java 环境。
+ **绝对会话一致**：直面页面 XHR / Fetch 流量，与当前标签页**同源登录态完全一致**，彻底消除“代理丢 Cookie”、“频繁掉登录”的痛点。
+ **开箱即用**：安装即生效，特别适合日常研发联调、接口排障及授权范围内的安全初筛。

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774269918968-23f970cf-1f27-44aa-bc69-e05b5551da1e.png)

#### 🤖 杀手锏：全流程 AI 智能赋能 (BYOK)
支持接入自有模型 API（BYOK），将 AI 无缝嵌入侧边栏工作流：

+ **智能用例与 Payload 生成**：在重放工作台自动梳理结构化测试思路；在微型 Fuzz 中结合上下文动态生成变异 Payload，告别臃肿的传统字典。

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774257395236-cc582664-756a-413d-9d6c-0ed8f36cab6a.png)

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774257742193-c672230d-4ea0-40ba-9747-06c858bfc9de.png)

+ **单包深度解读**：对复杂的 Request / Response 全文进行语义级 AI 解析，辅助风险研判。

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774255462153-66d3b0c9-abac-4290-bcb8-91a7adceca38.png)

+ **批量归纳与分析**：在独立工作台中勾选多条数据包，AI 自动从接口族、第三方调用中提取规律，辅助供应链、依赖面等横向风险初筛。

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774271731456-5f99fae9-fa00-4967-b9c4-4361b9172a86.png)

+ **双引擎静态狩猎**：**内置暗链检测规则 + AI 上下文语义解读** 强强联合，批量复盘多页面威胁，无死角覆盖静态隐患。

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774258901614-db5c3228-94c3-478d-83ef-7ec7b558268d.png)

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774260323302-dbd7d1ed-c2a1-46bc-8b45-873f767c3e06.png)

---

## 二、开发背景
在 **前后端分离、SPA、大量 XHR/Fetch / WebSocket** 的日常研发与安全测试中，工程师经常需要在「浏览器真实会话」与「抓包 / 改包 / 重放」之间反复切换：传统代理类工具（如 Burp）能力上限高，但需改系统代理、信任证书，且与浏览器标签页的 **Cookie / 登录态** 容易出现断层；地址栏旁的轻量扩展又往往 **缺少持久历史、结构化详情与闭环工作台**。

**Hx0 鹰眼** 的设计目标是：在 **不强制改系统代理** 的前提下，把 **抓包（HTTP / WebSocket）→ 筛选定位 → 详情审计 → 拦截改包 → 重放 → 微型 Fuzz → 敏感与暗链检测 → 可选 AI 分析** 收敛到 **一个侧边栏主工作台**，降低联调排障、授权范围内的接口审计与初筛类工作的 **上下文切换成本**。

---

## 三、功能介绍
核心工作流：**抓包**（可选 **WebSocket**）→ **筛选** → **看详情** → **重放**（HTTP / **WebSocket 帧**，可 **AI 生成测试用例**）→ **微型 Fuzz**（HTTP / **WS**，可 **AI 生成 Payload**）→ **暗链检测 / AI 报文分析**（支持勾选多条后的 **批量 AI / 暗链工作台**）→ **AI 任务台**（专业版，多阶段自动化）。

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774260380190-0782f4db-26f4-4cc1-9cf1-7229ab6cd183.png)

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774261939081-45f63827-3b75-42b6-8a60-ee9880984f1c.png)

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774261970277-62c763f6-aad0-479e-87bf-48a56bfd0d64.png)

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774262957215-d70ce779-0994-489f-976c-f171a159bdbb.png)

| 模块 | 说明 |
| --- | --- |
| **抓包** | 在页面主世界劫持 `fetch` / XHR，记录请求与响应（含 body，带容量保护）；可按 **域名/IP 通配**、**资源类型**（XHR/Fetch、**WebSocket**、JSON、HTML、JS、二进制等）、**自定义后缀** 收敛噪声。勾选 **WebSocket** 后记录握手（如 `GET 101`）与数据帧（`WS`，`OUT`/`IN`）。 |
| **历史（History）** | **IndexedDB** 持久化；支持类型 / Host / 方法 / 状态码 / **敏感命中** / 搜索多维筛选；默认可限定 **当前页面** 或查看 **全部数据包**。 |
| **拦截（Intercept）** | 队列式暂停 **HTTP 请求**；命中规则时 **WebSocket 出站/入站帧** 也可进入 **帧级** 队列，侧栏内 **编辑、放行、丢弃**；支持一键放行 / 丢弃；与抓包共用同一套目标规则。 |
| **详情审计** | **Pretty / Raw / Hex**；响应 **Render**（沙箱渲染）；**敏感信息** 聚合与高亮；点击标题可复制完整 URL、下载双栏原文分段 `.txt`；**Burp 风格** 导出。 |
| **重放工作台** | 编辑原始报文后一键重放；**WebSocket 帧重放** 共用同一工作台，经页面内仍为 **OPEN** 的连接发送出站帧（非重新握手）；**页面内重放**（应对部分 WAF 动态页）；撤销/重做；目标域名切换；**AI 生成测试用例**：按当前请求与选项让模型输出结构化用例列表，快速铺测试思路（需配置 AI）。 |
| **编解码与哈希** | MD5、SM3、SHA、ROT13、Base64、URL、Hex 等；作用范围可选 **选中文本 / 仅参数值 / 整行 URL**。 |
| **微型 Fuzz** | 使用 `§...§` 标记注入点；**开始 Fuzz** 与 **页面内 Fuzz**（HTTP/DOM）；**WebSocket 微型 Fuzz** 串行发包并以 **下一条入站帧** 为响应结果（依赖页内活动连接）；基线对比；**AI 智能 Payload**：由模型按注入上下文生成候选 payload 列表，减少手写字典成本；可结合 Render、敏感、**AI 结果分析**视图辅助判断。 |
| **暗链与静态威胁** | 对静态 HTML 等做 **规则扫描**；可配置 **高信誉顶级域** 降噪；报告可下载。可与 **AI 报文/语义解读** 配合，**批量暗链** 工作台便于对多条响应 **横向对比**，辅助梳理 **外链、第三方脚本与依赖线索**（供应链初筛场景）。 |
| **AI 分析（可选）** | **单包**：对 **请求 + 响应** 做解读、异常与风险辅助说明。**批量**：勾选多条历史，独立页 **逐条高亮 + 汇总报告**，适合 **多接口、多域名** 归纳与留证。**AI 任务台**：侧栏内多阶段自动化（智能渗透 / CTF），支持 **Skills 知识库注入**（内置渗透/CTF 模块、可导入外部 SKILL.md、任务级子模块勾选）、**运行中补充线索** 注入后续轮次。模型支持 OpenAI、DeepSeek、本地 LM Studio、**自定义 Base URL**；兼容 **OpenAI 风格** 与 **千帆代码计划等** 完整路径；数据 **只发往您配置的 Endpoint**（BYOK）。 |
| **鹰眼浏览器自动化 MCP（PRO）** | 面向安全工作流的浏览器 MCP；兼容 stdio / Streamable HTTP / legacy SSE，把标签页导航与鹰眼抓包、重放、变异、编解码、证据工具统一暴露给可信 Agent Host。 |
| **浏览器级 Agent（PRO）** | 在用户真实标签页和登录态中自主规划、多轮调用浏览器 + HawkEye 工具；支持安全批准模式、目标 / 计划、附件、视觉截图、长上下文记忆、自主联网研究与原生下载。 |
| **敏感信息匹配** | 内置规则（证件、手机、银行卡、邮箱、Shiro/JWT/Swagger/UEditor/Druid 等指纹、IP、域名、CTF Flag 等）+ **自定义正则**、**关键词库**；支持批量导入/导出、一键清空。 |
| **批量能力** | 批量导出、删除、**批量 AI 分析**、**批量暗链检测**（独立标签页工作台）、批量重放等。 |
| **国际化** | 界面 **中文 / English** 切换。 |


**Chrome 与 Firefox** 在侧栏托管方式、内网/自签名 HTTPS 辅助选项、拦截时的系统提示等方面存在差异，**核心业务功能对齐**；具体差异可在安装扩展后查看内置帮助说明。

---

## 四、版本说明（社区版 / 专业版）

Hx0 鹰眼当前采用 **社区版 / 专业版 / 首次 30 分钟试用专业版** 的分层策略：

- **社区版**：覆盖日常高频的 **抓包（含 WebSocket 基础观测）→ 看详情 → 普通重放（含 WebSocket 帧重放）→ 基础编解码** 主链路，以及 **拦截改包**（HTTP + 命中规则时的 **WebSocket 帧**）。
- **专业版**：进一步解锁 **页面内重放 / Fuzz、HTTP/WS 微型 Fuzz、油猴脚本、AI、AI 任务台、Skills 知识库、暗链、批量工作台与高级编解码** 等深度能力。
- **首次试用**：新安装后可先体验 **30 分钟专业版全功能**；试用结束且未激活时，会 **自动回落到社区版**。

### 功能差异表

| 功能项 | 社区版 | 专业版 | 说明 |
| --- | --- | --- | --- |
| 抓包开关、目标域名 / IP、抓包类型 / 后缀 | ✅ | ✅ | 社区版即可完成基础抓包与降噪 |
| 历史列表、当前页面 / 全部数据包切换、Host / 方法 / 状态码筛选 | ✅ | ✅ | 便于快速定位请求 |
| Pretty / Raw / Hex / Render、复制 / 单条下载 / 标题复制 URL | ✅ | ✅ | 社区版即可完成详情审计 |
| 内置敏感信息识别与聚合展示 | ✅ | ✅ | 支持内置规则命中查看 |
| 普通重放 | ✅ | ✅ | 社区版保留完整基础验证闭环；含与 HTTP 共用工作台的 **WebSocket 帧重放**（依赖页内 `OPEN` 连接） |
| **拦截开关、改包 / 放行 / 一键放行 / 一键丢弃（1.0.2 起社区版开放）** | ✅  | ✅ | 队列式拦截；**HTTP 与 WebSocket 帧**（命中 Host 等规则时）均可侧栏处理 |
| 悬浮球、另存为新标签、语言切换 | ✅ | ✅ | 日常效率入口保留在社区版 |
| **基础编解码**：MD5、SM3、SHA-1、SHA-256、ROT13、Base32 / Base64 / URL / Hex 编解码 | ✅ | ✅ | 社区版即可直接使用 |
| **高级编解码**：SHA-512、HMAC-SHA256、Base64URL、Unicode、HTML、JSON、JWT、时间戳转换 | ❌ | ✅ | 面向更深的验证、签名与分析场景 |
| **加密逻辑智能分析（1.0.1 新增）** | ❌ | ✅ | 结合当前请求上下文与同页 JS / HTML 线索，辅助判断编码、摘要、签名或混合加密链路 |
| 页面内重放、页面内 Fuzz、**HTTP / WebSocket 微型 Fuzz**、标记注入点 | ❌ | ✅ | 适合动态页、WAF、实时信道与高频参数试探 |
| 切换请求方法、目标域名切换 | ❌ | ✅ | 适合多环境联调与验证 |
| **智能代理分流器（1.0.1 新增，1.0.6 起社区版开放）** | ✅ | ✅ | 位于基础设置页“抓包类型 / 后缀”下方，可按站点规则将命中请求转发到 Burp、Yakit 或其他上游代理，未命中请求保持原网络路径；Firefox 版额外支持“兼容模式 / 接管模式” |
| **鹰眼浏览器自动化 MCP（1.0.6）** | ❌ | ✅ | 类似面向安全专版的 Playwright MCP，贯通浏览器操作与鹰眼抓包、重放、变异、敏感信息及证据工具 |
| **浏览器级 Agent / Agent 模式（1.0.6）** | ❌ | ✅ | 仅有效试用或专业版授权可用；在真实浏览器会话中执行多轮计划与工具调用 |
| AI 分析设置、AI 结果分析、AI 分析、AI 生成用例 | ❌ | ✅ | AI 能力统一归于专业版 |
| **AI 任务 / AI 任务台（1.0.2 起）** | ❌ | ✅ | 多阶段自动化：智能渗透、CTF 夺旗；**Skills 知识库注入**（1.0.3 完善默认推荐与手动优先策略）、**运行中补充线索**；**时间轴日志与可拖拽分栏**（1.0.5）；编排与工具链持续优化；联动历史、重放与验证并沉淀报告 |
| **AI Skills 知识库（1.0.3）** | ❌ | ✅ | 内置渗透/CTF 知识库与子模块（1.0.6：渗透 19 + CTF 28）；markdown 可编辑；可导入外部 Skill。高级设置是全局允许列表；Agent 新会话 Skills 默认关闭，用户还须在当前会话点击 `Skills`，未同时启用的 Skill 不会被调用 |
| **油猴脚本 / 页面脚本工作台（1.0.4）** | ❌ | ✅ | 导入 `.user.js`、脚本库管理、一键注入；AI 创建/优化脚本；**智能解码助手**（1.0.5）；与抓包重放等工具联动 |
| **AI 任务智能脚本调用（1.0.4）** | ❌ | ✅ | 任务运行中 AI 可列出、执行、创建页面脚本，与 Skills、重放、Fuzz 组合编排 |
| **高级编解码 / 智能套娃解码（1.0.5 增强）** | ❌ | ✅ | 重放台补齐 AES/DES/RSA/SM；AI 任务内置 `codec.transform`；详情内联「加密&编码」与重放台联动 |
| 暗链与静态威胁检测、报告下载、高信誉顶级域 | ❌ | ✅ | 规则扫描、报告与降噪能力 |
| **全量深度搜索、敏感信息匹配、自定义正则 / 关键词库（1.0.6 起社区版开放）** | ✅ | ✅ | 相比 1.0.5 下放到社区版；支持完整请求 / 响应深搜、内置规则、自定义正则、关键词库与批量导入导出 |
| 批量导出、批量删除、批量重放、批量 AI 分析、批量暗链检测 | ❌ | ✅ | 批量工作台统一归于专业版 |

> `1.0.1` 版本最初新增两项专业版能力：`智能代理分流器` 与 `加密逻辑智能分析`；其中智能代理分流器已在 `1.0.6` 下放社区版。
> `1.0.2` 版本：**WebSocket**（抓包/帧重放/**WS 微型 Fuzz**/**帧拦截**）、**AI 任务台**（含 **运行中补充线索**、多阶段编排加固），并将 **拦截模式** 能力下放至社区版。  
> `1.0.3` 版本：**AI 任务支持加载 Skills**、**抓包/拦截体验优化**、**在线激活** 等。  
> `1.0.4` 版本：**油猴脚本支持**、**AI 任务智能调用脚本**、**拦截/抓包可靠性** 与 **Firefox 双端对齐** 等。  
> `1.0.5` 版本：**AI 任务台全面升级**、**Skills 加厚与 AI 生成技能**、**编解码能力补齐** 与 **体验优化** 等。
> `1.0.6` 版本：**安全专用 HawkEye MCP（PRO）**、**浏览器级 Agent（仅 PRO）**、**Firefox / Chrome 性能重构**、**Agent Skills 默认关闭与双重授权**、**中英文 / 隐私协议同步**；同时向社区版开放**智能代理分流器、全量深度搜索和敏感信息匹配**。

### 一句话理解版本边界

- **社区版负责**：看包（HTTP / WebSocket）、理解、初步验证、基础编解码、**拦截改包、智能代理分流、全量深搜与敏感信息匹配**。
- **专业版负责**：页面上下文验证、变异测试、AI 分析、AI 任务与 Skills、**浏览器级 Agent / MCP**、暗链扫描、批量产出。
- 如果你只是想先确认产品价值，社区版已经足够完成最核心的主链路。

---

## 五、产品优势
1. **零代理门槛**：浏览器扩展形态，**无需单独 JVM、无需占用独立代理端口**，装完配置目标即可开抓。  
2. **会话一致**：与 **当前标签页同源会话** 一致，抓到的即页面真实发出的请求，重放时 **减少「突然掉登录」** 类问题。  
3. **一体化工作台**：历史、拦截、重放、编解码、微型 Fuzz、**WebSocket**、敏感、暗链、AI 在 **同一侧栏** 完成，减少多工具往返。  
4. **现代前端友好**：直面 **XHR/Fetch、WebSocket、FormData、multipart** 等场景，可在扩展容量限制内做 **Raw / Hex** 级审计。  
5. **动态页取证**：**页面内重放 / 页面内 Fuzz** 在真实 DOM 环境中加载并提取内容，辅助应对部分 **WAF 加密页 / 挑战页**。  
6. **敏感与暗链内置**：列表角标 + 详情聚合 + 可导出报告，适合 **联调自查与授权范围内的初筛**。  
7. **AI 能力成环**：**AI 任务台**（多阶段 + **Skills 知识库** + **运行中补充线索**）、**AI 生成测试用例**、**AI 生成 Fuzz Payload**、**单包请求/响应 AI 分析**、**批量 AI 分析**（多包汇总，便于 **供应链 / 依赖面** 类线索归纳）与 **暗链规则 + AI 解读** 可在 **同一侧栏工作流** 内完成，少切工具。  
8. **AI 可控（BYOK）**：自带模型与 Endpoint 配置，**数据只发往您填写的 API**，便于 DeepSeek、硅基流动、千帆等云端或 **内网 / 私有化** 模型。  
9. **轻量资源占用**：随浏览器进程运行，相对独立代理 + 重型客户端更轻。

---

## 六、与市面上主流工具对比
下表从形态、会话、工作流与专项能力等维度对比 **Hx0 鹰眼**、**Burp Suite**、**Yakit**、**HackBar / 简易扩展类**。**企业级深度漏扫、复杂 Intruder 模板、非浏览器全流量** 仍以专业平台为准，可与本产品 **组合使用**。

| 维度 | **Hx0 鹰眼** | **Burp Suite** | **Yakit** | **HackBar / 简易扩展类** |
| --- | --- | --- | --- | --- |
| **形态与部署** | 浏览器扩展；侧栏为 **主工作台**；可选悬浮球；**无 JVM、无单独代理端口** | 独立 Java 代理 + 浏览器证书；套件化、重量级 | 独立客户端 + 引擎/插件生态；偏安全平台 | 多为地址栏旁小面板或单条请求工具 |
| **上手与日常成本** | **装完即用**，不强制改系统代理；中英界面，流程在侧栏串联 | 需配代理、信任根证书、熟悉 Proxy/Repeater 等 | 需单独安装与熟悉工作流/流水线 | 上手快，能力点分散、缺「项目级」工作区 |
| **浏览器会话 / 登录态** | 与 **当前标签同源** 一致；重放时 **少出现掉登录断层** | 经代理；部分站点需额外处理 Cookie，常要手工同步到 Repeater | 多经代理或引擎，路径与纯扩展不同 | 常靠手工拼 Header/Cookie |
| **现代前端 API（XHR/Fetch/SPA + WS）** | 主世界劫持 fetch/XHR；可选 **WebSocket** 抓包 / 帧重放 / 帧拦截；支持 **multipart Raw/Hex** 审计（容量限制内） | 代理层全量可见，能力上限高 | 流量与插件可覆盖复杂场景 | 多数无持久历史、无 Hex/敏感聚合 |
| **历史、检索与工作台** | **IndexedDB 持久历史**；多维筛选（含 **WebSocket** 类型）；详情/重放/Fuzz/AI **同侧栏** | Proxy History 极强；与浏览器、IDE 切换多 | 平台化记录与协作强 | 通常 **无历史或极弱** |
| **系统代理 / 非浏览器流量** | 聚焦 **浏览器内** HTTP(S) 与 **页内 WebSocket** | 强 | 强 | 弱 |
| **拦截与改包** | **HTTP + WebSocket 帧** 队列式拦截；侧栏逐条或批量处理 | Proxy 拦截，行业事实标准 | 支持 MITM / 工作流编排 | 多数无或仅能改 URL 片段 |
| **重放 / Fuzz** | 重放台 + **HTTP/WS 微型 Fuzz** + **页面内重放/Fuzz** | Repeater / Intruder 成熟 | Web Fuzzer 等模块 | 通常无并发 Fuzz、无结构化对比 |
| **敏感 / 暗链 / 报告** | **内置规则 + 角标 + 详情聚合**；可导出 | Scanner、BApp 强；需许可与配置 | 插件与 PoC 丰富 | 极少内置 |
| **AI 辅助** | **BYO API**，数据走向 **自控**；**Skills 知识库** 与 **AI 任务台** 多阶段编排 | 多依赖第三方扩展或自建 | 持续扩展中 | 少见 |
| **主动扫描 / 大型自动化** | 非主战场；偏 **人工高频闭环** | Scanner、宏、插件生态 | PoC、批量检测、协作流 | 基本不具备 |
| **资源占用** | 随浏览器，**轻量** | 代理 + JVM，通常更高 | 视场景而定 | 极低，但能力面窄 |


**协作建议**：Hx0 鹰眼适合作为日常 **浏览器内主工作台**；需要全站主动扫描、超大规模字典、非浏览器客户端流量时，**叠加 Burp / Yakit** 形成「侧栏快循环 + 平台深挖掘」。

---

## 七、离线安装（v1.0.6 · ZIP only）

请只从本仓库 [Releases](https://github.com/asaotomo/Hx0-HawkEye/releases) 下载与浏览器对应的正式包：

- `Hx0-HawkEye-Chrome-V1.0.6-Official.Release.zip`
- `Hx0-HawkEye-Firefox-V1.0.6-Official.Release.zip`

本版**不发布 CRX / XPI**。Chrome 会限制或自动停用非商店来源的 CRX；Firefox 正式版要求签名 XPI。统一发布 ZIP 可以避免把不稳定的旁加载方式包装成“永久安装”，也便于核对包内只有正式运行文件。ZIP 中不含源码、构建脚本、source map、密钥或调试文件。

### Chrome / Edge / Chromium

1. 解压 Chrome ZIP 到一个**固定目录**，不要在安装后删除或移动。
2. 打开 `chrome://extensions/`（Edge 使用 `edge://extensions/`）。
3. 开启**开发者模式**。
4. 点击**加载已解压的扩展程序 / Load unpacked**。
5. 选择解压后直接包含 `manifest.json` 的目录，然后将扩展固定到工具栏。

升级时先从旧版导出需要保留的数据，关闭相关侧栏；用新包内容替换原固定目录，再回到扩展管理页点击**重新加载**。不要同时加载两个不同目录的 HawkEye，以免产生不同扩展 ID 和相互独立的本地数据。

### Firefox

1. 解压 Firefox ZIP。
2. 打开 `about:debugging#/runtime/this-firefox`。
3. 点击**临时载入附加组件 / Load Temporary Add-on**。
4. 选择解压目录中的 `manifest.json`。
5. Firefox 重新启动后，按上述步骤重新临时载入。

普通 Firefox 对未签名扩展不提供永久安装。本仓库不会通过关闭签名校验来伪装永久安装；如需组织级长期部署，请使用 Mozilla 官方签名/企业策略流程。

### 安装后入口

- **扩展图标弹窗**：抓包、拦截、目标范围、MCP 开关与高级设置。
- **侧边栏**：历史、拦截、重放、AI 任务、浏览器级 Agent 与页面脚本。
- **用户手册**：完整操作、Chrome / Firefox 差异、MCP 接入、Skills、隐私与排障。
## 八、用户手册
安装扩展后，在 **产品内** 打开《用户手册》即可查看完整使用教程，包括 **MCP / Agent 安装使用**、**主流 Browser MCP 对比**、**Chrome / Firefox 差异**、**请求头/体排障**、**截图落盘**、**常见问题**和 **授权说明**。

### MCP 和 Agent 一句话区分

- **HawkEye MCP** 是本地工具桥，不包含 AI 模型：安装 Node.js 18+，在弹窗下载单文件 `hawkeye-mcp-server.mjs`，点击「复制通用配置」后添加到 Codex、Cursor、Claude Code 等 MCP Host。不需 `npm install`。
- **内置 Agent 模式** 是鹰眼侧栏内的多轮规划/执行界面：在高级设置填 Base URL、API Key（如需）和 Model，再打开「抓包界面 → Agent 模式」；不需额外配置第三方 MCP Host。
- **AI 任务** 用于有 Scope、Skills、安全门禁和结构化报告的可重复授权测试；它和自由对话式 Agent 的产品形态不同。

与主流方案相比：[Playwright MCP](https://github.com/microsoft/playwright-mcp) 更偏跨浏览器测试/隔离自动化；[Chrome DevTools MCP](https://github.com/ChromeDevTools/chrome-devtools-mcp) 更偏 Chrome DevTools 和性能调试；[Browser MCP](https://docs.browsermcp.io/) 更偏已登录 Chrome 的通用页面操作。HawkEye 的核心差异是把 **Chrome + Firefox 真实会话、抓包、拦截改包、重放/fuzz、敏感/暗链证据与 Agent** 放进同一条工作流。详细对比见产品内手册 **§3.2**。

---

## 九、安全与合规
+ 请 **仅在取得授权的系统** 上使用抓包、拦截、重放与 Fuzz 功能。  
+ 启用 **AI 分析 / AI 任务 / Agent** 时，完成任务所需的报文与页面上下文可能发送至您配置的第三方或内网模型服务；默认自动脱敏会尽量遮蔽 Cookie、Token 等常见字段，但不能保证识别全部敏感数据。关闭脱敏后，原始认证上下文可能被发送。
+ HawkEye MCP Server 仅监听本机回环地址，但您信任并连接的第三方 Agent / MCP Host 仍可能把工具结果发送到其配置的模型服务；不用时请关闭 MCP 桥接。
+ 完整数据范围、例外、保存与用户权利以扩展内中英文《**用户协议与隐私政策**》为准。
+ **Render** 等能力请在可信环境中使用；即使采用沙箱策略，仍需谨慎对待不可信响应内容。  
+ 商业场景请遵守产品 **许可与授权** 约定（以软件内说明为准）。

---

## 十、如何获取激活码

新用户可先免费体验 **30 分钟专业版全功能**。试用结束后若未激活，将自动回落到社区版；如果体验满意，欢迎通过以下方式获取专业版激活码：

**访问[激活码获取教程](https://www.yuque.com/u12459488/bzqpay/udkx5qy1x6guinz0?singleDoc)，限时免费领取激活码**

---
    
## 十一、联系与反馈
**Hx0战队**

+ **Hx0 鹰眼官网**：[https://www.hx0.store/products/hawkeye](https://www.hx0.store/products/hawkeye)（产品介绍、下载与文档入口）
+ 微信公众号 / 知识星球：**Hx0战队**
+ 邮箱：[hx0studio@foxmail.com](mailto:hx0studio@foxmail.com)

反馈请尽量附带：浏览器类型与版本、扩展版本、复现步骤与截图。

---

## 十二、免责声明
本项目及扩展 **仅供安全研究、研发联调与授权测试**。使用者应遵守所在地法律法规及目标系统授权范围。  
对任何 **未授权测试** 及其后果，开发者与贡献者 **不承担任何责任**。


---

## 十三、1.0.1 更新日志

本次 `V1.0.1` 主要围绕两项专业版能力完善：

- **智能代理分流器（1.0.1 首发时为专业版，1.0.6 起社区版开放）**：在基础设置页 `抓包类型/后缀` 下方新增代理分流入口，可按站点规则把命中的浏览器请求转发到 Burp、Yakit 或其他上游代理，未命中的请求继续保持原有网络路径。适合把“浏览器原生会话抓包”与“代理深度调试”串成一个工作流，减少频繁切换系统代理的成本。

  <img width="430" height="573" alt="image" src="https://github.com/user-attachments/assets/db12989b-7d10-4b11-9859-a9da61a79d03" />

- **加密逻辑智能分析（专业版）**：功能在AI分析按钮右侧，模型会结合当前请求的 URL、参数、请求头、Body、响应线索，以及同页 JS / HTML 中的函数名、字段名和提交流程，辅助判断前端是否做了编码、摘要、签名或混合加密，适合复核改包前后的签名链路变化。（一句话总结：让AI帮你猜加密/编码/签名逻辑，省去人肉逆向的时间。）

  <img width="780" height="151" alt="image" src="https://github.com/user-attachments/assets/727c7ad7-c5e8-438f-a9e7-cc7f7afe5697" />

  <img width="1548" height="940" alt="image" src="https://github.com/user-attachments/assets/2c431003-88c4-4b1f-90b3-07c749de443c" />

  <img width="1548" height="940" alt="image" src="https://github.com/user-attachments/assets/ea538cdc-b9ce-4bfa-be6f-c762edb54f91" />

  <img width="1548" height="940" alt="image" src="https://github.com/user-attachments/assets/1c145765-ab5e-41e5-b905-455964b64190" />
  
- **稳定性补充**：同步补强了普通抓包模式下的请求头补全与代理释放细节，降低普通模式、拦截模式与代理切换场景下的显示差异和冲突概率。
- **侧栏和批量页面优化**：侧栏报文展示与交互优化（双端一致），批量页面整体布局优化。
- **页面内重放和页面内Fuzz功能优化**：更新后支持表单 POST（请求头 Content-Type: application/x-www-form-urlencoded）。
- **重放工作台优化**：编解码功能现支持响应体处理，新增作用域区分，并统一了请求与响应的撤销/重做记录。
- **「全部域名」筛选**：修复域名筛选为「全部域名」时与工作台范围（当前页 / 全部数据包）联动不当导致的列表或筛选状态异常。
- **抓包 / 拦截列表**：表头各列右侧竖条可拖拽调节列宽，宽度本地持久化，下次打开仍生效。
- **302 / 重定向抓包**：优化重定向（如 302）在 webRequest 与被动 CDP 等路径下的落库与去重，减少重复记录或类型不一致带来的漏抓、重复抓。
- **表头三态排序**：抓包 / 拦截列表表头支持「默认 → 升序 → 降序 → 回默认」；Fuzz 结果表同样三态，取消排序后按原始序号恢复顺序；点击列宽拖条不会触发排序。



## 十四、1.0.2 更新日志

本次 `V1.0.2` 围绕 **HTTP 重放增强**、**WebSocket 工作台**、**AI 任务台（含运行中补充线索与编排优化）** 及 **社区版拦截开放** 等重点升级，进一步提升 Web 安全测试、CTF 与日常抓包分析效率。

<img width="1055" height="1491" alt="v1 0 2海报" src="https://github.com/user-attachments/assets/853169b7-01bb-4f13-8d44-81fa68567e78" />

## 主要更新

### 1. 重放数据包支持关键请求头覆盖

重放工作台现已增强对特殊请求头的处理能力，支持在 Raw 请求中编辑并生效以下字段：

- `Referer: https://xxx.com`
- `User-Agent: xxx`
- `Origin: https://xxx.com`
- `X-Forwarded-For: x.x.x.x`

该能力适用于常见的来源校验、UA 校验、伪造来源、CTF Referer 绕过等场景。用户可以直接在 Raw 请求中修改请求头后重放，工具会尽量保持与 Burp Suite 类似的重放行为。

### 2. 新增 AI 任务模块

新增独立的 AI 任务模块，用于将抓包、请求分析、漏洞测试和报告生成串联成自动化流程。

当前 AI 任务支持两种模式：

- **智能渗透模式**  
  面向常规 Web 安全测试场景，AI 会基于目标站点、历史流量和页面上下文，自动进行信息收集、入口分析、攻击建模、漏洞探测和结果研判。

  <img width="3912" height="2070" alt="909110ca03be628642c272a91c8c7cc6" src="https://github.com/user-attachments/assets/e42f8720-613a-429b-952d-dd93fbb24a22" />


  <img width="3912" height="2070" alt="91bcbb07d5a3bd6db6ef5f9baea3563e" src="https://github.com/user-attachments/assets/fdaee4df-15b7-489d-8ecd-0462d7e9619d" />


- **CTF 夺旗模式**  
  面向 CTF Web 题目，AI 会围绕题目入口、提示、响应特征和可疑参数自动规划解题路径，尝试构造利用请求，并在命中 Flag 后生成复盘报告。

  <img width="3912" height="2070" alt="31c644c1426fc64801d7d1caac178e13" src="https://github.com/user-attachments/assets/c100544b-7ca3-4616-bb1a-7a45ddbeb64c" />

  <img width="3912" height="2070" alt="89ef599acf45a623a3dcd065a48c9119" src="https://github.com/user-attachments/assets/cd57e1c5-1a77-4d93-b3ea-5e124937b06e" />


AI 任务模块会记录执行过程、请求证据、关键 payload、Flag 命中结果和最终分析报告；**运行中**可通过工具栏 **「补充线索」** 队列化注入后续轮次，**不替代**启动前任务背景；底层 **多阶段自适应编排** 持续加固（工具链、预算与可读性等）。详见用户手册 §10。

### 3. 拦截模式开放给社区版

拦截模式现已开放给社区版用户使用（含命中规则时的 **HTTP 与 WebSocket 帧** 侧栏队列）。

社区版用户可以使用拦截模式完成请求暂停、查看、修改、放行等基础操作，更方便地进行手工测试、参数调试和请求验证。

<img width="1956" height="1035" alt="image" src="https://github.com/user-attachments/assets/0f4cb847-e564-40c1-84f3-b6bc2b7a73c5" />

### 4. WebSocket 抓包、重放、微型 Fuzz 与拦截改包

弹窗勾选 **WebSocket** 后，侧栏可按类型筛选；握手多为 `GET 101`，数据帧为 **`WS`**（**`OUT`** / **`IN`**）。**帧重放** 与 HTTP 共用重放工作台，依赖页内 **`OPEN`** 连接；**`§...§` + 微型 Fuzz** 以下一条入站帧为响应。**拦截** 下支持 **帧级** 编辑/放行/丢弃。定位为浏览器内页面 JS 创建的 WebSocket，非系统级 MITM；细节见用户手册 §5。

<img width="1548" height="942" alt="image" src="https://github.com/user-attachments/assets/392bcbfd-4356-459d-a6eb-0c2d58ff8bcd" />

### 5. AI 任务：运行中「补充线索」

任务**执行中**展开 **补充线索**，将新观察到的参数、回显、入口或 CTF hint 等写入并 **提交**；内容按时间戳 **排队**，在后续轮次以 **「运行中用户补充线索」** **追加**至模型上下文，用于纠偏、收窄；单次与队列有长度上限。**勿**粘贴真实口令；脱敏与授权要求同全文。
<img width="1548" height="942" alt="image" src="https://github.com/user-attachments/assets/a81e5507-1561-413e-971d-db82ae7fbf0e" />
<img width="1548" height="942" alt="image" src="https://github.com/user-attachments/assets/e6ddb672-c912-4099-9ad7-fdd82fe6efc9" />

### 6. AI 任务：编排与执行框架优化

对 **AI任务台** 多阶段自适应工作流整体加固：**多回合 Agent** 与真实 HTTP 取证闭环、**结构化运行时内存**（含失败记忆与侧栏指标对齐）、**协议校验与再规划** 等，使阶段衔接与 CTF 提前收尾更稳定。

---

## 十五、1.0.3 更新日志

本次 `V1.0.3` 主要带来三项更新：

### 1. AI 任务支持加载 Skills（专业版）

AI 任务台可注入内置 **渗透 / CTF 知识库**，也支持在高级设置 **导入外部 SKILL.md 或技能目录**；任务面板可按需勾选库与子模块，启动后作为上下文辅助多阶段自动化测试与研判。

<img width="1956" height="1040" alt="image" src="https://github.com/user-attachments/assets/63206722-eef8-4e76-ab67-64d631c17644" />


<img width="438" height="563" alt="image" src="https://github.com/user-attachments/assets/6d56a214-5d1c-4181-b421-fc1783f03c40" />


### 2. 抓包与拦截体验优化

优化侧栏 **抓包 / 拦截** 列表的浏览与操作：筛选与范围切换更连贯，列表展示与改包、放行等日常动作更顺手，减少高频调试时的来回切换。

### 3. 新增在线激活

单击弹窗 **状态徽章** 打开「软件激活」，新增 **在线激活** Tab，支持订阅或永久会员；权益联网同步并 **缓存到本机**，断网后可在有效期内继续使用专业版。与原有 **离线激活码** 并行，开通与续费更方便。

<img width="438" height="563" alt="image" src="https://github.com/user-attachments/assets/71313a25-a59d-4c02-80cf-9ee6ef6a75e2" />

---

## 十六、1.0.4 更新日志

本次 `V1.0.4` 主要带来四项更新：

### 1. 油猴脚本 + 页面脚本工作台（专业版）

支持导入 `.user.js` 油猴脚本，侧栏统一管理、一键注入；可用 AI 从流量创建或优化脚本，并与抓包、重放、敏感扫描等能力联动。人写脚本、AI 写脚本、AI 任务调度脚本三条路径打通。

<img width="1548" height="941" alt="image" src="https://github.com/user-attachments/assets/152c24a6-cf8e-41dd-a41e-641b11da5fb7" />

<img width="3080" height="1716" alt="e327bce7470c8582ba612072f9e9019b" src="https://github.com/user-attachments/assets/943ef6ca-0fb7-4047-9abf-789482b149c4" />



### 2. AI 任务智能脚本调用（专业版）

勾选 **智能脚本调用** 后，AI 任务在渗透 / CTF 过程中可自动列出、执行或创建页面脚本，把页面侧情报采回来，再继续重放验证与报告生成。

### 3. 拦截 / 抓包可靠性增强

本地靶场与自签名 HTTPS 拦截更稳定；修复拦截队列为空等回归问题；改包编辑器支持正常输入中文。

### 4. Firefox 稳定性与双端对齐

修复 Firefox 抓包、侧栏、拦截、重放、脚本注入等主链路问题，双端日常体验进一步对齐。

> 详细说明见仓库内 `1.0.4更新说明`。

---

## 十七、1.0.5 更新日志

本次 `V1.0.5` 主要带来四项更新：

### 1. AI 任务台全面升级（本版核心）

执行日志改为 **时间轴卡片流**（阶段 / AI / 测试 / 工具调用分色展示，工具调用可展开 JSON）；日志与报告 **左右分栏可拖拽**；启动前 **任务背景 AI 理解**；报告输出 **漏洞清单 + 请求/响应证据**；内置 `crypto.logic.analyze` 与 `codec.transform` 高级加解密。

<img width="3080" height="1788" alt="7adc70c64d50d5272a58d6aec4db0c55" src="https://github.com/user-attachments/assets/83e16c37-e808-438b-8b01-c9be189381e1" />


### 2. Skills 知识库加厚 + AI 生成技能

内置子模块扩容至 **渗透 19 + CTF 28**；主 Skill 新增 **「智能启用」** 开关；高级设置新增 **AI 生成技能**，可生成单个 Skill 或技能集合并保存为独立 Skill、内置库子模块或追加到已有导入 Skill。

<img width="1038" height="816" alt="image" src="https://github.com/user-attachments/assets/559350c7-dcbe-4552-9936-88cb0ea9b066" />

<img  height="740" alt="3b62bafea675b0fe0e2b790e8e4e689e" src="https://github.com/user-attachments/assets/b00e9183-4e18-4bb1-9561-042afe4494ab" />

<img  height="740" alt="cc4666c5f38a35d7174ebe3c357c2ef4" src="https://github.com/user-attachments/assets/e377d19c-b6c8-404c-9eb3-56e7b2c006d5" />


### 3. 编解码能力补齐

重放台补齐 **AES / DES / RSA / SM** 与智能套娃解码；内置页面脚本 **「智能解码助手」**（默认启用）：选中文本即尝试常见解码与哈希识别；高级 AES / 套娃仍走重放台或详情内联「加密&编码」。

<img width="1600" height="1164" alt="e958884a06b31b7830f092368ce2931f" src="https://github.com/user-attachments/assets/41721abe-97fd-4eeb-a2c0-95b8bf7b20a1" />

### 4. 体验优化与问题修复

修复 Chrome / Firefox 双端若干系统问题；优化拦截 / 调试模式 / 被动监听等开关联动；改进侧栏与设置交互提示；用户手册同步至 **v1.0.5**。

> 详细说明见仓库内 `1.0.5更新说明` 或 `1.0.5-git更新说明`。

---

## 十八、1.0.6 更新日志

### 1. 鹰眼浏览器自动化 MCP（PRO）

新增面向安全工作流的 HawkEye MCP，定位类似安全专版 Playwright MCP：Codex、Cursor、LM Studio 等支持 MCP 的 Agent Host 接入 `hx0-hawkeye` 后，可由 Host 中的模型自动调用 `browser_navigate`、`browser_type`、`browser_snapshot` 以及鹰眼抓包、重放、变异、编解码、TLS、敏感信息和证据工具控制真实浏览器。本地 Server 仅监听回环地址，支持 stdio、Streamable HTTP 与 legacy SSE；用户需主动开启扩展桥接。该能力独立于扩展内 AI 任务台。

<img width="1800" height="1382" alt="Codex、Cursor、LM Studio 等 Agent Host 通过 HawkEye MCP 自动控制浏览器" src="https://github.com/user-attachments/assets/ff0c2671-6559-4f38-b6f5-2a6a50c5375a" />

### 2. 浏览器级 Agent（PRO）

Agent 模式仅对有效试用或专业版授权开放。它以用户当前真实 HTTP(S) 标签页为任务起点，支持多轮计划、安全批准模式、复杂控件 / iframe / Shadow DOM 交互、视觉截图、附件、抓包研判、重放、编解码、自主联网研究、原生下载、长上下文记忆与可展开的工具证据。

<img width="1500" height="900" alt="v1.0.6 浏览器级 Agent" src="https://github.com/user-attachments/assets/26994329-4e55-42c4-b48d-9a60153ae146" />

<img width="3096" height="1882" alt="ee4d555e47df0404083987143a76c727" src="https://github.com/user-attachments/assets/cb8d9460-bb90-4bc8-be5f-5ea635b95bfb" />

<img width="3096" height="1882" alt="1570653742b0ce10142f775ebe5171af" src="https://github.com/user-attachments/assets/ed512839-09b8-4307-a8f0-bb620fc305fb" />


### 3. 极致性能与低占用

Firefox 重点去除常驻被动监听，让 `webRequest` 监听器只在实际需要时存活；同时对 DOM 快照、ref 建立、列表行、抓包通知、MutationObserver、Agent 与 MCP 传输做了单次遍历、缓存复用、批处理、紧凑化和有界分页。大结果通过 `next_cursor` 续读，避免为追求速度丢失证据。

### 4. Skills 默认关闭与严格允许列表

更新 19 个渗透子模块和 28 个 CTF 子模块的内置契约。Agent 新会话 Skills 默认关闭；用户必须同时满足「高级设置已启用」与「当前 Agent 会话已点击 Skills」。任一开关未开，Skill 正文都不会进入模型上下文，Agent 也不能绕过用户选择直接调用。

### 5. 相比 1.0.5 的社区版能力开放

智能代理分流器、全量深度搜索，以及敏感信息匹配（内置规则、自定义正则、关键词库与批量导入导出）在 1.0.6 起向社区版开放；AI 任务、AI Skills、浏览器级 Agent 与 HawkEye MCP 仍为专业版能力。
