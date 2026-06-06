# Body Root Cause Skill

一个基于**循证营养学 + 贝叶斯推理**的内服补剂诊断 Skill，帮助你从系统性根因出发，找到身体问题的真正答案。

## 它能解决什么问题

不是告诉你"吃什么好"，而是先帮你搞清楚"为什么会这样"。

**皮肤调理**
- 痤疮/闭口反复发作，外用无效
- 下巴/下颌线长痘（可能是激素或 PCOS）
- 出差/换城市后皮肤突然爆发
- 色斑、油皮、敏感等根因不明的皮肤问题

**通用补剂决策**
- 睡眠差，不知道选镁/L-茶氨酸还是甘氨酸
- 容易疲劳，分不清是缺铁、缺 B12 还是别的原因
- 想买基础补剂，不知道从哪里开始
- 健身、备孕、PCOS 等特定场景的补剂搭配

## 工作原理

```
问诊 → 贝叶斯权重更新 → 根因定位 → 分层干预方案
```

**7 大根因假设**，系统性排查：

| 假设 | 根因 |
|------|------|
| H1 | 雄激素性痤疮（激素驱动） |
| H2 | PCOS / 胰岛素抵抗 |
| H3 | 皮质醇过高（压力驱动） |
| H4 | 肠道菌群失调 / H. pylori |
| H5 | 营养缺乏（锌/维D/Omega-3） |
| H6 | 环境触发（水质/污染/饮食骤变） |
| H7 | 护肤品/药物诱发 |

**输出方案三层覆盖**——只处理触发因素会反复，只处理根因短期无效：

- **根本原因（Root Cause）**：长期存在的系统性问题
- **触发因素（Trigger）**：短期出现的外部事件  
- **维持因素（Perpetuating Factor）**：让问题持续的条件

## 安装方式

### Claude Code

**方式一：命令行一键安装（推荐）**

```bash
# 个人全局安装（所有项目可用）
mkdir -p ~/.claude/skills && \
  git clone https://github.com/JackZhong2017/body-root-cause-skill.git /tmp/brc-skill && \
  cp -r /tmp/brc-skill/skincare-internal ~/.claude/skills/body-root-cause

# Windows（PowerShell）
New-Item -ItemType Directory -Force "$env:USERPROFILE\.claude\skills"
git clone https://github.com/JackZhong2017/body-root-cause-skill.git "$env:TEMP\brc-skill"
Copy-Item -Recurse "$env:TEMP\brc-skill\skincare-internal" "$env:USERPROFILE\.claude\skills\body-root-cause"
```

**方式二：手动安装**

1. 下载本仓库：点击右上角 `Code → Download ZIP`，解压
2. 将 `skincare-internal` 文件夹复制到以下路径：

| 系统 | 路径 |
|------|------|
| macOS / Linux | `~/.claude/skills/body-root-cause/` |
| Windows | `%USERPROFILE%\.claude\skills\body-root-cause\` |

3. 确认目录结构为 `skills/body-root-cause/SKILL.md`（不要多嵌套一层）
4. 重启 Claude Code，输入 `/skills` 确认加载成功

> **项目级安装**：将文件夹放到项目目录下的 `.claude/skills/body-root-cause/`，仅对该项目生效。

---

### OpenClaw

**方式一：直接粘贴 GitHub 链接**

在对话中发送：
```
Install this skill: https://github.com/JackZhong2017/body-root-cause-skill
```
OpenClaw 会自动识别并安装。

**方式二：CLI 安装**

```bash
# 安装到当前工作区
openclaw skills install https://github.com/JackZhong2017/body-root-cause-skill

# 全局安装（所有 agent 可用）
openclaw skills install https://github.com/JackZhong2017/body-root-cause-skill --global
```

**方式三：ClawHub 安装**（上架后可用）

```bash
clawhub install body-root-cause
```

---

### 触发示例

安装完成后，直接在对话中提问即可自动触发：

```
我最近痤疮一直反复，吃什么能改善？
为什么我下巴总是长痘？
帮我搭配一套针对 PCOS 的补剂方案
我睡眠很差，镁/L-茶氨酸/甘氨酸哪个更适合我？
最近容易疲劳，不知道是缺铁还是缺 B12 还是别的原因
我想买基础补剂，不知道从哪里开始
```

## 重要说明

- 本 Skill **不做医疗诊断**，补剂建议不能替代处方药
- 若症状持续加重或常规调理 3 个月无响应，建议优先就医
- 所有推荐成分以有可信临床证据（RCT 或系统综述支持）为准入门槛
- 严格只处理内服建议，不输出外用护肤品推荐

## License

MIT
