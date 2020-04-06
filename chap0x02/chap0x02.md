## 实验：From GUI to CLI
### 一、asciinema 安装和配置：  
```
sudo apt-get install asciinema
asciinema auth
#账号关联过程
asciinema rec
#录制过程
exit
```
### 二、vimtutor操作录像
##### lesson1：  
[![asciicast](https://asciinema.org/a/66NGsmdMJMc2EGLaHLjf06RPl.png)](https://asciinema.org/a/66NGsmdMJMc2EGLaHLjf06RPl4)
##### lesson2：  
[![asciicast](https://asciinema.org/a/YyyZB0y9lE7NwAtdTi4HrrOqi.png)](https://asciinema.org/a/YyyZB0y9lE7NwAtdTi4HrrOqi)  
##### lesson3：  
[![asciicast](https://asciinema.org/a/ySbK1t3r4cT1wp2Myw36BUXmE.png)](https://asciinema.org/a/ySbK1t3r4cT1wp2Myw36BUXmE)  
##### lesson4：  
[![asciicast](https://asciinema.org/a/p2yVDvbwDKg2zXQPSG8x8gdti.png)](https://asciinema.org/a/p2yVDvbwDKg2zXQPSG8x8gdti)
##### lesson5：  
[![asciicast](https://asciinema.org/a/KBe6AVyCcB2crqbZW4tF3ve0g.png)](https://asciinema.org/a/KBe6AVyCcB2crqbZW4tF3ve0g)
##### lesson6：  
[![asciicast](https://asciinema.org/a/psg6IXLs2OtMmoabfZgD39bCT.png)](https://asciinema.org/a/psg6IXLs2OtMmoabfZgD39bCT)
##### lesson7：  
[![asciicast](https://asciinema.org/a/F8zP7XnYPplGBHQaI7Lr3yfCJ.png)](https://asciinema.org/a/F8zP7XnYPplGBHQaI7Lr3yfCJ)
  
### 三、VIMTUTOR完成后的自查清单
##### 1. 你了解vim有哪几种工作模式？
* Normal
* Insert
* Visual
* Replace
##### 2. Normal模式下，从当前行开始，一次向下移动光标10行的操作方法？如何快速移动到文件开始行和结束行？如何快速跳转到文件中的第N行？
* 一次向下移动光标10行 ：```10j```
* 移动到文件开始行: ```gg```   结束行：```G```
* 快速跳转到文件中的第N行：```NG```
##### 3. Normal模式下，如何删除单个字符、单个单词、从当前光标位置一直删除到行尾、单行、当前行开始向下数N行？
* 删除单个字符：```x```
* 删除单个单词：```dw```
* 删除到行尾：```d$```
* 删除单行：```dd```
* 删除向下数N行：```Ndd```
##### 4. 如何在vim中快速插入N个空行？如何在vim中快速输入80个-？
* 快速插入N个空行：```No``` （在光标下方插入） ```NO```(在光标上方插入)
* 快速输入80个-：```80i-```
##### 5. 如何撤销最近一次编辑操作？如何重做最近一次被撤销的操作？
* 撤销最近一次编辑操作：```u```
* 重做最近一次被撤销的操作：```CTRL+R```
##### 6. vim中如何实现剪切粘贴单个字符？单个单词？单行？如何实现相似的复制粘贴操作呢？
* 剪切单个字符：```x```
* 剪切单个单词：```dw```
* 剪切单行：```dd```
* 复制单个字符：```y```
* 复制单个单词：```yw```
* 复制单行：```yy```
* 剪切或者复制之后粘贴都是 ```p```
##### 7. 为了编辑一段文本你能想到哪几种操作方式（按键序列）？
* 从当前字符之前开始编辑：```i```
* 从当前字符之后开始编辑：```a```
* 在光标所在行的行末之后插入文本：```A```
* 删除字符：```x```
* 删除：```d motion```（```w```删到单词起始 ```e```删到当前单词末 ```$```删到行末）
* 替换字符：```r+要替换字符```
* 更改：```c motion```（同上）
* 字符串全文替换：```:%s/old/new/g```
##### 8. 查看当前正在编辑的文件名的方法？查看当前光标所在行的行号的方法？
* 都是```CTRL+G```
##### 9. 在文件中进行关键词搜索你会哪些方法？如何设置忽略大小写的情况下进行匹配搜索？如何将匹配的搜索结果进行高亮显示？如何对匹配到的关键词进行批量替换？
* 关键词搜索：
   * 从前往后查找 ```/keyword``` 
   * 从后往前查找 ```?keyword```
* 设置忽略大小写匹配搜索：```:set ic```
* 对匹配的搜索结果进行高亮显示: ```:set hls is```
* 关键词进行批量替换：```:%s/old/new/g```
##### 10. 在文件中最近编辑过的位置来回快速跳转的方法？
* 较旧位置：```Ctrl+i```
* 较新位置：```Ctrl+o```
##### 11. 如何把光标定位到各种括号的匹配项？例如：找到(, [, or {对应匹配的),], or }
* 将光标置于待匹配的括号处+```%```
##### 12. 在不退出vim的情况下执行一个外部程序的方法？
* ```:!+外部命令```
##### 13. 如何使用vim的内置帮助系统来查询一个内置默认快捷键的使用方法？如何在两个不同的分屏窗口中移动光标？
* 查询一个内置默认快捷键:  ```: help +快捷键```
* 在两个不同的分屏窗口中移动光标：```: Ctrl+w```
