# 路线 B｜高密度二维与 2.5D Motion Design

**并列首选**：Motion Canvas (TypeScript 动画编排 + 实时预览) + 可选 PixiJS 8/WebGL 滤镜 + SVG/分层插画 + FFmpeg。

## 为什么“2D”不一定简陋

此前问题不是缺 3D，而是**只实现最容易绘制的几何基元**。真正的 Motion Graphics 可以拥有：
- 高级字体设计、字距与行距、字体权重变化、真实 IDE 代码排版、编辑器 UI、矩阵和遮罩；
- 丰富的图形构图、插画、擦拭转场、蒙版、置换、模糊、粒子、运动拖尾；
- 前后多层视差、摄像机透视模拟和角色分层动画；
- 对音节、节拍、歌词 Cue 和段落极精确的时序控制。

Motion Canvas 的定位是**信息向量动画及音频同步**，不是现成的角色大制作编辑器；如果没有高质量分层人物资产，其画面仍可能很朴素。PixiJS 提供 WebGL/WebGPU、贴图、遮罩和 Filter，适合大量 sprite/多层元素的 GPU 合成；首轮选择成熟 WebGL 渲染，不默认实验性 WebGPU。

## 画面生产规则

1. **场景先设计到完整一屏**：层级栅格、留白、暖/冷色平衡、主次对比、一个明确的视觉事件；允许真实角色/原创建模图像和整块设计素材，而不是每个对象都从 `Line` 或 `Rect` 拼起来。
2. **动画有因果**：代码被写入 → 窗口响应 → 世界结构变化，而不是同一张画面反复横向摇摆。
3. **UI 可信**：编辑器行号、语法配色、控制台字距、代码窗口层级与状态变化都必须先经过 1:1 画面检查。代码雨要有前后层深度、亮度管理、节奏和局部聚焦，非随机字符矩阵覆盖。
4. **独立的字幕通道**：歌词按原时码渲染、清晰度与安全区测试；艺术效果不能破坏可读性。
5. **可重复导出**：用受控帧时钟驱动 Motion Canvas 时间事件；关键镜头用等价确定性函数计算位置/透明度，不依赖浏览器实时帧率。导出 PNG image sequence 或官方 FFmpeg exporter 后做实际解码 QA。

## 拟议实验镜头

- Scene 1（3 秒）：可信编辑器与多层窗口，最先出现一个干净的语义焦点。
- Scene 2（4 秒）：代码字体层、图标、数据瀑布通过遮罩和透视变成层叠空间；突出图形艺术和过渡，不靠简单摇摆。
- Scene 3（3 秒）：在允许使用的角色分层立绘/原创替身上展现人物微表情与肢体，窗口视觉与角色互动。

该路线很适合 **Bilibili 置顶宣传 PV、歌词动态排版、代码主题与世界观角色演示**，而且较方便语言模型逐次修复界面美术。

## 风险与依赖

- **字体中文回退/缺字**：检查真实机器字体。不要从他人仓库复制未经许可的字体。
- **向量动效过简洁**：必须有画面密度/变化/意义审核，不以「所有组件都能动」证明叙事成立。
- **插件兼容性**：PixiJS 和其滤镜版本需配套；每个效果先做真实 1080p 编码测试。
- **导出器成熟度**：Motion Canvas 自己提示 FFmpeg exporter 比较新；必要时走稳定的 image sequence → 已核验 FFmpeg，避免因一条 Exporter 失败全盘失控。

## 最小实测品

8–12 秒真实声音 MP4，核心是高信息密度 **真实 UI/代码/角色分层镜头**。至少比较两个音乐情绪段落，证实不仅是排版播片、旋转矩形、声谱棒或 PPT 换页。同步导出中段 frame 和最终解码视频，给独立审片者评分与修正理由。

**官方文档**
- [Motion Canvas 简介](https://motion-canvas.io/docs/)
- [Motion Canvas Time Events](https://motion-canvas.io/docs/time-events/)
- [Motion Canvas 图片序列导出](https://motion-canvas.io/docs/rendering/image-sequence/)
- [Motion Canvas FFmpeg 导出](https://motion-canvas.io/docs/rendering/video/)
- [PixiJS 项目](https://github.com/pixijs/pixijs)
- [PixiJS 滤镜](https://pixijs.io/filters/docs/index.html)
