---
tags: [VIM,Resource]
aliases: []
---
## Configuration Hierachy
```plain-text
.vim/
├─ pack/
│  ├─ demo-package/
│  │  ├─ start/
│  │  │  ├─ plugin1/
│  │  │  │  ├─ plugin
│  │  ├─ opt/
│  │  │  ├─ plugin2/
│  │  │  │  ├─ plugin
```

> `pack` is the folder containing different package . One package directory contains different plugin.
> While `start` is a special directory which loads the plugin under it when vim starts. The plugins under `opt` need to be loaded manually by typing `packadd {pack-name}`

## Script
- You can manually type `:source {path}` to add the script 

## Plugin
- Plugin is a directory with the name of Plugin and there will be scripts under `plugin` subfolder
- Installing a plugin means adding them into the 'runtime path'
	- Manually type `:set runtimepath+=$VIMCONFIG/arbitrary/demo-plugin`
 
## Packages
- Packages is a directory containing different Plugins
- By convention , we create package within a `$VIMCONFIG/pack` directory
- Package will contain a subfolder `start` , the directory containing the plugins that will be loaded when vim is started
>When vim starts , it will searches for plugins under `$VIMCONFIG/pack/*/start` directory , then vim will iterate through the plugins and source the scripts under them. Putting the Plugins under Package is same as installing them

### Indexing Documentation of Plugin
- When the Plugin is newly installed , `helptags` helps building the tags index under the document
	- `:helptags ALL` generate all tags of all Plugins
	- `:help {plugin-name}` to see the document
	- We can enter `CTRL ]` to jump anchor and `CTRL o` to come back

### How to install Plugin
- pull the Plugin git under `$VIMCONFIG/pack/*/start` if you want to load it when vim starts
- otherwise pull it under `$VIMCONFIG/pack/*/opt` , this `opt` folder is for optional Plugins
	- They need to be add manually by `packadd {pack-name}`	

### Minpac built-in package manager 
- Minpac is a minimal package manager that builds on top of Vim's new packages features
	- Therefore minpac has the least codebase but may not offer all features mature compared to other package manager
- We should first create a package directory called `minpac` because minpac plugin will pull the plugin under this package directory
	- This `minpac` package directory is used to contain the plugins minpac grasps
- To use minpac , we need to create the `~/vimrc` and add `packadd minpac`.  Since the minpac should be put under `minpac/opt` folder otherwise `packadd` can't be used
- then add `call minpac#init()` to initialize the package 
- To register *PLUGINs* with your minpac package , add `call minpac#add('authorname/name_plugin', {'type':'opt'})` , if you want to add to `opt` folder
- To download the plugins use `call minpac#update()`
- To make minpac manages itself , use `call minpac#add('k-takata/minpac', {'type' : 'opt'}`
