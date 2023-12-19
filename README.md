Домашнее задание к занятию 2. «Применение принципов IaaC в работе с виртуальными машинами»

Задача 1
    • Опишите своими словами основные преимущества применения на практике IaaC паттернов.
Непрерывная интеграция позволяет быстро находить ошибки в коде за счет постоянного тестирования небольшими объемами.
Непрерывная доставка также позволяет легко исправить или откатиться на недавнее состояние в случае ошибок.
    • Какой из принципов IaaC является основополагающим?
Получение стабильного и предсказуемого результата каждый раз при использовании(запуске) кода.

Задача 2

    • Чем Ansible выгодно отличается от других систем управление конфигурациями?
Его основные преимущества это использование SSH инфраструктуры без установки дополнительного 
окружения, а также наличие большого количества модулей.
    • Какой, на ваш взгляд, метод работы систем конфигурации более надёжный push или pull?
Думаю тот, что лучше протестирован и проверен в каком-то конкретном окружении.
Но в целом управление push мне кажется более надёжным. В этом случае одновременно получаем 
нужные конфигурации на машинах в нужный момент времени.


Задача 3

$ virtualbox --help | awk '/Oracle/{ print $5 }'
Selector

$ virtualbox --help
Oracle VM VirtualBox VM Selector v6.1.38_Ubuntu
(C) 2005-2022 Oracle Corporation
All rights reserved.

No special options.

If you are looking for --startvm and related options, you need to use VirtualBoxVM.


$ vagrant --version
Vagrant 2.2.6

$ ansible --version
ansible 2.9.6
  config file = /etc/ansible/ansible.cfg
  configured module search path = ['/home/dima/.ansible/plugins/modules', '/usr/share/ansible/plugins/modules']
  ansible python module location = /usr/lib/python3/dist-packages/ansible
  executable location = /usr/bin/ansible
  python version = 3.8.10 (default, Nov 22 2023, 10:22:35) [GCC 9.4.0]
$

Задача 4

$ vagrant ssh
Welcome to Ubuntu 20.04.6 LTS (GNU/Linux 5.4.0-162-generic x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Tue 19 Dec 2023 12:49:38 AM UTC

  System load:  0.0                Users logged in:          0
  Usage of /:   14.4% of 30.34GB   IPv4 address for docker0: 172.17.0.1
  Memory usage: 32%                IPv4 address for eth0:    10.0.2.15
  Swap usage:   0%                 IPv4 address for eth1:    192.168.56.11
  Processes:    143


This system is built by the Bento project by Chef Software
More information can be found at https://github.com/chef/bento
Last login: Tue Dec 19 00:20:53 2023 from 10.0.2.2


vagrant@server1:~$ sudo docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
vagrant@server1:~$














Домашнее задание к занятию 1. «Введение в виртуализацию. Типы и
функции гипервизоров. Обзор рынка вендоров и областей применения»

Задача 1
Паравиртуализации - необходима хостовая OS

Аппаратная - нет прослойки в виде хостовой OS. У гостевых OS доступ к ресурсам
напрямую.

Виртуализации на основе ОС - OS запускается в контейнерах.

Задача 2
Для WEB лучше виртуализация на основе ОС (контейнеры), легче достигается
масштабирование и регулировка нагрузки.

Для высоконагруженны баз данных подойдет аппаратная виртулизация, тк. можно
выделить максимум аппартаных ресурсов и обеспечить резервное копирование.

Для Windows систем, можно разместить на HYPER-V.

Для системы, выполняющич высокопроизводительные расчёты на GPU, можно разместить
на аппартаной виртулизации, т.к. можно задействовать максимум ресурсов.

Задача 3

1. vSphere ESXI - подойдет для данного сценария

2. PROXMOX - бесплатно, производительная, достаточно простая в управлении,
возможность автоматического резервного копировани1 виртуальных машин.

3. Hiper-V - без графики. Бесплатно, достатчно простая в упрвлении.

4. Docker - позволяет достаточно просто создавать контейнеры.

Задача 4
Неоднородность гетерогенной среды виртуализации требует более трудозатрат на
поддержку инфраструктуры инсталляциеии и настроек (могут быть очень разые подходы
для осуществления одно и той же задачи).
Полноценная поддрежка может затрудненна если не будет необходимых специалистов.
Я бы выбирал гомогенную среду (т.к. навыки специалистов,специалистов будет более
развиты в одном направлении и думаю приобретение будет дешевле, чем у разных вендоров)
















# devops-netology
Будут проигнорированы:
**/.terraform/*
поддиректория .terraform и все все директории и файлы ниже

*.tfstate
*.tfstate.*
все файлы с расширением .tfstate и файлы содержащие .tfstate.

crash.log
crash.*.log
все файлы crash.log и файлы начинающиеся с crash. и расширением .log

*.tfvars
*.tfvars.json
все файлы с расширением .tfvars и заканчивающиеся на .tfvars.json

override.tf
override.tf.json
*_override.tf
*_override.tf.json

все файлы override.tf, override.tf.json, все файлы вида aaa_override.tf и
bbb_override.tf.json

.terraformrc
terraform.rc
Будут проигнорированы все файлы terraform.rc и заканчивающиеся на .terraformrc

# !example_override.tf
Закоментировано, но если бы нет, то не будет игнорироваться, если бы был
соответствующий шаблон на игнорирование.
