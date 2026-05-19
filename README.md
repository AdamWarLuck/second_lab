# Инструкция по работе с Git

## Структура документа

1. Регистрация на GitHub и установка Git

2. Локальные команды Git

3. Удаленные команды Git и работа с форками

---

## 1. Регистрация на GitHub и установка Git



### Создание учетной записи GitHub

1. Перейдите на [github.com](https://github.com)

2. Нажмите кнопку **Sign up**

3. Введите email, придумайте пароль и username

4. Пройдите капчу и подтвердите email

5. Выберите тариф **Free**



### Установка Git

| ОС       | Команда / Действие                                                                 |
|----------|------------------------------------------------------------------------------------|
| Windows  | Скачайте установщик с [git-scm.com](https://git-scm.com), запустите, оставьте настройки по умолчанию. |
| macOS    | `brew install git` или `xcode-select --install`                                    |
| Linux    | `sudo apt update && sudo apt install git` (Debian/Ubuntu)                          |



**Проверка установки:**

```bash

git --version
```

**Пример вывода: git version 2.43.0**

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
```
## 3. Удаленные команды Git и работа с форками

### Основные команды работы с удаленным репозиторием
| Команда | Описание | Пример |
|---------|----------|--------|
| `git clone` | Клонирование репозитория | `git clone https://github.com/user/repo.git` |
| `git remote add` | Привязка удаленного репозитория | `git remote add origin https://github.com/user/repo.git` |
| `git fetch` | Загрузка метаданных без слияния | `git fetch origin` |
| `git pull` | Скачивание + автоматическое слияние | `git pull origin main` |
| `git push` | Отправка изменений на сервер | `git push origin main` |

### Принцип работы с форками (Fork)
**Fork** – это копия репозитория другого пользователя на вашем GitHub-аккаунте. Используется для участия в open-source проектах без прав на запись в оригинал.

**Типичный workflow:**
1. Нажмите кнопку **Fork** на странице оригинального репозитория.
2. Склонируйте свою копию: `git clone https://github.com/your-username/repo-forked.git`
3. Добавьте оригинал как `upstream`: `git remote add upstream https://github.com/original-owner/repo.git`
4. Работайте в своей ветке, делайте коммиты и пушьте в свой fork.
5. Создайте **Pull Request** на GitHub в оригинальный репозиторий.
6. Синхронизируйте fork с оригиналом: `git fetch upstream && git merge upstream/main`

**Пример полного цикла:**
```bash
git clone https://github.com/you/project-fork.git
cd project-fork
git remote add upstream https://github.com/author/project.git
git checkout -b feature/new-docs
```
# ... редактирование файлов ...
```bash
git add . && git commit -m "docs: add global commands"
git push origin feature/new-docs
```
# Далее создаём Pull Request через веб-интерфейс GitHub
