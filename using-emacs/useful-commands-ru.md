# Шпаргалка Emacs
- Выход `C-x-c`
- Отмена `C-g`
- Загрузка `.emacs` не выходя из редактора (также работает с другими Lisp файлами), 2 способа:
  1. `M-x` `load-file` `~</path>/.emacs`
  2. В буффере с открытым Lisp скриптом `M-x` `eval-buffer`
  3. Выбрать регион, затем `M-x` `eval-region`
  4. См больше на [Stackoverflow](https://stackoverflow.com/questions/2580650/how-can-i-reload-emacs-after-changing-it)
- Переключение между буферами, 3 способа: 
  1. `C-x` `b` `<name>`
  2. `C-x` `<влево|вправо>` 
  3. `/` на доп клавиатуре (оно же `C-x-b`) -- выводит список буферов для последующей работы с ними
- Переключение между окнами `C-x` `o`
- Переход на строку `M-g-g` `<номер>`
- Переход в начало и конец файла `M-<` и `M->`
- Удаление части строки справа от курсора (или целой строки) и помещение в буфер `C-k`
- Установка закладки `C-x` `r` `m` `RET`
- Установки закладки с именем `C-x` `r` `m` `<name>` `RET`
- Перейти на закладку с именем `C-x` `r` `b` `<name>` `RET`
- Список закладок `C-x` `r` `l`
- Сохранить закладки в файл по умолчанию `M-x` `bookmark-save`
- Перемещение вперед и назад по соответствующим скобкам `C-M-f` `C-M-b`
- Напечатать символ unicode `C-x` `8` `RET` `<unicode>`
- Комментировать текущую строку или закоментировать выделенное `M-;`
- Поиск и замена строки в нескольких файлах:
  - `C-x` `d`, затем выбрать каталог где искать
  - [`M-x` `dired-mark-files-regexp` `RET` `<маска для файлов где искать>`]
  - `M-x` `dired-do-query-replace-regexp` `RET` `<что менять>` `<на что менять>`
- Включить/отключить поддержку мыши в терминале `M-x` `xterm-mouse-mode`, выделение и вставку теперь надо делать с `Shift`, c `Alt` для болока
- Изменение размеров окон:
  1. С поддержкой мыши просто делать мышью
  2. Без поддержки можно назначить клавиши для удобства
  ```
  (global-set-key (kbd "A-<down>") 'enlarge-window)
  (global-set-key (kbd "A-<up>") 'shrink-window)
  (global-set-key (kbd "A-<left>") 'enlarge-window-horizontally)
  (global-set-key (kbd "A-<right>") 'shrink-window-horizontally)
  ```
