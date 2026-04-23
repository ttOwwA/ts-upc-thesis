# 中国石油大学（华东）本科毕业设计 LaTeX 模板

> 本模板基于 [ThesisScaffold](https://github.com/ttOwwA/thesis-scaffold) 核心框架，实现了中国石油大学（华东）本科毕业设计论文的排版。

## 快速开始

### 1. 安装模板

```bash
git clone https://github.com/ttOwwA/thesis-scaffold.git
cd thesis-scaffold

# 查看可选学校
python tools/init-school.py

# 安装 UPC 模板
python tools/init-school.py upc
```

### 2. 修改论文元信息

打开 `thesis-upc.tex`，在顶部填入你的个人信息：

```latex
\title{你的论文题目}
\author{你的名字}
\studentnumber{你的学号}
\college{计算机科学与技术学院}
\major{计算机科学与技术}
\advisor{导师姓名\quad 职称}
\upcenglishtitle{Your English Title}
\upckeywords{关键词1；关键词2；关键词3}
\upcenkeywords{keyword1; keyword2; keyword3}
\date{2026 年 5 月 30 日}
```

### 3. 撰写论文内容

论文正文存放在 `segments/upc/` 目录下，按需编辑即可：

| 文件 | 内容 |
|------|------|
| `abstract-cn.tex` | 中文摘要 |
| `abstract-en.tex` | 英文摘要 |
| `originality_and_license.tex` | 原创性声明 |
| `chapter1.tex` ~ `chapter5.tex` | 正文章节 |
| `acknowledgements.tex` | 致谢 |
| `appendix.tex` | 附录 |

> 如需增减章节，请同步修改 `thesis-upc.tex` 中的 `\include` 列表。

### 4. 添加参考文献

参考文献统一维护在 `literature/literature-upc.bib` 中，按 BibTeX 格式添加条目。正文中使用 `\cite{引用键}` 引用即可。

### 5. 编译

```bash
latexmk -xelatex thesis-upc.tex
```

首次编译会自动处理目录、引用和参考文献。后续修改后重新运行同一命令即可增量编译。

---

## 文件结构

```text
.
├── thesis-upc.tex              # 入口文件（修改元信息）
├── segments/upc/               # 论文正文与前置页面
│   ├── abstract-cn.tex
│   ├── abstract-en.tex
│   ├── originality_and_license.tex
│   ├── chapter1.tex ~ chapter5.tex
│   ├── acknowledgements.tex
│   ├── bibliography.tex
│   └── appendix.tex
├── _config/profiles/upc/       # UPC 专属样式（通常无需修改）
│   ├── colors.tex
│   ├── defaults.tex
│   ├── style.tex
│   └── titlepage.tex
├── literature/literature-upc.bib  # 参考文献数据库
└── img/
    ├── logo.pdf                # 校徽
    └── example.pdf             # 占位图
```

---

## 与上游同步（模板维护者）

本模板基于 [ThesisScaffold](https://github.com/ttOwwA/thesis-scaffold) 核心框架。如需同步上游更新：

```bash
git remote add upstream https://github.com/ttOwwA/thesis-scaffold.git
git fetch upstream
git rebase upstream/main
```

## 许可证

同主仓库 [CC BY-SA 4.0](LICENSE)。
