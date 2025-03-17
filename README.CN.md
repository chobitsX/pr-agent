<div align="center">

<div align="center">


<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://www.qodo.ai/wp-content/uploads/2025/02/PR-Agent-Purple-2.png">
  <source media="(prefers-color-scheme: light)" srcset="https://www.qodo.ai/wp-content/uploads/2025/02/PR-Agent-Purple-2.png">
  <img src="https://codium.ai/images/pr_agent/logo-light.png" alt="logo" width="330">

</picture>
<br/>

 [安装指南](https://qodo-merge-docs.qodo.ai/installation/) | 
[使用指南](https://qodo-merge-docs.qodo.ai/usage-guide/) | 
[工具指南](https://qodo-merge-docs.qodo.ai/tools/) | 
[Qodo Merge](https://qodo-merge-docs.qodo.ai/overview/pr_agent_pro/) 💎

PR-Agent 旨在通过提供 AI 反馈和建议，帮助高效审查和处理拉取请求（Pull Request）
</div>

[![Static Badge](https://img.shields.io/badge/Chrome-扩展-violet)](https://chromewebstore.google.com/detail/qodo-merge-ai-powered-cod/ephlnjeghhogofkifjloamocljapahnl)
[![Static Badge](https://img.shields.io/badge/专业版-应用-blue)](https://github.com/apps/qodo-merge-pro/)
[![Static Badge](https://img.shields.io/badge/开源版-应用-red)](https://github.com/apps/qodo-merge-pro-for-open-source/)
[![Discord](https://badgen.net/badge/icon/discord?icon=discord&label&color=purple)](https://discord.com/channels/1057273017547378788/1126104260430528613)
<a href="https://github.com/Codium-ai/pr-agent/commits/main">
<img alt="GitHub" src="https://img.shields.io/github/last-commit/Codium-ai/pr-agent/main?style=for-the-badge" height="20">
</a>
</div>

## 目录

- [新闻与更新](#新闻与更新)
- [概述](#概述)
- [示例结果](#示例结果)
- [立即尝试](#立即尝试)
- [Qodo Merge](https://qodo-merge-docs.qodo.ai/overview/pr_agent_pro/)
- [工作原理](#工作原理)
- [为什么使用 PR-Agent？](#为什么使用-pr-agent)

## 新闻与更新

### 2025年2月28日
新版本 v0.27 已发布。查看发布说明 [点击这里](https://github.com/qodo-ai/pr-agent/releases/tag/v0.27)。

### 2025年2月27日
- 将所有工具的默认模型更新为 `o3-mini`。您仍然可以通过在配置文件中设置 `model` 参数，将 `gpt-4o` 作为默认模型使用。
- Azure DevOps 的重要更新和错误修复，详见 [这里](https://github.com/qodo-ai/pr-agent/pull/1583)
- 添加了对调整 PR-Agent 工具 [响应语言](https://qodo-merge-docs.qodo.ai/usage-guide/additional_configurations/#language-settings) 的支持。

### 2025年2月6日
`/improve` 工具的新设计：

<kbd><img src="https://github.com/user-attachments/assets/26506430-550e-469a-adaa-af0a09b70c6d" width="512"></kbd>

### 2025年1月25日

开源 GitHub 组织已更新：
`https://github.com/codium-ai/pr-agent` →
`https://github.com/qodo-ai/pr-agent`

Docker 应该会自动重定向到新位置。
但是，如果您遇到任何问题，请将 GitHub action docker 镜像从
`uses: Codium-ai/pr-agent@main`
更新为
`uses: qodo-ai/pr-agent@main`

### 2025年1月2日

新工具 [/Implement](https://qodo-merge-docs.qodo.ai/tools/implement/)（💎），可将人工代码审查讨论和反馈转换为可直接提交的代码更改。

<kbd><img src="https://www.qodo.ai/images/pr_agent/implement1.png?v=2" width="512"></kbd>

### 2024年12月30日

根据社区反馈，我们已解决了开源 PR-Agent 项目中发现的两个漏洞。[修复](https://github.com/qodo-ai/pr-agent/pull/1425) 现已包含在今天发布的新版本 (v0.26) 中。

## 概述
<div style="text-align:left;">

各平台支持的命令：

|       |                                                                                                         | GitHub             | GitLab             | Bitbucket | Azure DevOps |
|-------|---------------------------------------------------------------------------------------------------------|:--------------------:|:--------------------:|:---------:|:------------:|
| 工具 | [Review](https://qodo-merge-docs.qodo.ai/tools/review/)                                                                                                  | ✅ | ✅ |     ✅     |      ✅       |
|       | [Describe](https://qodo-merge-docs.qodo.ai/tools/describe/)                                                                                                | ✅ | ✅ |     ✅     |      ✅       |
|       | [Improve](https://qodo-merge-docs.qodo.ai/tools/improve/)                                                                                                 | ✅ | ✅ |     ✅     |      ✅       |
|       | [Ask](https://qodo-merge-docs.qodo.ai/tools/ask/)                                                                                                     | ✅ | ✅ |     ✅     |      ✅       |
|       | ⮑ [Ask on code lines](https://qodo-merge-docs.qodo.ai/tools/ask/#ask-lines)                              | ✅ | ✅ |           |              |
|       | [Update CHANGELOG](https://qodo-merge-docs.qodo.ai/tools/update_changelog/)                                                                                     | ✅ | ✅ |     ✅     |      ✅       |
|       | [Ticket Context](https://qodo-merge-docs.qodo.ai/core-abilities/fetching_ticket_context/) 💎  | ✅ | ✅ |     ✅     |   |
|       | [Utilizing Best Practices](https://qodo-merge-docs.qodo.ai/tools/improve/#best-practices) 💎  | ✅ | ✅ |     ✅     |   |
|       | [PR Chat](https://qodo-merge-docs.qodo.ai/chrome-extension/features/#pr-chat) 💎  | ✅ |  |           |   |
|       | [Suggestion Tracking](https://qodo-merge-docs.qodo.ai/tools/improve/#suggestion-tracking) 💎  | ✅ | ✅ |           |   |
|       | [CI Feedback](https://qodo-merge-docs.qodo.ai/tools/ci_feedback/) 💎                                    | ✅ |                    |           |              |
|       | [PR Documentation](https://qodo-merge-docs.qodo.ai/tools/documentation/) 💎                         | ✅ | ✅ |           |              |
|       | [Custom Labels](https://qodo-merge-docs.qodo.ai/tools/custom_labels/) 💎                                | ✅ | ✅ |           |              |
|       | [Analyze](https://qodo-merge-docs.qodo.ai/tools/analyze/) 💎                                            | ✅ | ✅ |           |              |
|       | [Similar Code](https://qodo-merge-docs.qodo.ai/tools/similar_code/) 💎                                  | ✅ |                    |           |              |
|       | [Custom Prompt](https://qodo-merge-docs.qodo.ai/tools/custom_prompt/) 💎                                | ✅ | ✅ |     ✅     |              |
|       | [Test](https://qodo-merge-docs.qodo.ai/tools/test/) 💎                                                  | ✅ | ✅ |           |              |
|       | [Implement](https://qodo-merge-docs.qodo.ai/tools/implement/) 💎                                        | ✅ | ✅ |     ✅     |              |
|       | [Auto-Approve](https://qodo-merge-docs.qodo.ai/tools/improve/?h=auto#auto-approval) 💎                  |   ✅    |   ✅    |   ✅        |            |
|       |                                                                                                         |                    |                    |           |              |
| 使用方式 | [CLI](https://qodo-merge-docs.qodo.ai/usage-guide/automations_and_usage/#local-repo-cli)                                                                                                     | ✅ | ✅ |     ✅     |      ✅       |
|       | [App / webhook](https://qodo-merge-docs.qodo.ai/usage-guide/automations_and_usage/#github-app)                                                                                           | ✅ | ✅ |     ✅     |      ✅       |
|       | [Tagging bot](https://github.com/Codium-ai/pr-agent#try-it-now)                                                                                             | ✅ |                    |           |              |
|       | [Actions](https://qodo-merge-docs.qodo.ai/installation/github/#run-as-a-github-action)                                                                                                 | ✅ |✅|     ✅     |✅|
|       |                                                                                                         |                    |                    |           |              |
| 核心功能  | [PR 压缩](https://qodo-merge-docs.qodo.ai/core-abilities/compression_strategy/)                                                                  | ✅ | ✅ |     ✅     |      ✅       |
|       | 自适应和令牌感知文件补丁拟合                                                             | ✅ | ✅ |     ✅     |      ✅       |
|       | [多模型支持](https://qodo-merge-docs.qodo.ai/usage-guide/changing_a_model/)                                                                                 | ✅ | ✅ |     ✅     |      ✅       |
|       | [本地和全局元数据](https://qodo-merge-docs.qodo.ai/core-abilities/metadata/)          | ✅ | ✅ |     ✅     | ✅             |
|       | [动态上下文](https://qodo-merge-docs.qodo.ai/core-abilities/dynamic_context/)          | ✅ | ✅ |     ✅     | ✅             |
|       | [自我反思](https://qodo-merge-docs.qodo.ai/core-abilities/self_reflection/)          | ✅ | ✅ |     ✅     | ✅             |
|       | [静态代码分析](https://qodo-merge-docs.qodo.ai/core-abilities/static_code_analysis/) 💎         | ✅ | ✅ |           |              |
|       | [全局和 wiki 配置](https://qodo-merge-docs.qodo.ai/usage-guide/configuration_options/) 💎 | ✅ | ✅ |     ✅     |              |

</div>
<hr>

## 立即尝试

立即在您的公共 GitHub 仓库上尝试由 Claude Sonnet 驱动的 PR-Agent。只需在任何 PR 评论中提及 `@CodiumAI-Agent` 并添加所需命令。代理将根据您的命令生成响应。
例如，在任何拉取请求中添加以下文本的评论：
```
@CodiumAI-Agent /review
```
代理将回复您 PR 的审查结果。

请注意，这是一个推广机器人，仅适用于初步实验。
例如，它没有对您的仓库的"编辑"权限，因此无法更新 PR 描述或添加标签（`@CodiumAI-Agent /describe` 将以评论形式发布 PR 描述）。此外，该机器人不能用于私有仓库，因为它无法访问那里的文件。

---

## Qodo Merge 💎
[Qodo Merge](https://www.qodo.ai/pricing/) 是由 Qodo 提供的 PR-Agent 托管版本。它按月收费，并提供以下好处：
1. **完全托管** - 我们为您处理所有事情 - 托管、模型、定期更新等。安装过程非常简单，只需注册并将 Qodo Merge 应用添加到您的 GitHub\GitLab\BitBucket 仓库。
2. **增强隐私** - 不会存储数据或使用数据训练模型。Qodo Merge 将采用零数据保留政策，并使用具有零数据保留的 OpenAI 账户。
3. **改进支持** - Qodo Merge 用户将获得优先支持，并能够请求新功能和能力。
4. **额外功能** - 除了上述好处外，Qodo Merge 将强调更多定制化，并使用静态代码分析（除了 LLM 逻辑外）来改进结果。
查看 [这里](https://qodo-merge-docs.qodo.ai/overview/pr_agent_pro/) 了解 Qodo Merge 中可用的功能列表。

## 工作原理

以下图表说明了 PR-Agent 工具及其流程：

![PR-Agent 工具](https://www.qodo.ai/images/pr_agent/diagram-v0.9.png)

查看 [PR 压缩策略](https://qodo-merge-docs.qodo.ai/core-abilities/#pr-compression-strategy) 页面，了解更多关于我们如何将代码差异转换为可管理的 LLM 提示的详细信息。

## 为什么使用 PR-Agent？

一个合理的问题是：`"为什么使用 PR-Agent？它与现有工具相比有什么优势？"`

以下是 PR-Agent 的一些优势：

- 我们强调**实际实用性**。每个工具（review、improve、ask 等）只有一次 LLM 调用，不会更多。我们认为这对于团队的实际使用至关重要 - 能够快速（约 30 秒）且经济地获得答案。
- 我们的 [PR 压缩策略](https://qodo-merge-docs.qodo.ai/core-abilities/#pr-compression-strategy) 是一项核心能力，使我们能够有效处理短小和长篇 PR。
- 我们的 JSON 提示策略使我们能够拥有**模块化、可定制的工具**。例如，'/review' 工具类别可以通过 [配置](pr_agent/settings/configuration.toml) 文件控制。添加额外类别既简单又方便。
- 我们支持**多个 git 提供商**（GitHub、Gitlab、Bitbucket），**多种**使用工具的方式（CLI、GitHub Action、GitHub App、Docker 等），以及**多种模型**（GPT、Claude、Deepseek 等）。

## 数据隐私

### 自托管 PR-Agent

- 如果您使用自己的 OpenAI API 密钥托管 PR-Agent，这是您与 OpenAI 之间的事情。您可以在此处阅读他们的 API 数据隐私政策：
https://openai.com/enterprise-privacy

### Qodo 托管的 Qodo Merge 💎

- 当使用由 Qodo 托管的 Qodo Merge 💎 时，我们不会存储您的任何数据，也不会将其用于训练。您还将受益于具有零数据保留的 OpenAI 账户。

- 对于某些客户，Qodo 托管的 Qodo Merge 将使用 Qodo 的专有模型 — 如果是这种情况，您将收到通知。

- 不会被动收集代码和拉取请求的数据 — Qodo Merge 仅在您调用它时才会激活，然后它将仅提取和分析与执行的命令和查询的拉取请求相关的数据。

### Qodo Merge Chrome 扩展

- [Qodo Merge Chrome 扩展](https://chromewebstore.google.com/detail/qodo-merge-ai-powered-cod/ephlnjeghhogofkifjloamocljapahnl) 仅用于修改 GitHub PR 屏幕的视觉外观。它不会传输用户的仓库或拉取请求代码。只有当用户提交激活 PR-Agent 工具的 GitHub 评论时，代码才会被发送处理，这符合 Qodo-Merge 的标准隐私政策。

## 链接

- Discord 社区：https://discord.gg/kG35uSHDBc
- Qodo 网站：https://www.qodo.ai/
- 博客：https://www.qodo.ai/blog/
- 故障排除：https://www.qodo.ai/blog/technical-faq-and-troubleshooting/
- 支持：support@qodo.ai