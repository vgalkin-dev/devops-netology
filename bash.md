1. ##########################
с === 'a+b' // поскольку обращаемся не к переменным а конкатенируем строки
d === 1+2 // поскольку конкатенируем значения переменных
e === 3 // поскольку приводим типы и работаем с содержимым как с int

2. ##########################
Место заканчивается изза того что логи пишутся постоянно при каждой итерации которая проверяет доступность сервиса, который не работает. Решением является помещение команды break после записи в лог

3. ##########################
# !/bin/bash
declare -i per_item
declare -i
port=80
per_item=5
ip_list=('192.168.0.1' '173.194.222.113' '87.250.250.242')
j=0;
for ip in ${ip_list[@]}
do
    echo $ip
    let i=0
    while [ $i -lt $per_item ]
    do
        target="${ip}:${port}"
	      curl $target
	      "${target} | ${?}" >> curl.log
        let "i+=1"
    done
done

4. ##########################
# !/bin/bash
declare -i per_item
declare -i
port=80
per_item=5
ip_list=('192.168.0.1' '173.194.222.113' '87.250.250.242')
j=0;
for ip in ${ip_list[@]}
do
    echo $ip
    let i=0
    while (1==1)
    do
        target="${ip}:${port}"
	      curl $target
	      if (($? != 0))
	      then
	        $ip >> curl.log
	        break
	      fi
        let "i+=1"
    done
done
