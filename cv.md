# Darya Neprintseva

## Contacts
* __Location__: Moscow, Russia
* __Phone__: +7 925 730-37-52
* __Email__: muza33@ya.ru
* __GitHub__: [mdirect](https://github.com/mdirect)

## About Me
Junior frontend developer.

## Code Example
```
text_error="Корректный ввод: ./edit.sh file str1 str2"
 
if [ -z $1 ]
then
  echo "Не указан путь до файла"
  echo $text_error
  exit 1
fi
if [ -z $2 ]
then
  echo "Не указана строка для замены"
  echo $text_error
  exit 1
fi
if [ -z $3 ]
then
  echo "Не указана стока, которой заменять"
  echo $text_error
  exit 1
fi

now=`pwd`
root_src=$(dirname "$0")
log_file=$root_src/files.log
file=$root_src/`echo $1 | cut -d/ -f2-`

if [ -e $file ]
then
  if [ $2 = $3 ]
  then
  echo "Строки совпадают. Заменять нечего"
  else
    if ! grep -q "$2" "$file"
    then
    echo "Строка \"$2\" не найдена в файле"
    else
 
      # Замена в файле 
      sed -I '' 's/'$2'/'$3'/' $file
 
      # Запись в лог
      size=`ls -l $file | awk '{print $5}'`
      date=`stat -f "%Sm" -t "%Y-%m-%d %H:%M" $file`
      sha256=`shasum -a 256 $file | awk '{print $1}'`
      echo $1 - $size - $date - $sha256 - sha256 >> $log_file
    fi
  fi
else
echo "Файл не существует"
fi
```

## Skills
* HTML
* CSS/SASS
* JavaScript (Basic)
* Git
* C
* Bash

## Education
* __University__: Moscow Institute Electronics and Mathematics
* __Courses__:
  + CS50 lectures
  + School 21

## English
__Intermediate__
