# Resumes

多份 LaTeX 简历，push 后由 GitHub Actions 自动编译成 PDF 并提交回仓库。

## 规则

- 源文件（`.tex`）都放在 **`src/` 目录**，保持根目录整洁
- `src/` 下的**每个 `.tex` 文件**都会被自动编译成**同名 `.pdf`**，输出到**仓库根目录**，始终保持最新
- 例如 `src/Ruixing Liu_Resume.tex` → 根目录 `Ruixing Liu_Resume.pdf`
- 新增一份简历 = 在 `src/` 新增一个 `.tex` 文件，无需改任何配置
- 重命名简历 = 重命名 `src/` 里的 `.tex` 文件（记得删掉根目录的旧 PDF）

## 用法

1. 在 `src/` 里编辑或新增 `.tex` 文件
2. commit 并 push 到 `main` 分支
3. Actions 自动编译，把最新 PDF 用 `[skip ci]` 提交回仓库根目录

## 下载 PDF

- 直接下载仓库根目录对应的 `.pdf` 文件（始终是最新版）
- 或到 [Actions](../../actions) 页面，打开最近一次运行，下载 `resumes` artifact
