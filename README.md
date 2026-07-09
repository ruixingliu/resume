# Resumes

多份 LaTeX 简历，push 后由 GitHub Actions 自动编译成 PDF 并提交回仓库。

## 规则

- 仓库根目录下的**每个 `.tex` 文件**都会被自动编译成**同名 `.pdf`**，始终保持最新
- 例如 `Ruixing Liu_Resume.tex` → `Ruixing Liu_Resume.pdf`
- 新增一份简历 = 新增一个 `.tex` 文件，无需改任何配置
- 重命名简历 = 重命名 `.tex` 文件（记得删掉旧 PDF）

## 用法

1. 编辑或新增 `.tex` 文件
2. commit 并 push 到 `main` 分支
3. Actions 自动编译，把最新 PDF 用 `[skip ci]` 提交回仓库根目录

## 下载 PDF

- 直接下载仓库根目录对应的 `.pdf` 文件（始终是最新版）
- 或到 [Actions](../../actions) 页面，打开最近一次运行，下载 `resumes` artifact
