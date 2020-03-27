# Git學習筆記

## alias

### add
把檔案加到暫存區，加上`--all`參數就是全部檔案都加上。 

```
git add --all
```

### branch
列出、生成或刪除分支。  
#### `-r`和`-a`/`--all`
`-r`參數會列出遠端分支。  
`-a`參數會列出本地和遠端分支。  
```
git branch -a
```
#### `-d`、`-D`或`--delete`
把一個分支刪除掉。不過可用`reflog`找回。  

#### `-v`和`-vv`  
`-v`會顯示sha1和commit主指。  
`-vv`, print the path of the linked worktree (if any) and the name of the upstream branch。還不會翻譯。

### commit
#### `--amend`
可以修改最後一次提交。更早的修改用`rebase`

## .git/info
### .git/info/exclude
相當於.gitignore，不過不會加到提交中。

## [Git Hooks](https://git-scm.com/book/zh-tw/v2/Customizing-Git-Git-Hooks)
1. `.git/hooks`資料夾中有一堆sample，複製pre-commit.sample成pre-commit。
2. echo test > 測試.txt
3. git add 測試.txt
4. git commit -m "Test"會報錯，commit也不成功，因為中文名的檔案觸發了pre-commit中的錯誤。
5. 試試改改pre-commit看。



## 工具
### [gitignore.io](https://docs.gitignore.io/install/command-line)
```
git config --global alias.ignore \
'!gi() { curl -sL https://www.gitignore.io/api/$@ ;}; gi'
```
