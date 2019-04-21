## Laboratory work I

Данная лабораторная работа посвещена изучению утилит для разработки проектов

## Tasks

- [X] 1. Ознакомиться со ссылками учебного материала
- [X] 2. Выполнить инструкцию учебного материала
- [X] 3. Составить отчет и отправить ссылку личным сообщением в **Slack**

## Tutorial
Создание переменных окружения 'GITHUB_USERNAME и 'GIST_TOKEN , а также связывание команды edit с вызовом текстового редактора nano



# Присвоение переменной GITHUB_USERNAME имени пользователя на Github
$ export GITHUB_USERNAME=hijadelaluuna
$ export GIST_TOKEN=<сохраненный_токен>
$ alias edit=nano


Создание директории рабочей директории **workspace.

$ sudo mkdir -p $hijadelaluuna/workspace # создание директории workspace
$ cd $hijadelaluuna/workspace # переход к директории
$ pwd # полный путь до директории workspace
luna /workspace 
$ cd .. # переход выше
$ pwd
/home/luna


# Создание дочерних директорий в каталоге workspace

$ mkdir -p workspace/tasks/
$ mkdir -p workspace/projects/
$ mkdir -p workspace/reports/
$ cd workspace
$ls node  projects  reports  scripts  tasks


Установка *nodejs в рабочий каталог

# Archlinux
$ wget https://nodejs.org/dist/v6.11.5/node-v6.11.5-linux-x64.tar.xz
$ tar -xf node-v6.11.5-linux-x64.tar.xz
$ rm -rf node-v6.11.5-linux-x64.tar.xz
$ mv node-v6.11.5-linux-x64 node


Добавление nodejs в переменную среды 'PATH

$ ls node/bin # Просмотр содержимого каталога node/bin
gistup  gistup-open  gistup-rename  node  npm

$ echo ${PATH}
/usr/local/sbin:/usr/local/bin:/usr/bin:/usr/local/go/bin:/usr/lib/jvm/default/bin:/usr/bin/site_perl:/usr/bin/vendor_perl:/usr/bin/core_perl:/home/luna/010editor:/usr/local/src/go/bin

$ export PATH=${PATH}:`pwd`/node/bin

$ echo ${PATH}
/usr/local/sbin:/usr/local/bin:/usr/bin:/usr/local/go/bin:/usr/lib/jvm/default/bin:/usr/bin/site_perl:/usr/bin/vendor_perl:/usr/bin/core_perl:/home/luna/010editor:/usr/local/src/go/bin:/home/luna/workspace/node/bin
$ mkdir scripts
$ cat > scripts/activate<<EOF
export PATH=\${PATH}:`pwd`/node/bin
EOF
$ source scripts/activate # Исполнение содержимого файла как набора команд

Установка утилиты **Gistup для создания 'Gist

$ sudo pacman -S npm # установка npm
$ npm install -g gistup # установка Gistup
$ ls node/bin

Создание файла '.gistup.json, где находится 'gist token

$ cat > ~/.gistup.json <<EOF
{
  "token": "${GIST_TOKEN}"
}
EOF


## Report
Cоздание отчета по лабораторной работе 1

$ export LAB_NUMBER=01 # Добавление переменной с номером лабораторной работы
# Клонирование репозитория  в директорию tasks/lab01
$ git clone https://github.com/tp-labs/lab01 tasks/lab01 
$ mkdir reports/lab01 # Создание директории
$ cp tasks/lab01/README.md reports/lab01/REPORT.md # Копирование файла в каталог
$ cd reports/lab01 # Переход в каталогreports/lab01
$ edit REPORT.md # Редактирование файла с помощью nano
# Создание gist
$ gistup -m "lab01" # enter: yes↵ 



## Links

### Unix commands

- [ar](https://en.wikipedia.org/wiki/Ar_(Unix))
- [cat](https://en.wikipedia.org/wiki/Cat_(Unix))
- [cd](https://en.wikipedia.org/wiki/Cd_(command))
- [cp](https://en.wikipedia.org/wiki/Cp_(Unix))
- [cut](https://en.wikipedia.org/wiki/Cut_(Unix))
- [echo](https://en.wikipedia.org/wiki/Echo_(command))
- [env](https://en.wikipedia.org/wiki/Env_(shell))
- [ex](https://en.wikipedia.org/wiki/Ex_(editor))
- [file](https://en.wikipedia.org/wiki/File_(command))
- [find](https://en.wikipedia.org/wiki/Find)
- [ls](https://en.wikipedia.org/wiki/Ls)
- [man](https://en.wikipedia.org/wiki/Man_page)
- [mkdir](https://en.wikipedia.org/wiki/Mkdir)
- [mv](https://en.wikipedia.org/wiki/Mv)
- [nm](https://en.wikipedia.org/wiki/Nm_(Unix))
- [ps](https://en.wikipedia.org/wiki/Ps_(Unix))
- [pwd](https://en.wikipedia.org/wiki/Pwd)
- [rm](https://en.wikipedia.org/wiki/Rm_(Unix))
- [sed](https://en.wikipedia.org/wiki/Sed)
- [touch](https://en.wikipedia.org/wiki/Touch_(Unix))

### Package Managers

- [apt](http://help.ubuntu.ru/wiki/apt) | [dnf](https://en.wikipedia.org/wiki/DNF_(software)) | [yum](https://fedoraproject.org/wiki/Yum/ru)
- [brew](https://brew.sh) | [linuxbrew](http://linuxbrew.sh)
- [npm](https://docs.npmjs.com)

### Software

- [curl](https://www.gitbook.com/book/bagder/everything-curl/details)
- [wget](https://www.gnu.org/software/wget/manual/wget.pdf)
- [clang](https://clang.llvm.org)
- [g++](https://gcc.gnu.org/onlinedocs/gcc-4.0.2/gcc/G_002b_002b-and-GCC.html)
- [make](https://en.wikipedia.org/wiki/Make_(software))
- [open](https://developer.apple.com/legacy/library/documentation/Darwin/Reference/ManPages/man1/open.1.html)
- [openssl](https://www.openssl.org)
- [nano](https://www.nano-editor.org)
- [tree](https://linux.die.net/man/1/tree)
- [vim](http://www.vim.org)

```
Copyright (c) 2015-2019 The ISC Authors
```
