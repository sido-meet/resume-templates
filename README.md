# Resume Templates

简历模板收集（HTML / LaTeX / Markdown / 其他），纯模板参考，**不放个人简历内容**（姓名/邮箱/项目细节）。

## 模板索引

| 子模块 | 形式 | 编辑器 | 导出 | License | Upstream |
|---|---|---|---|---|---|
| `vibe-resume/` | HTML + CSS | 浏览器 / AI（HTML-first） | Chromium headless → PDF | MIT | [LiuMengxuan04/vibe-resume](https://github.com/LiuMengxuan04/vibe-resume) |
| `lapiscv/` | Markdown + CSS | Typora / VSCode / Obsidian | 内置 PDF 导出 | MIT | [BingyanStudio/LapisCV](https://github.com/BingyanStudio/LapisCV) |
| `awesome-cv/` | LaTeX | TeX 编辑器 / Overleaf | `latexmk` / Overleaf | **LPPL-1.3c（非 OSI）** ⚠️ | [posquit0/Awesome-CV](https://github.com/posquit0/Awesome-CV) |
| `sb2nov-resume/` | LaTeX | TeX 编辑器 / Overleaf | `latexmk` / Overleaf | MIT | [sb2nov/resume](https://github.com/sb2nov/resume) |

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
cd ../awesome-cv && git pull

# 添加新模板
git submodule add git@github.com:<owner>/<repo>.git <dirname>
```

## LPPL 风险说明（`awesome-cv/`）

`awesome-cv/` 是工业界引用率最高的 LaTeX 简历模板（27.8k ⭐），**但它用的是 LPPL-1.3c（LaTeX Project Public License），不是 OSI 认证的开源协议**。引入前请了解以下差异：

- **什么是 LPPL-1.3c**：LaTeX Project Public License，是 LaTeX 项目为 `.cls` / `.sty` 这类 LaTeX 内核包设计的 license。Debian / Fedora / OSI 等组织**不把它列入 "OSI-approved open source licenses"** 名单（属于 "free" 但 "non-OSI" 类别）。
- **关键条款**：如果你修改了 LPPL 下分发的文件（例如修改了 `awesome-cv.cls` 本身），**必须以 LPPL 协议分发修改后的版本**（所谓 "modified version must be renamed" + "carry the license"）。这与 MIT / BSD 的"随便改、闭源都行"完全不同。
- **对本仓库的影响**：
  - ✅ 把上游 repo **原样作为 submodule 引用**（不修改 `.cls`）—— 没问题。
  - ✅ 用它的 LaTeX 源**写自己的简历**（在 `sido-resume/` 别处 fork + 修改）—— 通常没问题，**前提是你不改 `awesome-cv.cls` 本体**，并且新文件单独署你自己的 license。
  - ❌ 如果你在本仓库或 `sido-meet/resume-templates` 里 **修改并重新分发 `awesome-cv.cls`** —— 必须以 LPPL-1.3c 再发布修改版，**不能再用 MIT 标识整个仓库**。
- **当前做法**：本仓库 `awesome-cv/` 子目录**只放上游原始代码**（frozen rule），所有衍生工作在 `sido-resume/` 项目里以单独的 fork / 副本进行，**不污染 submodule**。如未来需要在 `awesome-cv/` 内做修改，会单独在 README 标注并评估 license 兼容性。

参考：[LPPL 1.3c 全文（LICENCE 文件）](./awesome-cv/LICENCE)、[OSI 对 LPPL 的讨论](https://opensource.org/licenses/)（LPPL 不在 OSI 列表中）。