---
marp: true
headingDivider: 3
---

# Agent Skillsトレーニング（知識習得編） 🤖 <!-- omit in toc -->

～「**AIをただ使う人**」から「**AIに仕事を任せる人**」へ～

## はじめに 📝 <!-- omit in toc -->

- 対象： Agent Skillsの初学者 👶
- 目的： Agent Skillsの基本的な使い方を理解し、
  　　　 作成できるようになる
- 前提条件:
  - GitHub Copilot Chatの利用が可能であること
  - Visual Studio Codeの利用が可能であること
  - Pythonがインストールされていること

## 目次 📚 <!-- omit in toc -->

- [1. Agent Skillsとは何？](#1-agent-skillsとは何-1)
- [2. Agent Skillsを使ってみる](#2-agent-skillsを使ってみる-1)
- [3. Agent Skillsの仕組みを理解する](#3-agent-skillsの仕組みを理解する-1)
- [4. Agent Skillsを作ってみる](#4-agent-skillsを作ってみる-1)

## 1. Agent Skillsとは何？ 🤔

AIに作業してもらうための手順書やスクリプトをひとまとめにしたもの。

```text
skills/
└── log_analysis/          # ログを分析するスキル
     ├── SKILL.md           # 手順定義
     ├── scripts/             # スクリプト
     ├── references/      # 参考資料
     └── assets/              # アセット
```

例：1️⃣エラーログ解析 → 2️⃣原因と対策の検討 → 3️⃣レポート作成

### 1.1. Agent Skillsのメリット ✨

- **一貫性** 🔁
  手順を定義、AIが毎回同じ手順・品質でタスクを実行
- **知識共有** 🤝
  課内のノウハウをひとまとめにして共有
- **効率性** ⚡
  必要なときだけ読み込み、AIクレジット消費を最小化
- **再利用/ポータビリティ** ♻️
  一度作れば異なるAIツール上でも繰り返し利用可能

### 1.2. Agent Skillsの利用例 💡

- ドキュメントの作成 📄
  AIに特定のスタイルや品質で成果物（例：レポート、プレゼン資料）を作らせる
- ワークフローの自動化 ⚙️
  複数ステップのプロセスを標準化する（例：データ収集→分析→レポート作成）
- MCP拡張 🔌
  MCPの能力に「使い方の知識」を加える

## 2. Agent Skillsを使ってみる 🚀

一般公開されているskillを利用できます。
車輪の再発明はやめよう。

- [Anthropic Skills](https://github.com/anthropics/skills)
  **skill-creator**, docs, xlsx, pptx, pdf
- [GitHub Awesome Copilot](https://awesome-copilot.github.com/)
- [Microsoft Agent Skills](https://github.com/microsoft/agent-skills)
- skills.sh

## 3. Agent Skillsの仕組みを理解する 🧠

### 3.1. 基本構造

```text
skills/
└── log_analysis/          # ログを分析するスキル
     ├── SKILL.md           # 手順定義
     ├── scripts/             # スクリプト
     ├── references/      # 参考資料
     └── assets/              # アセット
```

- 最小構成（必須）は、SKILL.mdのみ。その他は必要に応じて追加。
- 配置場所は、`.github/skills`や`~/.copilot/skills`など任意の場所に配置可能。

### 3.2. SKILL.mdの構成

#### 3.2.1. Frontmatter

スキルの名前（フォルダ名と同一）といつこのスキルを利用するかを定義する部分。
必須は2項目（name, description）で、その他は任意。

```markdown
---
name: log_analysis
description: 指定されたログを分析し、エラー傾向と原因を特定してレポートを作成。ログファイル（拡張子 .log）を指定されたとき、この Skill を利用。
---
```

#### 3.2.2. Body

手順の具体的な内容を記述する部分。Markdown形式で自由に記述可能。

```markdown
入力情報、処理手順、出力情報、例外ケースを記述する。
```

## 4. Agent Skillsを作ってみる 🛠️

- ゴール:
  指定されたログを分析し、障害の原因特定、対策検討、結果出力するSkill
- 成果物構成

```text
skills/
└── log_analysis/
     ├── SKILL.md           # 作業手順
     ├── scripts/             # ログフィルタ実装
     ├── references/      # 参照資料
     └── assets/              # レポート雛形
```
