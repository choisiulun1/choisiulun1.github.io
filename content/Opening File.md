---
tags: [Modern VIM]
aliases: []
---
> Opening files is one of the most common tasks you will perform when coding. Vim's built-in funcitonality gives you basic commands for opening any readable file by specigying its filepath. Tab-completion can save you from typing every character of a filepath , but you may end up with many keystrokes to locaate the file you want. There are some techniques for opening files with less effort

```ad-note
This note uses Junegunn Choi’s excellent fzf tool. 
This consits of two parts: 
1. A standalone fzf program , which you can run in your shell
2. A Vim plugin, which depends upon the external program.
> Github: https://github.com/junegunn/fzf
```

## Install the independent program
```shell
$VIMCONFIG/pack/bundle/start/fzf/install --bin
```
- You will need to make sure that the bin directory is in your `$PATH`
	- add `export PATH=$PATH:$VIMCONFIG/pack/bundle/start/fzf/bin` to bash
- After sucessfully add it , `fzf --help` should be worked
- To use the plugin in vim , type `:FZF`
	- This open the fzf picker interface , if you want to dismiss it , type `<C-c>`
- The book suggests that we can add a mapping to vimrc to conveniently use the FZF
	- by adding `nnoremap <C-p>:<C-u>FZF<CR>`
		- In fact you can observe there is a `<C-u>` in the begining :
		- ![[Why do some Vim mappings include <C-u> after a colon#^11e3ac]]

## Finding files Using Fizzy Path Matching
- Use the fzf picker interface to search the files
	- for example , search for `table-of-contents.js` , you can type `tocj`
	- for a tup , you can use `<C-v>` to open the selected file in a vertical split

### How Does Fuzzy Matching Work
- You can provide a query to filter the list under the directory
- When you type `t` at the prompt , the list is filtered to only include file paths containing that letter. With the query `to` , `t` and `o` need to be <mark style="background: #ABF7F7A6;">in order</mark> but they don't have to be <mark style="background: #ABF7F7A6;">adjacent to each other</mark>
- As well as filtering the list of matches , the fuzzy finder also sorts the results using a ranking algorithm
- ![[Pasted image 20221227151854.png]]

### Operating the fzf interface
- There are two strategy to select the file you want
	- First , keep refining your query until your file is on the top of the result
	- Another way is to use `<C-k>` to change the selection
- `<CR>` actually triggers vthe default action on the selected item in the fzf interface
	- In this cae , it means to open the file in the current window
	- You can also use `<C-x>` | horizontal , `<C-v>` | vertical , `<C-t>` | new tab
### Fuzzy Finding Other Sources
- Actually you can also apply fzf to other sources. Sources is a terminology that is the list you feed to the fzf. After performing , the result is called <mark style="background: #ABF7F7A6;">sink</mark>.


- [[Nontrivial synthesized default constructor]]