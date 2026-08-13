# frontend-lab · 炫酷效果集

> 前端硬功底与想象力的展示场 —— CSS / Canvas / WebGL / 3D / 现代浏览器 API,每个 demo 都是一个可现场打开的炫酷效果。

**在线浏览:**
- 🚀 Vercel(主):https://frontend-lab-ten.vercel.app
- 📄 GitHub Pages(镜像):https://fe-ng.github.io/frontend-lab/

---

## 效果目录

| # | 名称 | 技术切面 | 线上演示 |
|---|---|---|---|
| 01 | Aurora · 3D 视差 Hero | `@property` 极光 + Canvas 星图 + preserve-3d 分层 + Scroll-Driven | [open](https://frontend-lab-ten.vercel.app/01-aurora-parallax/) |
| 02 | GLSL Aurora | WebGL fragment shader · 域翘曲 FBM · cos 色板 · 鼠标扰动 | [open](https://frontend-lab-ten.vercel.app/02-glsl-aurora/) |
| 03 | Three.js 粒子球 + Bloom | GPU instancing · UnrealBloom 后处理 · 拖拽 | [open](https://frontend-lab-ten.vercel.app/03-three-particles/) |
| 04 | Flow Field 粒子流场 | Canvas 2D · 值噪声 · ~700 粒子拖尾 · 指针牵引 | [open](https://frontend-lab-ten.vercel.app/04-flow-field/) |
| 05 | 纯 CSS 3D 立体场景 | preserve-3d 极致 · 玻璃立方体+内核+轨道环 · 零 JS | [open](https://frontend-lab-ten.vercel.app/05-css-3d-cube/) |
| 06 | GSAP 电影级滚动叙事 | ScrollTrigger pin+scrub · 横向 panel · 视差 | [open](https://frontend-lab-ten.vercel.app/06-gsap-scroll/) |
| 07 | View Transitions SPA | `startViewTransition` · 共享元素 morph · 降级 | [open](https://frontend-lab-ten.vercel.app/07-view-transitions/) |
| 08 | Metaballs 融球 | `blur + contrast(25)` gooey · 指针引力 | [open](https://frontend-lab-ten.vercel.app/08-metaballs-gooey/) |
| 09 | GLSL Raymarching | SDF 布尔并集 · 软阴影 · 菲涅尔 · 鼠标转视角 | [open](https://frontend-lab-ten.vercel.app/09-raymarch-shader/) |
| 10 | 3D Model Viewer | `<model-viewer>` · GLB · 进度条+CDN 兜底 | [open](https://frontend-lab-ten.vercel.app/10-model-viewer/) |
| 11 | Particle Text 粒子文字 | `getImageData` 采样 · 弹簧飞聚 · 鼠标排斥 | [open](https://frontend-lab-ten.vercel.app/11-particle-text/) |
| 12 | Audio Visualizer | Web Audio · 麦克风/合成音兜底 · 环形频谱 | [open](https://frontend-lab-ten.vercel.app/12-audio-visualizer/) |
| 13 | 3D Tilt Cards | perspective tilt · glare 高光 · magnetic 磁吸 | [open](https://frontend-lab-ten.vercel.app/13-tilt-cards/) |
| 14 | Generative Spirograph | hypotrochoid · 加色叠加 · 滑条改参 | [open](https://frontend-lab-ten.vercel.app/14-generative-spirograph/) |
| 15 | GPU Galaxy 星系 | Three.js shader points · 对数螺旋 · AdditiveBlending | [open](https://frontend-lab-ten.vercel.app/15-gpu-galaxy/) |
| 16 | L-system 分形树 | Canvas 2D 递归 · 风摆 · 点击重新生长 | [open](https://frontend-lab-ten.vercel.app/16-lsystem-tree/) |
| 17 | Boids 群飞 | 分离/对齐/聚合 · 鼠标吸附 · 朝向着色 | [open](https://frontend-lab-ten.vercel.app/17-boids/) |
| 18 | Magnetic Cursor | 自画光标 · lerp 拖尾 · 磁吸放大 · 涟漪 | [open](https://frontend-lab-ten.vercel.app/18-magnetic-cursor/) |
| 19 | Image Glitch / Datamosh | RGB 通道偏移 · 行扫描 · 块位移 · 像素操作 | [open](https://frontend-lab-ten.vercel.app/19-image-glitch/) |
| 20 | Hyperspace 超光速星场 | 3D 透视投影 · 径向拉线 warp | [open](https://frontend-lab-ten.vercel.app/20-hyperspace/) |
| 21 | Water / Caustics Shader | WebGL · 法线 fBm · 菲涅尔 · 焦散 · 涟漪 | [open](https://frontend-lab-ten.vercel.app/21-water-shader/) |
| 22 | Reaction-Diffusion | Gray-Scott · 9 点拉普拉斯 · 预设 · 涂抹播种 | [open](https://frontend-lab-ten.vercel.app/22-reaction-diffusion/) |
| 23 | Solar Orrery 太阳系 | 8 行星真实周期比 · 土星环遮挡 · 缩放调速 | [open](https://frontend-lab-ten.vercel.app/23-solar-orrery/) |
| 24 | Squash 3D 壁球 | three.js + 自定义物理 · 单人 rally · tin/outline 规则教学 | [open](https://frontend-lab-ten.vercel.app/24-squash-game/) |

---

## 怎么跑

每个 demo 是一个独立目录下的 `index.html`,**零构建、零依赖**(Three.js / GSAP / model-viewer 走 CDN)。本地任选其一即可:

```bash
# 直接用浏览器打开
open index.html            # 或双击

# 或起个静态服务器(推荐,Audiio/模型等需 http)
python3 -m http.server 8080   # → http://localhost:8080/
```

画廊首页 [`index.html`](./index.html) 是入口,列全部 demo,带:焦点环 hover(渐变描边跟随移动)、空闲预加载(进画廊 idle 预取重资源,demo 秒开)、滚动位置保活(从 demo 回来不回顶)。

## 设计原则

- **单文件**:一个 demo = 一个 `index.html`,自包含,可独立分享/打开。
- **硬功底切面**:每个 demo 主打一项可讲清原理的技术(不是堆砌库)。
- **可访问性**:全部支持 `prefers-reduced-motion` 降级;DPR 上限;响应式。
- **深色霓虹一致视觉**:`#05060d` 底 + `#7c5cff / #18d6c9 / #ff2e9a` 品牌色。

## 浏览器支持

现代 Chromium / Safari / Firefox。用到的新 API 与退化:
- `@property` / Scroll-Driven Animations(View Transitions)→ 不支持时 `@supports` 回退(IntersectionObserver 等)。
- WebGL / Three.js → 主流均支持;09/21 有 shader 编译错误兜底,不静默黑屏。
- View Transitions → Firefox 144+(2025-10)起支持;旧版直接切换降级。

## 部署

双部署,GitHub Pages + Vercel,`git push main` 两端自动更新。详见 [`DEPLOY.md`](./DEPLOY.md)。

## 新增一个 demo(规约)

1. 建目录 `NN-name/index.html`(NN 递增,kebab-case)。
2. 左上 overlay `NN · 名称`,右上 `← lab 首页` 相对链 `../`(勿用绝对 github.io,否则在 Vercel 上跳被墙站)。
3. 画廊 `index.html` 的 `.grid` 加一张 `<a class="demo">` 卡。
4. **本 README 表格加一行**(技术切面 + 线上链接)。
5. `git push` → 自动部署。

## 作者

[`FE-ng`](https://github.com/FE-ng)

## License

MIT
