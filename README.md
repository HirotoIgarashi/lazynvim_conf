# 💤 LazyVim

A starter template for [LazyVim](https://github.com/LazyVim/LazyVim).
Refer to the [documentation](https://lazyvim.github.io/installation) to get started.

## LazyVimを使う準備

### nvimのインストール

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

### Node環境のインストール

```bash
curl -sL https://raw.githubusercontent.com/jorgebucaran/fisher/main/functions/fisher.fish | source && fisher install jorgebucaran/fisher
fisher install jorgebucaran/nvm.fish
nvm install lts
nvm use lts
```

~/.config/fish/config.fishに

```fish
set -U nvm_default_version lts
```

### Rust環境のインストール

```bash
sudo apt install curl build-essential
curl --proto '=https' --tlsv1.2 https://sh.rustup.rs -sSf | sh
```

### :checkhealth

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

### :LazyHealth
