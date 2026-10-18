# 技术原始资料、许可证和调研证据

**核对时间：2026-10-18**。这里优先保存**项目官方页面、主维护仓库或正式许可文本**，不以随机二次汇总页作为已验证能力。链接证明框架存在及文档所宣称功能，**不证明我们本机安装成功或最终艺术效果已通过**。

| 路线 / 实现 | 官方出处 | 据此确认的范围 | 许可/注意 |
|---|---|---|---|
| Remotion React 影片 | https://www.remotion.dev/docs/render | 通过 CLI/服务器渲染视频，frame-based compositions | https://www.remotion.dev/docs/license/pricing — 条件化 Free License，**不是纯 MIT**；自动化产品/组织须再核对 |
| Remotion + Three | https://www.remotion.dev/docs/three-canvas | 官方 `<ThreeCanvas>` 与 `useCurrentFrame` 同步、时间轴往返 | WebGL GPU 后端需实机核实 |
| Remotion Chromium GPU | https://www.remotion.dev/docs/options/gl / https://www.remotion.dev/docs/options/chrome-mode | OpenGL 后端选择、Chrome 模式 | 不能把“浏览器支持 WebGL”当作已证实无头/硬件 GPU |
| Three.js WebGL2 | https://threejs.org/docs/pages/WebGLRenderer | 维护的 WebGL2 Renderer，WebGL1 不再受支持 | Three.js JS runtime，按版本固定 |
| Three.js 后期 | https://threejs.org/manual/pages/post-processing.html | EffectComposer 等后期链 | shader 可能造成质量/性能/时序差异 |
| Motion Canvas | https://motion-canvas.io/docs/ / https://motion-canvas.io/docs/time-events/ | TypeScript generator 动画与时间事件 | https://github.com/motion-canvas/motion-canvas/blob/main/LICENSE — MIT |
| Motion Canvas 导出 | https://motion-canvas.io/docs/rendering/image-sequence/ / https://motion-canvas.io/docs/rendering/video/ | 图像序列；FFmpeg exporter/音轨 | 官方承认 FFmpeg exporter 相对较新，需测试 |
| PixiJS | https://github.com/pixijs/pixijs | GPU 加速二维 texture/filter/mask/text & sprites | https://github.com/pixijs/pixijs/blob/dev/LICENSE — MIT；版本与 filter 兼容 |
| Blender Eevee | https://docs.blender.org/manual/en/latest/render/eevee/index.html | 实时 PBR 材质/光影与较快最终渲染 | https://github.com/blender/blender/blob/main/release/license/license.md — Blender GPL，实际扩展需注意 |
| Blender Grease Pencil | https://docs.blender.org/manual/en/latest/grease_pencil/properties/onion_skinning.html | 绘图关键帧/洋葱皮辅助动画 | 大型专业软件先获得用户安装批准 |
| Godot Movie Maker | https://docs.godotengine.org/en/stable/tutorials/animation/creating_movies.html | 2D/3D 非实时录制、固定 FPS、PNG/WAV 等输出 | https://godotengine.org/license/ — Godot MIT |
| ComfyUI / 工作流 | https://github.com/Comfy-Org/ComfyUI | 节点图片/视频模型、可保存 JSON 与 seed | https://github.com/Comfy-Org/ComfyUI/blob/master/LICENSE — GPLv3，节点/权重/服务分开核对 |
| Wan2.2 | https://github.com/Wan-Video/Wan2.2 | 官方视频模型与 GPU 条件示例 | 显存需求和模型具体条款按选型复核 |
| Live2D (可选) | https://www.live2d.com/en/sdk/license/ | 角色绑定 SDK 发布许可分类 | 专业编辑器/出版许可独立，不默认免费商用 |
| FFmpeg | https://ffmpeg.org/ffmpeg.html | 视频/音轨映射、编码、探针所需的核心工具 | 实际二进制编译许可证与 codec 组合要核对 |

## 第三方程序化 MV 的例子：事实分层

用户引用 [Bilibili BV1SgaY64EG5](https://www.bilibili.com/video/BV1SgaY64EG5/) 的作品说明：创作者**声称**用 Claude 编写的 Three.js / WebGL2 + GLSL 绘制 13,015 帧，且未用图像/视频生成模型。这个描述说明编程逐帧创作的实际研究方向，但本轮**未核实其项目源码、GPU/渲染环境和成片全时长，也未复制其画面**；不能凭作者一行声明复现该画质。

这里采集的是技术路径，不下载或再发布该作者的音乐/视频/封面。公开研究可保留作者来源和许可链接，不以“程序生成”推断画面无版权或工具没有商业条款。

## 本地视频版权与 AI 娘素材

本仓现有 [RIGHTS](../RIGHTS.md) 包含 ZipZipPipe 角色非商业/署名边界以及 DeepSeek 上善无形 CC BY-NC-SA 4.0 链。任何新角色 PV 仍需按真实素材与改编条件处理。第三方音乐如 Mili `world.execute(me);` 的使用也必须单独核对官方版权规约：

https://projectmili.com/copyright-guidelines

工具许可证（如 MIT、GPL）**不会代替角色形象、音乐、片源、配音或字体的版权许可证**；所有声称 AI 未参与图片生成的信用声明必须由实际 pipeline 证据支撑。

## 研究得出的明确技术判断

1. Three.js/WebGL2/GLSL + Remotion 适合 **DOM UI＋3D Shader 叠层合成与精确时间轴**；不是唯一高质量方法。
2. Motion Canvas/PixiJS 对 **精细排版、窗口、代码、角色分层与 motion design** 很有优势；不是简单纯几何画线。
3. Blender/Godot 与生成式模型在特定表达需求下可明显扩展媒介能力，但费用、资产、环境与一致性风险更复杂。
4. 最有可能稳定质量的不是单一工具，而是**真实动态样片先行＋独立美学 veto＋确定性全片时钟＋原始音乐/艺术版权核验**。
5. 所有结论均标为 **待真实 Pilot 样片检验**，没有凭空声称某条路线已获得美学 PASS。
