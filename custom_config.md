# Install cscope environment

1. install

apt install cscope 

2. add script

```bash
~$ cat /usr/local/bin/cscope-upd
#!/bin/bash

ctags -R .
cscope -Rbkq
```

3. build tags

run `cscope-upd` in your root of source code tree, then you can use features of *ctags* and *cscope*


# Custom config

add thes lines in .vimrc.custom.config

```
""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
" jason416
""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
""""""""""""""""""""""""""""""""""""""""
"        cscope setting
"""""""""""""""""""""""""""""""""""""""""
if has("cscope")
        set csprg=/usr/bin/cscope
        set csto=1
        set cst
        set nocsverb
        "add any database in current directory
        if filereadable("cscope.out")
                cs add cscope.out
        endif
        set csverb
endif

"""""""""""""""""""""""""""""""""""""""""
"    cscope shotcut key config
"""""""""""""""""""""""""""""""""""""""""
let mapleader = "\\"      " define <leader> as '\'
nmap <leader>s :cs find s <C-R>=expand("<cword>")<CR><CR>
nmap <leader>g :cs find g <C-R>=expand("<cword>")<CR><CR>
nmap <leader>c :cs find c <C-R>=expand("<cword>")<CR><CR>
nmap <leader>t :cs find t <C-R>=expand("<cword>")<CR><CR>
nmap <leader>e :cs find e <C-R>=expand("<cword>")<CR><CR>
nmap <leader>f :cs find f <C-R>=expand("<cfile>")<CR><CR>
nmap <leader>i :cs find i <C-R>=expand("<cfile>")<CR><CR>
nmap <leader>d :cs find d <C-R>=expand("<cword>")<CR><CR>

set notimeout

let &termencoding=&encoding
set fileencodings=utf-8,gbk

"""""""""""""""""""""""""""""""""""""""
"             lcoal set
""""""""""""""""""""""""""""""""""""""
colorscheme monokai
let g:tagbar_left = 1

set fencs=utf-8,ucs-bom,shift-jis,gb18030,gbk,gb2312,cp936
set termencoding=utf-8
set encoding=utf-8
set fileencodings=ucs-bom,utf-8,cp936,gb2312,gbk,gb18030
set fileencoding=utf-8
set mouse=n
"set mouse+=v
set nocompatible
set noignorecase "Not ignore case
set noexpandtab  "Not expand tab as space
set wrap         "Display in newline when words too long to show in one line

"set confirm
"set autoindent
"set cindent
"set smartindent
"set tabstop=4
"set softtabstop=4
"set shiftwidth=4
"set noexpandtab
"set smarttab
"set number
"set history=1000
"set nobackup
"set noswapfile
"set laststatus=2
"set iskeyword+=_,$,@,%,#,-
"set backspace=2
"set fillchars=vert:\ ,stl:\ ,stlnc:\
"set showmatch
"set matchtime=1
```


