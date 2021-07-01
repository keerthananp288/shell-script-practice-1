# shell-script-practice-1
only for documentation purpose

#grep usage
ps -ef | grep -i /lib/systemd/

ps -ef | grep -i  /lib/systemd/ | grep -v grep | awk '{print $1}'

grep "^[0-9]

grep -v "^[0-9]

#uptime usage
uptime

uptime | sed -n -e 's/^.*average://p'

uptime | sed -n -e 's/^.*average://p' | awk -F '.' '{print $1}'

#awk
uptime | awk -F ',' '{print $1}'

ls -l | awk '{print $1}'


ls -l | awk '{print $1, "-->" , $3}'

#sed
df -h | sed -n '1!p'

#if usage
uptime_op = 'uptime'
uptime_rc = $?
if [ $uptime_rc -eq 0 ]: then
echo "$uptime_op"
fi

#for loop
load_avg='uptime'
for i in $load_avg;
do
x=$x+$i
done
load_avg=x/3
if [ "$load_avg" <10 ]:
then
echo "normal"
else
echo "not normal"
fi

for item in *
do
if [ -f $item]:
then
echo "$item"
fi
done

#while loop
x=1
while [$x-le5]
do
echo "welcome $x times"
x= $(($x+1))
done


#load avg
top -b -n 1|grep "cpu(s)"

#disk utilization
iostat -xtc | sed -n -e '/device/,$p'

#file sys utilization
df -h | sed -n '1!p'


#arithmetic operation
a=30 b=13
echo `expr $a + $b`
echo `expr $a - $b`
echo `expr $a \* $b`
echo `expr $a % $b`
