Задание 1
c=a+b = a+b Тут сумма букв а не аргументов
d=$a+$b = 1+2 Сумма аргументов, но вывод в виде "число (знак плюс) число"
e=$(($a+$b)) = 3 Нормальная сумма

Задание 2
#!/bin/bash
while ((1==1))
  do
    curl google.com #https://localhost:4757
    if (($? != 0))
      then
      date >> curl.log
      else exit
    fi
  sleep 1
done

Задание 3
#!/bin/bash
  for i in 192.168.0.1, 173.194.222.113, 87.250.250.242
    do
      ping -c 5 $i >> log.log
    done

Задание 4
#!/bin/bash
array_int=(192.168.0.1 173.194.222.113 87.250.250.242)
  for ((b=1; b<=5; b++))
    do
    for a in ${array_int[@]}
      do
        ping -c 1 $a
        if (($? !=0))
        then
        echo $a >> error.log
        else ping -c 1 $a >> log.log
        fi
      done
    done
