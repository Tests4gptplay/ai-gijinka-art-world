# 路线 D｜Godot 场景／动画系统与离线 Movie Maker

**稳健替代候选**：Godot 4（MIT）+ SceneTree / AnimationPlayer / Tween / Shader / 2D-3D 角色 + Movie Maker + FFmpeg。

## 为什么考虑 Godot

这是成熟的实时场景系统：镜头对象、角色节点、UI 面板、信号和动画都有成套开发模型，适合具备“游戏界面感”和角色交互的视觉小说、程序化场景。更重要的是官方提供**非实时的 Movie Maker**：可按固定 FPS 输出逐帧视频/图像序列，降低实时录屏丢帧概率。官方文档明确可用于 procedural animation 和 motion design。

适合未来制作：GPT 龙娘 POV 指挥屏、多 AI 对话窗口、终端 UI 进入场景、关卡/空间穿梭、2D 角色舞台 + 3D 灯光等，不必把每件事自行实现为 drawLine 动画。

## 具体技术流程

```text
scene.tscn + animations + shaders + licensed assets
         ↓ fixed-fps Movie Maker
original frames PNG + WAV / or video intermediate
         ↓ FFmpeg controlled encode
final MP4 with source/caption timing
         ↓ native decode + playback QA
```

官方 Movie Maker CLI 用法示例（**文档用法，未在本机实际运行**）：

```text
godot --path /path/to/project --write-movie output.avi --fixed-fps 30
```

实际项目可以选择 PNG 帧序列并由外部 FFmpeg 编码；Godot 自带 OGV/AVI/PNG+WAV 等导出模式，并非直接万能 H.264/AAC 发布工具。音频混合采样率需要满足对 FPS 的要求，避免时钟漂移。

## 质量规则

- 场景树须包含高质量 art assets（角色、背景、质感、文字框、动态遮罩），不能因为 Godot 有 Shader 就堆单色方块。
- 使用 AnimationPlayer/脚本确定性按时钟定位关键帧，区别于游戏运行时每帧累加 delta。
- 大场景必须从分镜到节奏有真实视觉事件和镜头切换，不是连续摆动的静态场景。
- 最终比较 Godot 编码输出和 FFmpeg 真实 MP4 的字幕、粒子、色彩与闪烁表现；**播放器能动不等于 MV 有艺术质量**。

## 局限

Godot 是游戏引擎，电影级资产制作、字体级动画艺术、复杂素材合成可能依然不如专用 Motion Graphics/Blender 工作流；引擎安装与版本、出口限制、分辨率/字体都需要验证。**本仓未运行这套工作流，也未授权给 CAH 安装。**

官方文档：
- [Godot Movie Maker（stable）](https://docs.godotengine.org/en/stable/tutorials/animation/creating_movies.html)
- [Godot MIT license](https://godotengine.org/license/)
