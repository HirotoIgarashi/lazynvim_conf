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

cachyOSの場合はnodejsとnpmをインストールします。

```bash
curl -sL https://raw.githubusercontent.com/jorgebucaran/fisher/main/functions/fisher.fish | source && fisher install jorgebucaran/fisher
fisher install jorgebucaran/nvm.fish
nvm install latest
nvm use latest
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

### Pythonの仮想環境について

fish用

```fish
python3 -m venv ~/.venv
source ~/.venv/bin/activate.fish
.venv> pip install pylatexenc
```

```fish
fisher install cuducos/dirvenv.fish
```

### :LazyHealth

- conform:
  - conform.nvim report ~
    - WARNING markdown-toc unavailable: Condition failed
    - WARNING markdownlint-cli2 unavailable: Condition failed
    - WARNING prettier unavailable: Condition failed
- lazy:
  - luarocks ~
    - WARNING `lua` version `5.1` needed, but found `Lua 5.5.0  Copyright (C) 1994-2025 Lua.org, PUC-Rio`
    - WARNING {lua5.1} or {lua} or {lua-5.1} version `5.1` not installed
- mason.nvim [Language]
  - WARNING Go: not available
  - WARNING Ruby: not available
  - WARNING RubyGem: not available
  - WARNING Composer: not available
  - WARNING PHP: not available
  - WARNING javac: not available
  - WARNING java: not available
  - WARNING julia: not available
- render-markdown.nvim [latex]
  - [x] WARNING none installed: { "utftex", "latex2text" }

    Pythonの仮想環境でpip install pylatexencとすることでWARNINGがでなくなる

- Snacks.image
  - WARNING setup {disabled}
  - WARNING Missing Treesitter languages: `norg`
  - WARNING Image rendering in docs with missing treesitter parsers won't work
- Snacks.statuscolumn
  - WARNING setup {disabled}
- vim.lsp: Enabled Configurations
  - WARNING Unknown filetype 'markdown.mdx' (Hint: filename extension != filetype).
  - WARNING Unknown filetype 'javascript.jsx' (Hint: filename extension != filetype).
  - WARNING Unknown filetype 'typescript.tsx' (Hint: filename extension != filetype).
- vim.provider:
  - Perl provider (optional) ~
    - WARNING "Neovim::Ext" cpan module is not installed
    - WARNING No usable perl executable found
  - Python 3 provider (optional) ~
    - WARNING No Python executable found that can `import neovim`. Using the first available executable for diagnostics.
    - WARNING Could not load Python :
  - Ruby provider (optional) ~
    - WARNING `ruby` and `gem` must be in $PATH.
- which-key:
  - checking for overlapping keymaps ~
    - WARNING In mode `n`, <g> overlaps with <gx>, <g%>, <g[>, <g]>, <gri>, <gra>, <grn>, <grt>, <grr>, <grx>, <gc>, <gcO>, <gcc>, <gco>, <gO>:
    - WARNING In mode `x`, <i> overlaps with <il>, <ii>, <in>:
    - WARNING In mode `x`, <a> overlaps with <a%>, <al>, <ai>, <an>:
    - WARNING In mode `o`, <i> overlaps with <il>, <ii>, <in>:
    - WARNING In mode `o`, <a> overlaps with <al>, <ai>, <an>:
    - WARNING In mode `n`, <gc> overlaps with <gcO>, <gcc>, <gco>:
