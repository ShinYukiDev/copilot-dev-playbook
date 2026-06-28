# VS Code セットアップガイド

このガイドは、**GitHub Copilot を使った開発を始めるために必要な VS Code の環境構築手順**を、初学者向けにまとめたものです。

上から順に進めれば、すぐに開発を始められます。

## 対象者

- VS Code をこれからインストールする方
- GitHub Copilot を使った開発を始めたい方
- 環境構築で躓きたくない方

## 前提条件

開始前に、以下が完了していることを確認してください。

- [ ] Windows 10 / 11 をご使用
- [ ] インターネット接続が可能
- [ ] 必要に応じて、管理者権限でソフトウェアをインストール可能

---

## セットアップ手順

### 1. VS Code のインストール

1. [VS Code 公式ページ](https://code.visualstudio.com/) にアクセス
2. Windows 版をダウンロード
3. インストーラーを実行して、デフォルト設定でインストール完了

#### インストール確認

VS Code を起動して、バージョンが表示されれば OK です。

**左下のギア アイコン → About** で、インストールされたバージョンを確認できます.

---

### 2. 言語設定（オプション）

初期状態では英語ですが、日本語に設定できます。

1. **左側サイドバーの拡張機能 アイコン（正方形 4 つのマーク）** をクリック
2. 検索窓に **「Japanese Language Pack」** と入力
3. Microsoft 公式の拡張をインストール
4. VS Code を再起動（右下に「Change Language and Restart」が表示される場合もあります）

---

### 3. 推奨拡張機能のインストール

以下は、Copilot を活用した開発に「最小限必要」な拡張機能です。
すべてを一度にインストールする必要はありませんが、最初は **1. 〜 3. (Copilot 関連)**をインストール推奨です。

#### 3.1 Copilot 関連（必須）

**GitHub Copilot**
- 用途：AI コード補完
- インストール方法：
  1. 拡張機能検索で「GitHub Copilot」と入力
  2. GitHub, Inc. 公式版をインストール
  3. インストール後、左下ユーザー アイコンで GitHub にサインイン

**GitHub Copilot Chat**
- 用途：Copilot とチャット形式で会話しながら開発
- インストール方法：
  1. 拡張機能検索で「GitHub Copilot Chat」と入力
  2. GitHub, Inc. 公式版をインストール
  3. 自動的に Copilot と連携します

#### 3.2 コーディング基本拡張

**C# (Microsoft 公式)**
- 用途：C# 開発（初心者は C# からスタート推奨）
- インストール方法：検索で「C#」→ Microsoft 公式

**C# Dev Kit (Microsoft 公式)**
- 用途：C# デバッグなど開発支援
- 依存：C# 拡張が必要です

**.NET Install Tool (Microsoft 公式)**
- 用途：.NET SDK 管理
- インストール方法：検索で「.NET Install Tool」→ インストール

#### 3.3 ドキュメント・図解関連

**Markdown All in One (Yu Zhang)**
- 用途：Markdown ファイル編集・プレビュー
- インストール方法：検索で「Markdown All in One」→ インストール

**Mermaid Diagram Syntax Highlighting (Jämg)**
- 用途：フローチャート図の作成・プレビュー
- インストール方法：検索で「Mermaid」→ Jämg 版をインストール

#### 3.4 Git 関連

**Git Graph (mhutchie)**
- 用途：Git の歴史をビジュアル表示
- インストール方法：検索で「Git Graph」→ インストール

**GitLens (GitKraken)**
- 用途：コード行の Git 履歴表示、作者確認
- インストール方法：検索で「GitLens」→ GitKraken 公式版をインストール

---

### 4. インストール状況確認

#### 拡張機能の確認

左側サイドバーの **拡張機能 アイコン** をクリック。
以下の項目が表示されていれば、基本セットアップは完了です：

```
✓ GitHub Copilot
✓ GitHub Copilot Chat
✓ C#
✓ C# Dev Kit
✓ Markdown All in One
✓ Mermaid Diagram Syntax Highlighting
✓ Git Graph
```

---

### 5. 初期確認項目

#### 5.1 Copilot にサインインできているか

1. 左下 **ユーザー アイコン** をクリック
2. GitHub アカウントでサインイン済みなら、**アカウント名が表示**
3. まだなら **「Sign in to use GitHub Copilot」** をクリックして GitHub 認証

#### 5.2 Copilot Chat を試す

Copilot Chat が正常に動作するか確認します。

1. **Ctrl + Shift + I** キーを押す
2. 右側に Copilot Chat パネルが表示される
3. 以下のメッセージを入力：

   ```
   Hello, are you ready to help me code?
   ```

4. Copilot が応答すれば、Chat 機能は正常です ✓

#### 5.3 テストプロジェクトで動作確認

Copilot の コード補完が動作するか確認します。

1. **Ctrl + K → Ctrl + O** で新規フォルダを作成
2. フォルダ内に **test.cs** ファイルを作成
3. 以下のコメントを入力：

   ```csharp
   // ユーザーの入力を受け取る関数
   ```

4. **Ctrl + Enter** キーで Copilot の提案を表示
5. コード補完が表示されれば、補完機能は正常です ✓

---

## トラブルシューティング

### よくある問題

#### Q1: 「GitHub Copilot is not enabled for your account」と表示される

**原因**: GitHub アカウントが Copilot に対応していない、または未認証

**解決方法**:
1. 左下ユーザー アイコン → **GitHub へサインイン** をクリック
2. 新しく開くブラウザで GitHub 認証を完了
3. VS Code に戻ると自動で設定が反映されます
4. それでも解決しない場合は、VS Code を再起動

#### Q2: 「拡張機能のインストールに失敗した」と表示される

**原因**: ネットワーク接続の一時的な問題、または拡張機能競合

**解決方法**:
1. インターネット接続を確認
2. **Ctrl + Shift + P** で コマンドパレットを開く
3. 「Install Extensions from VSIX」で別の方法を試す
4. 個別の拡張を再度検索してインストール

#### Q3: Markdown プレビューが表示されない

**原因**: Markdown All in One がインストールされていない、または無効になっている

**解決方法**:
1. 拡張機能パネルで「Markdown All in One」を確認
2. 無効になっていたら **「Enable」** をクリック
3. .md ファイルを開いて、右上 **プレビュー アイコン**（虫眼鏡）をクリック

#### Q4: Git Graph が表示されない

**原因**: Git がインストールされていない、または Git コマンドが PATH に設定されていない

**解決方法**:
1. [Git 公式ページ](https://git-scm.com/) から Git をインストール
2. インストール後、OS を再起動
3. VS Code を再起動

---

## 次のステップ

セットアップが完了したら、以下に進みましょう：

### 📚 学習フロー（推奨順序）

1. **本ガイド（完了）** ← 環境構築
2. **`02_training` へ進む** ← 基礎を学ぶ
   - VS Code の基本操作
   - Copilot の使い方（実例）
   - C# や他の言語の開発

3. **`03_practice` で実務活用** ← テンプレート活用
   - プロンプト集
   - 指示テンプレート

4. **`04_best_practices` で改善** ← パターン学習
   - コーディングパターン
   - プロンプトパターン

---

## 補足

- **Copilot の提案は必ずしも正解ではありません**。内容を理解して活用してください。
- わからないことが出たら、Copilot Chat で質問してみましょう。「VS Code の設定方法」や「C# の書き方」など、何でも聞けます。
- 拡張機能は必要に応じていつでも追加・削除可能です。焦らず進めてください。
- **セットアップ済みのチーム環境がある場合**は、`.vscode/extensions.json` や `.vscode/settings.json` で拡張を一括管理することも可能です。

---

## 参考リンク

- [VS Code 公式ページ](https://code.visualstudio.com/)
- [GitHub Copilot 公式ドキュメント](https://docs.github.com/en/copilot)
- [GitHub Copilot Chat 使い方](https://docs.github.com/en/copilot/using-github-copilot/using-github-copilot-chat)
- [.NET SDK インストール](https://dotnet.microsoft.com/ja-jp/download)

---

最後に、環境構築がすべて完了したら、`02_training` でハンズオン学習を始めましょう。頑張ってください！
