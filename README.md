# 소소한 한국어 · 温馨韩语小窝

韩语学习单页应用：图片/文件 OCR 识别（浏览器本地引擎，离线可用）、语法智能分析（单词·助词·句型结构·语法点·训练题）、AI 对话机器人（可换头像/聊天背景）、中韩互译、荧光批注、页面中/英/日三语界面。

## 文件说明（全部平铺在同一层，无需子文件夹）

```
index.html                       入口页，自动跳转到学习页
korean-study.html                主页面，全部功能
tesseract.min.js                 OCR 引擎
worker.min.js                    OCR worker
tesseract-core-simd-lstm.wasm.js OCR 核心（SIMD）
tesseract-core-lstm.wasm.js      OCR 核心（兼容）
kor.traineddata.gz               韩语识别模型
eng.traineddata.gz               英语识别模型
```

页面会自动在当前目录或 `vendor/tesseract/` 下查找 OCR 引擎，两种布局都支持；都找不到时才回退网络 CDN。

## 部署到 EdgeOne Pages（导入 Git 仓库）

1. 把以上 8 个文件全部上传到 GitHub 仓库根目录
2. EdgeOne Pages → 新建项目 → 导入 Git 仓库 → 选择该仓库
3. 框架预设：静态站点 / 无；构建命令：留空；输出目录：`/`
4. 部署完成，用「域名管理」里的默认域名访问即可（根地址会自动跳转学习页）

## 本地预览

```bash
python3 -m http.server 8099
# http://localhost:8099/
```

## 隐私说明

- OCR 全在浏览器本地运行，图片不上传服务器
- AI 对话需要在页面 ⚙️ 中填入自己的大模型 API（OpenAI 兼容格式，如硅基流动）
- 头像、聊天背景、API Key 仅存于浏览器 localStorage
