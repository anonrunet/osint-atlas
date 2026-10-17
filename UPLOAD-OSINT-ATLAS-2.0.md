# Как обновить OSINT Atlas в GitHub через браузер

Архив `OSINT-Atlas-2.0.zip` — готовая структура репозитория. В корне архива лежат `README.md`, `.github/workflows/`, папка приложения `osint-atlas/`, отчёт проверки ссылок и заметки релиза.

## 1. Распакуй архив

Скачай ZIP и распакуй его на компьютере. Открой папку, куда распаковались файлы. Не загружай сам ZIP на GitHub: нужно переносить файлы из него.

## 2. Обнови корневые документы

1. Открой репозиторий `anonrunet/osint-atlas` на GitHub и убедись, что выбрана ветка `main`.
2. В корне репозитория нажми **Add file → Upload files**.
3. Перетащи из распакованного архива корневые файлы `README.md`, `SOURCE-AUDIT.md`, `RELEASE-v2.0.0.md` и `UPLOAD-OSINT-ATLAS-2.0.md`.
4. Внизу страницы в поле сообщения напиши `Prepare OSINT Atlas 2.0` и нажми **Commit changes**.

## 3. Замени файлы приложения

1. В репозитории открой папку `osint-atlas/`.
2. Нажми **Add file → Upload files**.
3. Из папки `osint-atlas` распакованного архива загрузи в это место: `index.html`, `app.js`, `data.js`, `dorks.js` и `README.md`.
4. Нажми **Commit changes**.
5. Затем открой папку `osint-atlas/assets/` в GitHub. Загрузи туда два файла из такой же папки в распакованном архиве: `favicon.svg` и `author-avatar.png`. Нажми **Commit changes**.

Загружай файлы **в уже существующие соответствующие папки**. Не создавай путь `osint-atlas/osint-atlas/` и не помещай папку проекта внутрь самой себя.

## 4. Проверь публикацию сайта

1. Вверху репозитория открой вкладку **Actions**.
2. Дождись workflow **Deploy OSINT Atlas to GitHub Pages** с зелёной галочкой.
3. Открой **Settings → Pages**. В разделе **Build and deployment** для **Source** должно быть выбрано **GitHub Actions**.
4. Сайт проекта должен открываться здесь: **https://anonrunet.github.io/osint-atlas/**. Если сразу видна старая версия, обнови страницу с очисткой кэша (Windows: `Ctrl+F5`, Mac: `Cmd+Shift+R`) и проверь, что последний запуск workflow зелёный.

Workflow `.github/workflows/deploy-pages.yml` уже включён в архив. Если такой файл уже есть в корне репозитория, оставь его на месте — он публикует содержимое папки `osint-atlas/`.

## 5. GitHub Release (необязательно)

После успешной публикации открой **Releases → Draft a new release**, создай тег `v2.0.0`, укажи заголовок `OSINT Atlas 2.0` и скопируй описание из файла `RELEASE-v2.0.0.md`. Это необязательное дополнение; сайт работает и без Release.
