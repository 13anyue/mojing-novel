# 墨境 AI 视觉小说平台（手机 GitHub Pages 版）

这是一个**纯前端、多文件、无需服务器**的视觉小说 / AI 文游制作器骨架，适合小白直接放进 GitHub Pages。

## 1. 最简单的部署方式

1. 在 GitHub 新建仓库，例如 `mojing-novel`。
2. 把本项目里的 `index.html`、`css`、`js`、`assets`、`data` 全部上传。
3. GitHub 仓库打开：
   `Settings → Pages`
4. Source 选择 `Deploy from a branch`
5. Branch 选择 `main`，文件夹选择 `/ (root)`，保存。
6. 等待 GitHub Pages 构建完成。
7. 访问：
   `https://你的用户名.github.io/mojing-novel/`

## 2. 手机上传

GitHub 手机网页也能操作：
- 打开仓库
- `Add file → Upload files`
- 上传整个项目文件
- Commit changes
- 回到 Settings → Pages

如果手机端一次上传文件夹不方便，可以先解压，然后分别进入 `css`、`js`、`assets` 创建对应目录再上传。

## 3. 功能模块

- 首页 / 项目设置
- 视觉小说剧情编辑器
- 独立地图
- NPC 独立资料册
- 背景库
- BGM 音频库
- 独立 HTML 状态栏
- AI 记忆：关键词加权的“仿向量”召回原型
- 自定义提示词 / 预设
- 正则输出后处理
- OpenAI-Compatible API 设置

## 4. 重要：API Key

不要把 API Key 直接写进 JavaScript 再上传 GitHub。

本项目目前只将 Key 放进浏览器 localStorage，方便原型测试，但仍属于**前端直连方案**：
- Key 在用户自己的浏览器里可被看到；
- 一些 API 不允许浏览器跨域；
- 如果要正式公开给别人使用，应增加自己的后端代理 / Serverless Function。

## 5. 以后如何升级成真正的 AI 文游

推荐架构：

玩家输入
→ 当前场景
→ NPC 卡
→ 状态栏 JSON
→ 关键词 / 向量召回
→ 世界观知识库
→ 系统提示词
→ 模型 API
→ 正则清洗
→ JSON 状态解析
→ 保存记忆
→ 更新地图 / 好感 / 道具

### 真正的向量记忆

当前版本故意使用“关键词命中”做零依赖原型，方便 GitHub Pages 直接运行。

后续可以换成：
- Embedding API
- Supabase / pgvector
- Cloudflare Workers + Vectorize
- Pinecone 等向量数据库

## 6. 视觉小说知识树

### 剧本与叙事
起承转合、多线叙事、分支网、角色支线、HE/BE、多周目。

### 美术
角色立绘、表情差分、头像、场景 BG、关键 CG、UI、按钮动效。

### 玩法
好感度、线索、道具、倒计时抉择、解谜、属性成长、状态分支。

### 工程
本项目是 Web 版编辑器。若最终制作传统视觉小说，可学习：
- Ren'Py：最适合入门
- Godot：适合独立游戏与自定义系统
- Unity：适合更复杂的 2D/3D 项目

## 7. 小白修改原则

只改：
- 页面文字：`js/app.js`
- 外观：`css/style.css`
- 页面入口：`index.html`
- 初始数据：`js/storage.js`
- 图片 / 音乐：`assets/`

建议每次只改一个功能，然后 Commit；出问题可以在 GitHub 的历史记录里恢复。

## 8. 下一阶段建议

如果要做成类似商业级 AI 视觉小说平台，下一版应加入：
1. 拖拽地图 + 连线
2. NPC 图片真实上传到 IndexedDB
3. 场景 JSON 编辑器
4. AI API 实际调用
5. JSON Schema 强制状态输出
6. 真正 Embedding 召回
7. 导入 / 导出项目 ZIP
8. 存档系统
9. 多周目变量
10. 手机 PWA 离线缓存
