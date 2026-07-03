# Resume Templates

简历模板收集（HTML / LaTeX / Markdown / 其他），纯模板参考，**不放个人简历内容**（姓名/邮箱/项目细节）。

## 模板索引

| 子模块 | 形式 | 编辑器 | 导出 | License | Upstream |
|---|---|---|---|---|---|
| `vibe-resume/` | HTML + CSS | 浏览器 / AI（HTML-first） | Chromium headless → PDF | MIT | [LiuMengxuan04/vibe-resume](https://github.com/LiuMengxuan04/vibe-resume) |
| `lapiscv/` | Markdown + CSS | Typora / VSCode / Obsidian | 内置 PDF 导出 | MIT | [BingyanStudio/LapisCV](https://github.com/BingyanStudio/LapisCV) |

## 添加模板的约定

- 每个模板一个子目录（`vibe-resume/`、`lapiscv/`、下一个就是 `<name>/`）
- 子目录是 git submodule，URL 在 `.gitmodules`
- 子目录里放：模板源码 + 原作者的 README/LICENSE（**不要删**）
- 子目录里**不放**个人简历内容，只放模板
- 想要 fork / 改造某个模板，在 `sido-resume/vibe-resume/` 或新开目录做，不要污染 submodule

## 更新方式

```bash
# 拉取所有 submodule 最新
git submodule update --remote --merge

# 单个更新
cd vibe-resume && git pull
cd ../lapiscv && git pull

# 添加新模板
git submodule add git@github.com:<owner>/<repo>.git <dirname>
```