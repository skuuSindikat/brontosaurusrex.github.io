---
layout: page
title: vim learning notes
published: true
---
![vim]({{site.baseurl}}/media/vimClean.png)

## .vimrc

[postbang/blob/master/.vimrc](https://github.com/brontosaurusrex/postbang/blob/master/.vimrc)

## copy/paste

Debian/openbox/urxvt/vim8

    apt install vim-gtk # vim-gtk3
    ctrl+alt+v < should now work to paste stuff from other clipboard, or
    middle-mouse-button < paste behaves differently
    "+p < paste from other clipboard 
    "+gp < this horror should paste as well
    "+yy < copy current line
    "+y20 < copy this and 20 lines below
    :help "+ < actually finds clipboard related help

Possibly worth checking gvim for some ideas and to see what is terminal to blame for and what is vim's fault. This is a huge showstopper.

## spellcheck 

soon.

## tabs
[http://vim.wikia.com/wiki/Using_tab_pages](http://vim.wikia.com/wiki/Using_tab_pages)  

Open multiple files in tabs:

    vim -p one.txt two.txt three.txt

shortkeys in normal mode

    gt < next
    gT < previous
    {i}gt < go to tab at position i

btw

    :e filename < opens file
    :tabe filename < opens file in new tab
    :qall < close all and exit

make each buffer appear in tab

    :tab sball

## buffers

    :buffers or :ls < list buffers
    :bi < jump to buffer i, where i is buffer number
    :bn :bp < next, previous buffer

[Buffers, windows, and tabs](https://sanctum.geek.nz/arabesque/buffers-windows-tabs/)  

## netrw - default dir browser can do a lot

    :Explore
    :Sexplore or :Sex < in horizontal split
    :Vexplore < in vertical split
    :Texplore < in new tab

[configure explorer in .vimrc](https://shapeshed.com/vim-netrw/#netrw-the-unloved-directory-browser)  

## search/replace

    /pattern
    ?pattern < backward
    n N < repeat
    * < search for word under cursor
    :%s/old/new/g < replace
    :%s/old/new/gc < with confirmations

[cheetsheet](http://www.worldtimzone.com/res/vi.html)

## obvious

    gg < goto start of file
    G < goto end of file
    end, home < end, start of line (also 0 and $)
    i, o < insert or insert on next line
    a < insert after selected char
    dw < delete word
    ci+brackets < delete stuff inside brackets
    :w < write
    :wq < write and quit
    :q < quit
    :q! < quit without saving
    di( < delete inside ()

    b < to go to beginning of current or previous word
    w < to go the beginning of next word
    e < to go to the end of current or next word
    ge < to go the end of the previous word
    # Try :h word-motions for more details and how to combine them with operations.

## less obvious

    ggVG < select contents of entire file
    U < selected text to UPPERCASE                                           
    u < selected text to lowercase                                     
    :retab < convert tabs to spaces 

## windows

    :split < horizont
    :vsplit < vertical    
    ctrl+w+j < move down a screen
    ctrl+w+k < up
    ctrl+w+h < left
    ctrl+w+l < right    
    :only < close others

## read/insert a file or command output into current

    :0r !ls < insert output of ls before 0 line
    :0r !head ~/bin/somescript < similar
    :r < below the cursor
    :$r !pwd < below the last line

[http://vim.wikia.com/wiki/Insert_a_file](http://vim.wikia.com/wiki/Insert_a_file)

## snippets

[https://brigade.engineering/sharpen-your-vim-with-snippets-767b693886db](https://brigade.engineering/sharpen-your-vim-with-snippets-767b693886db)

## to shell and back again

    ctrl+z, fg < will push vim to bg, fg in shell will bring it back

[link](http://stackoverflow.com/questions/1879219/how-to-temporarily-exit-vim-and-go-back)

## Debian

vi and vim are the same, they are symbolic links to 

    /usr/bin/vim.basic

vi and vim are the same on OSX as well.

## neovim?

> Neovim is emphatically a fork of Vim in order to leverage the work already spent on thousands of Vim plugins, while enabling new types of plugins and integrations.

[https://geoff.greer.fm/2015/01/15/why-neovim-is-better-than-vim/](https://geoff.greer.fm/2015/01/15/why-neovim-is-better-than-vim/)  
[https://neovim.io/doc/user/vim_diff.html#nvim-features](https://neovim.io/doc/user/vim_diff.html#nvim-features)

User visible differences:

- gt always work in nvim, sometimes fails in vim
- /search is interactive < this could be due to some sort of config difference, anyway seems like a sane deafult
- code coloration is different < again perhaps due to some sort of config ...

### urxvt and neovim

colorschemes defined in .config/nvim/init.vim do not apply well, workaround is to start nvim like 

    nvim -c "colors molokai" # < or make an alias like that

## latest vim on OSX

    brew install vim # brew update && brew upgrade # before that if needed
    # should install in /usr/local/bin/vim
    # do a softlink in user bin if defined and on $PATH, like
    cd $HOME/bin
    ln -s /usr/local/bin/vim vim # that should now call brew installed vim in the future sessions

## vim 8 and plugins

[https://shapeshed.com/vim-packages](https://shapeshed.com/vim-packages)

## books

 - [A Byte of Vim](https://vim.swaroopch.com/)
