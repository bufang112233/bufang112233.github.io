# 方雅庭 · 个人简历网页

## 项目概述
- 方雅庭的个人简历单页，托管在 GitHub Pages：`bufang112233.github.io`
- 单文件项目：`index.html`（含 HTML + CSS + JS）
- 仓库地址：`https://github.com/bufang112233/bufang112233.github.io`

## 用户身份
- 方雅庭，五邑大学电子信息工程（集成电路方向）2025 届学生
- 技能方向：C 语言、STM32、PCB 设计、嵌入式系统

## 技术架构

### 设计风格
- 简洁单栏卡片式布局，最大宽度 720px
- CSS 变量控制主题色（`--accent: #2563eb`）
- 无外部依赖，纯原生 HTML/CSS/JS

### 交互功能
1. **双击编辑** — 双击 `[data-editable]` 元素即可修改文字
2. **加号按钮** — 动态添加新的经历卡片 / 技能标签
3. **悬停删除** — 卡片和技能标签悬停时显示红色删除按钮
4. **导出 HTML** — 右下角按钮，生成清理后的完整 HTML 代码
5. **localStorage 自动保存** — 编辑内容自动存入浏览器本地存储，下次打开自动恢复
6. **重置按钮** — 清除 localStorage 数据，恢复到原始 HTML 内容

### 代码结构
```
index.html
├── <style>   — 全部 CSS（CSS 变量、布局、卡片、响应式、打印）
├── <body>
│   ├── .edit-toast      — 编辑提示条
│   ├── #btnExport       — 导出按钮
│   ├── #btnReset        — 重置按钮
│   ├── .modal-overlay   — 导出弹窗
│   └── .resume          — 简历主体
│       ├── .header      — 头像、姓名、简介、社交链接
│       ├── #sec-education — 教育背景（卡片列表）
│       ├── #sec-project   — 项目经历（卡片列表）
│       ├── #sec-skills    — 技能栈（标签组）
│       ├── #sec-contact   — 联系方式
│       └── .footer        — 页脚
└── <script>  — 全部 JavaScript（编辑、增删、导出、localStorage）
```

### 关键 JS 函数
| 函数 | 作用 |
|------|------|
| `startEdit(el)` | 进入编辑模式 |
| `stopAllEdits()` | 退出所有编辑 |
| `addCard(sectionId)` | 在指定 section 添加新卡片 |
| `addSkill()` | 添加新技能标签 |
| `saveToLocal()` | 序列化 `.resume` 的 innerHTML 到 localStorage（300ms 防抖）|
| `loadFromLocal()` | 页面加载时从 localStorage 恢复内容 |
| `clearLocalData()` | 清除 localStorage 并刷新页面 |

### localStorage 键名
- `resume-autosave-v2` — 存储序列化的简历 HTML 和保存时间戳

## 常见任务

### 修改样式
- 主题色改为 `--accent` CSS 变量
- 所有 CSS 在 `<style>` 标签内

### 修改内容
- 直接在网页上双击编辑即可（自动保存到 localStorage）
- 如需永久更新源代码，编辑后用「导出 HTML」按钮复制代码替换 `index.html`

### 部署
- `git add index.html && git commit -m "..." && git push origin main`
- GitHub Pages 自动部署，1-2 分钟后在 `bufang112233.github.io` 生效

## Git 远程
- origin: `https://github.com/bufang112233/bufang112233.github.io.git`
- 分支: `main`
