# myalias
关于linux和dos下的一些常用的alias

## linux下的假名

### 自定义的假名

```
alias grep='grep --color'
alias mysqlt='mysql -hrm-wz99533o97cxwt7d5.mysql.rds.aliyuncs.com -uchief2016 -pYong813211'
alias mysqlc='mysql -u chief2016 -p -h rm-wz99533o97cxwt7d5.mysql.rds.aliyuncs.com -D invoicing<'
alias ctomcat='cd /usr/local/tomcat/twdrp-tomcat-8.0.30'
alias redis-cli='cd /usr/local/redis/redis-3.2.6/src;./redis-cli -h r-wz9d0e141641e1a4.redis.rds.aliyuncs.com'
alias ..='cd ..'

```
1. 在$HOME下加入自己的.alias文件
2. 在$HOME/.bash_profile或.bashrc中加入语句：

```
if [ -f ~/.alias ]; then  
    . ~/.alias  
fi
```
### 根据文件类型解压 
```
#根据文件类型解压  
extract(){  
if [ -f $1 ]; then  
         case $1 in  
             *.tar.bz2)   tar xjf $1        ;;  
             *.tar.gz)    tar xzf $1     ;;  
             *.bz2)       bunzip2 $1       ;;  
             *.rar)       unrar e $1     ;;  
             *.gz)        gunzip $1     ;;  
             *.tar)       tar xf $1        ;;  
             *.tbz2)      tar xjvf $1      ;;  
             *.tgz)       tar xzvf $1       ;;  
             *.zip)       unzip $1     ;;  
             *.Z)         uncompress $1  ;;  
             *.7z)        7z x $1    ;;  
             *)           echo "'$1' cannot be extracted via extract()" ;;  
         esac  
else  
         echo "'$1' is not a valid file"  
fi  
}
```

## dos下的假名

1. 关闭所有在运行的CMD窗口
2. 创建文件C:\cmd-alias.bat，包含以下内容：
```
doskey sayhello=echo Hello $*
doskey cattxt=type xxxxxxxxxxxx.txt $*
@doskey ls=dir /b $*
@doskey l=dir /od/p/q/tw $*
```
> - doskey就相当于Linux中的alias，
>- $*表示这个命令还可能有其他参数，
>- @表示执行这条命令时不显示这条命令本身
>- 第二个命令type xxxxxxxxxxxx.txt的作用是读取txt文件内容并打印到屏幕，等同于Linux下的cat

3. 使用Win+R，输入regedit进入注册表，找到HKEY_LOCAL_MACHINE\Software\Microsoft\Command Processor，右键新建，字符串值，名为AutoRun，值为C:\cmd-alias.bat，保存退出。
4. 打开CMD，即可享受自定义命令

### 常用假名

```
doskey sayhello=echo Hello $*
doskey cattxt=type $*
doskey su=net user Administrator
doskey cp=copy source
doskey rm=del /Q
doskey diff=fc /w $*
@dockey tree=tree /f
@doskey ls=dir /b $*
@doskey l=dir /od/p/q/tw $*
```
