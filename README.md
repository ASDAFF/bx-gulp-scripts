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

## Конфигурационный файл
Пример файла конфигурации config.default.js нужно переименовать в index.js и разместить в каталоге (каталог проекта)/src/config/.

Таким образом, полный путь будет выглядеть:

    (каталог проекта)/src/config/index.js
    
В конфигурационном файле следует задать значение константы ```templateName```. В качестве значения указать идентификатор вашей темы оформления.

Если расположение файлов отличается от предлагаемого, то следует изменить значения констант путей расположения ресурсных файлов и файлов с результатами сборки.

## Рекомендации по расположению файлов
### Ресурсные файлы темы
Все исходники ресурсов темы рекомендуется распологать в каталоге:

    src/assets/templates/(Имя Темы)
    
Этот каталог своей структурой преимущественно повторяет структуру каталога с темой оформления. В нём размещаются файлы:

Подкаталог  | Назначение
----------- | -----------
components  | Оформление компонент. Структура каталога полностью повторяет структуру соответствующего каталога темы оформления. В каталоге содержаться файлы: **js** (JavaScript в формате ECMAScript 6), **scss** (Стили компонент) и изображения (Пропускаются через компрессор Gulp).
images      | Изображения, которые будут помещены в результирующий каталог темы после компрессора.
sprites     | Каталог для исходных наборов, из которых будут формироваться спрайты.
js          | JavaScript файлы в нотации ECMAScript 6.
scss        | Общие для темы оформления **SCSS** файлы.

### Каталог оформления темы
Каталог темы оформления сайта рекомендуется размещать по пути:

    local/templates/(Имя Темы)
    
Несмотря на то, что рекомендуется все модификации помещать в каталог ```local```, можно встретить сайты, где модифицированная тема находится в каталоге ```bitrix/templates/(Имя Темы)```. Компиляцию ресурсных файлов можно настроить и на этот каталог, путём изменения путей в константах конфигурационного файла: ```src/config/index.js```.

## Зависимости Node.js
Для нормальной работы всех функций **Gulp** предусмотренных пакетом в файл ```package.json``` следует добавить секцию зависимостей:

    "devDependencies": {
        "@babel/core": "^7.1.2",
        "@babel/preset-env": "^7.1.0",
        "browser-sync": "^2.24.7",
        "del": "^3.0.0",
        "fs": "0.0.1-security",
        "gulp": "^3.9.1",
        "gulp-autoprefixer": "^6.0.0",
        "gulp-babel": "^8.0.0",
        "gulp-cache": "^1.0.2",
        "gulp-concat": "^2.6.1",
        "gulp-cssnano": "^2.1.3",
        "gulp-group-css-media-queries": "^1.2.2",
        "gulp-if": "^2.0.2",
        "gulp-image-resize": "^0.13.0",
        "gulp-imagemin": "^4.1.0",
        "gulp-notify": "^3.2.0",
        "gulp-plumber": "^1.2.0",
        "gulp-rename": "^1.4.0",
        "gulp-sass": "^4.0.1",
        "gulp-sourcemaps": "^2.6.4",
        "gulp-string-replace": "^1.1.1",
        "gulp-strip-comments": "^2.5.2",
        "gulp-strip-css-comments": "^2.0.0",
        "gulp-uglify": "^3.0.1",
        "gulp-zip": "^4.2.0",
        "gulp.spritesmith": "^6.9.0",
        "imagemin-pngquant": "^6.0.0",
        "jquery": "^3.3.1",
        "jquery-match-height": "^0.7.2",
        "merge-stream": "^1.0.1",
        "path": "^0.12.7",
        "vinyl-buffer": "^1.0.1"
      } 
