# Sugar++ Neovim theme setup
Welcome to this simple guide on how to use the [Neovim](https://neovim.io) syntax highlighting plugin for [sugar++](https://github.com/REBORN-lang/sugarpp) syntax highlighting.

**1. Setup file structure**
- From your `~` (_home_) directory
- Navigate to the `.config/nvim/` directory with the following command: \
`$ cd .config/nvim/`
- Create directories `syntax` and `ftdetect` with the following command: \
`$ mkdir syntax ftdetect`

**2. Add files**
- Navigage inside `syntax/` with the following command: \
`$ cd syntax`
- Create a file named `spp.vim` with the following command: \
`$ touch spp.vim` \
And add the following contents to said file:
```lua
" syntax/spp.vim — syntax highlighting for .spp (sugar++)

if exists("b:current_syntax")
  finish
endif

" load full C++ syntax
runtime! syntax/cpp.vim

" sugar++ keywords
syntax keyword sugarppKeyword main let include
syntax keyword sugarppCtrl if else elif while for switch

" highlight sugar++ keywords
highlight link sugarppKeyword Statement
highlight link sugarppCtrl Conditional

" mark this buffer as sugar++ syntax
let b:current_syntax = "spp"
```
- Now go back to `~/.config/nvim/` with the following command: \
`$ cd ..`
- Navigate into `ftdetect/` with the same command as last time
- Create a file named `spp.vim` and add the following contents to said file:
```vim
au BufRead,BufNewFile *.spp set filetype=spp
```
### Done!
