# Shell - Emalator
Shell Emulator – это программа-эмулятор командной оболочки с графическим интерфейсом, которая имитирует работу shell в операционной системе типа Unix.
## Основные функции
### Поддержка комманд 
```ls:``` выводит список файлов в текущей директории.

```cd <директория>```: изменяет текущую директорию.

```pwd:``` показывает текущую директорию.

```cat <файл>```: выводит содержимое указанного файла.

```wc <файл>:``` считает количество строк, слов и символов в файле.

```exit```: завершает работу программы.
### Интерфейс
**Командная строка:** пользователь может вводить команды вручную, результаты которых будут отображаться в текстовом поле.

**Графический интерфейс с кнопками:** нажатием кнопки выполняется соответствующая команда

### Работа с виртуальной файловой системой:
Программа загружает архив с файловой системой (в формате ZIP), после чего происходит её эмуляция.

## Структура проекта
```
├── commands.py      # Логика выполнения команд оболочки
├── config.xml       # Файл конфигурации программы
├── config_reader.py # Модуль для чтения конфигурационного файла
├── main.py          # Главный файл для запуска программы
├── shellgui.py      # Графический интерфейс программы
├── tests.py         # Тесты для команд оболочки
├── vfs.zip          # Архив с тестовой файловой системой
├── virtual_fs.py    # Логика работы с виртуальной файловой системой
└── README.md        # Описание репозитория
```

## Установка и запуск:

1. Клонировать репозитирий
```git clone https://github.com/yourusername/shell-emulator.git```
2. Убедиться, что установлена версия Python 3.x и необходимые библиотеки:
```pip install tkinter```
3. Запустить программу:
```python3 main.py```

## Настройка:
Программа использует файл ```config.xml``` для своей конфигурации. Пример содержимого этого файла:
```
<?xml version="1.0" encoding="UTF-8"?>
<configuration>
  <username>user</username>
  <computername>localhost</computername>
  <zip_path>test_fs.zip</zip_path>
  <script_path>startup_script.sh</script_path>
</configuration>
```

Обратите внимание, что параметр zip_path должен содержать корректный путь к файлу архива (может быть как относительным, так и абсолютным). Вы можете самостоятельно изменить содержимое файла конфигурации.

# Примеры использования:

## Навигация по директориям:
```
user@localhost:~$ cd documents
user@localhost:~/documents$ ls
notes.txt
```

## Просмотр содержимого файла:
```
user@localhost:~/documents$ cat notes.txt
Notes for project.
```

## Подсчет строк, слов и символов в файле:
```
user@localhost:~/documents$ wc notes.txt
10 20 30 notes.txt
```

## Тестирование:
Для тестирования выполните команду:
```
python3 -m unittest test_commands.py
```

## Зависимости:
Программа использует стандартные библиотеки Python, включая tkinter, а также библиотеку zipfile для работы с архивами.


