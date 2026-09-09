# 🦅 Hx0 HawkEye: Full-stack Lightweight Traffic Capture, Interception/Replay, MCP & AI Agent Security Auditing Extension


【[中文](./README.md) / English】


![](https://img.shields.io/badge/Network-No_system_proxy-success)  ![](https://img.shields.io/badge/UI-Sidebar_integrated-5865F2)  ![](https://img.shields.io/badge/Session-Same_origin_XHR_Fetch_WS-00A86B)  ![](https://img.shields.io/badge/Capture-Intercept-4285F4)  ![](https://img.shields.io/badge/Capability-Traffic_replay-blue)  ![](https://img.shields.io/badge/Capability-Micro_Fuzz-8B5CF6)  ![](https://img.shields.io/badge/Capability-Sensitive_data-FF69B4)  ![](https://img.shields.io/badge/Capability-Dark_link_scan-333333)  ![](https://img.shields.io/badge/AI-BYOK_optional-orange)

![](https://img.shields.io/badge/Version-1.0.6-6D28D9) ![](https://img.shields.io/badge/PRO-Security_MCP-7C3AED) ![](https://img.shields.io/badge/Agent-Browser_level-2563EB) ![](https://img.shields.io/badge/Release-ZIP_only-0F766E)

<img width="1672" height="941" alt="1.0.6-en" src="https://github.com/user-attachments/assets/b26de860-f2d3-47d2-93b0-671c5a034d76" />


## v1.0.6 highlights

> **0909 release update:** Models and memory: add DeepSeek V4.1 Flash (image-capable) as a candidate, switch the OpenAI default to GPT-6 Astra while keeping GPT-5.6, and honor max/low thinking parameters; history-summary recall is off by default; a new default persona, “HawkEye Universal Browser Assistant,” is added. Agent UX: Import Conversation is now a small header button to the left of “+”, restoring tool cards from exported Markdown; Skills start off, the picker opens up-and-right from the Skills button, a second click closes it and deselects the button, and smart routing no longer caps how many skills load; task suggestions cover everyday browsing (for example opening Bilibili, searching Ultraman, and playing a result) as well as security troubleshooting. Reliability: fixes stale-tab actions after a switch, crashes after closing the task tab, unintended downloads during file discovery, and checkpoint limits blocking new tasks; improves Goal/Plan progress retention, interruption recovery, and duplicate-submission protection; Skill save now shows a real receipt, and empty responses / exhausted output budgets retry at most once.

> **0906 release update:** This update focuses on long-running Agent tasks and reliability: it fixes actions targeting the old tab after a switch, failures after closing the task tab, unintended downloads during file discovery, and checkpoint limits blocking new tasks. It improves Goal/Plan progress retention, interruption recovery and duplicate-submission protection, reduces history synchronization, and moves title and memory maintenance to the background. It also strengthens web research, page-metric evidence and Firefox input handling, adds the Ctrl+H capture-UI shortcut, and synchronizes the bilingual manual and Chrome/Firefox release packages.

> **0904 release update:** This update improves Agent model compatibility and interaction: it adds a per-conversation deep-thinking toggle, refines DeepSeek, GLM-5.3-Flash, and local/custom model support, fixes missing tool-call arguments and long-text overflow, and unifies the HawkEye Agent label. It also adds local OpenSSL/CryptoJS AES passphrase decryption, rejects unsupported codec actions instead of falsely reporting success, strengthens DeepSeek empty-response retries and diagnostics with fallbacks grounded in actual tool results, and synchronizes the bilingual manual and Chrome/Firefox release packages.

> **0902 maintenance refresh:** expands mainstream model compatibility with Zhipu GLM, Xiaomi MiMo, and SiliconFlow presets plus automatic Base URL billing-route detection; repairs legacy GLM/MiMo profile crossovers and improves request-error feedback. Context-window input now uses token presets/custom values, known vision models enable image input automatically, optional background broadcasts no longer raise `Receiving end does not exist` while the side panel is closed, and the bilingual manual is synchronized.

> **0830 maintenance refresh:** without reducing capture or interception coverage, this build strengthens Firefox listener initialization and request header/body retention, smart web codecs, trusted Chrome/Firefox input, and screenshot evidence file saving. It also updates the bilingual manual, MCP/Agent setup, and the mainstream Browser MCP comparison.

- **HawkEye Browser Automation MCP (PRO)**: positioned like a security-specialized Playwright MCP. MCP-capable Agent Hosts such as Codex, Cursor, and LM Studio connect to `hx0-hawkeye`, letting the Host model autonomously call browser and HawkEye tools in the user's real tab. It supports stdio, Streamable HTTP, and legacy SSE and is separate from the in-extension AI Task Console.
- **Browser-level Agent (PRO)**: plans and executes multi-turn navigation, complex control / iframe interaction, traffic analysis, replay verification, public-web research, and native downloads inside the user's real tab and login session—not merely chat or one-shot AI reporting. Agent Mode requires an active trial or Professional license.
- **Community features opened in v1.0.6**: compared with v1.0.5, Smart Proxy Router, Full Deep Search, and built-in/custom sensitive-information matching plus keyword libraries are now available in Community.
- **Firefox and Chrome performance redesign**: one-pass bounded DOM snapshots, early offscreen rejection, lifecycle-bound Firefox `webRequest` listeners, compact Agent/MCP transport, batched notifications, observer reuse, and resumable large results through `next_cursor`, without dropping task evidence.
- **Trusted input and evidence files**: Chrome prefers CDP `Input.dispatchKeyEvent` / `Input.dispatchMouseEvent`, while Firefox uses a native-input relay with focus fallback. `browser_screenshot` can save an image locally when `save_to_file: true` is explicitly supplied; the default remains image-only with no disk write.
- **Two explicit Skill gates**: built-in pentest / CTF knowledge bases are updated for v1.0.6. Skills are off in every new Agent conversation. The user must first enable allowed Skills/sub-modules in Advanced Settings, then click `Skills` in the current Agent conversation; relevance matching can use only that allowlist.

<img width="1800" height="1382" alt="Codex, Cursor, or LM Studio controlling the browser through HawkEye MCP" src="https://github.com/user-attachments/assets/ff0c2671-6559-4f38-b6f5-2a6a50c5375a" />

<img width="1500" height="900" alt="v1.0.6 Browser-level Agent" src="https://github.com/user-attachments/assets/b9491db0-727c-4a09-8020-0f87abd97efe" />

## 1. What it is
**Skip the proxy hassle—truly ready out of the box.** Hx0 HawkEye is a lightweight security workbench for Chrome, Firefox, and mainstream Chromium browsers. Inside the user's real tabs and signed-in sessions, it unifies **traffic capture and interception/tampering (including WebSocket), replay, micro-Fuzz, sensitive-data / dark-link detection, AI-assisted security auditing, HawkEye MCP, and browser-level Agent workflows (PRO)** so manual analysis, external Agent Hosts, and in-extension automation share the same browser evidence and security tools.

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774276035508-0a9af8e0-4a11-4c83-9fe7-8ea82484d093.png)

#### ⚡ Core advantage: why not a classic proxy?
+ **Zero environment overhead**: no Burp Suite required, no system proxy, no root trust or Java setup.
+ **Session fidelity**: sees real page **XHR / Fetch / WebSocket** traffic with the **same origin login state** as the active tab—no more “proxy ate my cookies” or constant re-auth pain.
+ **Works immediately after install**: ideal for day-to-day dev/debug, API triage, and **authorized** first-pass security review.

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774275081238-a9d3306e-b723-4e0f-846b-38ef9a50ca02.png)

#### 🤖 Differentiator: end-to-end AI (BYOK)
Bring your own model API (BYOK) and embed AI into the sidebar workflow:

+ **Smart cases & payload generation**: structured test ideas in the replay workbench; context-aware mutated payloads in micro Fuzz—without bloated static wordlists.

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774275467560-2fe55566-6241-4482-b932-f1bd41dcd726.png)

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774275500332-6fb4554b-861f-4e98-81ee-dbe1bf42d005.png)

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774276635896-103172aa-4680-4c76-b96a-d31a1dfce8b0.png)

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774276656535-f6f1c42d-6fdf-499e-a7eb-2122ef98d4d6.png)

+ **Deep single-request analysis**: semantic AI read-through of full Request / Response for risk triage.

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774275567642-5018496d-2b53-4674-bd7a-3d65d0806658.png)

+ **Batch synthesis**: select multiple packets in a dedicated workbench; AI extracts patterns across APIs and third-party calls to support supply-chain / dependency-surface **first-pass** review.

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774275663993-07154b5a-c440-4b22-820c-c3645a284671.png)

+ **Dual-engine static hunting**: **built-in dark-link rules + AI contextual interpretation** for batch replay across pages and broad static coverage.



<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774275800441-dc18805d-35b8-46a5-a983-afef8e05450a.png)

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774275958382-e5751509-132f-4ebc-8736-0f6e642048ec.png)

---

## 2. Why we built it
With **SPAs, heavy XHR/Fetch, and WebSocket**, engineers constantly switch between “real browser session” and “capture / tamper / replay.” Classic proxies (e.g. Burp) are powerful but need system proxy and trust, and **cookies / login state** can diverge from the tab; lightweight toolbar extensions often lack **durable history, structured detail, and a closed-loop workbench**.

**Hx0 HawkEye** aims to keep **no mandatory system proxy** while folding **capture (HTTP / WebSocket) → filter → detail audit → intercept → replay → micro Fuzz → sensitive & dark-link checks → optional AI** into **one sidebar hub**, cutting context-switch cost for dev triage and **authorized** API review.

---

## 3. Features
Core flow: **Capture** (optional **WebSocket**) → **Filter** → **Detail** → **Replay** (HTTP / **WebSocket frames**; optional **AI test cases**) → **Micro Fuzz** (HTTP / **WS**; optional **AI payloads**) → **Dark-link / AI packet analysis** (including **batch AI / dark-link workbenches** after multi-select) → **AI Task Console** (Pro, multi-stage automation).

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774276082646-8aad5093-4c32-4595-9c6b-a5378a0f564d.png)

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774276530139-e52d8423-756d-4ad1-83f2-7ceb512d6508.png)

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774276559659-94bcce01-2393-4383-84db-91ba9453bb99.png)

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774276602069-b749ad60-8ba6-49a1-8129-acca2f9b1aaf.png)

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774276735904-99b04e61-1646-479c-85bf-92b9998bece0.png)

| Module | Description |
| --- | --- |
| **Capture** | Hooks `fetch` / XHR in the page world; records requests and responses (including bodies, with size guards). Noise control via **host/IP wildcards**, **resource types** (XHR/Fetch, **WebSocket**, JSON, HTML, JS, binary, etc.), and **custom suffixes**. With **WebSocket** enabled, records handshakes (e.g. `GET 101`) and frames (`WS`, `OUT` / `IN`). |
| **History** | **IndexedDB** persistence; filters by type, host, method, status, **sensitive hits**, search; default scope **current page** or **all packets**. |
| **Intercept** | Queued hold for **HTTP**; **WebSocket** outbound/inbound **frames** can enter a **frame** queue when rules match; **edit, forward, drop** in the sidebar; bulk actions; shares target rules with capture. |
| **Detail audit** | **Pretty / Raw / Hex**; response **Render** (sandbox); **sensitive** aggregation & highlights; copy full URL from title; download split raw **.txt**; **Burp-style** export. |
| **Replay** | Edit raw traffic and replay; **WebSocket frame replay** shares the same workbench and sends via a still-**OPEN** page socket (not a fresh handshake); **in-page replay** (some WAF challenge pages); undo/redo; host switch; **AI test cases** from current request/options (requires AI config). |
| **Encode / hash** | MD5, SM3, SHA, ROT13, Base64, URL, Hex, etc.; scope: **selection / param values only / full URL line**. |
| **Micro Fuzz** | `§...§` injection points; **Start Fuzz** and **in-page Fuzz** (HTTP/DOM); **WebSocket micro Fuzz** sends serially and uses the **next inbound frame** as the response (needs an active page socket); baseline diff; **AI payloads** from model context; pair with Render, sensitive, and **AI result** views. |
| **Dark link & static threats** | Rule scan on static HTML, etc.; **high-trust TLD** allowlist; downloadable reports; **AI packet/semantic** interpretation; **batch dark-link** workbench for **horizontal compare** and **third-party script clues** (supply-chain first pass). |
| **AI (optional)** | **Single packet**: interpret **request + response**, anomalies and risk notes. **Batch**: multi-select history, dedicated tab with **per-row highlights + summary** for multi-endpoint evidence. **AI Task Console**: multi-stage automation (penetration / CTF) in the sidebar, with **Skills knowledge-base injection** (built-in penetration/CTF modules, import external `SKILL.md`, per-task submodule selection), **in-task supplementary hints** queued into later turns. Models: OpenAI, DeepSeek, local LM Studio, **custom base URL**; **OpenAI-compatible** and paths such as **Baidu Qianfan coding plans**; traffic goes **only to your configured endpoint** (BYOK). |
| **HawkEye Browser Automation MCP (PRO)** | A browser MCP for security workflows. It supports stdio / Streamable HTTP / legacy SSE and exposes tab navigation plus HawkEye capture, replay, mutation, codec, and evidence tools to a trusted Agent host. |
| **Browser-level Agent (PRO)** | Plans and invokes browser + HawkEye tools inside the user's real tab and login state, with approval modes, goals/plans, attachments, visual screenshots, long-context memory, autonomous web research, and native downloads. |
| **Sensitive matching** | Built-in rules (IDs, phones, cards, email, Shiro/JWT/Swagger/UEditor/Druid fingerprints, IP, domain, CTF flags, etc.) plus **custom regex** and **keyword lists**; import/export, clear-all. |
| **Batch** | Bulk export/delete, **batch AI**, **batch dark-link** (separate tab), batch replay, etc. |
| **i18n** | UI **中文 / English**. |


**Chrome vs Firefox** differ in sidebar hosting, intranet/self-signed HTTPS helpers, and intercept prompts; **core features align**. See in-extension help after install for details.

---

## 4. Editions (Community / Pro)

Hx0 HawkEye currently uses a three-state model: **Community**, **Pro**, and a **30-minute first-install Pro trial**.

- **Community** keeps the essential loop: **capture (including WebSocket) → inspect → standard replay (including WebSocket frames) → basic encode/decode**, plus **intercept** (**HTTP** and matching **WebSocket frames**).
- **Pro** unlocks **in-page replay / fuzzing, HTTP/WS micro Fuzz, Tampermonkey scripts, AI, AI Task Console, Skills knowledge base, dark-link review, batch workbenches, and advanced encode/decode tools**.
- **First-install trial** grants **full Pro capability for 30 minutes**. If no activation code is applied after the trial, the product **automatically falls back to Community**.

### Feature Comparison Table

| Feature                                                                                                           | Community Edition | Professional Edition | Description                                                                                                                                                                                                                                                                                                            |
| ----------------------------------------------------------------------------------------------------------------- | ----------------- | -------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Packet Capture Toggle, Target Domain / IP, Capture Type / Suffix Filters                                          | ✅                 | ✅                    | The Community Edition is sufficient for basic traffic capture and noise reduction                                                                                                                                                                                                                                      |
| History List, Current Page / All Packets Switch, Host / Method / Status Code Filters                              | ✅                 | ✅                    | Quickly locate and filter requests                                                                                                                                                                                                                                                                                     |
| Pretty / Raw / Hex / Render Views, Copy / Single Export / Copy URL by Title                                       | ✅                 | ✅                    | Full packet detail auditing is available in the Community Edition                                                                                                                                                                                                                                                      |
| Built-in Sensitive Information Detection & Aggregated Display                                                     | ✅                 | ✅                    | Supports built-in rule-based detection                                                                                                                                                                                                                                                                                 |
| Standard Replay                                                                                                   | ✅                 | ✅                    | Full basic replay workflow; includes **WebSocket frame replay** via the shared workbench (requires an `OPEN` socket in the page)                                                                                                                                                                                                                                                      |
| **Interception Toggle, Modify / Forward / Forward All / Drop All (Community since v1.0.2)**                      | ✅                 | ✅                    | Queue-based intercept for **HTTP** and **WebSocket frames** when host rules match                                                                                                                                                                                                                                                                                                   |
| Floating Action Button, Open as New Tab, Language Switching                                                       | ✅                 | ✅                    | Daily productivity features remain available in the Community Edition                                                                                                                                                                                                                                                  |
| **Basic Encoding & Decoding**: MD5, SM3, SHA-1, SHA-256, ROT13, Base32 / Base64 / URL / Hex                       | ✅                 | ✅                    | Directly available in the Community Edition                                                                                                                                                                                                                                                                            |
| **Advanced Encoding & Decoding**: SHA-512, HMAC-SHA256, Base64URL, Unicode, HTML, JSON, JWT, Timestamp Conversion | ❌                 | ✅                    | Designed for advanced verification, signing, and analysis workflows                                                                                                                                                                                                                                                    |
| **Intelligent Encryption Logic Analysis (Added in v1.0.1)**                                                       | ❌                 | ✅                    | Combines request context with related JS / HTML clues to help identify encoding, hashing, signatures, or hybrid encryption workflows                                                                                                                                                                                   |
| In-Page Replay, In-Page Fuzzing, **HTTP / WebSocket Micro Fuzz**, Injection Point Marking                                           | ❌                 | ✅                    | Suitable for dynamic pages, WAF testing, real-time channels, and high-frequency parameter probing                                                                                                                                                                                                                                   |
| Switch HTTP Method, Switch Target Domain                                                                          | ❌                 | ✅                    | Useful for multi-environment debugging and verification                                                                                                                                                                                                                                                                |
| **Intelligent Proxy Router (v1.0.1; Community since v1.0.6)**                                                     | ✅                 | ✅                    | Located below “Capture Type / Suffix” in Settings. Requests matching site rules can be automatically forwarded to upstream proxies such as Burp Suite or Yakit, while unmatched traffic continues using the original network path. The Firefox version additionally supports “Compatibility Mode” and “Takeover Mode”. |
| **HawkEye Browser Automation MCP (v1.0.6)**                                                                        | ❌                 | ✅                    | A security-specialized Playwright-like MCP joining browser interaction with HawkEye capture, replay, mutation, sensitive-data, and evidence tools |
| **Browser-level Agent / Agent Mode (v1.0.6)**                                                                      | ❌                 | ✅                    | Requires an active trial or Professional license; performs multi-turn planning and tool calls in the real browser session |
| AI Analysis Settings, AI Result Analysis, AI Analysis, AI Test Case Generation                                    | ❌                 | ✅                    | All AI-related capabilities are included in the Professional Edition                                                                                                                                                                                                                                                   |
| **AI Task Console (since v1.0.2)**                                                                                    | ❌                 | ✅                    | Multi-stage automation: Intelligent Penetration and CTF modes; **Skills knowledge-base injection** (v1.0.3: smarter defaults and manual-selection priority), **in-task supplementary hints**; **timeline log with draggable split** (v1.0.5); tighter orchestration and tool chains; ties history, replay, and evidence into reports                                                                                                                                |
| **AI Skills Knowledge Base (v1.0.3)**                                                                               | ❌                 | ✅                    | v1.0.6 includes 19 pentest + 28 CTF sub-modules and external Skill import. Advanced Settings is the global allowlist; Skills start off in each new Agent conversation and must also be clicked there. Anything not enabled at both gates cannot be called                                                                                                                                                                      |
| **Tampermonkey / Page Script Workspace (v1.0.4)**                                                                   | ❌                 | ✅                    | Import `.user.js`, script library management, one-click inject; AI create/optimize scripts; **Smart Decode Assistant** (v1.0.5); integrates with capture, replay, and scanning tools                                                                                                                                                                                                                                        |
| **AI Task Smart Script Dispatch (v1.0.4)**                                                                          | ❌                 | ✅                    | During tasks, AI can list, run, and create page scripts—combines with Skills, replay, and Fuzz orchestration                                                                                                                                                                                                                                                                    |
| **Advanced codec / smart nested decode (enhanced in v1.0.5)**                                                       | ❌                 | ✅                    | Replay workbench adds AES/DES/RSA/SM; AI tasks include `codec.transform`; inline packet codec aligned with replay                                                                                                                                                                                                                                                    |
| Hidden Link & Static Threat Detection, Report Export, High-Reputation Top-Level Domains                           | ❌                 | ✅                    | Rule scanning, reporting, and advanced noise-reduction capabilities                                                                                                                                                                                                                                                    |
| **Full Deep Search, Sensitive Matching, Custom Regex / Keyword Libraries (Community since v1.0.6)**              | ✅                 | ✅                    | Moved to Community compared with v1.0.5; includes full request/response search, built-in rules, custom regex, keyword libraries, and batch import/export                                                                                                                                                                |
| Batch Export, Batch Delete, Batch Replay, Batch AI Analysis, Batch Hidden-Link Detection                          | ❌                 | ✅                    | Unified batch-processing workflow exclusive to the Professional Edition                                                                                                                                                                                                                                                |

> Version `1.0.1` initially introduced two Professional features: `Intelligent Proxy Router` and `Intelligent Encryption Logic Analysis`; the router moved to Community in `1.0.6`.
> Version `1.0.2` adds **WebSocket** (capture / frame replay / **WS micro Fuzz** / frame intercept), the **AI Task Console** (including **in-task hints** and multi-stage orchestration improvements), and moves **intercept** capabilities to the Community Edition.  
> Version `1.0.3` adds **Skills injection for AI tasks**, **capture/intercept UX improvements**, and **online activation**.  
> Version `1.0.4` adds **Tampermonkey script support**, **AI smart script dispatch**, **capture/intercept reliability**, and **Firefox cross-browser alignment**.  
> Version `1.0.5` adds **AI Task Console overhaul**, **thicker Skills + AI Generate Skill**, **codec enhancements**, and **UX improvements**.
> Version `1.0.6` adds the **security-specialized HawkEye MCP (PRO)**, **browser-level Agent (PRO only)**, **Firefox / Chrome performance redesign**, **default-off Agent Skills with two explicit gates**, and **bilingual / privacy-agreement parity**; it also opens **Smart Proxy Router, Full Deep Search, and Sensitive Matching** to Community.

### Understanding the Edition Boundaries in One Sentence

- **Community Edition focuses on:** packet inspection (**HTTP / WebSocket**), understanding, basic verification, essential encoding/decoding, **intercept/tamper, Smart Proxy Router, Full Deep Search, and Sensitive Matching**.
- **Professional Edition focuses on:** page-context validation, mutation testing, AI analysis, AI tasks & Skills, the **browser-level Agent / MCP**, hidden-link scanning, and large-scale batch workflows.
- If you simply want to evaluate the product’s core value first, the Community Edition is already sufficient for the most important primary workflow.

---

## 5. Product strengths
1. **No proxy wall**: extension form factor—**no separate JVM, no dedicated proxy port**; configure targets and capture.  
2. **Session match**: same **same-origin session** as the active tab; fewer **random logouts** on replay.  
3. **One workbench**: history, intercept, replay, encoders, micro Fuzz, **WebSocket**, sensitive, dark-link, AI—**same sidebar**.  
4. **Modern frontends**: **XHR/Fetch, WebSocket, FormData, multipart**; **Raw / Hex** within extension limits.  
5. **Dynamic-page forensics**: **in-page replay / in-page Fuzz** runs in real DOM—helps with some **WAF / challenge** pages.  
6. **Sensitive & dark-link built-in**: list badges, detail rollups, exportable reports for **dev self-check and authorized first pass**.  
7. **AI in the loop**: **AI Task Console** (multi-stage + **Skills knowledge base** + **in-task hints**), **AI test cases**, **AI Fuzz payloads**, **single-packet AI**, **batch AI** (multi-packet summary for **supply-chain / dependency** hints), **dark-link rules + AI**—same sidebar, fewer tools.  
8. **AI under your control (BYOK)**: you choose model and endpoint; **data only goes to your API**—cloud (DeepSeek, SiliconFlow, Qianfan, etc.) or **on-prem**.  
9. **Light footprint**: runs with the browser vs heavy standalone proxy stacks.

---

## 6. Comparison with common tools
Compared across shape, session, workflow, and specialties: **Hx0 HawkEye**, **Burp Suite**, **Yakit**, **HackBar / simple extensions**. **Enterprise deep scanning, complex Intruder, non-browser traffic** still belong on dedicated platforms—use **alongside** this product.

| Dimension | **Hx0 HawkEye** | **Burp Suite** | **Yakit** | **HackBar / simple extensions** |
| --- | --- | --- | --- | --- |
| **Shape & deploy** | Browser extension; **sidebar = main hub**; optional floating ball; **no JVM, no proxy port** | Java proxy + browser trust; suite, heavy | Desktop + engine/plugin ecosystem; security platform | Often toolbar mini-panel or single-request helpers |
| **Day-to-day cost** | **Install and go**; no forced system proxy; EN/ZH UI, flow in sidebar | Proxy, root trust, Proxy/Repeater learning curve | Install + pipeline/workflow learning | Fast start, scattered features, weak “project” workspace |
| **Browser session** | **Same tab origin**; fewer login gaps on replay | Via proxy; cookie juggling into Repeater common | Via proxy/engine; different from pure extension | Manual headers/cookies |
| **Modern APIs (XHR/Fetch/SPA + WS)** | Page-world fetch/XHR hooks; optional **WebSocket** capture / frame replay / frame tamper; **multipart Raw/Hex** (within limits) | Full proxy visibility, very capable | Plugins cover complex cases | Often no history, no Hex/sensitive rollups |
| **History & workbench** | **IndexedDB**; rich filters (including **WebSocket** type); detail/replay/fuzz/AI **in sidebar** | Proxy History very strong; more app switching | Platform records & collaboration | Usually **no or weak history** |
| **System proxy / non-browser** | **In-browser** HTTP(S) and **page WebSocket** | Strong | Strong | Weak |
| **Intercept** | **HTTP + WebSocket frames**; queued; per-item or bulk in sidebar | Proxy intercept, industry standard | MITM / workflows | Rare or URL-only |
| **Replay / fuzz** | Replay + **HTTP/WS micro Fuzz** + **in-page replay/fuzz** (e.g. form POST) | Repeater / Intruder mature | Web Fuzzer, etc. | Rarely concurrent fuzz or structured diff |
| **Sensitive / dark-link / reports** | **Built-in rules + badges + rollups**; export | Scanner, BApps; licensing/config | Rich PoC/plugins | Rarely built-in |
| **AI assist** | **BYO API**, **you control data path**; **Skills knowledge base** and **AI Task Console** multi-stage orchestration | Often third-party or DIY | Growing | Uncommon |
| **Active scan / heavy automation** | Not the focus; **manual tight loop** | Scanner, macros, plugins | PoC, batch, collaboration | Minimal |
| **Resource use** | With browser, **light** | Proxy + JVM, usually higher | Varies | Tiny but narrow |


**Suggested combo**: HawkEye as daily **in-browser hub**; add **Burp / Yakit** for full-site scanning, huge wordlists, or non-browser clients—“fast sidebar loop + deep platform.”

---

## 7. Offline install (v1.0.6 · ZIP only)

Download exactly one official package for your browser from [GitHub Releases](https://github.com/asaotomo/Hx0-HawkEye/releases):

- `Hx0-HawkEye-Chrome-V1.0.6-Official.Release.zip`
- `Hx0-HawkEye-Firefox-V1.0.6-Official.Release.zip`

This release intentionally ships **no CRX or XPI**. Chrome restricts or disables non-store CRX installs, while release Firefox requires signed XPI packages. ZIP-only distribution avoids presenting fragile sideload paths as permanent installs and keeps the packaged runtime contents inspectable. The archives contain no source, build scripts, source maps, secrets, or debug files.

### Chrome / Edge / Chromium

1. Extract the Chrome ZIP to a **stable folder**; do not move or delete it afterward.
2. Open `chrome://extensions/` (use `edge://extensions/` in Edge).
3. Enable **Developer mode**.
4. Click **Load unpacked**.
5. Select the extracted directory that directly contains `manifest.json`, then pin HawkEye to the toolbar.

Before upgrading, export anything important and close HawkEye sidebars. Replace the old fixed-folder contents with the new release, then click **Reload** on the extensions page. Do not load two HawkEye directories at once; different extension IDs keep separate local data.

### Firefox

1. Extract the Firefox ZIP.
2. Open `about:debugging#/runtime/this-firefox`.
3. Click **Load Temporary Add-on**.
4. Select `manifest.json` in the extracted directory.
5. Load it again after every Firefox restart.

Regular Firefox does not permanently install unsigned extensions. This repository does not recommend disabling signature enforcement to imitate permanent installation; organization-wide deployment should use Mozilla signing or enterprise policy.

### After install

- **Toolbar popup**: capture/intercept, target scope, MCP control, and Advanced Settings.
- **Sidebar**: History, Intercept, Replay, AI Tasks, browser-level Agent, and Page Scripts.
- **User Manual**: complete operation guide, browser differences, MCP setup, Skills, privacy, and troubleshooting.
## 8. User manual
After install, open the **in-product User Manual** for full tutorials covering **MCP / Agent setup**, a **mainstream Browser MCP comparison**, **Chrome / Firefox differences**, **request header/body troubleshooting**, **screenshot file save**, **FAQ**, and **licensing**.

### MCP vs Agent in one minute

- **HawkEye MCP** is a local tool bridge, not an AI model. Install Node.js 18+, download the single `hawkeye-mcp-server.mjs` file from the popup, click **Copy universal config**, and add it to an MCP Host such as Codex, Cursor, or Claude Code. No `npm install` is required.
- **Built-in Agent Mode** is HawkEye's multi-turn planning/execution UI. Configure Base URL, API key if required, and Model under Advanced settings, then open **Capture UI → Agent Mode**. It does not require a third-party MCP Host.
- **AI Tasks** are repeatable authorized workflows with Scope, Skills, safety gates, and structured reports, rather than a free-form Agent conversation.

For positioning: [Playwright MCP](https://github.com/microsoft/playwright-mcp) focuses on cross-browser test/isolated automation; [Chrome DevTools MCP](https://github.com/ChromeDevTools/chrome-devtools-mcp) on Chrome DevTools and performance debugging; [Browser MCP](https://docs.browsermcp.io/) on general actions in an existing logged-in Chrome tab. HawkEye's core distinction is one workflow combining **real Chrome + Firefox sessions, capture, intercept/tamper, replay/fuzz, sensitive/dark-link evidence, and Agent execution**. See in-product Manual **§3.2** for the detailed comparison.

---

## 9. Security & compliance
+ Use capture, intercept, replay, and Fuzz **only on systems you are authorized to test**.  
+ **AI analysis, AI Tasks, and Agent Mode** may send traffic and page context needed for the task to the third-party or internal model endpoint you configured. Default automatic redaction attempts to mask common Cookie/Token fields but cannot guarantee every secret is detected. Disabling it may send raw authentication context.
+ HawkEye MCP Server listens only on local loopback, but a trusted third-party Agent / MCP host may still forward tool results to its configured model service. Turn the bridge off when unused.
+ See the in-extension bilingual **Terms & Privacy agreement** for the complete data scope, exceptions, retention, and user rights.
+ Use **Render** and similar features in trusted environments; sandboxing reduces but does not remove risk from malicious responses.  
+ Commercial use: follow **license** terms in the product.

---

## 10. How to Obtain the Activation Code

New users can first use the **full Pro trial for 30 minutes**. When the trial ends without activation, the product automatically falls back to **Community**. If the experience fits your workflow, you can obtain a Pro activation code through the following methods:

**Visit [the activation code tutorial](https://www.yuque.com/u12459488/bzqpay/udkx5qy1x6guinz0?singleDoc) to get your activation code for free for a limited time.**

---

## 11. Contact & feedback
**Hx0 Team (Hx0战队)**

+ **Hx0 HawkEye website**: [https://www.hx0.store/products/hawkeye](https://www.hx0.store/products/hawkeye) (product overview, downloads, and docs)
+ WeChat official account / knowledge planet: **Hx0战队**
+ Email: [hx0studio@foxmail.com](mailto:hx0studio@foxmail.com)

Please include browser + version, extension version, repro steps, and screenshots when reporting issues.

---

## 12. Disclaimer
This project and extension are for **security research, development debugging, and authorized testing** only. Obey applicable laws and scope of authorization.  
The authors and contributors **assume no liability** for **unauthorized testing** or its consequences.

---

## 13. 1.0.1 Changelog

This `1.0.1` update primarily focuses on the enhancement of two professional edition capabilities:

- **Smart Proxy Dispatcher (Professional Edition)**: Added a proxy dispatch entry below the `Capture Type / Suffix`on the basic settings page. It can forward browser requests matching site rules to Burp, Yakit, or other upstream proxies, while unmatched requests continue on their original network path. This is suitable for integrating "native browser session capture" and "in-depth proxy debugging" into a single workflow, reducing the overhead of frequently switching system proxies.
  

<img width="430" height="599" alt="image" src="https://github.com/user-attachments/assets/64221294-63da-4aff-aeec-69250f0b6650" />


- **Encryption Logic Intelligent Analysis (Professional Edition)**: Located to the right of the AI Analysis button. The model combines clues from the current request's URL, parameters, headers, body, and response, along with function names, field names, and submission flows from JS/HTML on the same page, to help determine if encoding, hashing, signing, or hybrid encryption is implemented on the front-end. It is suitable for reviewing changes in signature chains before and after packet modification.（In a nutshell: Let AI help you guess encryption, encoding, or signature logic, saving you the time of manual reverse engineering.）

  <img width="1548" height="940" alt="image" src="https://github.com/user-attachments/assets/f6a6e38e-21c2-4531-b6a9-56234e43e043" />

  <img width="1531" height="929" alt="image" src="https://github.com/user-attachments/assets/718d6ad7-1f99-4c99-b3c7-108afdd48ac0" />

  <img width="1548" height="940" alt="image" src="https://github.com/user-attachments/assets/213b5822-bcf7-404c-baa7-69111dd1116b" />

  <img width="1548" height="940" alt="image" src="https://github.com/user-attachments/assets/b762a1cc-6054-4d17-9fa1-0adec61f35b8" />

  <img width="1548" height="940" alt="image" src="https://github.com/user-attachments/assets/e255ea62-6817-4ad3-815e-c1f7b40c77e2" />

  
- **Stability Improvements**: Concurrently strengthened details related to request header completion and proxy release in the standard capture mode, reducing display discrepancies and the probability of conflicts when switching between standard mode, intercept mode, and proxy settings.
- **Sidebar and Batch Page Optimization**: Sidebar message display and interaction optimization (consistent across both ends), overall layout optimization of batch pages.  
- **Enhanced In-Page Replay and In-Page Fuzz Functions**: Updated to support form POST (Request Header Content-Type: application/x-www-form-urlencoded).
- **Replay Workspace Optimized**:  Encoding/decoding functions now support response body processing, added scope differentiation, and unified undo/redo records for both requests and responses.
- **“All domains” filter**: Fixed incorrect list or filter behavior when the host filter is set to “All domains” and it interacts with the workbench scope (current tab vs all traffic).
- **Capture / intercept list**: Column widths can be adjusted by dragging the vertical handles on the right side of each header cell; widths are saved locally and restored the next time you open the panel.
- **302 / redirect capture**: Improved how redirects (e.g. 302) are recorded and deduplicated across webRequest and passive CDP paths, reducing duplicate entries and missed captures caused by inconsistent typing.
- **Three-state header sorting**: The capture / intercept table headers cycle default → ascending → descending → default. The Fuzz results table uses the same pattern; clearing sort restores the original row order by sequence; clicking a column-width handle does not trigger sorting.

## 14. 1.0.2 Changelog

This `v1.0.2` release strengthens **HTTP replay headers**, adds a **WebSocket workbench**, expands the **AI Task Console** (**in-task hints** + **orchestration improvements**), and brings **intercept** to the Community Edition—boosting Web assessments, CTF workflows, and daily capture analysis.

<img width="1055" height="1491" alt="v1 0 2海报-en" src="https://github.com/user-attachments/assets/98ec2d5e-e410-40c3-92fd-088a87f2d467" />


## Main Updates

### 1. Replay Requests Now Support Critical Header Overrides

The Replay Workbench has been enhanced to better handle special request headers. You can now edit and apply the following fields directly inside Raw requests:

- `Referer: https://xxx.com`
- `User-Agent: xxx`
- `Origin: https://xxx.com`
- `X-Forwarded-For: x.x.x.x`

This feature is useful for common scenarios such as referer validation bypass, User-Agent verification, forged origins, and CTF Referer bypass techniques. Users can directly modify request headers in Raw mode and replay them, with behavior designed to closely resemble the replay experience of Burp Suite.

### 2. Added AI Task Module

A brand-new standalone AI Task Module has been introduced to automate the workflow of traffic capture, request analysis, vulnerability testing, and report generation.

The AI Task Module currently supports two modes:

- **Intelligent Penetration Mode**
  Designed for standard Web security testing scenarios. Based on the target site, historical traffic, and page context, the AI can automatically perform information gathering, entry-point analysis, attack modeling, vulnerability probing, and result evaluation.
  
<img width="3912" height="2070" alt="a7d48640ee2e4fed8032b4cf48229b23" src="https://github.com/user-attachments/assets/707007d2-7dc9-48c2-8981-8e7732219690" />

- **CTF Capture-the-Flag Mode**
  Designed for Web-based CTF challenges. The AI automatically plans solving strategies around challenge entry points, hints, response behaviors, and suspicious parameters. It attempts to construct exploitation requests and generates a post-analysis report after successfully capturing the Flag.

  <img width="3912" height="2070" alt="27e66bc42b733225d16ceccd9e78eed7" src="https://github.com/user-attachments/assets/a00c9dc2-8203-4a2a-aadd-ee32971d0138" />

The AI Task module records execution, evidence, key payloads, Flag hits, and final reports; while **running**, use toolbar **Supplementary hints** to **queue** context for later turns **without replacing** the pre-launch brief. The underlying **multi-stage adaptive orchestration** is continuously hardened (tool chain, budgets, readability). See in-product User Manual §10.

### 3. Interception Mode Is Now Available in the Community Edition

Interception Mode is now officially available for Community Edition users (**HTTP** and **WebSocket frames** when rules match).

Community Edition users can now pause, inspect, modify, and forward requests through Interception Mode, making manual testing, parameter debugging, and request verification much more convenient.

<img width="1956" height="1035" alt="image" src="https://github.com/user-attachments/assets/6154a019-fbbe-45d6-bbbf-3b68227db08b" />

### 4. WebSocket Capture, Replay, Micro Fuzz, and Intercept

Enable **WebSocket** under capture types, then filter by type in the sidebar; handshakes often show as `GET 101`, frames as **`WS`** (**`OUT`** / **`IN`**). **Frame replay** shares the HTTP workbench and needs an **`OPEN`** page socket; **`§...§` + Micro Fuzz** uses the next inbound frame as the response. **Intercept** supports **per-frame** edit/forward/drop. Scope is page-created WebSockets inside the browser—not a system MITM. Details: User Manual §5.

<img width="1548" height="942" alt="image" src="https://github.com/user-attachments/assets/d7a6f0fa-4894-4e30-a729-2c962aad194a" />

### 5. AI Tasks: In-Task Supplementary Hints

While a task **runs**, expand **Supplementary hints**, enter newly noticed parameters, reflections, paths, or CTF hints, and **Submit**; entries are **queued** with timestamps and appended as **runtime user supplementary hints** for later model turns, with per-turn and queue size caps. **Do not** paste real secrets; redaction and authorization rules match the full AI workflow.

<img width="1548" height="942" alt="image" src="https://github.com/user-attachments/assets/6634413a-4d35-4e2f-b286-5c7a88c29c84" />
<img width="1548" height="942" alt="image" src="https://github.com/user-attachments/assets/c40d4f83-6d44-46a6-b8e3-d170f274c2f7" />

### 6. AI Tasks: Orchestration and Execution Improvements

The **AI Task Console** multi-stage adaptive pipeline is tightened: **multi-turn agent** loops with real HTTP evidence, **structured runtime memory** (including failure memory aligned with sidebar metrics), and **protocol checks / replanning** for steadier stages and CTF early-finalize paths.

---

## 15. 1.0.3 Changelog

This `v1.0.3` release brings three main updates:

### 1. AI Tasks Support Skills Loading (Pro)

The **AI Task Console** can inject built-in **penetration / CTF knowledge bases**, or **import external SKILL.md files and skill folders** from Advanced Settings. Pick libraries and submodules in the task panel—they are injected as context to support multi-stage automated testing and triage.

<img width="438" height="575" alt="image" src="https://github.com/user-attachments/assets/82d7170f-cd6b-4e38-9b78-49a788af2b3a" />

<img width="1956" height="1040" alt="image" src="https://github.com/user-attachments/assets/9f970717-f7df-4dc6-910f-74c70b989cad" />


### 2. Capture & Intercept Experience Improvements

Smoother **capture / intercept** workflows in the sidebar: cleaner filtering and scope switching, easier list browsing, and more fluid edit/forward actions for day-to-day debugging and manual testing.

### 3. Online Activation Added

**Single-click** the popup **status badge** to open Software activation with a new **Online** tab for subscription or lifetime membership. Benefits sync online and are **cached locally**, so Pro features continue offline while the cache/subscription remains valid—alongside the existing **offline activation code** path for easier checkout and renewal.

<img width="438" height="575" alt="image" src="https://github.com/user-attachments/assets/e2a80834-6d66-4ffa-bcf3-8151b322de59" />

---

## 16. 1.0.4 Changelog

This `v1.0.4` release brings four main updates:

### 1. Tampermonkey Scripts + Page Script Workspace (Pro)

Import `.user.js` userscripts and manage them in the sidebar with one-click inject. AI can create or optimize scripts from traffic and tie them into capture, replay, and sensitive scanning. Human-written scripts, AI-written scripts, and AI-orchestrated scripts share one workflow.

<img width="3046" height="1688" alt="041bc1f31c42a9d53fedf9c92b972b9a" src="https://github.com/user-attachments/assets/067a5dab-9e00-4cd9-a964-012d5733f8d5" />

<img width="3096" height="1882" alt="f48bb626b893c2efe11b0cdf9c8e69b9" src="https://github.com/user-attachments/assets/1e805ed7-b7ab-4fc8-a6b3-a9e779ce5507" />


### 2. AI Task Smart Script Dispatch (Pro)

Enable **Smart Script Dispatch** so AI tasks can list, run, or create page scripts during pentest / CTF—pull page-side intelligence back, then continue replay verification and reporting.

### 3. Capture / Intercept Reliability

More stable intercept for local labs and self-signed HTTPS; fixes regressions such as empty intercept queues; packet editor now accepts Chinese input correctly.

### 4. Firefox Stability and Cross-Browser Alignment

Fixes Firefox capture, sidebar, intercept, replay, and script injection; daily experience is further aligned across Chrome and Firefox.

> See `1.0.4更新说明` in the repo for the full release notes.

---

## 17. 1.0.5 Changelog

This `v1.0.5` release brings four main updates:

### 1. AI Task Console Overhaul (Core Release)

Execution log redesigned as a **timeline card stream** (color-coded stage / AI / test / tool-call cards; expandable tool JSON); **draggable split** between log and report; **task background AI understanding** before launch; reports include **vulnerability inventory + request/response evidence**; built-in `crypto.logic.analyze` and `codec.transform` for advanced crypto workflows.

<img width="1526" height="891" alt="image" src="https://github.com/user-attachments/assets/a1e25ad7-7aa1-4b01-a42f-adec0a4dbcc6" />

### 2. Thicker Skills Library + AI Generate Skill

Built-in sub-modules expanded to **19 pentest + 28 CTF**; **Smart Enable** toggle per main Skill; **AI Generate Skill** in Advanced Settings—create a single skill or collection and save as standalone Skill, built-in sub-module, or append to an imported skill.

<img width="2084" height="1700" alt="ac1eb01ce372ddf86b80d79ce4ac610b" src="https://github.com/user-attachments/assets/889cea2a-0751-434b-bab7-d2ff84bf4a0e" />

<img width="450" height="570" alt="a9c5841467cee3adc1a220001c27b2b5" src="https://github.com/user-attachments/assets/15b6d6a5-8718-4442-a8d1-6a4a71be5a6a" />

<img width="450" height="570" alt="image" src="https://github.com/user-attachments/assets/68b436cd-5b20-466a-b425-dd7bb22750ed" />


### 3. Codec Capabilities Completed

Replay workbench adds **AES / DES / RSA / SM** and smart nested decode; built-in **Smart Decode Assistant** (enabled by default): select text on any page for common decode and hash hints; advanced AES / nested chains still go through replay or inline packet codec.

<img width="1024" height="523" alt="image" src="https://github.com/user-attachments/assets/c0ffab9d-2de8-4e67-8d24-2f24dc5250e9" />


### 4. UX Improvements and Bug Fixes

Fixed various Chrome / Firefox system issues; better coordination among intercept / debug mode / passive listening toggles; improved sidebar and settings copy; user manual updated to **v1.0.5**.

---

## 18. v1.0.6 changelog

### 1. HawkEye Browser Automation MCP (PRO)

HawkEye now exposes a security-oriented browser MCP, positioned like a security-specialized Playwright MCP. MCP-capable Agent Hosts such as Codex, Cursor, and LM Studio connect to `hx0-hawkeye`; the Host model can then autonomously call `browser_navigate`, `browser_type`, `browser_snapshot`, and HawkEye capture, replay, mutation, codec, TLS, sensitive-data, and evidence tools in the real browser. The loopback-only server supports stdio, Streamable HTTP, and legacy SSE and requires the user to enable the extension bridge. This capability is separate from the in-extension AI Task Console.

<img width="1800" height="1382" alt="Codex, Cursor, or LM Studio controlling the browser through HawkEye MCP" src="https://github.com/user-attachments/assets/ff0c2671-6559-4f38-b6f5-2a6a50c5375a" />

### 2. Browser-level Agent (PRO)

Agent Mode requires an active trial or Professional license. It starts from the user's real current HTTP(S) tab and supports multi-turn planning, approval modes, complex controls / iframe / Shadow DOM interaction, visual screenshots, attachments, traffic analysis, replay, codecs, autonomous public-web research, native downloads, durable long-context memory, and expandable tool evidence.

<img width="1500" height="900" alt="v1.0.6 Browser-level Agent" src="https://github.com/user-attachments/assets/b9491db0-727c-4a09-8020-0f87abd97efe" />

### 3. Extreme performance and low resource use

Firefox no longer keeps passive capture listeners alive unnecessarily: `webRequest` listeners exist only while their feature state requires them. DOM snapshots, ref assignment, list rows, capture notifications, MutationObserver reuse, Agent transport, and MCP transport now use one-pass traversal, caches, batching, compact envelopes, and bounded pagination. Large results remain resumable through `next_cursor`, preserving evidence while reducing transfer and memory cost.

### 4. Default-off Skills and a strict allowlist

The 19 pentest and 28 CTF built-in sub-modules now include the v1.0.6 runtime contract. Skills are off in new Agent conversations. Both Advanced Settings enablement and the current conversation's Skills control must be on; otherwise Skill bodies never enter model context and Agent cannot bypass the user's selection.

### 5. Community capabilities opened since v1.0.5

Smart Proxy Router, Full Deep Search, and Sensitive Information Matching (built-in rules, custom regex, keyword libraries, and batch import/export) are available in Community starting with v1.0.6. AI Tasks, AI Skills, browser-level Agent, and HawkEye MCP remain Professional features.
