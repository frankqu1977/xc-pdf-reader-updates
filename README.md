# XC PDF Reader

> 面向 Windows 的轻量 PDF / OFD / XPS / PostScript / Markdown 阅读、标注与文档处理工具。
>
> 当前版本：**V1.2.399**（2026-11-27）

XC PDF Reader 把阅读、检索、批注、表单、OCR、翻译和打印放进同一个窗口，减少在多个软件之间来回切换。程序基于 WPF / .NET Framework 4.8.1，安装包不额外分发运行时。

---

## 下载

| 类型 | 文件 | 适用场景 |
|---|---|---|
| 安装版（推荐） | `XC_PDF_Reader_1.2.399_Setup.exe` | 普通用户，自动创建开始菜单项与卸载入口 |
| 便携版 | `XC_PDF_Reader_1.2.399_Portable_Net481.zip` | 解压即用，不写安装目录，适合 U 盘或受控环境 |
| 在线更新包 | `XC_PDF_Reader_1.2.399.zip` | 阅读器内置“检查更新”使用，也可手动覆盖便携目录 |

- 最新发布页：<https://github.com/frankqu1977/xc-pdf-reader-updates/releases/latest>
- 在线更新清单：<https://frankqu1977.github.io/xc-pdf-reader-updates/update.json>

---

## 主要功能

### 阅读与浏览

- 多标签打开多份文档，退出时可批量保存；可恢复上次打开的文件与浏览位置。
- 单页 / 双页对开、连续滚动、顺逆时针旋转、护眼暖色、夜间反色。
- 预设缩放 8.33%–6400%，支持实际大小、适应宽度、符合页面、符合可见区域。
- 页面虚拟化渲染，超大页数文档按视口按需加载。
- 对比 / 分屏：左右各开一份文档，同步缩放与按页比例滚动。
- 文档内链接可点击跳转，外部 URL 可打开浏览器。

### 查找与文本

- `Ctrl+F` 查找栏：上一个 / 下一个、命中计数、页面高亮、全词匹配、区分大小写、包含注释。
- 高级搜索按页分组列出结果，支持取消与结果上限，搜索结束自动归还页句柄。
- 跨页、跨文档选择与复制；多段落正向 / 反向拖选按连续文本流合并。
- 悬停取词翻译、划词翻译、全文 AI 翻译与生词本。

### 标注与页面

- 高亮、下划线、删除线、波浪线、便签、矩形、椭圆、直线、箭头、手绘。
- 文本框、文字印章、图片印章、内置印章、Adobe 风格调色板与不透明度。
- 书签新建 / 子书签 / 重命名 / 删除 / 排序，写回 PDF 增量更新。
- 缩略图侧栏、注释列表、按作者 / 类型 / 时间筛选。
- 页面旋转、删除、导出为 PDF / PNG / JPG，导出时重编页码。
- 水印、页眉页脚、文档属性编辑、文件去保护。

### OCR、表单与打印

- PaddleOCR PP-OCRv5 中英文识别，输出保留原图的可搜索 PDF，也可导出纯文本。
- AcroForm 表单填写与保存。
- 打印范围、份数、方向、色彩模式、边距、质量与小册子排版。
- 使用 Microsoft Print to PDF 打印时保留文本层，输出 PDF 可选中、复制和搜索。
- 打印设置持久化，下次打开自动恢复。

### 外观与扩展

- 跟随系统 / 深色 / 浅色主题，主题色与动效可调。
- 常规、主题、动效、页面显示、页面渲染、性能、标注样式、文件关联、取词翻译、OCR、AI 大模型等偏好设置。
- 内存预算、渲染线程数、双缓冲、性能 HUD 与诊断信息。
- OpenAI 兼容云端接口，以及本地 Ollama / LM Studio；内置多组免费云端模型预设。

---

## 支持格式

| 格式 | 扩展名 | 说明 |
|---|---|---|
| PDF | `.pdf` | 原生支持，含加密文档、表单、批注、书签 |
| OFD | `.ofd` | 原生支持，含版式文档与签章显示 |
| XPS / OXPS | `.xps` `.oxps` | 原生支持 |
| PostScript | `.ps` `.eps` | 需本机安装 Ghostscript；缺失时给出指引 |
| Markdown | `.md` `.markdown` | 阅读与转换为 PDF |

---

## 系统要求

- Windows 10 21H2+ / Windows 11，64 位（x64）。
- .NET Framework 4.8.1（Windows 11 内置；Windows 10 21H2+ 一般为内置）。
- OCR 模型首次使用时联网下载（约 15 MB），之后可离线识别。
- AI 翻译需自行配置接口地址、模型与密钥。

---

## 安装与升级

### 安装版

1. 下载 `XC_PDF_Reader_1.2.399_Setup.exe`。
2. 运行安装向导，按需勾选桌面快捷方式。
3. 安装前会检测 .NET Framework 4.8.1；已有实例运行时，安装程序会提示关闭。

### 便携版

1. 下载 `XC_PDF_Reader_1.2.399_Portable_Net481.zip` 并解压到固定目录。
2. 运行 `XC PDF Reader.exe`。
3. 不要直接从压缩包的临时视图运行，否则在线更新只会写入临时目录。

### 在线更新

阅读器读取 `update.json` 比较版本，下载更新包后退出、备份、覆盖并重启。用户设置与最近文件保存在 `%APPDATA%\PdfReader\`，卸载默认不删除。

---

## 从源码构建

### 环境

- Visual Studio 2022 / 2026（含“.NET 桌面开发”和 C++ 桌面组件）
- .NET Framework 4.8.1 Developer Pack
- Inno Setup 6（仅生成安装包时需要）

### 编译

```powershell
$env:DOTNET_ROOT = 'C:\Program Files\dotnet'
$env:Path = 'C:\Program Files\dotnet;C:\Windows\System32;' + $env:Path

& 'C:\Program Files\Microsoft Visual Studio\18\Community\MSBuild\Current\Bin\MSBuild.exe' `
  .\xcPDFReader.csproj /t:Rebuild /p:Configuration=Release /m /v:m /nologo
```

产物位于 `bin\Release\net481\XC PDF Reader.exe`。发布前要求 **0 error / 0 warning**。

### 生成三套发布包

```powershell
# 1. 便携目录 + 便携 zip
pwsh -File .\Installer\PublishNet481.ps1 -Version 1.2.399

# 2. Inno Setup 安装包
& 'C:\Program Files (x86)\Inno Setup 6\ISCC.exe' .\Installer\XC_PDF_Reader.iss

# 3. 在线更新 zip + update.json
pwsh -File .\Tools\BuildUpdatePackage.ps1
```

发布产物分别位于：

- `bin\Publish\Net481\XC_PDF_Reader_1.2.399_Portable_Net481.zip`
- `bin\Publish\03_Setup\XC_PDF_Reader_1.2.399_Setup.exe`
- `Updates\XC_PDF_Reader_1.2.399.zip`
- `Updates\update.json`

---

## 目录结构

```text
XC PDF Reader/
├─ XC_PDFReader_Net481/          # WPF / .NET Framework 4.8.1 工程
│  ├─ Controls/                  # 页面视图、工具栏、缩略图等控件
│  ├─ Pdf/                       # pdfium 封装、页面与文本模型
│  ├─ Translation/               # 取词、划词、全文翻译
│  ├─ Diagnostics/               # 性能 HUD、压力探针、诊断信息
│  ├─ Docs/                      # 使用说明、更新日志、测试报告
│  ├─ Installer/                 # Inno Setup 脚本与便携发布脚本
│  ├─ Tools/                     # 更新包构建与发布脚本
│  ├─ Updates/                   # 在线更新清单与更新包
│  └─ bin/                       # Release 与发布产物
└─ README.md
```

---

## 文档

- 使用说明：`XC_PDFReader_Net481/Docs/使用说明.md`
- 更新日志：`XC_PDFReader_Net481/Docs/更新日志.md`
- Bug 修复记录：`XC_PDFReader_Net481/Docs/Bug修复记录.md`
- 1.2.398 代码审查与压力测试报告：`XC_PDFReader_Net481/Docs/代码审查与压力测试报告_1.2.398.md`

---

## 已知说明

- 首次冷启动可能受 Windows Defender 扫描、文件索引和磁盘缓存影响；热启动与多文档标签建立已做分阶段优化。
- 超大页数文档在高缩放下仍有较高的渲染峰值；滚动后会按视口和 LRU 规则释放。
- PostScript 支持依赖 Ghostscript，安装包不内置。
- OCR 模型不包含在安装包内，首次使用需联网下载。
- AI 翻译不内置密钥，需要用户自行配置模型服务。

---

## 反馈

- 发布与更新仓库：<https://github.com/frankqu1977/xc-pdf-reader-updates>
- 问题反馈请附：版本号、Windows 版本、文档格式与页数、复现步骤、是否可稳定复现。
- 涉及隐私文档时，请先删除正文或替换为可公开的样本。
