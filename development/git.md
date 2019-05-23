Useful git commands
=================

How to sort local branches by the last commit date
---------------------------------

I'm not very good at keeping my local branch list short and deleting branches not used anymore. As I jump from a branch to branch I can easily forget which branch I was working previously. If you are like me you will find the following command very useful:  

```
gbs='git for-each-ref --sort=committerdate refs/heads/ --format='\''%(HEAD) %(color:yellow)%(refname:short)%(color:reset) - %(color:red)%(objectname:short)%(color:reset) - %(contents:subject) - %(authorname) (%(color:green)%(committerdate:relative)%(color:reset))'\'''
```

> **Tip:** Delete branch as soon as you don't need it.


### Tools

- [Git History](https://githistory.xyz/)