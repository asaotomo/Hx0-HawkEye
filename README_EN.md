# 🦅 Hx0 HawkEye: Browser Capture & Analysis Powerhouse with Replay, MCP and AI Agent


【[中文](./README.md) / English】


![](https://img.shields.io/badge/Network-No_system_proxy-success)  ![](https://img.shields.io/badge/UI-Sidebar_integrated-5865F2)  ![](https://img.shields.io/badge/Session-Same_origin_XHR_Fetch_WS-00A86B)  ![](https://img.shields.io/badge/Capture-Intercept-4285F4)  ![](https://img.shields.io/badge/Capability-Traffic_replay-blue)  ![](https://img.shields.io/badge/Capability-Micro_Fuzz-8B5CF6)  ![](https://img.shields.io/badge/Capability-Sensitive_data-FF69B4)  ![](https://img.shields.io/badge/Capability-Dark_link_scan-333333)  ![](https://img.shields.io/badge/AI-BYOK_optional-orange)

![](https://img.shields.io/badge/Version-1.0.7-6D28D9) ![](https://img.shields.io/badge/PRO-Security_MCP-7C3AED) ![](https://img.shields.io/badge/Agent-Browser_level-2563EB) ![](https://img.shields.io/badge/Release-ZIP_only-0F766E)

**1.0.7 official release · Inspect requests. Understand data. Keep verification connected.**

Built on capture, intercept, replay and AI automation, this release adds an independent codec workbench and refines page assistants and evidence workflows. Agent also supports concurrent chats, context references, attachments and file delivery. New users can explore the complete feature overview below; existing users can start with the 1.0.7 highlights and walkthroughs.

[1.0.7 highlights](#whats-new) · [All features](#features) · [Community / PRO](#editions) · [Download and install](#install) · [Quick start](#quick-start) · [Full release history](#history)

![Hx0 HawkEye 1.0.7 release poster](https://github.com/user-attachments/assets/c8a626d3-47ce-4d36-b656-1fe96292dc49)

*Sample data illustrates the workflow.*

<a id="whats-new"></a>
## What's new in 1.0.7?

<a id="update-20261104"></a>
### 2026.11/4 Update

> This update builds on **v1.0.7** for Chrome and Firefox, with **MCP Server 1.0.15**.
>
> - **Page performance and smart routing**: fix refresh/request loops, bound response-body concurrency, size and waits, and avoid redundant proxy-rule updates. Improve rapid switching, concurrent saves and recovery after failures.
> - **Model capability support**: refine GLM, Kimi, MiMo, MiniMax, Grok, GPT and DeepSeek parameter/capability handling, label sources and retain per-model manual preferences.
> - **Task-aware web search**: browser engines, DeepSeek Search and Tencent Yuanbao Search. When enabled, search according to the request, freshness needs and evidence gaps. Fix missing news-summary bodies; disabling search takes effect immediately.
> - **Agent / MCP background work**: use separate task tabs with the existing login session and minimize browsing interruptions. Keep advanced scripts, media controls and fullscreen available; borrow the foreground when necessary, restore when appropriate and report the effects.
> - **More natural action demos**: enable only when requested. Mouse-only actions show no keyboard; typing highlights matching keys. The cursor follows the actual hit point. Chinese uses offline pinyin demonstrations, passwords stay masked and skipped long-text animation is disclosed.
> - **MCP Server 1.0.15**: 54 tools in the full profile, including independent action-demo sessions. Improve background entry, foreground borrowing/restoration, evaluation timeouts and queue recovery. Add mouse buttons, double-clicks, inner scrolling and complex targeting, with loaded-build receipts.
> - **Scene suggestions with fewer model calls**: show page-matched offline ideas first, then replace them with AI results. Reuse suggestions in the browser session; resizing, focus and layout changes do not trigger generation. Align the loading notice with the composer.
> - **Codecs and interface polish**: improve decoding and selection detection. Dismiss the smart decoding assistant until page reload. Fix dark mode, untranslated English controls, immediate approval-policy changes, OS-specific notification help and button alignment.
> - **Personas, Skills and user manuals**: update presets and bilingual help for current capabilities while preserving custom content. The 13-card tour now leads with search, background work, action demos and MCP.

This release turns individual data operations into reusable workflows, and connects page signals to results you can verify.

| Core update | What it helps you do | Where to start |
| --- | --- | --- |
| **Dedicated codec workbench** | Combine 147 operations into recipes of up to 16 steps, with feedback for each step | Codec → Codec & tools |
| **Smart multilayer decoding and AI assistance** | Identify formats, inspect candidates and paths, verify AI proposals locally | Codec → Smart decoding |
| **Text / JSON comparison and binary recovery** | Find meaningful response changes; recover original files from Hex / Base64 | Codec → Text / JSON comparison; Output → Save to file |
| **QR / barcodes and IP network tools** | Generate and read codes offline; calculate IPv4 / IPv6 addresses and ranges precisely | Codec → corresponding tab |
| **Four official page assistants** | Page intelligence, decoding, pentest analysis and phishing mail review alongside the page | Scripts → select assistant → Inject into current page |
| **Agent and MCP integration** | AI scene suggestions, goal/plan modes and resumable work; 4 concurrent chats, @ references and shared workbench tools | [Agent workspace and attachments](#agent-workspace); Basic settings → HawkEye Browser Automation MCP |
| **Context, attachments and file delivery** | Per-model image settings, real bookmarks, image/code inputs, local scanning, live editing and report downloads | Agent → model menu / @ references / ＋ attachments |
| **Queued Agent follow-ups** | Queue follow-ups or send them now, retry failed sends with messages and attachments retained; other chats keep running | Agent → waiting queue → Send now |
| **Three-point micro Fuzz** | Configure multiple parameters and preview a bounded test before running it | Replay → mark injection points → micro Fuzz |
| **Feature tour and update indicator** | Learn the main features after installation or updates; daily official update checks when reachable | Extension popup; red dot above the footer version |

<a id="agent-concurrency"></a>
### Concurrent Agent chats and task status

Chrome and Firefox support up to **4 different chats running at once**. Follow-up tasks within one chat run in order. A fifth task shows “Waiting for a slot” and starts automatically when capacity is available. Creating or switching chats keeps other tasks running; **Stop** affects the current chat only. Tasks retain their target tabs, and tasks using the same tab take turns performing browser actions.

- Running chats show a spinner. Chats waiting for capacity, a reply or approval, paused chats, and completed chats show their corresponding status.
- Hover over a chat card or focus it with the keyboard to reveal delete **×**. Delete removes the chat; use **Stop** to end the current task.
- Add follow-ups to the waiting queue while a task runs. **Send now** stops that chat’s current task and submits the selected follow-up while other chats keep running. Failed sends can be retried with their messages and attachments retained. When all execution slots are occupied, the new task waits automatically.


---

## 1. What it is
**Basic capture needs no system proxy configuration.** Hx0 HawkEye is a lightweight security workbench for Chrome, Firefox, and mainstream Chromium browsers. Inside the user's real tabs and signed-in sessions, it unifies **traffic capture and interception/tampering (including WebSocket), replay, micro-Fuzz, sensitive-data / dark-link detection, AI-assisted security auditing, HawkEye MCP, and browser-level Agent workflows (PRO)** so manual analysis, external Agent Hosts, and in-extension automation share the same browser evidence and security tools.

![Hx0 HawkEye overview](https://github.com/user-attachments/assets/b7692007-a1a4-43ee-8072-9a3831404993)


#### ⚡ Core advantage: why not a classic proxy?
+ **Low setup cost for basic capture**: no Burp, system proxy, or Java setup is required; optional MCP integration separately requires Node.js.
+ **Close to the real browser session**: observes page XHR / Fetch / WebSocket traffic. Replay can reuse relevant session context, subject to browser and site rules for cookies, request permissions, and response bodies.
+ **Browser-based workflow**: load the extension and set target rules to start capturing for development, API triage, and **authorized** first-pass review.

![](https://github.com/user-attachments/assets/c94f0426-8bfb-4c8c-afa0-bece07a583af)

#### 🤖 Differentiator: end-to-end AI (BYOK)
Bring your own model API (BYOK) and embed AI into the sidebar workflow:

+ **Smart cases & payload generation**: structured test ideas in the replay workbench; context-aware mutated payloads in micro Fuzz—without bloated static wordlists.

![](https://github.com/user-attachments/assets/0224c67f-68f8-4784-b8d7-70bc5bc595d3)

![](https://github.com/user-attachments/assets/fff2297b-b156-4dd7-b94d-cd3927e244ca)

![](https://github.com/user-attachments/assets/d763a097-c650-4f8a-b4fd-a18a13144dba)

![](https://github.com/user-attachments/assets/7cc11ab1-c3d9-42c8-95ca-6d223cb51aaf)

+ **Single-request analysis**: AI uses the request and response evidence actually captured; when an original response body is unavailable, diagnostics explain the gap rather than treating replay as the original response.

![](https://github.com/user-attachments/assets/9897a393-41fc-4a20-a4a5-525e5704796e)

+ **Batch synthesis**: select multiple packets in a dedicated workbench; AI extracts patterns across APIs and third-party calls to support supply-chain / dependency-surface **first-pass** review.

![](https://github.com/user-attachments/assets/a34486fd-3638-4b19-9991-b10c39179bd6)

+ **Dual-engine static hunting**: **built-in dark-link rules + AI contextual interpretation** for batch replay across pages and broad static coverage.


![](https://github.com/user-attachments/assets/5c60dfe2-aeca-48fc-8e26-5b59c28200c1)

![](https://github.com/user-attachments/assets/41bdefd6-3c29-4e53-9a5f-e0cf6a95720b)

---

## 2. Why we built it
With **SPAs, heavy XHR/Fetch, and WebSocket**, engineers constantly switch between “real browser session” and “capture / tamper / replay.” Classic proxies (e.g. Burp) are powerful but need system proxy and trust, and **cookies / login state** can diverge from the tab; lightweight toolbar extensions often lack **durable history, structured detail, and a closed-loop workbench**.

**Hx0 HawkEye** aims to keep **no mandatory system proxy** while folding **capture (HTTP / WebSocket) → filter → detail audit → intercept → replay → micro Fuzz → sensitive & dark-link checks → optional AI** into **one sidebar hub**, cutting context-switch cost for dev triage and **authorized** API review.

---

<a id="features"></a>
## 3. Features
Core flow: **Capture** (optional **WebSocket**) → **Filter** → **Detail** → **Replay** (HTTP / **WebSocket frames**; optional **AI test cases**) → **Micro Fuzz** (HTTP / **WS**; optional **AI payloads**) → **Dark-link / AI packet analysis** (including **batch AI / dark-link workbenches** after multi-select) → **AI Task Console** (Pro, multi-stage automation).

![](https://github.com/user-attachments/assets/67fa397b-ff68-4713-abe6-f58358515576)

![](https://github.com/user-attachments/assets/bca01d9f-e391-41c0-b238-482ff2286af1)

![](https://github.com/user-attachments/assets/410628b4-05b7-42c2-95a0-b83becb95fbb)

![](https://github.com/user-attachments/assets/310b0cb7-d813-4cca-a389-7a1b55850a6a)

![](https://github.com/user-attachments/assets/74ac68db-1903-4207-ba73-1e27106a2131)

| Module | Description |
| --- | --- |
| **Capture** | Combines page `fetch` / XHR with browser request events; filters by **host/IP wildcard, resource type, or suffix**, and shows WebSocket handshakes plus `OUT`/`IN` frames. Request and original response bodies depend on browser availability and size limits. Chrome can try passive listening; Firefox has no matching switch. |
| **History** | History saved locally with type, host, method, status, sensitive-hit, and search filters. Scope: **current domain / current tab / all records**; the toolbar badge follows captured traffic for the active site. |
| **Intercept** | Queues matching HTTP requests and outbound/inbound WebSocket frames; the sidebar refreshes automatically and supports edit, forward, drop, and bulk actions. Capture and intercept share target rules. |
| **Detail audit** | **Pretty / Raw / Hex**; response **Render** (sandbox); **sensitive** aggregation & highlights; copy full URL from title; download split raw **.txt**; **Burp-style** export. |
| **Replay** | Requests open in **Pretty** by default. Edits made in Pretty or Raw both replay, and view switching preserves edits. Includes undo/redo, target switching, optional AI test cases, and WebSocket frame replay through a still-`OPEN` page socket; Pro also adds in-page replay. |
| **Encode / hash** | MD5, SM3, SHA, ROT13, Base64, URL, Hex, etc.; scope: **selection / param values only / full URL line**. |
| **Micro Fuzz** | `§...§` injection points; **Start Fuzz** and **in-page Fuzz** (HTTP/DOM); **WebSocket micro Fuzz** sends serially and uses the **next inbound frame** as the response (needs an active page socket); baseline diff; **AI payloads** from model context; pair with Render, sensitive, and **AI result** views. |
| **Dark link & static threats** | Rule scan on static HTML, etc.; **high-trust TLD** allowlist; downloadable reports; **AI packet/semantic** interpretation; **batch dark-link** workbench for **horizontal compare** and **third-party script clues** (supply-chain first pass). |
| **AI (optional)** | Single-packet analysis uses actually captured request/response evidence; batch analysis summarizes selected traffic in a separate workbench. AI Tasks support multi-stage work, Skills, and in-task hints. Providers include OpenAI, DeepSeek, Grok, MiniMax, Gemini, Ollama (local), LM Studio (local), and custom endpoints. Model requests go to the user-selected service (BYOK). |
| **HawkEye Browser Automation MCP (PRO)** | A browser MCP for security workflows. It supports stdio / Streamable HTTP / legacy SSE and exposes tab navigation plus HawkEye capture, replay, mutation, codec, and evidence tools to a trusted Agent host. |
| **Browser-level Agent (PRO)** | Uses browser and HawkEye tools across multiple turns in a real tab; chat can change capture, intercept, proxy, scripts, and extension settings. Supports goals/plans, attachments, visual evidence, and task progress recovery. Cross-chat summary memory is off by default. |
| **Sensitive matching** | Built-in rules (IDs, phones, cards, email, Shiro/JWT/Swagger/UEditor/Druid fingerprints, IP, domain, CTF flags, etc.) plus **custom regex** and **keyword lists**; import/export, clear-all. |
| **Batch** | Bulk export/delete, **batch AI**, **batch dark-link** (separate tab), batch replay, etc. |
| **i18n** | UI **中文 / English**. |
| **Independent codec workbench (1.0.7)** | 147 operation entries, recipes of up to 16 steps, parameters, live processing and recipe import / export; each basic or advanced operation checks its edition entitlement. |
| **Smart decoding and data comparison (1.0.7)** | Multi-layer candidates and paths, locally verified AI suggestions, text / JSON comparison and original-byte file recovery; IP, QR and barcode tools are also available. |
| **Four official page assistants (1.0.7)** | Page intelligence, smart decoding, penetration analysis and phishing mail review, with manual injection, match rules and script shortcuts. |
| **Feature tour and update notices (1.0.7)** | A feature tour introduces the main entry points; daily official update checks for your browser when online. |


**Chrome and Firefox** differ in sidebar hosting, response-body capture, and intercept prompts. Chrome passive listening works only when the browser exposes a body; Firefox has no equivalent switch. See the in-extension manual for limits.


### 1.0.7 illustrated walkthroughs: extend your existing workflow

### 3.1 Dedicated codec workbench

![The 1.0.7 codec workbench running a real SM3 → Base64 recipe in Chrome](https://github.com/user-attachments/assets/270ea917-ee23-48da-8483-cd21b69b071b)

**147 operations. Up to 16 steps per recipe.** Search for operations, add steps and reorder them. Run automatically as input changes, or disable Auto run and execute manually. Each step shows its status, so failures can be traced to the relevant operation.

Codec handling preserves UTF-8 BOMs and correctly processes CTR counter carry, empty input, Quoted-Printable wrapping and HTML entities. Local decoding results remain available while AI analysis is pending or fails.

Try it:

1. Open **Codec → Codec & tools** and enter `flag{hello}`.
2. Add **SM3**, then **Base64 Encode**.
3. Inspect the output, copy it, use it as new input or save it. Export the recipe and import it again when needed.

This example hashes the input with SM3, then Base64-encodes the hexadecimal digest text. **A hash is a one-way digest, not a ciphertext that can simply be decrypted.** Recipe exports exclude input text and keys.

| Operation group | Examples |
| --- | --- |
| Common encoding and text | Base32 / Base64 / URL / Hex, Morse, JSON, JWT, regex and text processing |
| Digests and checksums | MD5, SM3, SHA variants, HMAC, CRC / Adler / BCC / LRC |
| Parameterized cryptography | AES, DES / Triple DES, RSA, SM2 / SM4 / SM9, RC4, Rabbit and OpenSSL |
| Extended encodings and CTF | Base62 / Base85 / ASCII85 / basE91 / Base92, UU / XX, Base100 Emoji, Bech32; classical ciphers and static script decoding |
| Everyday utilities | Precise integer base conversion, Unix timestamps, Chinese RMB amounts, colors / units and CSV / JSON |

Advanced operations require PRO and the correct keys, IVs, modes or challenge parameters. SM9 uses compatible GmSSL DER keys and accepts 1–255 plaintext bytes per operation. JSFuck / AA / JJEncode use bounded static decoding without executing the recovered code.

### 3.2 Smart decoding and AI assistance

![A real five-layer decode with its reusable path and recovered flag](https://github.com/user-attachments/assets/a9f179fc-ad5c-4cb1-a165-1a0d91d850d0)

**PRO** Smart decoding supports **76 decoding / parsing paths** and processes data locally. Candidates are ranked by readability and format signals, with intermediate layers retained. Verified paths can be loaded into a recipe.

1. Open **Codec → Smart decoding** and choose **CTF five-layer example**.
2. Keep maximum depth at `5` and start smart decoding.
3. Inspect `Base64 → URL → Hex → Unicode → ROT13` and the result `flag{ctf_5_layers}`. Use **Load decoder path** to continue in the recipe workbench.

Basic Morse supports common punctuation too. Select **Morse Decode** in the workbench, or pass this input to Smart decoding:

```text
..-. .-.. .- --. -....- -- --- .-. ... .
```

The result is **`FLAG-MORSE`**; `-....-` represents a hyphen. Smart decoding can also work through layers of encoded input, subject to its format, depth and required parameters.

For further assessment, choose **AI assistance**. AI can explain format signals, propose paths and give likely causes and next verification steps. Allowed proposals run through local tools. When no path succeeds, the analysis still provides suggestions and identifies missing conditions. **Advice and verified results are shown separately; a model hypothesis is not presented as recovered plaintext.**

Passwords, private keys, IVs, matrices, mappings and local dictionaries are not sent to AI. Bounded input excerpts and non-key candidates may be sent. Configure the provider under **Advanced → AI service**.

### 3.3 Text and JSON comparison

![JSON structural comparison ignores object key order and highlights pending → paid](https://github.com/user-attachments/assets/35ad636b-07d1-4449-985a-cdbc8ded1911)

Paste two responses into **Text / JSON comparison**, choose text or JSON structural mode, and run the comparison. Character highlighting, previous / next difference navigation, pagination and complete diff export are available.

Original:

```json
{"order_id":"demo-107","status":"pending","amount":129,"role":"viewer"}
```

Modified:

```json
{"role":"viewer","amount":129,"status":"paid","order_id":"demo-107"}
```

JSON mode ignores object key order and preserves array order. Here it identifies the change to `status`, rather than the reordered fields. Large integers retain their precision for order IDs and API regression checks.

### 3.4 Binary data and file recovery

Hex / Base64 decoding supports raw-byte output and **Save to file**. For example, decode an image's hexadecimal representation and save the original PNG bytes without converting them through potentially destructive UTF-8 text.

Choose Hex or Base64 decode → select byte output → inspect the result → **Save to file**. Separator detection, byte editing and lossless reuse are supported. The file type depends on the actual bytes; choosing an extension does not change its contents.

### 3.5 QR codes and barcodes

![Generating a QR code for the official repository, with local image decoding](https://github.com/user-attachments/assets/7a74efc7-5b81-4bc3-bea5-753ac668296e)

**PRO** supports local generation of QR and **9 one-dimensional barcode types**, with SVG / PNG export. Import an image, drag a webpage image or paste a screenshot to read a code.

Try **QR / Barcodes → QR Code**, enter `https://github.com/asaotomo/Hx0-HawkEye` and generate the code. Drag it into the image decoding area to inspect the content.

Each image returns the first recognized result, with a 6 MiB image limit and a 6-second decoding timeout. Blur, occlusion or complex backgrounds may prevent recognition. Decoded links are not opened automatically.

### 3.6 IP network tools

![IPv4 conversion and network calculations performed locally](https://github.com/user-attachments/assets/97227dfc-c5a6-48a7-a303-cc0bc7ca1ac4)

**PRO** supports IPv4 / IPv6 format conversions, prefixes / masks, ranges and precise address counts. Results are grouped into cards, with individual copying and JSON export.

Try **IPv4**, address `192.168.1.23`, prefix `24`, then calculate. The network is `192.168.1.0/24`, with `256` total addresses and the conventional usable host range `192.168.1.1–192.168.1.254`. This is a local calculation; it does not scan the network.

### 3.7 Four official page assistants

All four official assistants require **PRO** and support copy, collapse, close, light / dark themes and Chinese / English interfaces. Open **Scripts**, select an assistant and choose **Inject into current page**. Panels open at the visible page’s bottom-right corner in Chrome and Firefox, stay visible alongside the sidebar and can be dragged to a convenient position. Smart Decode mainly responds to likely encoded selections and can also be opened from the script menu.

| Assistant | Use case | How to use the output |
| --- | --- | --- |
| **Page Intelligence Assistant** | Forms, hidden fields, links, script endpoints and sensitive signals | Inspect category counts, expand or filter details, rescan and save JSON |
| **Smart Decode Assistant** | Encoded page selections, capture details and replay content | Open the panel / decode the selection, inspect local candidates, optionally use AI or continue in the workbench |
| **Smart Pentest Assistant** | Analysis from the page, HawkEye traffic, source and lightweight checks | Configure AI, run manually, review evidence and unverified findings, save Markdown |
| **Phishing Mail Guard** | An opened webmail message or an imported EML | Review local risk evidence, optionally preview and request AI review, export HTML / print to PDF |

Page Intelligence findings do not establish a vulnerability. Pentest hypotheses need further verification within the authorized scope. Large pages or restricted content may not be read in full; the interface explains any missing content and why it could not be read.

![Local review of a fictional EML: risk signals, evidence, authentication information and fixed controls](https://github.com/user-attachments/assets/15f797c2-f1d4-4b13-93cd-636e67588a8f)

**Start with Mail Guard:**

1. Open a message in a supported webmail service and use **Open / local rescan**. Unsupported or unmatched pages show an explanation.
2. Alternatively, choose **Import EML**. On an ordinary demonstration page, first set the script's injection scope to **Manual**, save it and inject it.
3. Review local evidence and coverage. Request **AI deep review** if needed, or export a report.

Reading-page adapters cover common services including Gmail, QQ / enterprise mail, Outlook and NetEase. Page redesigns, cross-origin bodies or special layouts may affect extraction; EML is an alternative. EML files are limited to 5 MiB. The assistant does not send mail or execute attachments. SPF / DKIM / DMARC details come from available message headers; offline analysis does not independently perform DNS checks or cryptographic signature verification. **No detected risk does not prove safety.**

The scripts workbench also imports `.user.js` and ordinary JavaScript, with editing, checks and AI creation / optimization. Common GM / GM4 APIs are supported; full Tampermonkey API coverage, some MAIN-world behaviors and special dependencies remain limited.

### 3.8 Browser-level Agent

![Agent home with task ideas for AI decoding, JSON comparison, recipes and three-point Fuzz](https://github.com/user-attachments/assets/616ffa38-4914-48f7-a3d1-5f90a19941bf)

**PRO** Agent Mode connects the current browser to HawkEye tools. Goal mode, plan mode, deep thinking, Skills, execution records, saved progress and task recovery are available.

**AI scene suggestions** are on by default and provide **three or four ideas** from the current page, recent conversation, selected persona and Skills, and opted-in historical memory. Click an idea to send it. Page-matched offline cards appear first and are replaced by AI results; failures retain labeled offline ideas. The browser session reuses cached suggestions. Resizing the sidebar, focus changes and layout changes do not regenerate them; use **Refresh** for another batch. Turning the feature off in Advanced settings hides AI pills, cancels pending requests and stops generation. Built-in home cards and local Refresh remain available, while normal chat and task execution continue.

**Search, background work and action demos:** when search is enabled, Agent retrieves evidence according to the request, knowledge gaps and freshness needs, then delivers a sourced answer. Background work uses separate muted task tabs and does not copy unsaved edits. Ordinary steps minimize interruptions; necessary advanced scripts, playback, fullscreen and native input may use foreground capabilities and restore the original tab when appropriate. Enable action demos explicitly: mouse-only actions show no keyboard, and typing shows matching keys. The overlay does not take over your mouse or keyboard. Search, background and approval-policy changes apply to subsequent steps immediately.

<a id="agent-workspace"></a>
#### Workspace, references and attachment updates

1. **Agent workspace and task ideas**: Reopening the sidebar restores its last tab. New ideas cover real bookmark organization, folder classification and filename plans, static page recreation and attachment revisions.
2. **Model menu and @ references**: Search and switch models, with image-input settings saved for each model. Type `@` anywhere in the composer to reference selected text, tabs, bookmarks, attachments, generated files and enabled Skills, with each source clearly identified. The model setup shortcut opens Advanced model settings directly; capabilities identify their API / official-documentation / preset sources and retain manual choices.
3. **Images and code attachments**: Paste or drop webpage images, text and code files. Detect text encodings and deduplicate/name images. Skill references do not use attachment slots. QR/barcode attachments and current-page images/canvases/SVG use local scanning independently of model vision. Multi-code long images return ordered results and pixel regions. Matching MCP tools also expose scanning and real bookmarks.
4. **Files and live code editing**: Preview, edit and download code or reports with meaningful filenames. Generated JS/JSON is checked for syntax errors. Code preview and editing include line numbers and highlighting; Run confirms the corresponding webpage before execution. Refreshing task records preserves unsaved edits and your reading position.
5. **Real bookmarks and local pages**: Read, page, classify, move and rename actual browser bookmarks with backups and protected roots/non-empty folders. Read permitted file:// pages. Folder classification uses supplied listings and does not move original disk files.
6. **Smart decoding and assistant placement**: Ordinary language selections stay quiet; digits, braces and encoded material continue to open local decoding. Four assistants anchor to the visible page’s bottom-right corner, stay visible alongside a sidebar and retain dragged positions where possible. Dismiss the smart decoding assistant for the rest of the current page lifecycle; reloading the page restores it.
7. **Task clarification and language settings**: When scope, goals or parameters are missing, Agent offers choices and accepts custom answers; recommended choices require your confirmation. Built-in Skill names and descriptions follow the interface language, and help is available in Chinese and English. Text/file requests use the composer, decisions show concrete options and dismissed questions can be reopened from their pending-reply bubble. Preset personas and built-in Skills follow current capabilities while custom content is retained.

Type `@` anywhere in the composer to open the context menu shown below. Model image-input settings are saved per model; local QR and barcode scanning also works with model vision disabled.

![Agent context menu: selected webpage text, tabs, Skills, browser bookmarks and local file uploads](https://github.com/user-attachments/assets/3d170d35-9553-41cc-bce1-d131d10fabb5)

Start with a clear, read-only goal:

> Inspect the current local demo page. List its endpoints, forms and hidden fields with evidence sources. Read only; do not log in or submit forms.

Use **Plan mode** to review the steps before execution. For public-web research, Agent can read **1–7 pages** concurrently. Search can read up to 7 result bodies, and deeper research can read up to 15 pages. CAPTCHAs, timeouts, network problems or repeated failures can limit progress, and results identify evidence gaps.

To use Skills, first select available skills in Advanced settings, then enable `Skills` in the current Agent chat. Configure the model service, page access and risk confirmation policy for the task, and verify important actions and conclusions.

### 3.9 Capture, interception and replay

![Real Fetch requests from the local fixture appear in capture history](https://github.com/user-attachments/assets/50195e76-f397-4551-8b61-e599cdc0ebbb)

Enable capture in Basic settings, set the target domain / IP and type rules, then reload the target page. History supports current-domain, current-tab and all-record views, plus Host / method / status / keyword filters. Main-panel startup and capture-panel expansion are optimized to avoid occasional second clicks. Response-body reads have concurrency, size and time limits; smart routing avoids repeated proxy-rule writes.

Details include Pretty / Raw / Hex / Render, with local edit drafts for requests and responses. Modify parameters in Replay and inspect the response. WebSocket supports frame observation, replay and rule-matched interception; frame replay needs an available connection. Sensitive matching, custom rules, deep keyword search and smart proxy routing remain available in Community.

**PRO three-point micro Fuzz:** select text in Replay, add up to three `§...§` injection points, configure a payload list for each point, choose the combination mode and check the preview before running.

| Three points, two payloads each | Tests, excluding baseline | Best suited to |
| --- | --- | --- |
| Sequential | 6 | Change one point at a time to isolate effects |
| Parallel / row-synchronized | 2 | Treat each row as a parameter set; lists must have equal lengths |
| Cartesian | 8 | Test combinations; counts grow quickly |

One extra baseline request is sent. Set an execution limit in the UI. HTTP, in-page and WebSocket Fuzz share the planner; external MCP Fuzz retains stricter target and execution limits.

Three-point walkthrough:

1. Select each value in an authorized replay request and choose **Mark injection point**. The counter reaches **3 / 3** and each value is wrapped in `§`.
2. Open **Micro Fuzz** and configure each injection-point tab separately, one payload per line.
3. Choose the mode, concurrency and delay. Check the preview and execution limit before starting. Four values at each of three points give **4 × 4 × 4 = 64** Cartesian combinations, plus one baseline request.
4. Select a result and inspect the actual substituted request alongside the status, response length, timing and body. HTTP 200 alone does not indicate a vulnerability.

![Three marked injection points in Replay](https://github.com/user-attachments/assets/1cd1980e-aeef-446f-9fe7-5d34455fae3a)

![Independent payload lists, 64 combinations and request/response inspection](https://github.com/user-attachments/assets/edf0a1ae-05de-428d-871a-927f25475711)

*Practice these steps on systems you own or are authorized to test.*


Passive full-body capture uses browser debugging APIs. Some cross-origin `no-cors` responses remain restricted by Chromium. Render and ordinary replay do not bypass browser security rules.

### 3.10 HawkEye MCP integration

**PRO** local MCP Server **1.0.15** exposes the real browser session, capture, replay, analysis and codec workbench to compatible clients. It supports stdio and Streamable HTTP / SSE. The single-file server runs with Node.js 18 or newer.

Server 1.0.15 provides **54 tools**, which can be enabled as needed. Testing scope can specify both host and port. Use custom Fuzz payloads and returned record IDs to view historical replay / Fuzz responses. Request and response interception are separate stages: check the response queue after releasing a request. See §3.1 in the extension manual.


1. Enable **HawkEye Browser Automation MCP** in the extension's Basic settings.
2. Find `mcp-server/hawkeye-mcp-server.mjs` in the extracted package and follow the connection instructions in the UI.
3. Copy the supplied configuration to the client. Confirm it can read the current page before using further tools.

Escape Windows paths correctly for JSON / TOML. If no usable download path is available, locate `mcp-server/hawkeye-mcp-server.mjs` in the actual extension installation and verify it exists before configuring the client. After updating, reload the extension and target pages, replace the companion MJS, restart the MCP Host and refresh its tool list. Extension-owned JavaScript is obfuscated; the MJS remains readable.

**Background and demo calls:** when the user requests background work, the client can enable an independent workspace with `browser_tabs` and `action: "background"`; ordinary behavior remains the default. `hawkeye_evaluate` accepts `timeoutMs` and `foreground: true`, borrows the foreground when needed and reports `foregroundFallback`, `foregroundStatus`, `foregroundRestored` and actual effects. Timed-out scripts are not replayed. `browser_action_demo` is off by default and enabled only on explicit user request, independently per MCP session. Connection receipts include the loaded `extensionRuntime` build and capabilities.

**Mouse input and complex pages:** left/right/middle buttons, double-clicks and nearest-container scrolling are supported; Chrome can explicitly use a native wheel. Take a new snapshot after opening a webpage context menu and select its item by ref. Browser/OS menus are outside DOM snapshots. Forms are relocated after scrolling and selection is checked, with frame-local targeting and bounded virtual-list searches. Canvas targets require screenshot-confirmed points. For owned slider fixtures, metrics/dryRun expose CSS geometry, ratio basis and displacement; solve requires acceptance evidence from the current challenge. Event delivery or dialog closure alone is not success. Third-party anti-bot checks need human handling, and unavailable native input returns an explicit error.

Example stdio configuration; replace the path with your actual absolute path:

```json
{
  "mcpServers": {
    "hx0-hawkeye": {
      "command": "node",
      "args": ["/absolute/path/mcp-server/hawkeye-mcp-server.mjs"]
    }
  }
}
```

In 1.0.7, catalog lookup, recipe execution, comparison, code generation / decoding and workbench display / export connect to Agent, AI Tasks and MCP. A third-party client's handling of tool results depends on that client's and model service's configuration. Disable the bridge when not in use.

### 3.11 Feature introductions and updates

After installation or an upgrade, the feature tour introduces the main features and their entry points. Start using HawkEye after the tour, or close it at any time. The first four of 13 cards introduce search, background work, action demos and MCP 1.0.15. Both manuals explain the suggestion switch, recommendation context, caching, Refresh and fallback behavior.

When the official GitHub service is reachable, the extension attempts an update check at least daily. Offline or unreachable intranet environments are skipped quietly, without interrupting local work. An available update adds a red dot above the footer version link, which opens the official project.

Update notices use the **official ZIP for your browser and the build identity in the release notes**. Older builds of the same 1.0.7 version show a red dot after the next online check; installing the matching build clears it. An existing daily-check cache can defer detection until the next day. Updates are not installed automatically.

---

<a id="editions"></a>
## 4. Editions (Community / Pro)

Hx0 HawkEye currently uses a three-state model: **Community**, **Pro**, and a **30-minute first-install Pro trial**.

- **Community** keeps the essential loop: **capture (including WebSocket) → inspect → standard replay (including WebSocket frames) → basic encode/decode**, plus **intercept** (**HTTP** and matching **WebSocket frames**).
- **Pro** unlocks **in-page replay / fuzzing, HTTP/WS micro Fuzz, Tampermonkey scripts, AI, AI Task Console, Skills knowledge base, dark-link review, batch workbenches, and advanced encode/decode tools**.
- **First-install trial** grants **full Pro capability for 30 minutes**. If no activation code is applied after the trial, the product **automatically falls back to Community**.

### Feature Comparison Table

| Feature                                                                                                           | Community Edition | Professional Edition | Description                                                                                                                                                                                                                                                                                                            |
| ----------------------------------------------------------------------------------------------------------------- | ----------------- | -------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Packet Capture Toggle, Target Domain / IP, Capture Type / Suffix Filters                                          | ✅                 | ✅                    | The Community Edition is sufficient for basic traffic capture and noise reduction                                                                                                                                                                                                                                      |
| History List, Current Domain / Current Tab / All Records, Host / Method / Status Filters                         | ✅                 | ✅                    | Tab scope includes requests to other subdomains; the badge follows active-site traffic                                                                                                                                                                                                                                                                                     |
| Pretty / Raw / Hex / Render Views, Copy / Single Export / Copy URL by Title                                       | ✅                 | ✅                    | Full packet detail auditing is available in the Community Edition                                                                                                                                                                                                                                                      |
| Built-in Sensitive Information Detection & Aggregated Display                                                     | ✅                 | ✅                    | Supports built-in rule-based detection                                                                                                                                                                                                                                                                                 |
| Standard Replay                                                                                                   | ✅                 | ✅                    | Pretty is the default; Pretty and Raw edits both replay. WebSocket frame replay needs an `OPEN` page socket                                                                                                                                                                                                                                                      |
| **Interception Toggle, Modify / Forward / Forward All / Drop All (Community since v1.0.2)**                      | ✅                 | ✅                    | Queue-based intercept for **HTTP** and **WebSocket frames** when host rules match                                                                                                                                                                                                                                                                                                   |
| Floating Action Button, Open as New Tab, Language Switching                                                       | ✅                 | ✅                    | Daily productivity features remain available in the Community Edition                                                                                                                                                                                                                                                  |
| **Basic Encoding & Decoding**: MD5, SM3, SHA-1, SHA-256, ROT13, Base32 / Base64 / URL / Hex                       | ✅                 | ✅                    | Directly available in the Community Edition                                                                                                                                                                                                                                                                            |
| **Advanced Encoding & Decoding**: SHA-512, HMAC-SHA256, Base64URL, Unicode, HTML, JSON, JWT | ❌                 | ✅                    | Designed for advanced verification, signing, and analysis workflows                                                                                                                                                                                                                                                    |
| **Intelligent Encryption Logic Analysis (Added in v1.0.1)**                                                       | ❌                 | ✅                    | Combines request context with related JS / HTML clues to help identify encoding, hashing, signatures, or hybrid encryption workflows                                                                                                                                                                                   |
| In-Page Replay, In-Page Fuzzing, **HTTP / WebSocket Micro Fuzz**, Injection Point Marking                                           | ❌                 | ✅                    | Suitable for dynamic pages, WAF testing, real-time channels, and high-frequency parameter probing                                                                                                                                                                                                                                   |
| Switch HTTP Method, Switch Target Domain                                                                          | ❌                 | ✅                    | Useful for multi-environment debugging and verification                                                                                                                                                                                                                                                                |
| **Intelligent Proxy Router (v1.0.1; Community since v1.0.6)**                                                     | ✅                 | ✅                    | Located below “Capture Type / Suffix” in Settings. Requests matching site rules can be automatically forwarded to upstream proxies such as Burp Suite or Yakit, while unmatched traffic continues using the original network path. The Firefox version additionally supports “Compatibility Mode” and “Takeover Mode”. |
| **HawkEye Browser Automation MCP (v1.0.6)**                                                                        | ❌                 | ✅                    | Local Server 1.0.15 uses the real browser session for capture, intercept, replay, analysis, and evidence tools |
| **Browser-level Agent / Agent Mode (v1.0.6)**                                                                      | ❌                 | ✅                    | Available during an active trial or with Pro; chat can change extension settings and use tools, with task progress recovery; cross-chat summary memory is off by default |
| AI Analysis Settings, AI Result Analysis, AI Analysis, AI Test Case Generation                                    | ❌                 | ✅                    | All AI-related capabilities are included in the Professional Edition                                                                                                                                                                                                                                                   |
| **AI Task Console (since v1.0.2)**                                                                                    | ❌                 | ✅                    | Multi-stage automation: Intelligent Penetration and CTF modes; **Skills knowledge bases**, **in-task supplementary hints**; **timeline log with draggable split** (v1.0.5);  ties history, replay, and evidence into reports                                                                                                                                |
| **AI Skills Knowledge Base (v1.0.3)**                                                                               | ❌                 | ✅                    | v1.0.6 includes 19 pentest + 28 CTF sub-modules and external Skill import. Select available skills in Advanced Settings, then enable Skills in the current Agent chat. Skills are off by default in new chats                                                                                                                                                                      |
| **Tampermonkey / Page Script Workspace (v1.0.4)**                                                                   | ❌                 | ✅                    | Import `.user.js`, script library management, one-click inject; AI create/optimize scripts; **Smart Decode Assistant** (v1.0.5); integrates with capture, replay, and scanning tools                                                                                                                                                                                                                                        |
| **AI Task Smart Script Dispatch (v1.0.4)**                                                                          | ❌                 | ✅                    | During tasks, AI can list, run, and create page scripts alongside Skills, replay and Fuzz                                                                                                                                                                                                                                                                    |
| **Advanced codec / smart nested decode (enhanced in v1.0.5)**                                                       | ❌                 | ✅                    | Replay workbench adds AES/DES/RSA/SM; AI tasks can use codec tools; codec controls are also available in packet details and replay                                                                                                                                                                                                                                                    |
| Hidden Link & Static Threat Detection, Report Export, High-Reputation Top-Level Domains                           | ❌                 | ✅                    | Rule scanning, reporting, and advanced noise-reduction capabilities                                                                                                                                                                                                                                                    |
| **Full Deep Search, Sensitive Matching, Custom Regex / Keyword Libraries (Community since v1.0.6)**              | ✅                 | ✅                    | Moved to Community compared with v1.0.5; includes full request/response search, built-in rules, custom regex, keyword libraries, and batch import/export                                                                                                                                                                |
| Batch Export, Batch Delete, Batch Replay, Batch AI Analysis, Batch Hidden-Link Detection                          | ❌                 | ✅                    | Unified batch-processing workflow exclusive to the Professional Edition                                                                                                                                                                                                                                                |
| **Independent recipes and text / JSON comparison (1.0.7)** | ✅ | ✅ | Up to 16 steps; Community can combine basic operations, while advanced operations still require PRO |
| **Unix time and RMB uppercase tools (1.0.7)** | ✅ | ✅ | Local daily utilities in the codec workbench |
| **Smart decoding, IP / QR / barcodes and advanced data tools (1.0.7)** | ❌ | ✅ | Decode paths and AI suggestions are verified locally; configure your own model service |
| **Four official page assistants (1.0.7)** | ❌ | ✅ | Use the script workbench; page and mailbox support depends on match rules |
| **Feature tour and official update notices (1.0.7)** | ✅ | ✅ | Dismiss the tour in one click; package updates are indicated, never installed automatically |

147 is the total operation-entry count, not the number unlocked in Community. Every recipe step checks the corresponding entitlement. PRO does not include third-party model-service fees.

> `1.0.7`: independent codec workbench, 16-step recipes, smart decoding, text / JSON comparison, binary recovery, QR / barcodes and IP utilities; refined page assistants, three-point Fuzz, Agent / MCP integration, feature introductions and update notices.

> Version `1.0.1` initially introduced two Professional features: `Intelligent Proxy Router` and `Intelligent Encryption Logic Analysis`; the router moved to Community in `1.0.6`.

> Version `1.0.2` adds **WebSocket** (capture / frame replay / **WS micro Fuzz** / frame intercept), the **AI Task Console** (including **in-task hints** and task execution improvements), and moves **intercept** capabilities to the Community Edition.

> Version `1.0.3` adds **Skills injection for AI tasks**, **capture/intercept UX improvements**, and **online activation**.

> Version `1.0.4` adds **Tampermonkey script support**, **AI smart script dispatch**, **capture/intercept reliability**, and **Firefox cross-browser alignment**.

> Version `1.0.5` adds **AI Task Console overhaul**, **thicker Skills + AI Generate Skill**, **codec enhancements**, and **UX improvements**.

> Version `1.0.6` (0930) adds **HawkEye MCP (PRO)**, **browser-level Agent (PRO)**, task recovery and pending approvals, Pretty replay editing, current-domain/current-tab capture scopes, and updated AI providers. It improves body-capture diagnostics, WebSocket/intercept refresh, bilingual settings, and the macOS dark theme. **Smart Proxy Router, Full Deep Search, and Sensitive Matching** are available in Community.

### Understanding the Edition Boundaries in One Sentence

- **Community Edition focuses on:** packet inspection (**HTTP / WebSocket**), understanding, basic verification, essential encoding/decoding, **intercept/tamper, Smart Proxy Router, Full Deep Search, and Sensitive Matching**.
- **Professional Edition focuses on:** page-context validation, mutation testing, AI analysis, AI tasks & Skills, the **browser-level Agent / MCP**, hidden-link scanning, and large-scale batch workflows.
- If you simply want to evaluate the product’s core value first, the Community Edition is already sufficient for the most important primary workflow.

---

## 5. Product strengths
1. **No system proxy for basic capture**: browser extension with no JVM dependency; optional MCP runs as a separate local service.

2. **Close to the page session**: tab scope includes cross-subdomain requests; replay can reuse relevant browser context, while authentication and cross-origin rules remain browser/site decisions.

3. **One workbench**: history, intercept, replay, encoders, micro Fuzz, **WebSocket**, sensitive, dark-link, AI—**same sidebar**.

4. **Modern frontends**: **XHR/Fetch, WebSocket, FormData, multipart**; **Raw / Hex** within extension limits.

5. **Dynamic-page forensics**: **in-page replay / in-page Fuzz** runs in real DOM—helps with some **WAF / challenge** pages.

6. **Sensitive & dark-link built-in**: list badges, detail rollups, exportable reports for **dev self-check and authorized first pass**.

7. **AI in the loop**: **AI Task Console** (multi-stage + **Skills knowledge base** + **in-task hints**), **AI test cases**, **AI Fuzz payloads**, **single-packet AI**, **batch AI** (multi-packet summary for **supply-chain / dependency** hints), **dark-link rules + AI**—same sidebar, fewer tools.

8. **AI under your control (BYOK)**: configure OpenAI, DeepSeek, Grok, MiniMax, Gemini, SiliconFlow, Ollama, LM Studio, or a custom service; model requests use the selected endpoint. Review redaction settings before sending traffic.

9. **Light footprint**: runs with the browser vs heavy standalone proxy stacks.

---

## 6. Comparison with common tools
Compared across shape, session, workflow, and specialties: **Hx0 HawkEye**, **Burp Suite**, **Yakit**, **HackBar / simple extensions**. **Enterprise deep scanning, complex Intruder, non-browser traffic** still belong on dedicated platforms—use **alongside** this product.

| Dimension | **Hx0 HawkEye** | **Burp Suite** | **Yakit** | **HackBar / simple extensions** |
| --- | --- | --- | --- | --- |
| **Shape & deploy** | Browser extension; **sidebar = main hub**; optional floating ball; **no JVM for basic capture**; optional MCP uses a local port | Java proxy + browser trust; suite, heavy | Desktop + engine/plugin ecosystem; security platform | Often toolbar mini-panel or single-request helpers |
| **Day-to-day cost** | **Install and go**; no forced system proxy; EN/ZH UI, flow in sidebar | Proxy, root trust, Proxy/Repeater learning curve | Install + pipeline/workflow learning | Fast start, scattered features, weak “project” workspace |
| **Browser session** | Captures traffic from the selected tab, including other hosts; replay follows browser and site session rules | Via proxy; cookie juggling into Repeater common | Via proxy/engine; different from pure extension | Manual headers/cookies |
| **Modern APIs (XHR/Fetch/SPA + WS)** | Page hooks plus browser request events; **WebSocket** handshakes/frames; **multipart Raw/Hex** within size limits; original response bodies depend on browser availability | Full proxy visibility, very capable | Plugins cover complex cases | Often no history, no Hex/sensitive rollups |
| **History & workbench** | Locally saved history with current-domain, current-tab, and all-record scopes; detail/replay/fuzz/AI **in sidebar** | Proxy History very strong; more app switching | Platform records & collaboration | Usually **no or weak history** |
| **System proxy / non-browser** | **In-browser** HTTP(S) and **page WebSocket** | Strong | Strong | Weak |
| **Intercept** | **HTTP + WebSocket frames**; queued; per-item or bulk in sidebar | Proxy intercept, industry standard | MITM / workflows | Rare or URL-only |
| **Replay / fuzz** | Pretty-default replay with Pretty/Raw edits, **HTTP/WS micro Fuzz**, and Pro in-page replay/fuzz | Repeater / Intruder mature | Web Fuzzer, etc. | Rarely concurrent fuzz or structured diff |
| **Sensitive / dark-link / reports** | **Built-in rules + badges + rollups**; export | Scanner, BApps; licensing/config | Rich PoC/plugins | Rarely built-in |
| **AI assist** | User-selected model endpoint, **Skills**, AI Tasks, and Pro Agent/MCP tools | Often third-party or DIY | Growing | Uncommon |
| **Active scan / heavy automation** | Not the focus; **manual tight loop** | Scanner, macros, plugins | PoC, batch, collaboration | Minimal |
| **Resource use** | With browser, **light** | Proxy + JVM, usually higher | Varies | Tiny but narrow |


**Suggested combo**: HawkEye as daily **in-browser hub**; add **Burp / Yakit** for full-site scanning, huge wordlists, or non-browser clients—“fast sidebar loop + deep platform.”

---

<a id="install"></a>
## 7. Offline install (v1.0.7 · ZIP only)

| Browser | 1.0.7 official package |
| --- | --- |
| Chrome / Chromium | [Download Chrome ZIP](./Hx0-HawkEye-Chrome-V1.0.7-Official.Release.zip) |
| Firefox | [Download Firefox ZIP](./Hx0-HawkEye-Firefox-V1.0.7-Official.Release.zip) |

[SHA-256 checksums](./SHA256SUMS) · [Official repository](https://github.com/asaotomo/Hx0-HawkEye) · [Product website](https://www.hx0.store/products/hawkeye)

Download exactly one official package for your browser from [GitHub Releases](https://github.com/asaotomo/Hx0-HawkEye/releases):

- `Hx0-HawkEye-Chrome-V1.0.7-Official.Release.zip`
- `Hx0-HawkEye-Firefox-V1.0.7-Official.Release.zip`

Checksums (SHA-256):

```text
ecb6e1f66b1714042cefbe0e5c3e7395bf26e008769cdc21ae58b34f7b0b2de3  Hx0-HawkEye-Chrome-V1.0.7-Official.Release.zip
1410ebfedfd778d71aeb509b1bcb2b76ff1a5b77f7a8a281b8a8b6d2707f37de  Hx0-HawkEye-Firefox-V1.0.7-Official.Release.zip
```

This release provides **two ZIP packages: Chrome and Firefox**. Extract and load the Chrome package in Chrome / Edge, or load the Firefox package temporarily. For a Firefox installation that survives restarts, follow the Developer Edition guide below.


After extraction, select the directory that directly contains these files. Do not select the ZIP itself or an extra outer directory:

```text
HawkEye installation directory/
├── manifest.json       ← Select this directory level
├── _locales/
├── src/
└── mcp-server/
```

Choose the instructions for your browser below. The Firefox temporary-install figure is a step diagram.

### Chrome / Edge / Chromium

1. Extract the Chrome ZIP to a **stable folder**; do not move or delete it afterward.
2. Open `chrome://extensions/` (use `edge://extensions/` in Edge).
3. Enable **Developer mode**.
4. Click **Load unpacked**.
5. Select the extracted directory that directly contains `manifest.json`, then pin HawkEye to the toolbar.

![Chrome extension manager: Developer mode and Load unpacked](https://github.com/user-attachments/assets/b43bc41c-edc3-4240-8948-0c098ed4e63f)

The installed card should show **Hx0 HawkEye · 1.0.7** with its switch enabled. See the [official Chrome instructions](https://developer.chrome.com/docs/extensions/get-started/tutorial/hello-world) for the equivalent controls.


Before upgrading, export anything important and close HawkEye sidebars. Replace the old fixed-folder contents with the new release, then click **Reload** on the extensions page. Do not load two HawkEye directories at once; different extension IDs keep separate local data.

### Firefox

1. Extract the Firefox ZIP.
2. Open `about:debugging#/runtime/this-firefox`.
3. Click **Load Temporary Add-on**.
4. Select `manifest.json` in the extracted directory.
5. Load it again after every Firefox restart.

![Firefox temporary installation step diagram](https://github.com/user-attachments/assets/0ec2e944-b7c6-47c3-a0f4-844211d3ac7e)

After selecting `manifest.json`, HawkEye appears under temporary extensions. Reload it after restarting Firefox. See [Mozilla’s temporary installation guide](https://extensionworkshop.com/documentation/develop/temporary-installation-in-firefox/).


### Firefox Developer Edition: persistent installation

For an installation that **survives browser restarts**, use [Firefox Developer Edition](https://www.mozilla.org/firefox/developer/). Mozilla permits unsigned extensions in this edition after changing the signature preference. [Mozilla signing guidance](https://extensionworkshop.com/documentation/publish/signing-and-distribution-overview/)

1. Install and launch **Firefox Developer Edition**. Confirm the edition under Help → About Firefox. This unsigned persistent-install method does not apply to regular release Firefox.
2. Download the **Firefox official ZIP** above and verify its SHA-256. Make a copy and change `.zip` to `.xpi`, for example `Hx0-HawkEye-Firefox-V1.0.7-Official.Release.xpi`. **Do not extract or re-compress it.** XPI uses ZIP format; renaming keeps its bytes and checksum unchanged. On Windows, enable View → Show → File name extensions first to avoid `.xpi.zip`. [Mozilla packaging guidance](https://extensionworkshop.com/documentation/publish/package-your-extension/)
3. Open `about:config` in Developer Edition, read and accept the browser notice, find `xpinstall.signatures.required`, and set it to **false**. This disables extension-signature enforcement in that browser profile; install only trusted packages whose checksums you have verified.
4. Open `about:addons` → Extensions → gear menu → **Install Add-on From File**, select the renamed `.xpi`, and confirm installation and permissions. Use this file-install path rather than the temporary `about:debugging` path; do not select `manifest.json` here.
5. Verify that **Hx0 HawkEye 1.0.7** is enabled. Quit and restart Developer Edition, then verify it remains installed and opens its popup/sidebar.
6. To upgrade, install the new package with the same add-on ID through the file-install flow, confirm the update, and reload existing web pages. Temporary installs and different Firefox editions/profiles may keep separate data; export important data before migrating.

![Official Developer Edition: HawkEye remains enabled after restart](https://github.com/user-attachments/assets/dffb31b6-d1b3-42a5-85cf-858c094f2c6c)

*The yellow verification notice indicates an unsigned package. Confirm HawkEye is enabled and remains installed after restarting the browser.*

The official download remains ZIP-only; your locally renamed XPI is not Mozilla-signed. The package includes a stable Firefox add-on ID. Persistent means retained across restarts, not guaranteed compatibility with every future browser release. Restoring signature enforcement can disable unsigned extensions.


After upgrading, reload existing target pages before using page assistants or floating controls.

Verify in the release directory on macOS / Linux:

```sh
shasum -a 256 -c SHA256SUMS
```

On Windows, use `Get-FileHash -Algorithm SHA256` and compare each ZIP digest with its entry in the checksum file.

### After install

- **Toolbar popup**: capture/intercept, target scope, MCP control, and Advanced Settings.
- **Sidebar**: History, Intercept, Replay, AI Tasks, browser-level Agent, Page Scripts, and the independent Codec workbench.
- **User Manual**: complete operation guide, browser differences, MCP setup, Skills, privacy, and troubleshooting.
<a id="quick-start"></a>
## 8. User manual
After install, open the **in-product User Manual** for full tutorials covering **MCP / Agent setup**, a **mainstream Browser MCP comparison**, **Chrome / Firefox differences**, **request header/body troubleshooting**, **screenshot file save**, **FAQ**, and **licensing**.

### MCP vs Agent in one minute

- **HawkEye MCP** is a local tool bridge, not an AI model. Install Node.js 18+, download the single `hawkeye-mcp-server.mjs` file from the popup, click **Copy universal config**, and add it to an MCP Host such as Codex, Cursor, or Claude Code. No `npm install` is required.
- **Built-in Agent Mode** is HawkEye's multi-turn planning/execution UI. Configure Base URL, API key if required, and Model under Advanced settings, then open **Capture UI → Agent Mode**. It does not require a third-party MCP Host.
- **AI Tasks** are repeatable authorized workflows with Scope, Skills, safety gates, and structured reports, rather than a free-form Agent conversation.

For positioning: [Playwright MCP](https://github.com/microsoft/playwright-mcp) focuses on cross-browser test/isolated automation; [Chrome DevTools MCP](https://github.com/ChromeDevTools/chrome-devtools-mcp) on Chrome DevTools and performance debugging; [Browser MCP](https://docs.browsermcp.io/) on general actions in an existing logged-in Chrome tab. HawkEye's core distinction is one workflow combining **real Chrome + Firefox sessions, capture, intercept/tamper, replay/fuzz, sensitive/dark-link evidence, and Agent execution**. See in-product Manual **§3.2** for the detailed comparison.


### Three-minute quick start and common issues

1. **Inspect one request:** open the target, enable capture with a domain limit, reload it and inspect a request / response in History.
2. **Process some data:** open Codec and try Base64 decoding or the SM3 → Base64 recipe above. Copy and check the result.
3. **Add AI when needed:** configure the model service in Advanced settings, begin with a read-only goal, then use assistants, Agent or MCP as appropriate.

The complete bilingual manual, edition comparison and User Agreement / Privacy Policy are available inside the extension and updated for 1.0.7.

| Common issue | What to check |
| --- | --- |
| No AI output / service not configured | Check the provider endpoint, model and authentication in Advanced → AI service; inspect the readable error. Stopping the wait does not guarantee server-side processing stops |
| Format recognized, no plaintext | Check characters, separators, depth, keys / IVs / modes. Hashes cannot simply be reversed; missing conditions remain unverified |
| No script menu / page does not match | Select and save the correct script, inject on a supported ordinary page and reread menus. Browser-internal pages may prohibit injection; use EML for mail when appropriate |
| Empty full response / cross-origin failure | Check permissions and response-body diagnostics. Some `no-cors`, CSP, cross-origin and debugging API restrictions cannot be removed by the extension |
| Bing errors / excessive redirects | Agent recognizes error pages and attempts search-entry fallback, retaining diagnostics if it fails. Upstream behavior, network and Cookie state can still affect access |
| Invalid extension context after an update | Reload the target page, then reopen the assistant or Agent |

Version 1.0.7 improves reading and navigation in assistants, script menus, AI result cards and Markdown tables. Edits are easier to retain, and cancellation or search failures show clearer messages. Browser security restrictions still apply, so some resources may not load.

---

## 9. Security & compliance
+ Use capture, intercept, replay, and Fuzz **only on systems you are authorized to test**.  
+ **AI analysis, AI Tasks, and Agent Mode** may send traffic and page context needed for the task to the third-party or internal model endpoint you configured. Default automatic redaction attempts to mask common Cookie/Token fields but cannot guarantee every secret is detected. Disabling it may send raw authentication context.
+ HawkEye MCP Server listens only on local loopback, but a trusted third-party Agent / MCP host may still forward tool results to its configured model service. Turn the bridge off when unused.
+ See the in-extension bilingual **Terms & Privacy agreement** for the complete data scope, exceptions, retention, and user rights.
+ Use **Render** and similar features in trusted environments; sandboxing reduces but does not remove risk from malicious responses.  
+ Commercial use: follow **license** terms in the product.
+ **1.0.7 local data tools:** Codec, comparison, IP calculations and basic mail checks run locally. Smart-decoding passwords, private keys, IVs, matrices, mappings and dictionaries are not sent to AI. Mail AI review sends only the previewed excerpt and evidence after an explicit click.

---

## 10. How to Obtain the Activation Code

New users can first use the **full Pro trial for 30 minutes**. When the trial ends without activation, the product automatically falls back to **Community**. If the experience fits your workflow, you can obtain a Pro activation code through the following methods:

**Visit [the activation code tutorial](https://www.yuque.com/u12459488/bzqpay/udkx5qy1x6guinz0?singleDoc) for current activation options and official promotion details.**

---

## 11. Contact & feedback
**Hx0 Team (Hx0战队)**

+ **Hx0 HawkEye website**: [https://www.hx0.store/products/hawkeye](https://www.hx0.store/products/hawkeye) (product overview, downloads, and docs)
+ WeChat official account / knowledge planet: **Hx0战队**
+ Email: [hx0studio@foxmail.com](mailto:hx0studio@foxmail.com)

Please include browser + version, extension version, repro steps, and screenshots when reporting issues.


You can also report through [GitHub Issues](https://github.com/asaotomo/Hx0-HawkEye/issues). Include error details; mask accounts, unrelated extensions, secrets and sensitive traffic in screenshots first.

---

## 12. Disclaimer
This project and extension are for **security research, development debugging, and authorized testing** only. Obey applicable laws and scope of authorization.  
The authors and contributors **assume no liability** for **unauthorized testing** or its consequences.

---

<a id="history"></a>
## 13. 1.0.1 Changelog

> The sections below describe earlier features and updates, with screenshots of the UI at the time. Follow the v1.0.7 guidance on this page for current controls and edition boundaries.

This `1.0.1` update primarily focuses on the enhancement of two professional edition capabilities:

- **Smart Proxy Dispatcher (Professional Edition)**: Added a proxy dispatch entry below the `Capture Type / Suffix`on the basic settings page. It can forward browser requests matching site rules to Burp, Yakit, or other upstream proxies, while unmatched requests continue on their original network path. This is suitable for integrating "native browser session capture" and "in-depth proxy debugging" into a single workflow, reducing the overhead of frequently switching system proxies.
  

![image](https://github.com/user-attachments/assets/64221294-63da-4aff-aeec-69250f0b6650)


- **Encryption Logic Intelligent Analysis (Professional Edition)**: Located to the right of the AI Analysis button. The model combines clues from the current request's URL, parameters, headers, body, and response, along with function names, field names, and submission flows from JS/HTML on the same page, to help determine if encoding, hashing, signing, or hybrid encryption is implemented on the front-end. It is suitable for reviewing changes in signature chains before and after packet modification.（In a nutshell: Let AI help you guess encryption, encoding, or signature logic, saving you the time of manual reverse engineering.）

  ![image](https://github.com/user-attachments/assets/f6a6e38e-21c2-4531-b6a9-56234e43e043)

  ![image](https://github.com/user-attachments/assets/718d6ad7-1f99-4c99-b3c7-108afdd48ac0)

  ![image](https://github.com/user-attachments/assets/213b5822-bcf7-404c-baa7-69111dd1116b)

  ![image](https://github.com/user-attachments/assets/b762a1cc-6054-4d17-9fa1-0adec61f35b8)

  ![image](https://github.com/user-attachments/assets/e255ea62-6817-4ad3-815e-c1f7b40c77e2)

  
- **Stability Improvements**: Improved request-header display and reliability when switching between normal capture, interception and proxy settings.
- **Sidebar and Batch Page Optimization**: Sidebar message display and interaction optimization (consistent across both ends), overall layout optimization of batch pages.  
- **Enhanced In-Page Replay and In-Page Fuzz Functions**: Updated to support form POST (Request Header Content-Type: application/x-www-form-urlencoded).
- **Replay Workspace Optimized**:  Encoding/decoding functions now support response body processing, added scope differentiation, and unified undo/redo records for both requests and responses.
- **“All domains” filter**: Fixed incorrect list or filter behavior when the host filter is set to “All domains” and it interacts with the workbench scope (current tab vs all traffic).
- **Capture / intercept list**: Column widths can be adjusted by dragging the vertical handles on the right side of each header cell; widths are saved locally and restored the next time you open the panel.
- **302 / redirect capture**: Improved recording of redirects (e.g. 302), with fewer missed requests and duplicate entries.
- **Three-state header sorting**: The capture / intercept table headers cycle default → ascending → descending → default. The Fuzz results table uses the same pattern; clearing sort restores the original row order by sequence; clicking a column-width handle does not trigger sorting.

## 14. 1.0.2 Changelog

This `v1.0.2` release strengthens **HTTP replay headers**, adds a **WebSocket workbench**, expands the **AI Task Console** (**in-task hints**), and brings **intercept** to the Community Edition—boosting Web assessments, CTF workflows, and daily capture analysis.

![v1 0 2海报-en](https://github.com/user-attachments/assets/98ec2d5e-e410-40c3-92fd-088a87f2d467)


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
  
![a7d48640ee2e4fed8032b4cf48229b23](https://github.com/user-attachments/assets/707007d2-7dc9-48c2-8981-8e7732219690)

- **CTF Capture-the-Flag Mode**
  Designed for Web-based CTF challenges. The AI automatically plans solving strategies around challenge entry points, hints, response behaviors, and suspicious parameters. It attempts to construct exploitation requests and generates a post-analysis report after successfully capturing the Flag.

  ![27e66bc42b733225d16ceccd9e78eed7](https://github.com/user-attachments/assets/a00c9dc2-8203-4a2a-aadd-ee32971d0138)

AI Tasks record execution, request evidence, key payloads, Flag hits and final reports. Use **Supplementary hints** while a task runs to provide new information for its next steps. See the in-product User Manual §10.

### 3. Interception Mode Is Now Available in the Community Edition

Interception Mode is now officially available for Community Edition users (**HTTP** and **WebSocket frames** when rules match).

Community Edition users can now pause, inspect, modify, and forward requests through Interception Mode, making manual testing, parameter debugging, and request verification much more convenient.

![image](https://github.com/user-attachments/assets/6154a019-fbbe-45d6-bbbf-3b68227db08b)

### 4. WebSocket Capture, Replay, Micro Fuzz, and Intercept

Enable **WebSocket** under capture types, then filter by type in the sidebar; handshakes often show as `GET 101`, frames as **`WS`** (**`OUT`** / **`IN`**). **Frame replay** shares the HTTP workbench and needs an **`OPEN`** page socket; **`§...§` + Micro Fuzz** uses the next inbound frame as the response. **Intercept** supports **per-frame** edit/forward/drop. Scope is page-created WebSockets inside the browser—not a system MITM. Details: User Manual §5.

![image](https://github.com/user-attachments/assets/d7a6f0fa-4894-4e30-a729-2c962aad194a)

### 5. AI Tasks: In-Task Supplementary Hints

While a task runs, expand **Supplementary hints**, enter newly discovered parameters, responses, paths or CTF hints, and choose **Submit**. The task considers these details in later steps. Individual submissions and the queue have length limits; follow the interface prompts and do not paste real passwords.

![image](https://github.com/user-attachments/assets/6634413a-4d35-4e2f-b286-5c7a88c29c84)
![image](https://github.com/user-attachments/assets/c40d4f83-6d44-46a6-b8e3-d170f274c2f7)

### 6. AI Tasks: Execution Improvements

AI Tasks use earlier request evidence and failed steps to adjust their plans. Once the goal is met or a Flag is found, they organize results into a report.

---

## 15. 1.0.3 Changelog

This `v1.0.3` release brings three main updates:

### 1. AI Tasks Support Skills Loading (Pro)

The **AI Task Console** can inject built-in **penetration / CTF knowledge bases**, or **import external SKILL.md files and skill folders** from Advanced Settings. Pick libraries and submodules in the task panel—they are injected as context to support multi-stage automated testing and triage.

![image](https://github.com/user-attachments/assets/82d7170f-cd6b-4e38-9b78-49a788af2b3a)

![image](https://github.com/user-attachments/assets/9f970717-f7df-4dc6-910f-74c70b989cad)


### 2. Capture & Intercept Experience Improvements

Smoother **capture / intercept** workflows in the sidebar: cleaner filtering and scope switching, easier list browsing, and more fluid edit/forward actions for day-to-day debugging and manual testing.

### 3. Online Activation Added

**Single-click** the popup **status badge** to open Software activation with a new **Online** tab for subscription or lifetime membership. Benefits sync online and are **cached locally**, so Pro features continue offline while the cache/subscription remains valid—alongside the existing **offline activation code** path for easier checkout and renewal.

![image](https://github.com/user-attachments/assets/e2a80834-6d66-4ffa-bcf3-8151b322de59)

---

## 16. 1.0.4 Changelog

This `v1.0.4` release brings four main updates:

### 1. Tampermonkey Scripts + Page Script Workspace (Pro)

Import `.user.js` userscripts and manage them in the sidebar with one-click inject. AI can create or optimize scripts from traffic and tie them into capture, replay, and sensitive scanning. Use scripts you write, scripts created with AI, or scripts run by AI Tasks in the same workspace.

![041bc1f31c42a9d53fedf9c92b972b9a](https://github.com/user-attachments/assets/067a5dab-9e00-4cd9-a964-012d5733f8d5)

![f48bb626b893c2efe11b0cdf9c8e69b9](https://github.com/user-attachments/assets/1e805ed7-b7ab-4fc8-a6b3-a9e779ce5507)


### 2. AI Task Smart Script Dispatch (Pro)

Enable **Smart Script Dispatch** so AI tasks can list, run, or create page scripts during pentest / CTF—pull page-side intelligence back, then continue replay verification and reporting.

### 3. Capture / Intercept Reliability

More stable intercept for local labs and self-signed HTTPS; fixes regressions such as empty intercept queues; packet editor now accepts Chinese input correctly.

### 4. Firefox Stability and Cross-Browser Alignment

Fixes Firefox capture, sidebar, intercept, replay, and script injection; daily experience is further aligned across Chrome and Firefox.


---

## 17. 1.0.5 Changelog

This `v1.0.5` release brings four main updates:

### 1. AI Task Console Overhaul (Core Release)

Execution records appear on a timeline with expandable tool results. Drag the divider to adjust the log and report widths. Before starting, AI can help interpret the task brief. Reports include **findings and request / response evidence**, with support for encryption-logic analysis and advanced codec operations.

![image](https://github.com/user-attachments/assets/a1e25ad7-7aa1-4b01-a42f-adec0a4dbcc6)

### 2. Thicker Skills Library + AI Generate Skill

Built-in sub-modules expanded to **19 pentest + 28 CTF**; **Smart Enable** toggle per main Skill; **AI Generate Skill** in Advanced Settings—create a single skill or collection and save as standalone Skill, built-in sub-module, or append to an imported skill.

![ac1eb01ce372ddf86b80d79ce4ac610b](https://github.com/user-attachments/assets/889cea2a-0751-434b-bab7-d2ff84bf4a0e)

![a9c5841467cee3adc1a220001c27b2b5](https://github.com/user-attachments/assets/15b6d6a5-8718-4442-a8d1-6a4a71be5a6a)

![image](https://github.com/user-attachments/assets/68b436cd-5b20-466a-b425-dd7bb22750ed)


### 3. Codec Capabilities Completed

Replay workbench adds **AES / DES / RSA / SM** and smart nested decode; built-in **Smart Decode Assistant** (enabled by default): select text on any page for common decode and hash hints; advanced AES / nested chains still go through replay or inline packet codec.

![image](https://github.com/user-attachments/assets/c0ffab9d-2de8-4e67-8d24-2f24dc5250e9)


### 4. UX Improvements and Bug Fixes

Fixed various Chrome / Firefox system issues; better coordination among intercept / debug mode / passive listening toggles; improved sidebar and settings copy; user manual updated to **v1.0.5**.

---

## 18. v1.0.6 changelog

### 1. HawkEye Browser Automation MCP (PRO)

HawkEye now exposes a security-oriented browser MCP, positioned like a security-specialized Playwright MCP. MCP-capable Agent Hosts such as Codex, Cursor, and LM Studio connect to `hx0-hawkeye`; the Host model can then autonomously call `browser_navigate`, `browser_type`, `browser_snapshot`, and HawkEye capture, replay, mutation, codec, TLS, sensitive-data, and evidence tools in the real browser. The loopback-only server supports stdio, Streamable HTTP, and legacy SSE and requires the user to enable the extension bridge. This capability is separate from the in-extension AI Task Console.

![Codex, Cursor, or LM Studio controlling the browser through HawkEye MCP](https://github.com/user-attachments/assets/ff0c2671-6559-4f38-b6f5-2a6a50c5375a)

### 2. Browser-level Agent (PRO)

Agent Mode requires an active trial or Professional license. It starts from the user's real current HTTP(S) tab and supports multi-turn planning, approval modes, complex controls / iframe / Shadow DOM interaction, visual screenshots, attachments, traffic analysis, replay, codecs, autonomous public-web research, native downloads, durable long-context memory, and expandable tool evidence.

![v1.0.6 Browser-level Agent](https://github.com/user-attachments/assets/b9491db0-727c-4a09-8020-0f87abd97efe)

### 3. Performance and resource use

Lower Firefox background resource use and improved large-page reading, capture-list updates and Agent / MCP responsiveness. Large results can be read in pages, keeping workflows responsive without losing evidence.

### 4. Choose which Skills Agent uses

The built-in knowledge base includes 19 pentest and 28 CTF sub-modules. Skills are off in new Agent chats. To use them, select available skills in Advanced Settings and enable **Skills** in the current chat.

### 5. Community capabilities opened since v1.0.5

Smart Proxy Router, Full Deep Search, and Sensitive Information Matching (built-in rules, custom regex, keyword libraries, and batch import/export) are available in Community starting with v1.0.6. AI Tasks, AI Skills, browser-level Agent, and HawkEye MCP remain Professional features.

### 6. 0930 capture and interaction improvements

- Capture history distinguishes current domain, current tab, and all records. Cross-subdomain requests remain visible under the originating tab. Intercept queues refresh automatically, and missing original request or response bodies show diagnostics.
- Replay opens in Pretty by default; edits in Pretty or Raw are sent. WebSocket frames, batch replay, AI analysis, and dark-link results have clearer feedback.
- Settings delete confirmations use in-extension dialogs. Firefox shortcut buttons match Chrome; English persona content updates when switching language, and dark-link settings remain scrollable in short popups and rule names wrap. Pending Agent approvals can be reopened from the waiting indicator, while backdrop and Escape no longer dismiss the approval dialog.
- Local MCP Server 1.0.13 improves setup and connection diagnostics.

---

## 19. 1.0.7 changelog

- **Independent codec workbench:** 147 operation entries and recipes of up to 16 steps, with one workspace for basic data processing and advanced parameterized operations.
- **Smart decoding and practical data tools:** multi-layer paths, locally verified AI suggestions, Morse punctuation, text / JSON comparison, binary-file recovery, IP and QR / barcode tools.
- **Four official page assistants:** shortcuts, AI results and analysis suggestions, with improved reading and controls; mail review supports local EML files.
- **Agent / MCP and micro Fuzz:** AI scene suggestions, task-dependent page concurrency, Markdown-table rendering and three-point Fuzz; local MCP Server 1.0.15.
- **Feature tour and update notices:** A feature tour introduces the main entry points, with daily online checks for official updates.
- **Stability and diagnostics:** improved target URL matching, page interaction after upgrades and cancellation feedback; clearer search failures and fallback options.

See the illustrated [feature walkthroughs](#features) and [quick start](#quick-start). The 1.0.1–1.0.6 changelogs are on this page; a [separate history archive](./CHANGELOG_ARCHIVE_EN.md) is also available.

<!-- HX0_BUILD_INFO {"schema":1,"builds":{"Chrome":{"version":"1.0.7","platform":"Chrome","buildId":"26b3770f8c52103abdf374d84f0a2ef648514b041d06edb39609be32a820f5ee","builtAt":"2026-11-04T05:58:44.585Z"},"Firefox":{"version":"1.0.7","platform":"Firefox","buildId":"fc97421a0feceb39a5b53f2f215fd4337842c4ce69ce47ab195d1cc55825a31f","builtAt":"2026-11-04T05:58:44.568Z"}}} -->

