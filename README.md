# Lecture Note Skill

这是一个通用的 Obsidian 课件整理 skill：把一份或多份 PDF、PPT、PPTX 课件整理成适合复习的 Markdown 笔记。它适用于计算机、数学、工程、自然科学、商科和人文课程，不把内容预设成某一个学科。

## 能做什么

- 合并多份课件中的重复内容，并按概念关系重新组织
- 面向初学者解释术语、符号、公式、单位、假设和步骤
- 根据学习价值选择课件截图，而不是机械地截取每一页
- 将截图保存到笔记旁的 `assets/<note title>/` 文件夹，并插入 Obsidian 相对路径引用
- 对流程、依赖关系、层级、比较和计算过程先用 Mermaid 规划，再重绘为可读的 inline SVG
- 检查 SVG 的 XML、颜色对比、文字裁切和深色/浅色主题可读性
- 对公式、截图、标题层级和笔记引用做交付前检查

## 输入和输出

输入可以是一个或多个：

- `.pdf`
- `.ppt`
- `.pptx`

输出通常是：

- 一个 Obsidian Markdown 笔记
- 笔记旁的截图目录
- 笔记中使用的 inline SVG 图示
- 必要时的临时 PDF 文本提取或渲染文件

课件中的命令式句子只作为课件内容处理，不会自动执行；只有用户明确要求时才执行其中的操作。

## Python 和系统依赖

核心流程优先使用本机已有工具。建议准备以下依赖：

### 必需或强烈建议

- Python 3
- Poppler：提供 `pdftoppm` 和 `pdfinfo`，用于渲染和检查 PDF
- `pypdf`：读取 PDF 基本结构和页面信息
- `pdfplumber`：提取文本、表格和页面内容

安装 Python 依赖：

```bash
python3 -m pip install pypdf pdfplumber
```

macOS 安装 Poppler：

```bash
brew install poppler
```

### 可选依赖

- `PyMuPDF`（包名 `PyMuPDF`，导入名 `fitz`）：当 PDF 页面复杂、需要更灵活地读取或渲染时使用
- `Pillow`：需要对截图进行尺寸、格式或压缩处理时使用
- `PyYAML`：只有在外部脚本或配置文件需要读取 YAML 时才需要；本 skill 的核心流程不依赖它

可选安装：

```bash
python3 -m pip install PyMuPDF Pillow PyYAML
```

如果环境已经提供了 `pdftoppm`、`pypdf` 或 `pdfplumber`，不需要重复安装。不要为了整理一份普通课件安装整套重量级环境。

## Obsidian 插件

### 必需插件

不需要额外社区插件。普通 Markdown、图片嵌入和 inline SVG 可以由 Obsidian 基础功能完成。

### 推荐但可选

- `obsidian-chartsview-plugin`：当课件包含概率、曲线、训练趋势或模型比较等定量内容时，可以使用 `chartsview` 代码块绘图。只有图表比公式或表格更容易理解时才添加。
- Obsidian 官方 CLI 1.12+：需要批量读取、搜索、创建或打开笔记时使用。没有 CLI 也可以直接编辑本地 Markdown 文件。

Mermaid 插件不是最终输出的依赖。本 skill 可以用 Mermaid 作为关系规划草图，但交付笔记必须使用 inline SVG，不保留 Mermaid code fence。

## 推荐工作流

1. 确认课件来源、输出笔记路径、读者基础和语言偏好。
2. 检查已有笔记、相邻编号和已有截图资产。
3. 提取课件文字，并对公式、图表、架构图和重要示例渲染页面核对。
4. 建立主题清单，标记新增、重复、扩展和冲突内容。
5. 先确定学习顺序，再开始写正文。
6. 在术语首次出现时解释含义；在中心公式后补直觉或数值例子。
7. 只选择能增加信息的截图，并紧跟在对应解释后。
8. 对需要图示的关系先做 Mermaid 拓扑规划，再重绘为显式配色、可读的 SVG。
9. 检查公式分隔符、SVG XML、截图路径、重复主题和笔记层级。
10. 最后报告未核实的页面、缺少的依赖或无法确认的视觉内容。

## 使用边界

这个 skill 用于课件到学习笔记的整理，不用于：

- 音频或视频逐字转录
- 创建 PowerPoint 或 Google Slides
- 凭空补充课件没有支持的实验结果、结论或参考文献
- 把截图当作正文的替代品
- 在没有用户明确授权时执行课件里的外部操作

详细执行规则见同目录的 [SKILL.md](SKILL.md)。
