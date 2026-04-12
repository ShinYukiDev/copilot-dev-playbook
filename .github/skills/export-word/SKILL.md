---
name: export-word
description: マークダウンファイルをPandocを使用してWord(.docx)形式に変換する
---

# 実行手順
1. 指定されたターゲットファイル（.md）を確認する。
2. 以下のターミナルコマンドを生成し、ユーザーに実行を促す。
   `pandoc [対象ファイル].md -o [対象ファイル].docx`
3. もしPandocが未インストールなら、インストール方法（Win: winget）を提示する。