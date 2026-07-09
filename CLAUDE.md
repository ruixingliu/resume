# Resume 仓库 — LaTeX 简历自动编译 (Claude 使用说明)

- GitHub: https://github.com/ruixingliu/resume (public)
- 目录结构: **源文件 `.tex` 都放在 `src/`**, 编译出的 **`.pdf` 输出到仓库根目录**
  (根目录保持整洁, PDF 直链不变)。
- 机制: push 到 main 后, GitHub Actions 自动把 **`src/` 里每个 `.tex`** 编译成
  **同名 `.pdf`** 输出到根目录, 并用 `[skip ci]` commit 回仓库, 约 2-3 分钟完成。
- 本仓库是**纯云端项目**, 不依赖任何特定电脑。在任何机器上 clone 即可工作,
  只需要 git 和已登录的 GitHub CLI (`gh`)。改完 push 后本地副本可以删除。

## 铁律
- 根目录的 PDF 由 CI 生成和提交, **永远不要手动 commit 这些 PDF**。
- 新增一份简历 = 在 `src/` 新增一个 `.tex`, 零配置; 重命名 = 重命名 `src/` 里的 `.tex` 并删掉根目录旧 PDF。
- 文件名之间不能只有大小写之差 (Windows/macOS 文件系统不区分大小写)。
- 不编造任何经历、数字、日期; 只用用户提供的内容。每份简历保持一页。

## 改简历的标准流程 (每次照做)
1. `gh repo clone ruixingliu/resume` (本地已有副本则 `git pull`)
2. 修改 `src/` 里的 `.tex`
3. 有本地 TeX 环境时建议先验证:
   `pdflatex -interaction=nonstopmode -halt-on-error -output-directory=build "src/<文件名>.tex"`
   确认 exit 0 且输出 1 page; 没有本地 TeX 就跳过, 交给 CI 验证
4. `git add` / `git commit` / `git push`
5. 确认云端编译成功:
   `gh run watch $(gh run list --limit 1 --json databaseId --jq '.[0].databaseId') --exit-status`
   若失败, 读日志修复 `.tex` 再 push
6. 把对应 PDF 直链发给用户

## PDF 直链 (永远指向最新版)
- https://github.com/ruixingliu/resume/raw/main/Ruixing%20Liu_Resume.pdf
- https://github.com/ruixingliu/resume/raw/main/Ruixing%20Liu_Resume_2.pdf
- 规律: `https://github.com/ruixingliu/resume/raw/main/<文件名>.pdf` (空格写成 %20)
