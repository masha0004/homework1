# Эмулятор для оболочки языка OS

## 1. Общее описание

Этот проект представляет собой эмулятор оболочки языка OS, реализованный на Python. Эмулятор поддерживает базовые команды командной строки, такие как `ls`, `cd`, `pwd`, `cp`, `whoami` и `exit`. Все действия пользователя логируются в формате JSON с временными метками, а виртуальная файловая система загружается из архива tar.

### Основные особенности:
- Эмуляция команд UNIX-подобной оболочки.
- Поддержка виртуальной файловой системы, загружаемой из архива tar.
- Логирование всех действий пользователя.
- Поддержка базовых команд для работы с файлами и директориями.

## 2. Описание всех функций и настроек

### Класс `ShellEmulator`

#### `__init__(self, username, fs_path, log_path)`

```Python
 def __init__(self, username, fs_path, log_path):
    self.username = username
    self.fs_path = fs_path
    self.log_path = log_path
    self.current_dir = '/'
    self.log_data = []
    self._file_system = {self.current_dir: []}  # инициализируем корневую директорию
    self.load_filesystem()
```

- **Описание**: Инициализирует эмулятор оболочки.
- **Параметры**:
  - `username`: Имя пользователя для эмулятора.
  - `fs_path`: Путь к архиву tar с виртуальной файловой системой.
  - `log_path`: Путь к файлу для записи логов.

#### `load_filesystem(self)`

- **Описание**: Загружает виртуальную файловую систему из архива tar.

#### `log_action(self, action)`

- **Описание**: Записывает действия в лог.

#### `ls(self)`

- **Описание**: Выводит список файлов в текущей директории.

#### `cd(self, path)`

- **Описание**: Меняет текущую директорию.
- **Параметры**:
  - `path`: Путь к новой директории.

#### `pwd(self)`

- **Описание**: Выводит текущую директорию.

#### `cp(self, source, destination)`

- **Описание**: Копирует файл из исходной директории в конечную.
- **Параметры**:
  - `source`: Путь к исходному файлу.
  - `destination`: Путь к конечному файлу.

#### `whoami(self)`

- **Описание**: Выводит имя текущего пользователя.

#### `exit(self)`

- **Описание**: Завершает работу эмулятора и записывает логи.

#### `run(self)`

- **Описание**: Основной цикл работы эмулятора, ожидающий ввода команд от пользователя.

## 3. Описание команд для сборки проекта

Для работы с проектом необходимо иметь установленный Python 3.12

### Клонирование репозитория:

```bash
git clone https://github.com/masha0004/homework1/tree/main
cd Configuration-management
```

### Установка зависимостей:

```bash
cd homework1
pip install -r requirements.txt
```

### Запуск эмулятора:
```bash
python "src/shell_emulator.py" --username "username" --fs "config/virtual_fs.tar" --log "config/session_log.json"
```
## 4. Пример использования:

![prewiew (1) (1)](https://github.com/user-attachments/assets/bd67fff9-6052-48f1-9745-7adc7fd82fe6)

## 5. Результаты прогона тестов:

![image](https://github.com/user-attachments/assets/749945c3-f281-4827-b8a1-7adbd60ff6ff)
