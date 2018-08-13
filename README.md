# Gulp скрипты для сборки шаблонов 1С-Битрикс

## Установка
Установка зависит от того, как используется Git в проекте Битрикс

### Используется корневой репозиторий на весь проект
Скрипты добавляются, как модуль к основному репозиторию:

    git submodule add https://github.com/mvandrew/bx-gulp-scripts.git src/scripts

### Git не успользуется в проекте
Скрипты могут быть установлены путём клонирования репозитория в каталог (каталог проекта)/src/scripts:

    git clone https://github.com/mvandrew/bx-gulp-scripts.git src/scripts
    
Или просто скопированы файлы скриптов в каталог (каталог проекта)/src/scripts.