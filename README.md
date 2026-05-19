# Инструкция по работе с Git

## Структура документа

1. Регистрация на GitHub и установка Git

2. Локальные команды Git

3. Удаленные команды Git и работа с форками

---

## 1. Регистрация на GitHub и установка Git



### Создание учетной записи GitHub

1. Перейдите на \[github.com](https://github.com)

2. Нажмите кнопку **Sign up**

3. Введите email, придумайте пароль и username

4. Пройдите капчу и подтвердите email

5. Выберите тариф **Free**



### Установка Git

| ОС       | Команда / Действие                                                                 |

|----------|------------------------------------------------------------------------------------|

| Windows  | Скачайте установщик с \[git-scm.com](https://git-scm.com), запустите, оставьте настройки по умолчанию. |

| macOS    | `brew install git` или `xcode-select --install`                                    |

| Linux    | `sudo apt update && sudo apt install git` (Debian/Ubuntu)                          |



**Проверка установки:**

```bash

git --version

# Пример вывода: git version 2.43.0

---

## 2. Локальные команды Git

| Команда | Описание | Пример |
|---------|----------|--------|
| `git init` | Инициализация нового репозитория | `git init my-project` |
| `git status` | Проверка статуса файлов | `git status` |
| `git add` | Добавление файлов в индекс | `git add .` (все) или `git add file.txt` |
| `git commit` | Фиксация изменений | `git commit -m "fix: исправлена орфография"` |
| `git log` | История коммитов | `git log --oneline --graph` |
| `git diff` | Показать изменения до коммита | `git diff HEAD` |
| `git branch` | Список веток | `git branch -a` |
| `git switch` / `checkout` | Переключение веток | `git switch local` |
| `git stash` | Временное сохранение изменений | `git stash push -m "work in progress"` |

**Пример типичного локального цикла:**
```bash
git init demo
echo "Hello Git" > readme.md
git add readme.md
git commit -m "init: first commit"
git log --oneline

