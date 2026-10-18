# 路线 A｜浏览器电影级混合合成

**推荐第一候选**：Remotion（可替换为自有逐帧时间轴）+ React/HTML/CSS/SVG + Three.js WebGL2/GLSL + FFmpeg。

## 为什么比基础绘线更值得试

- 模型擅长写 **HTML 结构、CSS 界面与交互 UI**，可直接制作真实可信的 IDE、终端窗口、编辑器面板、数据屏、无数层文字显示；这些都是艺术舞台本身，不是几根线拼出的“想象 UI”。
- Three.js 摄像机、层级、透明贴图、3D 场景加 shader 带来空间纵深、材质和灯光可能性；GLSL 可做程序性光效、折射、粒子、故障、体积感觉；**但需要真正设计材质/灯光/镜头，不会自动“变漂亮”**。
- 画面可以像影视合成一样分层：场景背景、角色/场景、动态数据层、字幕层、色彩/光效层。不要把所有艺术目标塞进单个 `drawLine()`。

## 建议系统架构

```text
song/cues/shot-manifest.json      （只在获授权工程内存放音频）
              |
         frame index n
              |
         time = n / fps
              |
    Remotion / equivalent clock
     /           |            \
 React DOM    WebGL2/Three    character/video assets
 CSS SVG UI   GLSL/materials   layer/rig/keyshots
     \           |            /
       ordered composite + grade + captions
                    |
        frame sequence / renderer
                    |
             FFmpeg + audio
                    |
             encoded MP4 QA
```

推荐用 Remotion `useCurrentFrame()` 或等价的固定 `renderAtFrame(n)` 控制一切运动；对 Three.js 应使用 Remotion 官方 `<ThreeCanvas>` 同步 API，而非实际墙钟驱动 `useFrame`。输出时以单一 frame id 驱动字体、摄像机、shader uniform `u_time`、纹理与人物参数。注意部分后期效果有历史缓冲，随机跳转帧需要重置或状态重建。

## 具体可以设计的镜头

- **终端空间**：真实排版的多栏终端、代码语法高亮、层层嵌套的窗口，一部分内容随音乐淡入；不是随机绿色乱码铺屏。
- **数字世界觉醒**：从 2D 编辑器逐层突破到 3D 场景，代码成为光粒阵列，透视镜头推进、失焦与色散带来张力。
- **角色舞台**：已授权分层 GPT 白龙娘前景在 2.5D 演出，背后信息架构与 3D 粒子随旋律变幻；确保角/翼/鳞尾辨认清楚。
- **歌词**：文字视觉与真实画面材质整合，但字幕安全区单独处理，不故意让 shader 盖住中文。

## 风险 / 预备验证

1. **WebGL GPU 后端**：浏览器有 WebGL2 不等于无头渲染能稳定用 GPU。Remotion 有 `--gl`、`--chrome-mode` 等渲染选择；先用实际 Windows 主机跑 1920×1080、连续 300 帧，检测设备状态/CPU fallback/GPU driver/帧色差，不能靠 README 自报“已可运行”。
2. **许可证**：Remotion 不是通用 MIT 授权；官方对个人/3人及以下组织等提供 Free License，团队性质、商业规模或自动化产品可能需要其他许可。发布供第三方重复使用的公共框架前重新确认许可证。
3. **Shading / 纹理**：Bloom/Glitch 应服务情绪，不得恒定堆满；初稿至少提供前中后不同镜头语言，避免变成昂贵的“几根发光线”。
4. **导出一致性**：字体准备/加载完成才截图；DOM 与 WebGL 的色彩、透明、缩放、pixelRatio、Alpha 必须物理校验。不能在高分辨率导出时重复缩放字幕。
5. **真实编码审查**：预览浏览器正确但 FFmpeg 容器/抗锯齿/色彩可能不同；抽检**最终解码**画面，连续播放 10 秒而非光看单帧。

## 最小实测品

一条 **8–12 秒** 1080p30 实际 MP4：至少 3 个真正不同的镜头（UI → 3D 深度变化 → 角色/歌词或真实设计的收束画面），3 层以上可读视觉层级，正确合成有权使用的音频/合成节拍；提供原始渲染时间戳、无头 GPU 后端记录、真实视频 contact sheet + 短片连续审片记录。

**官方文档**
- [Remotion ThreeCanvas](https://www.remotion.dev/docs/three-canvas)
- [Remotion render CLI](https://www.remotion.dev/docs/render)
- [Remotion OpenGL 后端](https://www.remotion.dev/docs/options/gl)
- [Remotion 许可证](https://www.remotion.dev/docs/license/pricing)
- [Three.js WebGLRenderer](https://threejs.org/docs/pages/WebGLRenderer)
- [Three.js postprocessing](https://threejs.org/manual/pages/post-processing.html)
