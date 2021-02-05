# vim-java-decompiler
Vim can read Java class file use by decompiler Jar file

## Quick Start
1. Download Decompiler Jar
```bash
curl 'https://github.com/t0239184/vim-java-decompiler/raw/master/cfr_0_115.jar' --create-dirs -o ~/.vim/java_decompiler/cfr_0_115.jar 
```
2. Download shell file
```bash
curl 'https://raw.githubusercontent.com/t0239184/vim-java-decompiler/master/get-class-from-jar.sh' -o ~/.vim/java_decompiler/get-class-from-jar.sh
```
3. Append this script to .vimrc
```vim
" Java Decompiler
au BufRead *.class call SetClassOptions()
function SetClassOptions()
  silent %!~/.vim/java_decompiler/get-class-from-jar.sh %
  set readonly
  set ft=java
  silent normal gg=G
  set nomodified
endfunction
```
