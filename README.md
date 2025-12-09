

- 一个基于 React + Vite 的 3D 圣诞树 Web 应用，使用 React Three Fiber（Three.js）渲染高保真场景。
- 支持 AI 手势识别（MediaPipe），用“张开手掌/握拳”在“散开 ↔ 聚合”之间切换；左右移动手掌控制视角旋转。
- 照片来源可动态扫描本地资源，也可在页面中“上传多张图片”即时生成你的专属圣诞树。
- 原创链接：https://github.com/moleculemmeng020425/christmas-tree#  本项目在此基础上进行修改
![Project Preview](public/preview.png)
特性

- 交互式 3D 场景：树叶粒子、双面拍立得、彩灯闪烁、圣诞元素与顶部金色五角星。
- AI 手势控制：摄像头识别 Open Palm / Closed Fist / 手掌移动。
- 自定义照片：
  - 启动时自动扫描 src/assets/photos 中的图片（支持任意文件名，含 jpg/jpeg/png/webp ）。
  - 页面右下角“上传照片”按钮支持多选上传，上传后“仅使用上传的照片”渲染。
  - 文件名为 top.* （如 top.jpg / top.png ）的图片优先显示。
- 参数面板（右上角“参数设置”）：可调整树叶粒子、照片挂件、圣诞元素与彩灯数量，实时生效。
- 调试面板（右下角“🛠 DEBUG”）：查看摄像头画面与关键点覆盖，便于确认手势识别。
技术栈

- 前端框架：React 18、Vite
- 3D 渲染：React Three Fiber（Three.js）
- 3D 辅助： @react-three/drei 、 @react-three/postprocessing
- AI 手势识别： @mediapipe/tasks-vision
- 数学/粒子辅助： maath
目录结构（关键）

- src/App.tsx ：主场景、手势控制器、参数面板与上传逻辑
- src/assets/photos/ ：默认内置照片扫描目录（支持任意文件名）
- src/main.tsx 、 src/index.css 、 src/App.css ：入口与样式
- public/ ：公共静态资源（例如 vite.svg ），不参与打包处理路径
- vite.config.ts ：Vite 配置（GitHub Pages 需设置 base ）
环境要求

- Node.js ≥ 18（建议 18 或 20），自带 npm
- 浏览器需支持 WebGL/WebAssembly 与摄像头权限（Chrome/Edge/Firefox/Safari）
快速开始

- 安装依赖： npm install
- 开发启动： npm run dev
- 构建产物： npm run build
- 本地预览： npm run preview （用于模拟线上构建结果）
使用说明

- 手势控制：
  - 张开手掌（Open Palm）→ Disperse（散开）：圣诞树炸裂为漫天粒子与照片
  - 握紧拳头（Closed Fist）→ Assemble（聚合）：元素聚合为完整圣诞树
  - 手掌左右移动 → 旋转视角：向左移树向左转，向右移树向右转
  - 手掌上下移动 → 俯仰视角：向上移抬高视角，向下移降低视角
- 上传照片：点击右下角“上传照片”多选图片（PC/手机相册均可），上传后仅用本次上传的照片生成圣诞树；支持 jpg/jpeg/png/webp 。
- 参数面板（右上角“参数设置”）：
  - 树叶粒子数量 ：树身密度；越大越华丽，性能压力越高
  - 拍立得照片数量 ：照片挂件数量（不足时循环纹理）
  - 圣诞元素数量 ：礼物盒、球、拐杖糖的总数
  - 彩灯数量 ：闪烁的灯泡数量
- 调试：点击“🛠 DEBUG”显示摄像头画面与关键点；若提示权限被拒绝，请在浏览器地址栏允许摄像头。
自定义照片（启动时扫描）

### 📄 License
MIT License. Feel free to use and modify for your own holiday celebrations!
### Merry Christmas! 🎄✨