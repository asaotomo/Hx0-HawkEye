# 🦅 Hx0 HawkEye: Full-stack lightweight capture & AI security auditing extension


【[中文](./README.md) / English】


![](https://img.shields.io/badge/Network-No_system_proxy-success)  ![](https://img.shields.io/badge/UI-Sidebar_integrated-5865F2)  ![](https://img.shields.io/badge/Session-Same_origin_XHR_Fetch-00A86B)  ![](https://img.shields.io/badge/Capture-Intercept-4285F4)  ![](https://img.shields.io/badge/Capability-Traffic_replay-blue)  ![](https://img.shields.io/badge/Capability-Micro_Fuzz-8B5CF6)  ![](https://img.shields.io/badge/Capability-Sensitive_data-FF69B4)  ![](https://img.shields.io/badge/Capability-Dark_link_scan-333333)  ![](https://img.shields.io/badge/AI-BYOK_optional-orange)

## 1. What it is
**Skip the proxy hassle—truly ready out of the box.** Hx0 HawkEye is a native browser extension (Chrome / Firefox and mainstream Chromium) that gives you a full **capture, intercept, replay, micro-Fuzz, and AI-assisted auditing** loop directly in the sidebar.

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774276035508-0a9af8e0-4a11-4c83-9fe7-8ea82484d093.png)

#### ⚡ Core advantage: why not a classic proxy?
+ **Zero environment overhead**: no Burp Suite required, no system proxy, no root trust or Java setup.
+ **Session fidelity**: sees real page **XHR / Fetch** traffic with the **same origin login state** as the active tab—no more “proxy ate my cookies” or constant re-auth pain.
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
With **SPAs and heavy XHR/Fetch**, engineers constantly switch between “real browser session” and “capture / tamper / replay.” Classic proxies (e.g. Burp) are powerful but need system proxy and trust, and **cookies / login state** can diverge from the tab; lightweight toolbar extensions often lack **durable history, structured detail, and a closed-loop workbench**.

**Hx0 HawkEye** aims to keep **no mandatory system proxy** while folding **capture → filter → detail audit → intercept → replay → micro Fuzz → sensitive & dark-link checks → optional AI** into **one sidebar hub**, cutting context-switch cost for dev triage and **authorized** API review.

---

## 3. Features
Core flow: **Capture** → **Filter** → **Detail** → **Replay** (optional **AI test cases**) → **Micro Fuzz** (optional **AI payloads**) → **Dark-link / AI packet analysis** (including **batch AI / dark-link workbenches** after multi-select).

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
| **Capture** | Hooks `fetch` / XHR in the page world; records requests and responses (including bodies, with size guards). Noise control via **host/IP wildcards**, **resource types** (XHR/Fetch, JSON, HTML, JS, binary, etc.), and **custom suffixes**. |
| **History** | **IndexedDB** persistence; filters by type, host, method, status, **sensitive hits**, search; default scope **current page** or **all packets**. |
| **Intercept** | Queued hold; **edit, forward, drop** in the sidebar; bulk actions; shares target rules with capture. |
| **Detail audit** | **Pretty / Raw / Hex**; response **Render** (sandbox); **sensitive** aggregation & highlights; copy full URL from title; download split raw **.txt**; **Burp-style** export. |
| **Replay** | Edit raw traffic and replay; **in-page replay** (some WAF challenge pages, GET); undo/redo; host switch; **AI test cases** from current request/options (requires AI config). |
| **Encode / hash** | MD5, SM3, SHA, ROT13, Base64, URL, Hex, etc.; scope: **selection / param values only / full URL line**. |
| **Micro Fuzz** | `§...§` injection points; **Start Fuzz** and **in-page Fuzz** (GET); baseline diff; **AI payloads** from model context; pair with Render, sensitive, and **AI result** views. |
| **Dark link & static threats** | Rule scan on static HTML, etc.; **high-trust TLD** allowlist; downloadable reports; **AI packet/semantic** interpretation; **batch dark-link** workbench for **horizontal compare** and **third-party script clues** (supply-chain first pass). |
| **AI (optional)** | **Single packet**: interpret **request + response**, anomalies and risk notes. **Batch**: multi-select history, dedicated tab with **per-row highlights + summary** for multi-endpoint evidence. Models: OpenAI, DeepSeek, local LM Studio, **custom base URL**; **OpenAI-compatible** and paths such as **Baidu Qianfan coding plans**; traffic goes **only to your configured endpoint** (BYOK). |
| **Sensitive matching** | Built-in rules (IDs, phones, cards, email, Shiro/JWT/Swagger/UEditor/Druid fingerprints, IP, domain, CTF flags, etc.) plus **custom regex** and **keyword lists**; import/export, clear-all. |
| **Batch** | Bulk export/delete, **batch AI**, **batch dark-link** (separate tab), batch replay, etc. |
| **i18n** | UI **中文 / English**. |


**Chrome vs Firefox** differ in sidebar hosting, intranet/self-signed HTTPS helpers, and intercept prompts; **core features align**. See in-extension help after install for details.

---

## 4. Product strengths
1. **No proxy wall**: extension form factor—**no separate JVM, no dedicated proxy port**; configure targets and capture.  
2. **Session match**: same **same-origin session** as the active tab; fewer **random logouts** on replay.  
3. **One workbench**: history, intercept, replay, encoders, micro Fuzz, sensitive, dark-link, AI—**same sidebar**.  
4. **Modern frontends**: **XHR/Fetch, FormData, multipart**; **Raw / Hex** within extension limits.  
5. **Dynamic-page forensics**: **in-page replay / in-page Fuzz** runs in real DOM—helps with some **WAF / challenge** pages.  
6. **Sensitive & dark-link built-in**: list badges, detail rollups, exportable reports for **dev self-check and authorized first pass**.  
7. **AI in the loop**: **AI test cases**, **AI Fuzz payloads**, **single-packet AI**, **batch AI** (multi-packet summary for **supply-chain / dependency** hints), **dark-link rules + AI**—same sidebar, fewer tools.  
8. **AI under your control (BYOK)**: you choose model and endpoint; **data only goes to your API**—cloud (DeepSeek, SiliconFlow, Qianfan, etc.) or **on-prem**.  
9. **Light footprint**: runs with the browser vs heavy standalone proxy stacks.

---

## 5. Comparison with common tools
Compared across shape, session, workflow, and specialties: **Hx0 HawkEye**, **Burp Suite**, **Yakit**, **HackBar / simple extensions**. **Enterprise deep scanning, complex Intruder, non-browser traffic** still belong on dedicated platforms—use **alongside** this product.

| Dimension | **Hx0 HawkEye** | **Burp Suite** | **Yakit** | **HackBar / simple extensions** |
| --- | --- | --- | --- | --- |
| **Shape & deploy** | Browser extension; **sidebar = main hub**; optional floating ball; **no JVM, no proxy port** | Java proxy + browser trust; suite, heavy | Desktop + engine/plugin ecosystem; security platform | Often toolbar mini-panel or single-request helpers |
| **Day-to-day cost** | **Install and go**; no forced system proxy; EN/ZH UI, flow in sidebar | Proxy, root trust, Proxy/Repeater learning curve | Install + pipeline/workflow learning | Fast start, scattered features, weak “project” workspace |
| **Browser session** | **Same tab origin**; fewer login gaps on replay | Via proxy; cookie juggling into Repeater common | Via proxy/engine; different from pure extension | Manual headers/cookies |
| **Modern APIs (XHR/Fetch/SPA)** | Page-world fetch/XHR hooks; **multipart Raw/Hex** (within limits) | Full proxy visibility, very capable | Plugins cover complex cases | Often no history, no Hex/sensitive rollups |
| **History & workbench** | **IndexedDB**; rich filters; detail/replay/fuzz/AI **in sidebar** | Proxy History very strong; more app switching | Platform records & collaboration | Usually **no or weak history** |
| **System proxy / non-browser** | **Browser HTTP(S)** focus | Strong | Strong | Weak |
| **Intercept** | Queued; per-item or bulk in sidebar | Proxy intercept, industry standard | MITM / workflows | Rare or URL-only |
| **Replay / fuzz** | Replay + **micro Fuzz** + **in-page replay/fuzz (GET)** | Repeater / Intruder mature | Web Fuzzer, etc. | Rarely concurrent fuzz or structured diff |
| **Sensitive / dark-link / reports** | **Built-in rules + badges + rollups**; export | Scanner, BApps; licensing/config | Rich PoC/plugins | Rarely built-in |
| **AI assist** | **BYO API**, **you control data path** | Often third-party or DIY | Growing | Uncommon |
| **Active scan / heavy automation** | Not the focus; **manual tight loop** | Scanner, macros, plugins | PoC, batch, collaboration | Minimal |
| **Resource use** | With browser, **light** | Proxy + JVM, usually higher | Varies | Tiny but narrow |


**Suggested combo**: HawkEye as daily **in-browser hub**; add **Burp / Yakit** for full-site scanning, huge wordlists, or non-browser clients—“fast sidebar loop + deep platform.”

---

## 6. Offline install (release build)
This extension uses low-level network capture and security APIs and is **not listed on the Chrome or Firefox add-on stores**. Download the **release** package from this repo’s **Releases** page (or mirrors/attachments noted in the release notes), then follow your browser below for **offline install**.

> Actual archive names follow each release. Examples: `Hx0-HawkEye-Chrome-V1.0.0-Official.Release` (folder / `.crx`) and `Hx0-HawkEye-Firefox-V1.0.0-Official.Release` (folder / `.xpi`). Version numbers update per release.
>

### Browser compatibility & recommended methods
| **Browser** | **Recommended method** | **Pros** | **Cons / notes** |
| --- | --- | --- | --- |
| **⭐⭐⭐⭐⭐** **Microsoft Edge** | **Drag-drop** `.crx` | Simplest, persists, few security nag dialogs | Turn on **Developer mode** on the extensions page first |
| **⭐⭐⭐⭐⭐** **360 Speed / QQ / Sogou** | **Drag-drop** `.crx` | Easiest in China desktop browsers; few blocks | Generally smooth for third-party extensions |
| **⭐⭐⭐⭐** **Google Chrome** | Load **unpacked folder** | Persists across restarts | **Do not delete** the unpacked folder; some builds show “disable dev-mode extensions” at startup—dismiss to continue |
| **⭐⭐⭐** **Firefox Developer / ESR** | Install `.xpi` | Persistent, store-like experience | Specific Firefox builds + `about:config` tweak |
| **⭐⭐** **Firefox (release)** | **Temporary load** (folder) | Any Firefox version, no advanced prefs | **Extension disappears after browser quit**—reload each session; good for one-off testing |


### Step-by-step
#### 1. ⭐⭐⭐⭐⭐ Recommended · Edge / 360 Speed / QQ / Sogou
These browsers are friendly to local extensions; `.crx` usually **survives restart** with fewer prompts.

1. Open extensions:  
    - **Edge**: `edge://extensions/`  
    - **360 Speed**: `chrome://extensions/`  
    - **QQ Browser**: `qqbrowser://extensions/`  
    - **Sogou**: `se://extensions/`
2. Enable **Developer mode** (Edge: “Developer mode”; often bottom-left or top-right).
3. **Drag** `Hx0-HawkEye-Chrome-V1.0.0-Official.Release.crx` onto the page.
4. Confirm **Add extension**.

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774270129480-cf1a6ea4-5466-4179-98b8-0d3a0770ac96.png)

#### 2. ⭐⭐⭐⭐ · Google Chrome
Chrome tightly restricts non-store `.crx`; prefer **unpacked folder**.

1. Unzip to a **fixed path** (e.g. `D:\Tools\Hx0-Extension\`); **do not delete** `Hx0-HawkEye-Chrome-V1.0.0-Official.Release`.
2. Open `chrome://extensions/`.
3. Enable **Developer mode** (top right).
4. **Load unpacked** → select that folder.
5. Pin the extension. If you see “Disable extensions in developer mode,” **close the banner**—capture usually still works.

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774270197440-8104787e-3b2f-4c85-ad78-d7c00d8bffa2.png)

#### 3. ⭐⭐⭐ / ⭐⭐ · Mozilla Firefox
Unsigned extensions are restricted; for **permanent** install use **Firefox Developer Edition** or **ESR**.

**Option A: ****⭐⭐⭐**** Permanent (Developer / ESR)**

1. Open `about:config`, accept risk.
2. Find `xpinstall.signatures.required`, set to `false`.

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774270335728-56339724-4b13-4e5d-aa3d-4537b31e2c22.png)

3. Open `about:addons` → Extensions.
4. Gear **⚙** → **Install Add-on From File…**
5. Choose `Hx0-HawkEye-Firefox-V1.0.0-Official.Release.xpi`.

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774270404338-e04bc8ac-19af-42ba-b952-5dc0852b4902.png)

**Option B: ****⭐⭐**** Temporary (any Firefox; lost on quit)**

1. After each Firefox start, open `about:debugging`.
2. **This Firefox** → **Load Temporary Add-on…**
3. In the unpacked `Hx0-HawkEye-Firefox-V1.0.0-Official.Release` folder, select `manifest.json`.
4. Repeat after **every** browser restart.

<!-- 这是一张图片，ocr 内容为： -->
![](https://cdn.nlark.com/yuque/0/2026/png/12839102/1774270459374-5be17f95-c8c4-4155-99a2-e17831e76862.png)

### After install
+ **Toolbar popup**: capture/intercept toggles, targets & types, open capture UI (sidebar)
+ **Sidebar**: history, intercept, replay workbench
+ **Options**: language, AI, payload encoding, sensitive rules, dark-link, etc. (Chrome: `chrome://extensions` → Details → Extension options)

---

## 7. User manual
After install, open the **in-product User Manual** for full tutorials, **Chrome / Firefox differences**, **FAQ**, and **licensing** (exact entry depends on build).

---

## 8. Security & compliance
+ Use capture, intercept, replay, and Fuzz **only on systems you are authorized to test**.  
+ **AI analysis** may send traffic to third-party or internal model endpoints—**redact** and assess cross-border / compliance rules.  
+ Use **Render** and similar features in trusted environments; sandboxing reduces but does not remove risk from malicious responses.  
+ Commercial use: follow **license** terms in the product.

---

## 9. How to Obtain the Activation Code

New users can try it for free for 30 minutes. If you are satisfied with the trial, you are welcome to purchase the product activation code through the following methods:

+ **Method One:** Purchase the activation code on [Xianyu (Idle Fish)]
  
1.[Purchase Link 1](https://m.tb.cn/h.igkesa4?tk=dNrvUzjjrXt)

2.[Purchase Link 2](https://m.tb.cn/h.ihX27bl?tk=Qfan5Zb5B82)

+ **Method Two:​** Join the [Hx0 Team] Knowledge Planet. The first 100 members can obtain a one-year free authorization activation code (the first 10 members can get a permanent authorization), and other members of the planet can enjoy a 20% discount on purchases.
<img width="280" alt="image" src="https://github.com/user-attachments/assets/7e786e1b-815c-46d5-8b7d-252b7eca5d79" />

+ **Method Three:​** Overseas users, please contact the official email (hx0studio@foxmail.com) to purchase an activation code.
---

## 10. Contact & feedback
**Hx0 Team (Hx0战队)**

+ WeChat official account / knowledge planet: **Hx0战队**
+ Email: [hx0studio@foxmail.com](mailto:hx0studio@foxmail.com)

Please include browser + version, extension version, repro steps, and screenshots when reporting issues.

---

## 11. Disclaimer
This project and extension are for **security research, development debugging, and authorized testing** only. Obey applicable laws and scope of authorization.  
The authors and contributors **assume no liability** for **unauthorized testing** or its consequences.

