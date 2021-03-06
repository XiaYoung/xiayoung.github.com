---
layout : post
category : D Developing Tools
tags : [Git]
---

[learnGit](http://pcottle.github.io/learnGitBranching/)

# main  

---

### git commands  

* commit  
* branch  
* checkout  
* cherry-pick  
* reset  
* revert  
* rebase  
* merge  

### Introduction Sequence

1. commits
2. branching
3. merging  
	合并commits,合并后的commit有多个parents
4. rebase  
	复制commits,只有一个parent  
	好处：让commit tree十分干净，全是直线
	坏处：会改变commit tree的history.例如：c1原来在c3之前，可以被rebase到c3之后变成c1'  

### Ramping Up

1. Detach yo' HEAD commit hash
2. Reletive refs (^)
3. Reletive refs#2 (~)
4. Reversing changes in Git

### Moving Work Around

1. Cherry-pick 
2. Interactive rebase  
	`git rebase -i HEAD~4 --aboveAll`

### A Mixed Bag

1. Grabbing just 1 commit
2. Juggling Commits  
	`git commit --amend`  
	`git rebase branch1 branch2`  
	将branch2放在branch1之上，HEAD在branch2
3. Juggling Commits#2		
4. Git Tags  
	`git tag v1 C1`
5. Git Describe  
	`git describe <ref>`  
	`<tag>_<numCommits>_g<hash>`

### Advanced Topics

1. multiple rabasing
2. multiple parents  
	`git HEAD^2`  
	选择第二个分支  
	`git HEAD~^2^`  
	连续试用操作符  
3. branch spaghetti

# Remotes

---

### commands

* clone
* fetch
* pull
* push

### Push & Pull -- Git Remotes

1. clone
2. remote branches  
	`origin/master  
	<remote name>/<branch name>`    
	origin/master will only update when the remote updates.  
3. git fetchin'  
	从云端下载本地没有的东西
4. git pullin'  
	`git pull`  
	相当于  
	`git fentch  
	git merge`  
	下载，并跟本地合并
5. fake teamworking
6. pushin'  
	将本地上传，并让云端合并。前提是 本地的origin/master 和 云端的master在同一个位置。  
	若云端的master已经update了，将push失败。
7. diverged history

### To Origin And Beyond -- Advanced Git Remotes!

1. push master
2. merging with remotes
3. remote tracking  
	`git checkout -b foo o/master`  
	`git branch -u o/master foo`  
	手动指定 remote-tracking  
	具有 remote-tracking 的 branch 才能push和pull  
4. git push arguments  
	`git push <remote> <place>`  
	无视where we are checked out  
5. git push arguments -- expanded!  
	`git push origin <source>:<destination>`  
	destination如果在remote上不存在，将会被创建  
6. Fetch arguments  
	`git fetch origin foo`
7. source of nothing  
	`git push origin :foo`  
	将删除remote上的foo  
	`git fetch origin :bar`  
	将在本地创建一个新的branch bar
8. pull arguments  

---

## markdown tips

1. 标题 和 block 前后都要空一行  
2. 换行的时候，行尾要加至少2个空格  

## words I don't know

1. That's why most commits have **ancestor** commits above them -- we **designate** this with arrows in our visualization.
**ancestor： 祖先**  

2. Commits are very lightweight and switching between them is **wicked** fast!    
3. Branches in Git are **incredibly** lightweight as well.
4. This is why many Git **enthusiasts chant** the **mantra**: branch early , and branch often.
5. Because there is no storage / memory overhead with making many branches, it's easier to logically divide up your work than have big **beefy** branches.
6. For now though, just remember that a branch **essentially** says "I want to include the work of this commit and all parent commits."
7. Rebasing essentially takes a set of commits, "copies" them, and **plops** them down somewhere else.
8. **asterisk** 星号 *
9. Once you're comfortable moving around. your powers with other git commands will be **amplified**!
10. Here we will **reveal** HEAD before and after a commit.
11. HEAD was hiding **underneath** our master branch all along.底层地
12. **Detaching** HEAD just means attaching it to a commit instead of a branch.
13.  **caret** 符号 ^
14. **tilde** 符号 ~
15. The next concept we're going to cover is "moving work around" -- in other words, it's a way for developers to say "I want this work here and that work there" in **precise**, **eloquent**, flexible ways.    
16.  You can choose to completely **omit** some commits.
17. This is designated by `pick` -- **toggling** `pick` off means you want to drop the commit.
18.  I'm trying to track down a bug but it is quite **elusive**.
19. Lastly, pay attention to the goal state here -- since we move the commits twice, they both get an **apostrophe** appended. 撇号
20. Branches are easily **mutated**, often temporary, and always changing.
21. The difficulty comes in when the history of the repository **diverges**. 
22. This level is pretty **hefty**.
23. Some developers love to **preserve** history and thus prefer merging.
24. This is commonly referred to as a **colon refspec**.
