# iwencai-skills

基于[同花顺问财](https://www.iwencai.com/) API 的 Claude Code Skills 集合，提供 A 股、港股、美股的智能选股与金融数据查询能力。

## 包含 Skills

| Skill | 说明 |
|-------|------|
| `hithink-astock-selector` | 问财选 A 股——自然语言筛选 A 股 |
| `hithink-hkstock-selector` | 问财选港股——自然语言筛选港股 |
| `hithink-usstock-selector` | 问财选美股——自然语言筛选美股 |
| `hithink-market-query` | 行情数据查询 |
| `hithink-finance-query` | 财务数据查询 |
| `hithink-business-query` | 公司经营数据查询 |
| `hithink-insresearch-query` | 机构研究与评级查询 |
| `announcement-search` | 公告搜索 |
| `news-search` | 新闻搜索 |
| `valuation-model` | 估值模型方法论 |

## 安装

### 方式一：`ln` 安装（推荐）

将本仓库 clone 到本地，然后用符号链接把需要的 skill 挂载到 Claude Code 的 skills 目录：

```bash
# clone 仓库
git clone https://github.com/YOUR_USERNAME/iwencai-skills.git ~/iwencai-skills

# 安装单个 skill（以 A 股选股为例）
ln -s ~/iwencai-skills/skills/问财选A股/hithink-astock-selector ~/.claude/skills/hithink-astock-selector

# 安装全部 skills（一键脚本）
for skill_dir in ~/iwencai-skills/skills/*/; do
  skill=$(ls "$skill_dir")
  ln -sf "${skill_dir}${skill}" ~/.claude/skills/"${skill}"
done
```

> `~/.claude/skills/` 是 Claude Code 加载 skill 的默认目录。如果该目录不存在，请先执行 `mkdir -p ~/.claude/skills`。

### 方式二：直接复制

```bash
cp -r ~/iwencai-skills/skills/问财选A股/hithink-astock-selector ~/.claude/skills/
```

### 验证安装

重启 Claude Code 后，在对话中输入选股相关问题（如"帮我选出最近一周涨幅超过 10% 的 A 股"），skill 会自动触发。

## 使用示例

```
帮我选出 PE 低于 20、ROE 大于 15% 的 A 股
最近一周港股中涨幅最大的科技股有哪些？
帮我找出市值超过 500 亿的医药板块美股
查一下贵州茅台最近三年的营收和净利润
```

## 许可证

[MIT](LICENSE)
# iwencai-skills
