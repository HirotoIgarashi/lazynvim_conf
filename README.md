<!-- mtoc-start -->

* [1. Vimのチュートリアル](#1-vimのチュートリアル)
  * [1.1. 編集の基本](#11-編集の基本)
  * [1.2. 高度な編集](#12-高度な編集)
  * [1.3. 検索](#13-検索)
  * [1.4. 大きなサイズのテキストの編集および複数ファイルの編集](#14-大きなサイズのテキストの編集および複数ファイルの編集)
  * [1.5. 複数のウィンドウの扱い](#15-複数のウィンドウの扱い)
  * [1.6. 基本的なビジュアルモード](#16-基本的なビジュアルモード)
  * [1.7. プログラマ向けコマンド](#17-プログラマ向けコマンド)
  * [1.8. 基本的な略語、キーボード割り当て、初期設定ファイル](#18-基本的な略語キーボード割り当て初期設定ファイル)
  * [1.9. 基本的なコマンドモードの操作](#19-基本的なコマンドモードの操作)
  * [1.10. GUIの基本的使い方](#110-guiの基本的使い方)
  * [1.11. テキストファイルの使い方](#111-テキストファイルの使い方)
  * [1.12. 自動完了](#112-自動完了)
  * [1.13. オートコマンド](#113-オートコマンド)
  * [1.14. ファイル回復とコマンドライン引数](#114-ファイル回復とコマンドライン引数)
  * [1.15. その他のコマンド](#115-その他のコマンド)
  * [1.16. 操作方法](#116-操作方法)
  * [1.17. 本書で分類されていないトピックス](#117-本書で分類されていないトピックス)
* [2. Vimの詳細](#2-vimの詳細)
* [3. 💤 LazyVim](#3--lazyvim)
  * [3.1. LazyVimを使う準備](#31-lazyvimを使う準備)
    * [3.1.1. nvimのインストール](#311-nvimのインストール)
    * [3.1.2. Node環境のインストール](#312-node環境のインストール)
    * [3.1.3. Rust環境のインストール](#313-rust環境のインストール)
    * [3.1.4. `:checkhealth`](#314-checkhealth)
    * [3.1.5. Pythonの仮想環境について](#315-pythonの仮想環境について)
    * [3.1.6. `:LazyHealth`](#316-lazyhealth)

<!-- mtoc-end -->

# 1. Vimのチュートリアル

## 1.1. 編集の基本

## 1.2. 高度な編集

## 1.3. 検索

## 1.4. 大きなサイズのテキストの編集および複数ファイルの編集

## 1.5. 複数のウィンドウの扱い

## 1.6. 基本的なビジュアルモード

## 1.7. プログラマ向けコマンド

## 1.8. 基本的な略語、キーボード割り当て、初期設定ファイル

## 1.9. 基本的なコマンドモードの操作

## 1.10. GUIの基本的使い方

## 1.11. テキストファイルの使い方

## 1.12. 自動完了

## 1.13. オートコマンド

## 1.14. ファイル回復とコマンドライン引数

## 1.15. その他のコマンド

## 1.16. 操作方法

## 1.17. 本書で分類されていないトピックス

# 2. Vimの詳細

# 3. 💤 LazyVim

A starter template for [LazyVim](https://github.com/LazyVim/LazyVim).
Refer to the [documentation](https://lazyvim.github.io/installation) to get started.

## 3.1. LazyVimを使う準備

### 3.1.1. nvimのインストール

```bash
curl -LO https://github.com/neovim/neovim/releases/latest/download/nvim-linux-x86_64.appimage
chmod u+x nvim-linux-x86_64.appimage
./nvim-linux-x86_64.appimage
```

```bash
mkdir -p ~/.local/bin
mv nvim-linux-x86_64.appimage ~/.local/bin/nvim
nvim
```

### 3.1.2. Node環境のインストール

cachyOSの場合はnodejsとnpmをインストールします。

```bash
curl -sL https://raw.githubusercontent.com/jorgebucaran/fisher/main/functions/fisher.fish | source && fisher install jorgebucaran/fisher
fisher install jorgebucaran/nvm.fish
nvm install latest
nvm use latest
```

以下の記述はnodejsとnpmをインストールすることで不要になった

~/.config/fish/config.fishに

```fish
set -U nvm_default_version lts
```

### 3.1.3. Rust環境のインストール

```bash
sudo apt install curl build-essential
curl --proto '=https' --tlsv1.2 https://sh.rustup.rs -sSf | sh
```

### 3.1.4. `:checkhealth`

```fish
mkdir -p ~/.config/nvim
touch ~/.config/nvim/init.lua
# or touch ~/.config/nvim/init.vim if using Vimscript
sudo apt install ripgrep
cargo install ast-grep --locked
sudo apt install sqlite3 libsqlite3-dev
npm install -g @mermaid-js/mermaid-cli

nvm use latest
npm install -g neovim

curl -L https://cpanmin.us | sudo perl - App::cpanminus
sudo cpanm -n Neovim::Ext
# Neovim::Extのメッセージはシステムのバグであるらしく無視してもよい
# WARNINGが鬱陶しい時は~/.config/nvim/init.luaに
# vim.g.loaded_perl_provider = 0
# の１行を追加する
python3 -m venv ~/.config/nvim/venv
source ~/.config/nvim/venv/activate.fish
pip install --upgrade pynvim
# init.luaに
# vim.g.python3_host_prog = vim.fn.expand('~/.config/nvim/venv/bin/python')
# を追加する
# not found prettier
# :lazyExtraでprettierをインストールします。
```

### 3.1.5. Pythonの仮想環境について

fish用

```fish
python3 -m venv ~/.venv
source ~/.venv/bin/activate.fish
.venv> pip install pylatexenc
```

```fish
fisher install cuducos/dirvenv.fish
```

### 3.1.6. `:LazyHealth`

- conform:
  - conform.nvim report
    - [ ] WARNING markdown-toc unavailable: Condition failed

    - [ ] WARNING markdownlint-cli2 unavailable: Condition failed

    ```fish
    sudo npm install -g markdown-toc markdownlint-cli2
    ```

    - [x] WARNING prettier unavailable: Condition failed

    lazyExtraでprettierをアンインストールすることで解消しました。

- lazy:
  - luarocks ~
    - [x] WARNING `lua` version `5.1` needed, but found `Lua 5.5.0  Copyright (C) 1994-2025 Lua.org, PUC-Rio`
    - [x] WARNING {lua5.1} or {lua} or {lua-5.1} version `5.1` not installed

      ```fish
      sudo pacman -S lua51
      ```

- mason.nvim [Language]
  - [x] WARNING Go: not available

    ```fish
    sudo pacman -Syu
    sudo pacman -S go
    ```

  - [x] WARNING Ruby: not available

    ```fish
    sudo pacman -Syu
    sudo pacman -S ruby
    ```

  - [x] WARNING RubyGem: not available

  ```fish
  sudo pacman -Syu
  sudo pacman -S ruby rubygems
  ```

  - [x] WARNING Composer: not available

  ```fish
  sudo pacman -Syu
  sudo pacman -S composer
  ```

  - [x] WARNING PHP: not available

    ```fish
    sudo pacman -Syu
    sudo pacman -Syu php
    ```

  - [x] WARNING javac: not available

    ```fish
    sudo pacman -Syu
    sudo pacman -S jdk-openjdk
    ```

  - [x] WARNING java: not available

  javacをインストールしたら解決したらしい
  - [x] WARNING julia: not available

    ```fish
    sudo pacman -Syu
    sudo pacman -S julia
    ```

- render-markdown.nvim [latex]
  - [x] WARNING none installed: { "utftex", "latex2text" }

    Pythonの仮想環境でpip install pylatexencとすることでWARNINGがでなくなる

- Snacks.image
  - [x] WARNING setup {disabled}

    pluginsにsnacks.luaを追加してimage = { enabled = true },の行を追加するとWARNINGがでなくなる

  - [x] WARNING Missing Treesitter languages: `norg`

    pluginsにneorg.luaを追加することでWARNINGがでなくなる

  - WARNING Image rendering in docs with missing treesitter parsers won't work

- Snacks.statuscolumn
  - [x] WARNING setup {disabled}

    pluginsにsnacks.luaを追加してstatuscolumn = { enabled = true },の行を追加するとWARNINGがでなくなる

- vim.lsp: Enabled Configurations
  - WARNING Unknown filetype 'markdown.mdx' (Hint: filename extension != filetype).
  - WARNING Unknown filetype 'javascript.jsx' (Hint: filename extension != filetype).
  - WARNING Unknown filetype 'typescript.tsx' (Hint: filename extension != filetype).
- vim.provider:
  - Perl provider (optional) ~
    - [x] WARNING "Neovim::Ext" cpan module is not installed

    Neovim::Extをインストールするとバージョンが古いというメッセージに変わる。
    - [x] WARNING No usable perl executable found

      cpanminusをインストールして

      ```fish
      sudo /usr/bin/vendor_perl/cpanm -n Neovim::Ext
      ```

      perl executable: /usr/bin/perl
      と出力されるので動作上は問題ないことにする

  - Python 3 provider (optional) ~
    - [x] `g:python3_host_prog` is not set. Searching for pynvim-python in the environment.

~/.config/nvim/lua/config/options.luaに以下の行を追加する

```lua
vim.g.python3_host_prog = vim.fn.expand("~/.venv/bin/python3")
```

````

    - [x] WARNING No Python executable found that can `import neovim`. Using\
the first available executable for diagnostics.

      ```fish
      pip3 install pynvim
      ```

    - [x] WARNING Could not load Python :

* Ruby provider (optional) ~
  - [x] WARNING `ruby` and `gem` must be in $PATH.

  ```fish
  sudo pacman -Syu
  sudo pacman -S ruby
````

```fish
gem install neovim
```

~/.config/fish/config.fishに以下の行を追加します

```fish
set PATH /home/hiroto/.local/share/gem/ruby/3.4.0/bin/ $PATH
```

- which-key:
  - checking for overlapping keymaps ~
    - WARNING In mode `n`, <g> overlaps with <gx>, <g%>, <g[>, <g]>, <gri>, <gra>, <grn>, <grt>, <grr>, <grx>, <gc>, <gcO>, <gcc>, <gco>, <gO>:
    - WARNING In mode `x`, <i> overlaps with <il>, <ii>, <in>:
    - WARNING In mode `x`, <a> overlaps with <a%>, <al>, <ai>, <an>:
    - WARNING In mode `o`, <i> overlaps with <il>, <ii>, <in>:
    - WARNING In mode `o`, <a> overlaps with <al>, <ai>, <an>:
    - WARNING In mode `n`, <gc> overlaps with <gcO>, <gcc>, <gco>:
