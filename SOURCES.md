# 原帖、核验链接与来源优先级

**核验时间：2026-10-18。** 本次直接核对到的作者 B 站视频简介与展示顺序标为 **A**；经公开仓库保存的 Pixiv 页码、作者声明、下载 SHA 记录但本轮未能直接读取 Pixiv 页全文的，标为 **B（可复核归档）**；各同人系列自身简介为 **A-独立作品**；传播站的性格归纳只能算 **C**。

| ID | 来源 | 类别 | 可以支持的事实 | 限制 |
|---|---|---|---|---|
| Z01 | [ZipZipPipe B 站空间](https://space.bilibili.com/4168597) | 作者身份 | 《大AI和小AI们》等作品的作者页入口 | 主页数据随时间变化 |
| Z02 | [《大AI和小AI们》 BV1tE9XBbErS](https://www.bilibili.com/video/BV1tE9XBbErS/) | **A 原作者视频** | 2026-05-03 北京时间（UTC 05-02，后续已核原帖 pubdate）；九款出现顺序；大 AI / 小 AI；DeepSeek 原型署名 | 视频标注未经授权禁止转载；本库不复制视频帧 |
| Z03 | [《AI娘的日常》 BV1mwRzBdEzk](https://www.bilibili.com/video/BV1mwRzBdEzk/) | **A 原作者视频** | 2026-05-04；梗图/日常，网络/模型/公司体验梗 | 梗非作者统一人格设定 |
| Z04 | [《“亿万”身家的她们》 BV1bARXBYEZz](https://www.bilibili.com/video/BV1bARXBYEZz/) | **A 原作者视频** | 2026-05-09；作者述及图片开放分享并允许再创作 | 视频本体「未经授权禁止转载」与图像许可有别 |
| Z05 | [《AI娘化》 Pixiv #148186519](https://www.pixiv.net/artworks/148186519) | **B 作者高清图合集** | 作者 ID 18604994；17 图；GPT p03 / Qwen p12 等；署名与非商用；DeepSeek 单独适用 CC | 本轮直接打开 Pixiv 受限制，页码/声明由已保存证据复核 |
| Z06 | [上善无形原鲸鱼娘许可](https://www.bilibili.com/opus/1231977657712771073) | **B 上游作者动态** | 鲸鱼娘原型与 CC BY-NC-SA 4.0 线索 | 需要逐帖复核／保留授权快照 |
| Z07 | [ZipZipPipe DeepSeek 二创许可动态](https://t.bilibili.com/1231980045693616162) | **B 作者动态** | DeepSeek 女仆二创的许可链 | 不扩展到其它全部角色 |
| Z08 | [shuaizenge/ai-girls 素材仓](https://github.com/shuaizenge/ai-girls) / [catalog](https://github.com/shuaizenge/ai-girls/blob/main/catalog.json) | **B 素材索引** | 八位作者原稿、Q版视频秒数、图像来源/哈希 | 发现 p10 被误标 Gemini 变体；需对照另一来源 |
| Z09 | [AI Moe Atlas](https://selinlee.github.io/ai-moe-atlas/zh/models/) / [RIGHTS](https://github.com/SelinLee/ai-moe-atlas/blob/main/RIGHTS.md) | **B 独立考据** | 11 位形象识别、原图页码、可追溯许可证据 | 并非作者本人统一立绘本 |
| Z10 | [这个刀子真甜 GPT 龙娘日常 BV1EvKK6NEoi](https://www.bilibili.com/video/BV1EvKK6NEoi/) | **A-独立二创** | GPT 小龙娘＋DeepSeek 日常角色；明确图形来源 | 不是 ZipZipPipe 钦定家庭 |
| Z11 | [冬冰 AI 中转站公寓 BV1fthi6mEEz](https://www.bilibili.com/video/BV1fthi6mEEz/) | **A-独立二创** | 同住公寓日常、创作者自述剧情/性格虚构 | 不可冒充原设 |
| Z12 | [lieyang AI 学院 BV19Jhx6VE8A](https://www.bilibili.com/video/BV19Jhx6VE8A/) | **A-独立二创** | 视觉小说＋回合制、作者提供剧情和原创人物 | 独立世界与年龄/实力设定 |
| Z13 | [GPT/DeepSeek 二创桌宠](https://github.com/tqlearning/ai-girl-chatgpt-pets) | **C 工具衍生** | 使用 ZipZipPipe 等社区参考制作桌宠 | 不能改写原著作者/许可 |
| Z14 | [B 站动态 / opus #1244428286878023718](https://www.bilibili.com/opus/1244428286878023718) | **原帖待核验线索** | 可检索的关联话题为“GPT-6 Astra”和白龙娘参考，尚未核对原帖正文 | 本轮不能直接打开全文/下载多图，不断言其中有完整世界观或作者版角色说明 |

### 固定版本的考据数据

- [shuaizenge/ai-girls 固定提交](https://github.com/shuaizenge/ai-girls/tree/2c2c029ac4c59e1ebc909788a64ce75df0cbe711) — 素材目录与图像对象，用于本次等字节复制缩略预览。每件对象 Git Blob SHA 写在 manifest。
- [SelinLee/ai-moe-atlas 固定提交](https://github.com/SelinLee/ai-moe-atlas/tree/018bc3ca6c8d946006dacfc0bca7bf65a6dff4d6) — Llama / MiniMax / 豆包 ZipZipPipe 图像识别与原帖页码、保留声明。
- Pixiv 源图 `148186519_p3.jpg` 等的 SHA-256 与分辨率见本目录 [assets/manifest.json](assets/manifest.json) 或上述两仓对应 `catalog.json / manifest.json`。对衍生缩略图本库只声明复制的 Git Blob SHA 一致，不谎称本轮独立重抓 Pixiv 原站。

### 仍需核查

1. B 站 opus #1244428286878023718 **原帖全文和逐张图**；现只保留公开 URL，未核对原帖全文。
2. Pixiv《AI娘化》17 张全页的原站逐图可达性，尤其 p10 Doubao 与社区错标的 `gemini variant`。
3. MiniMax Q 版原视频的准确展示秒数及其无视频截帧的原始静态高清图。
4. 所有角色原作者后续改款、正侧背设定图、Q 版原始透明图的真伪/署名。
5. 粉丝作品的商业/二创范围不能仅靠“开源”“随便用”推定许可。
