# じゃんけんアプリ開発トレーニング（C#・コンソール）

このリポジトリは、**GitHub Copilot** を活用したC#コンソールアプリ（じゃんけんゲーム）の開発を通じて、CopilotやVS Codeの使い方を学ぶためのトレーニング教材です。

## 対象者

- VS CodeおよびGitHub Copilotの初学者
- VS CodeでのC#開発を学びたい方

## 前提条件

- [ ] [.NET SDK](https://dotnet.microsoft.com/ja-jp/download) をインストール済み
- [ ] 下記の拡張機能をインストール済み
  - [ ] C# for Visual Studio Code（Microsoft公式）
  - [ ] C# Dev Kit（Microsoft公式）

## フォルダ構成

```plaintext
JankenApp/
├── src/      # アプリ本体
├── tests/    # テストコード
├── docs/     # 仕様書などドキュメント
└── README.md
```

## トレーニング手順

### 0. フォルダ作成

- この`JankenApp`フォルダをローカルの任意の場所にコピーする。
- VS Codeでコピーした`JankenApp`フォルダを開く。
- `src`、`tests`、`docs` フォルダを作成します。

### 1. ソリューション・プロジェクト作成

- VS Code上で作成。
- またはターミナルで以下を実行。

  ```powershell
  dotnet new sln -n JankenApp --format sln
  dotnet new console -o src/JankenApp
  dotnet new xunit -o tests/JankenApp.Tests
  dotnet sln add src/JankenApp/JankenApp.csproj
  dotnet sln add tests/JankenApp.Tests/JankenApp.Tests.csproj
  dotnet add tests/JankenApp.Tests/JankenApp.Tests.csproj reference src/JankenApp/JankenApp.csproj
  dotnet build
  ```

- ビルドが成功することを確認します。

### 2. Copilotでコメント駆動実装

`src/JankenApp/Program.cs` でコメントを書き、Copilotの提案を活用して実装します。

```csharp
// グー、チョキ、パーのいずれかの入力を受け取る
```

```csharp
// 入力値が正しいか検証する
```

```csharp
// コンピュータの手をランダムに生成する
```

```csharp
// 勝敗を判定する
```

```csharp
// 結果を表示する
```

### 3. リファクタリング

- メソッド分割やロジックの分離を行い、可読性・保守性を高めます。
- 必要に応じてXMLコメントを追記します。

### 4. `/explain` コマンドで処理内容説明

- Copilot Chatの `/explain` コマンドで、実装したコードの処理内容を説明させます。

### 5. コードレビュー

- Copilot Chatやペアでコードレビューを行い、改善点を洗い出します。

### 6. テストコード作成

- `tests/JankenApp.Tests` にxUnit形式でテストコードを追加します。
- Copilotの提案を活用しながら、各メソッドのテストを作成します。

### 7. テスト実行

- VS Code上のテストエクスプローラーを使用してテストを実行する。
- または、ターミナルで以下を実行する。

  ```powershell
  dotnet test
  ```

- テストがすべて成功することを確認します。

### 8. 仕様書作成

- `docs` フォルダに、アプリの仕様や設計、使い方などをまとめたドキュメントを作成します。

---

## 補足

- Copilotの提案は必ずしも正解とは限りません。内容を理解しながら進めましょう。
- わからない点はCopilot Chatで質問してみましょう。
