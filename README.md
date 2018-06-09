# termux-config
## 1.Termux是什么
> Termux is a terminal emulator and Linux environment bringing powerful terminal access to Android.  

__```获取Termux:```__  [_酷安_](http://www.coolapk.com/apk/com.termux)  
## 2.为Termux更换国内镜像源
> 由于一些原因，Termux本身自带的镜像源在国内并不是很快。所以为其更换为国内源则很有必要

更换为[清华大学镜像源](https://mirrors.tuna.tsinghua.edu.cn/help/termux/)方法：  

- __使用HTTP服务方式：__  
  1.使用 ```apt edit-sources```  
    - 如果提示  
```
$ apt edit-sources E: Sub-process editor returned an error code (100)
```
则需要设置一下```$EDITOR```  
```
export EDITOR=vi  
apt edit-sources
```  

  2.将里面的内容替换为如下  
```
# The termux repository mirror from TUNA:
deb [arch=all,arm] http://mirrors.tuna.tsinghua.edu.cn/termux stable main
```
  - 由于CPU类型不同，[]里内容会区别，参照原配置修改
  - 如果对于文件原先内容有所顾忌，不想删除，可以在原文件前方加上“#”注释



- __使用HTTPS服务方式：__  
  1.首先需要安装如下包  
```
apt install apt-transport-https
```  
2.余下步骤则参考上方HTTP配置方式  
  - 但替换内容则改为如下  
```
# The termux repository mirror from TUNA:
deb [arch=all,arm] https://mirrors.tuna.tsinghua.edu.cn/termux stable main
```
