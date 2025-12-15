# ScholarPlot - AI 科研学术图表生成器

## 🎯 产品介绍

**ScholarPlot** 是一款专为科研人员打造的 AI 学术图表生成工具。无论是论文中的数据可视化图表、神经网络架构图、实验流程图，还是复杂的机制原理图，ScholarPlot 都能在几秒钟内为您生成**符合顶级 SCI 期刊发表标准**的专业图表。

### 🔬 为什么选择 ScholarPlot？

| 痛点 | ScholarPlot 解决方案 |
|------|---------------------|
| 使用 Python/R 绑图太繁琐 | **自然语言描述**，AI 自动生成代码和图表 |
| 图表不符合期刊规范 | 内置 **Nature/Science/IEEE 等期刊风格模板** |
| 架构图、流程图难以绘制 | 支持**机制图、架构图、流程图**等多种类型 |
| 反复修改浪费时间 | **实时编辑**，一键调整样式和数据 |
| 图表分辨率不够 | 输出 **300dpi 高清图**，支持 SVG 矢量格式 |

### 🎨 支持的图表类型

- **📈 数据图表**：折线图、柱状图、散点图、箱线图、热力图、小提琴图、雷达图...
- **🧬 科研机制图**：分子通路图、信号机制图、反应原理图...
- **🏗️ 架构示意图**：神经网络架构、系统框架图、模型结构图...
- **📋 流程图**：实验流程、算法流程、方法学示意图...
- **📊 对比分析图**：多组对比、韦恩图、桑基图...

🌐 官方网站：https://figure.thirdme.com

---

## 🔌 MCP 集成

ScholarPlot 提供 MCP (Model Context Protocol) 接口，让您可以在 Claude Desktop、Cursor、Dify、n8n 等 AI 工具中**直接调用 ScholarPlot 生成图表**，无需离开工作环境。

🌐 MCP 文档：https://figure.thirdme.com/mcp

---

## 🚀 快速开始

### 步骤一：获取 API Key

1. 访问 [MCP API 页面](https://figure.thirdme.com/mcp)
2. 输入您的邮箱地址
3. 点击「生成 API Key」按钮
4. 复制生成的 API Key（请妥善保管，它与您的订阅和使用配额关联）

> ⚠️ **重要提示**：请妥善保管您的 API Key。生成新的 Key 将会替换现有的 Key。如果您重新生成了 Key，请务必更新您的 MCP 配置。

### 步骤二：配置 Claude Desktop

将以下配置添加到您的 Claude Desktop 配置文件 `mcp.json` 中：

**配置文件位置：**
- **macOS**: `~/Library/Application Support/Claude/claude_desktop_config.json`
- **Windows**: `%APPDATA%\Claude\claude_desktop_config.json`

**配置内容：**

```json
{
  "mcpServers": {
    "scholarplot-sci-figure": {
      "url": "https://figure.thirdme.com/api/mcp-sse?key=YOUR_API_KEY"
    }
  }
}
```

将 `YOUR_API_KEY` 替换为您在步骤一中获取的实际 API Key。

### 步骤三：在 Claude 中使用

配置完成后，重启 Claude Desktop，即可直接让 Claude 生成科研学术图表：

**示例对话：**

```
请帮我生成一个展示深度学习模型训练过程中 Loss 曲线的折线图，包含 Training Loss 和 Validation Loss 两条曲线，X 轴为 Epoch (1-100)，Y 轴为 Loss 值。
```

```
请绘制一个神经网络架构图，包含输入层、3个隐藏层（分别有 128、64、32 个神经元）和输出层。
```

Claude 将自动调用 MCP API 处理请求，并返回符合 SCI 期刊标准的专业学术图表。

---

## ✨ 核心功能

### 🤖 AI 驱动的图表生成

| 功能 | 描述 |
|------|------|
| **智能解析** | AI 自动理解您的图表需求，智能提取关键信息 |
| **SCI 标准** | 生成的图表严格符合顶级 SCI 期刊发表标准 |
| **多类型支持** | 支持数据图表、机制图、流程图、原理图、结构示意图等 |
| **高质量输出** | 矢量级清晰度，纯白背景，专业配色方案 |

### 📊 支持的图表类型

- **数据可视化图表**：折线图、柱状图、散点图、箱线图、热力图、雷达图等
- **科研机制图**：分子机制图、信号通路图、反应流程图
- **架构示意图**：神经网络架构图、系统框架图、模型结构图
- **流程图**：实验流程图、算法流程图、方法学流程图
- **对比分析图**：对比柱状图、韦恩图、桑基图

### 🔧 快速集成

| 特性 | 说明 |
|------|------|
| **配置简单** | 仅需添加配置文件和 API Key |
| **广泛兼容** | 支持所有 MCP 兼容工具 |
| **即插即用** | 配置完成后立即可用，无需额外开发 |

### 🔒 安全可靠

| 特性 | 说明 |
|------|------|
| **UUID 认证** | 基于 UUID 的身份认证机制 |
| **频率限制** | 防止滥用，确保服务稳定性 |
| **用量追踪** | 实时追踪 API 使用量和配额 |

### 📊 共享订阅

| 特性 | 说明 |
|------|------|
| **统一配额** | API 与网页版共享同一订阅配额 |
| **灵活使用** | 可在多个平台和工具中使用同一订阅服务 |

---

## 📖 API 参考

### Endpoint

```
GET/POST https://figure.thirdme.com/api/mcp-sse?key=YOUR_API_KEY
```

### 可用工具

#### `generate_sci_figure`

根据描述生成符合 SCI 期刊标准的科研学术图表。

**输入参数：**

| 参数名 | 类型 | 必填 | 描述 |
|--------|------|------|------|
| `description` | string | ✅ | 图表描述，包含数据、类型、样式要求等 |
| `figureType` | string | ❌ | 图表类型：`line_chart`, `bar_chart`, `scatter`, `heatmap`, `flowchart`, `architecture`, `mechanism` 等 |
| `style` | string | ❌ | 风格偏好：`nature`, `science`, `ieee`, `default` |
| `dataValues` | object | ❌ | 精确数据值（用于数据图表） |

**输出：**

返回包含以下内容的 JSON 对象：

```json
{
  "figureUrl": "https://figure.thirdme.com/figures/xxx.png",
  "figureCode": "// 可编辑的图表代码",
  "metadata": {
    "type": "line_chart",
    "style": "nature",
    "resolution": "300dpi",
    "format": "PNG/SVG"
  }
}
```

#### `edit_figure`

编辑已生成的图表，调整样式、数据或布局。

**输入参数：**

| 参数名 | 类型 | 必填 | 描述 |
|--------|------|------|------|
| `figureId` | string | ✅ | 需要编辑的图表 ID |
| `editInstructions` | string | ✅ | 编辑指令，如"将柱状图颜色改为蓝色" |

**输出：**

返回更新后的图表 URL 和代码。

### 错误码

| 错误码 | 描述 |
|--------|------|
| -32001 | 用户未找到 |
| -32003 | 需要订阅或使用配额已用完 |
| -32004 | 图表生成失败 |
| -32005 | 不支持的图表类型 |
| -32006 | 数据格式错误 |

---

## 🛠️ 支持的平台

| 平台 | 状态 |
|------|------|
| Claude Desktop | ✅ 已支持 |
| OpenAI (MCP 兼容) | ✅ 已支持 |
| Cursor | ✅ 已支持 |
| Dify | ✅ 已支持 |
| n8n | ✅ 已支持 |
| 其他 MCP 兼容工具 | ✅ 已支持 |

---

## 💡 使用案例

### 案例一：生成论文 Loss 曲线图

在 Claude Desktop 中，您可以这样请求：

```
请帮我生成一个训练过程的 Loss 曲线图：
- X 轴：Epoch (1-50)
- Y 轴：Loss
- 包含 Training Loss（从 2.5 下降到 0.1）和 Validation Loss（从 2.8 下降到 0.15）
- 风格：Nature 期刊标准
```

### 案例二：绘制神经网络架构图

```
请绘制一个 Transformer 架构图，包含：
- 输入嵌入层
- 6 层 Encoder（包含 Multi-Head Attention 和 Feed Forward）
- 6 层 Decoder
- 输出层
- 使用 NeurIPS 风格，扁平化设计，无渐变
```

### 案例三：生成实验流程图

```
请生成一个药物筛选实验流程图：
1. 化合物库筛选 (10,000 compounds)
2. 高通量初筛 (Hit rate: 2%)
3. 二次验证 (200 compounds)
4. 活性测定 (50 compounds)
5. 毒性评估 (20 compounds)
6. 先导化合物 (5 compounds)

使用箭头连接各步骤，标注数量变化。
```

### 案例四：批量生成论文图表

```
我正在撰写一篇关于图像分类的论文，需要以下图表：
1. 模型架构图（CNN + Attention）
2. 训练曲线图（Accuracy 和 Loss）
3. 混淆矩阵热力图
4. 不同模型性能对比柱状图

请依次帮我生成这些图表，保持统一的视觉风格。
```

### 案例五：集成到自动化工作流

在 n8n 或 Dify 中，您可以将图表生成集成到自动化工作流中，实现批量处理和自动化操作。例如：

- 自动从实验数据生成标准化图表
- 批量将数据表格转换为可视化图表
- 论文写作辅助工作流中的图表自动生成

---

## 📝 注意事项

| 事项 | 说明 |
|------|------|
| **API Key 安全** | 请妥善保管您的 API Key，不要分享给他人或提交到公开仓库 |
| **配额限制** | API 使用受订阅配额限制，请合理使用 |
| **数据准确性** | 提供精确的数据值以获得最准确的图表输出 |
| **图表类型** | 明确指定图表类型可获得更精准的结果 |
| **处理时间** | 简单图表约 5-10 秒，复杂图表可能需要 30 秒以上 |
| **数据安全** | 处理后的数据将在 24 小时后自动从服务器删除 |

---

## ❓ 常见问题

### Q: 在哪里可以获取 API Key？

A: 访问 https://figure.thirdme.com/mcp，输入邮箱地址即可生成 API Key。

### Q: 如何测试 API Key 是否有效？

A: 在 MCP API 页面生成 Key 后，可以使用页面上的「测试 API Key」功能验证 Key 的有效性。

### Q: API 使用是否收费？

A: API 使用与网页版共享同一订阅配额。具体定价请参考 [定价页面](https://figure.thirdme.com/pricing)。

### Q: 支持哪些期刊风格？

A: 目前支持 Nature、Science、IEEE、Cell 等主流 SCI 期刊风格，并持续增加中。

### Q: 图表可以导出什么格式？

A: 支持 PNG（300dpi 高清）、SVG（矢量格式）、PDF 等多种格式导出。

### Q: 如何确保数据准确性？

A: 
- 使用 `dataValues` 参数提供精确数值
- 在描述中明确标注关键数据点
- 生成后仔细核对，如有问题可使用 `edit_figure` 工具修正

### Q: 生成的图表版权归谁？

A: 生成的图表版权归用户所有，可自由用于学术论文发表。

### Q: 如何处理订阅和配额问题？

A: API 与网页版使用同一订阅服务。您可以在网页版管理订阅和查看使用情况。

---

## 📧 支持与反馈

如果您在使用过程中遇到任何问题或有任何建议，请通过以下方式联系我们：

| 渠道 | 联系方式 |
|------|----------|
| 📧 邮箱 | support@thirdme.com |
| 🌐 官网 | https://figure.thirdme.com |
| 📄 API 文档 | https://figure.thirdme.com/mcp |
| 💬 GitHub Issues | [提交 Issue](https://github.com/peizhou/mcp-sci-figure/issues) |

---

## 📄 许可证

本服务遵循 ScholarPlot 的[服务条款](https://figure.thirdme.com/terms)和[隐私政策](https://figure.thirdme.com/privacy)。

---

## 🎉 开始使用 MCP API，让 AI 为您的科研论文创建专业级学术图表！

[![ScholarPlot](https://img.shields.io/badge/ScholarPlot-AI%20Scientific%20Figures-blue)](https://figure.thirdme.com)
[![MCP Compatible](https://img.shields.io/badge/MCP-Compatible-green)](https://figure.thirdme.com/mcp)
[![SCI Standard](https://img.shields.io/badge/SCI-Journal%20Standard-orange)](https://figure.thirdme.com)

---

## 🏷️ 相关标签

`mcp` `scientific-figures` `sci-charts` `academic-visualization` `ai-figure-generator` `mcpserver` `claude-mcp` `cursor-mcp` `research-tools` `publication-ready` `nature-style` `neurips-style`
