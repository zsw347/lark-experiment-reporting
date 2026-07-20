# 飞书实验报告规范

这是一个通用的飞书实验报告 Codex Skill。它统一实验目标、方法说明、协议边界、指标表格、排名高亮、不确定性、结果来源和写后验证流程，不绑定特定项目或领域。

## 安装

在 Codex 中调用 `$skill-installer`，并提供以下仓库路径：

```text
https://github.com/zsw347/lark-experiment-reporting/tree/main/lark-experiment-reporting
```

也可以运行 Codex 自带的安装脚本：

```bash
python scripts/install-skill-from-github.py --repo zsw347/lark-experiment-reporting --path lark-experiment-reporting
```

安装后，在下一轮对话中使用：

```text
$lark-experiment-reporting
```

## 适用内容

- 分类、回归、排序/检索、生成、预测和多模态实验
- 工程性能测试、科学实验及在线 A/B 测试
- baseline、论文复现、项目方法、消融和探索性结果的分区展示
- 交叉验证/OOF、固定 Test、外部评估、时间回测和线上实验协议
- 完整指标表、最佳与第二佳高亮、不确定性、产物追溯和写后核验

技能目录位于 [`lark-experiment-reporting/`](lark-experiment-reporting/)。
