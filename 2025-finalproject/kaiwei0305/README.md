# 课程学习自述

## 一、ubuntu系统的安装
初次接触ubuntu，最先遇到的问题是BIOS页面与教程页面的差异，一边在百度搜索，一边在ai询问，在经过一个下午，终于安装好ubuntu系统，在一系列的
初始化设置后，通过 CTRL+ALT+T 正式开始了linux系统的探索。

## 二、Shell，vim脚本的学习
1.在文件操作学习中，我掌握了空文件创建、目录内容查看的基本技能。
例如：
```bash
man touch
touch /tmp/missing/semester
ls /tmp/missing

ls -a
ls -t
ls -h
ls --color=auto
```
2.Shell脚本编写是课程的一大难点，却也是收获最丰的部分。我尝试编写了包含循环、条件判断与日志记录的脚本，过程中语法错误频出，但通过反复调>试最终实现功能。这个过程让我深刻体会到脚本自动化的魅力。
例如：
```bash
#!/usr/bin/env bash
count=0
last_n=0
log_file="/tmp/missing/script_log.txt"
> "$log_file"
echo "脚本开始运行，日志将记录到 $log_file" | tee -a "$log_file"
while true; do
    n=$((RANDOM % 100))
    count=$((count + 1))
    last_n=$n
    echo "第 $count 次运行，当前n的值为：$n" | tee -a "$log_file"
    if [ $n -eq 42 ]; then
        echo "Error occurred." | tee -a "$log_file"
        echo "Cause by sth." >&2 | tee -a "$log_file"
        echo "-===== 出错信息汇总 =====-" | tee -a "$log_file"
        echo "出错前共运行了 $((count - 1)) 次" | tee -a "$log_file"
        echo "最后一次正常运行的n值为：$last_n" | tee -a "$log_file"
        exit 1
    fi
    echo "Everything is ok." | tee -a "$log_file"
    echo "-------------------------" | tee -a "$log_file"
done
```
3.此外还学习了通过学习系统文件查看，以此来获取电池容量、系统温度等信息。
例如：
```bash
cat /sys/class/power_supply/BAT0/capacity
cat /sys/class/thermal/thermal_zone0/temp
echo "$(( $(cat /sys/class/thermal/thermal_zone0/temp) / 1000 )) °C"
```

## 三、Linux系统架构、命令行环境与数据整理
1.程序从暂停进程到后台运行，再到查找与终止进程，每一步操作都加深了我对程序运行机制的理解。
例如：
```bash
sleep 10000
^Z
bg
pgrep -af sleep
pkill -f sleep
```
2.为提升操作效率，我学习了别名设置与历史命令分析。
例如：
```bash
alias dc='cd'
history | awk '{$1="";print substr($0,2)}' | sort | uniq -c | sort -n | tail -n 10
pwd
dc /home/kaiwei
```
3.Sed命令让我掌握了文本替换技巧，但也遭遇了文件被清空的“陷阱”。这段经历让我明白，使用命令时需充分理解执行逻辑，避免数据丢失。
例如：
```bash
man sed
echo "good" > test.txt
cat test.txt
sed 's/good/bad/' test.txt > test.txt
# 此时文件被清空，原因是Shell先截断输出文件再读取，导致内容丢失
echo "good" > test.txt
sed -i 's/good/bad/' test.txt
cat test.txt
```
4.日志分析的学习让我学会用awk处理复杂文本数据，从系统启动日志中提取并计算平均启动时长、中位数和最长时长。
例如：
```bash
journalctl --list-boots | tail -10 | awk '
function to_unixtime(date_str) {
    sub(/^[A-Za-z]{3} /, "", date_str)
    split(date_str, d, /[-: ]/)
    return mktime(d[1]" "d[2]" "d[3]" "d[4]" "d[5]" "d[6])
}
{
    start_str = $4 " " $5 " " $6
    end_str = $7 " " $8 " " $9
    start = to_unixtime(start_str)
    end = to_unixtime(end_str)
    duration = (end - start) / 60
    print duration
}
' | sort -n | awk '
#以下省略
```

## 四、Git命令
1.从本地仓库初始化到提交历史追踪，我逐步掌握了 Git 的核心工作流。通过git init创建仓库、git add暂存变更、git commit固化版本,git remote关>联远程地址，git push将本地代码同步到云端。

## 五、总结与展望
从对Linux命令行一无所知，到能熟练进行文件操作、编写脚本、分析系统信息与日志，每一次命令的成功执行、每一个脚本的调试完成，都让我收获满满>。未来，我将继续深入学习Linux高级功能，把这些技能运用到实际项目中，不断提升技术能力。
