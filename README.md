# InferenceProviderProfitCalculator

一个用于计算 LLM 推理服务成本和利润的在线工具。

## 🚀 快速发布指南

### 方式 1: GitHub Pages（推荐 - 最简单免费）

1. **创建 GitHub 仓库**
   - 登录 GitHub
   - 点击 "New repository"
   - 输入仓库名称（如：`llm-cost-calculator`）
   - 设置为 Public
   - 点击 "Create repository"

2. **上传文件**
   - 将 `index.html` 上传到仓库
   - 或者使用命令行：
   ```bash
   git clone https://github.com/你的用户名/llm-cost-calculator.git
   cd llm-cost-calculator
   # 将 index.html 复制到这个文件夹
   git add index.html
   git commit -m "Add LLM cost calculator"
   git push origin main
   ```

3. **启用 GitHub Pages**
   - 在仓库页面点击 "Settings"
   - 左侧菜单找到 "Pages"
   - Source 选择 "Deploy from a branch"
   - Branch 选择 "main"
   - 点击 "Save"

4. **访问网站**
   - 几分钟后，你的网站将在以下地址可用：
   - `https://你的用户名.github.io/llm-cost-calculator/`

## 📊 计算逻辑

基于以下核心公式：

```javascript
// 单个请求处理时间
const timePerRequest = (inputTokens / inputThroughput) + (outputTokens / outputThroughput);

// 考虑利用率的有效请求数
const effectiveRequestsPerHour = (3600 / timePerRequest) * (utilizationRate / 100);

// 混合推理成本
const computeCostPerMillion = (gpuRentalCost / totalTokensPerHour) * 1000000;

// 毛利率计算
const grossMargin = ((totalRevenuePerHour - gpuRentalCost) / totalRevenuePerHour) * 100;
```

## 🎯 使用场景

- LLM 服务提供商成本分析
- GPU 租赁成本效益评估
- 定价策略制定
- 业务模式验证

## 📈 参数说明

| 参数 | 描述 | 单位 |
|------|------|------|
| GPU 租赁成本 | 每小时 GPU 租赁费用 | USD/hr |
| 有效利用率 | GPU 实际使用率 | % |
| 输入/输出 Tokens | 典型请求的 Token 数量 | count |
| 输入/输出吞吐 | GPU 处理速度 | Tokens/s/GPU |
| Token 定价 | 每百万 Token 的售价 | USD/M Tokens |

## 🤝 贡献

欢迎提交 Issues 和 Pull Requests 来改进这个工具。

## �� 许可证

MIT License 