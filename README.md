<p align="center">
  <a href="https://www.bright.cn/">
    <img src="https://mintlify.s3.us-west-1.amazonaws.com/brightdata/logo/light.svg" width="300" alt="Bright Data 标志">
  </a>
</p>

# 房地产 AI 代理系统

基于 AI 的房地产公开数据抽取解决方案

<div align="center">
  <img src="https://img.shields.io/badge/python-3.9+-blue"/>
  <img src="https://img.shields.io/badge/License-MIT-blue"/>
</div>

---

## 🌟 概览

房地产 AI 代理系统是一个基于 Python 的解决方案，利用 AI 代理与 Bright Data 的 Model Context Protocol（MCP）服务器，从多数据源抽取、处理并输出结构化的房产数据。

- 自动化抽取来自 [Zillow](https://www.bright.cn/products/web-scraper/zillow)、[Realtor.com](https://www.bright.cn/products/web-scraper/realtor)、Redfin 等房地产网站的公开房产数据  
- 集成 Bright Data 代理，实现强大的反爬与地理解锁能力  
- 使用 Nebius Qwen 大模型进行自适应、通过模式校验的房产数据抽取  
- 以结构化 JSON 输出结果，便于分析与下游应用

---

## 目录

- ✨ 功能
- 🚀 快速开始
- 🔧 环境配置
- 💡 使用示例
- 📈 关键能力
- 🔒 安全最佳实践

---

## ✨ 功能

- 智能 AI 代理：使用 CrewAI 与大模型进行自适应抽取与房产细节解析。
- Bright Data 集成：无缝支持代理轮换与通过 MCP 服务器的验证码处理。
- 严格 JSON 模式：始终返回 snake_case、通过模式校验的 JSON。
- 即插即用：数分钟内搭建高级房产数据管道。
- 跨平台：Python 3.9；Bright Data MCP 服务器需要 Node.js。

---

## 🚀 快速开始

1. 克隆此仓库

   ~~~sh
   git clone https://github.com/brightdata-com/real-estate-ai-agents.git
   cd real-estate-ai-agents
   ~~~

---

## 🔧 环境配置

### 先决条件

- Python 3.9+
- Node.js + npm（用于 Bright Data MCP 服务器）
- 拥有带 API Token 的 Bright Data 账号
- Nebius AI API Key

### 虚拟环境

macOS/Linux
~~~sh
python3.9 -m venv venv
source venv/bin/activate
~~~

Windows
~~~sh
python3.9 -m venv venv
.\venv\Scripts\activate
~~~

### 安装依赖

~~~sh
pip install "crewai-tools[mcp]" crewai mcp python-dotenv pandas
~~~

### 配置环境变量

在项目目录创建 `.env` 文件，并加入以下内容：

~~~env
BRIGHT_DATA_API_TOKEN="your_api_token_here"
WEB_UNLOCKER_ZONE="your_web_unlocker_zone"
BROWSER_ZONE="your_browser_zone"
NEBIUS_API_KEY="your_nebius_api_key"
~~~

---

## 💡 使用示例

运行代理：

~~~sh
python real_estate_agents.py
~~~

如果成功，脚本会从房产列表页面抽取数据，并输出类似如下的结果：

~~~json
{
  "address": "123 Main Street, City, State 12345",
  "price": "$450,000",
  "bedrooms": 3,
  "bathrooms": 2,
  "square_feet": 1850,
  "lot_size": "0.25 acres",
  "year_built": 1995,
  "property_type": "Single Family Home",
  "listing_agent": "John Doe, ABC Realty",
  "days_on_market": 45,
  "mls_number": "MLS123456",
  "description": "Beautiful home with updated kitchen...",
  "image_urls": ["https://example.com/image1.jpg", "https://example.com/image2.jpg"],
  "neighborhood": "Downtown Historic District"
}
~~~

---

## 📈 关键能力

- 抽取地址、价格、卧室数、卫生间数、建筑面积、占地面积、建造年份、房产类型、挂牌经纪人、在市天数、MLS 编号、描述、图片 URL 与社区信息等。
- 严格的 JSON 模式校验：始终输出 snake_case 键名。
- 通过 Bright Data 的 MCP 技术栈处理代理轮换、验证码与反爬保护。
- 易于扩展更多数据字段与自定义数据源。

---

## 🔒 安全最佳实践

- 将所有 API Key 与凭据安全地存放于 `.env` 文件。
- 在使用前始终对抽取的数据进行校验与清洗。
- 遵守 robots.txt 与网站服务条款。

---

<p align="center">
  <a href="https://www.bright.cn/">
    <img src="https://mintlify.s3.us-west-1.amazonaws.com/brightdata/logo/light.svg" width="200" alt="Bright Data 标志">
  </a>
</p>
