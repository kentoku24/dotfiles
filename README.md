# Dotfiles Management & Setup Guide

このリポジトリは macOS の開発環境設定（Homebrew, mise, zsh, VS Code等）を管理します。

---

## 1. 日々のメンテナンス（今のMacでの作業）

新しいアプリをインストールしたり、設定を変更した後に実行します。
これにより、現在の環境の状態が `dotfiles` リポジトリに保存されます。

### 手順

```bash
# 1. dotfilesディレクトリへ移動
cd ~/dotfiles

# 2. Homebrewでインストールしたアプリ一覧を更新（上書き）
brew bundle dump --force --file=~/dotfiles/Brewfile

# 3. VS Codeの拡張機能一覧を更新（VS Codeを使っている場合）
code --list-extensions > ~/dotfiles/vscode_extensions.txt

# 4. 変更分をGitにコミットしてGitHubへプッシュ
git add .
git commit -m "Update environment: $(date +%Y-%m-%d)"
git push origin main



# 新環境での手順

## Xcode Command Line Tools のインストール（ポップアップが出たら「インストール」をクリック）
xcode-select --install

## Homebrew のインストール

## Homebrew のパスを一時的に通す（まだdotfilesがないため）
eval "$(/opt/homebrew/bin/brew shellenv)"

brew install git mise stow

git clone [https://github.com/kentoku24/dotfiles.git](https://github.com/kentoku24/dotfiles.git) ~/dotfiles

