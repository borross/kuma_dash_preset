# kuma_dash_preset
Скрипт ипорта/экспорта дашбордов и пресетов для KUMA


\* 14.08.2023 - добавлен импорт экспорт Пресетов

Предварительно нужно:
* поместить mongoexport и mongoimport из  https://box.kaspersky.com/d/53acc02f7a3c4d89a327/  в папку /opt/kaspersky/kuma/mongodb/bin/
* сделать chmod +x по этим файлам (chmod +x /opt/kaspersky/kuma/mongodb/bin/*)
* чтобы использовать скрипт (ему надо chmod +x kuma_dash_preset.sh)

При импорте-экспорте нужно указывать полный путем, пример, /root/DNS_EXPORT_CLEAR.json

! выберите после импорта тип дашборда Universal в веб-интерфейсе KUMA

Параметры запуска скрипта `kuma_dash_preset.sh`

`-exportDash "<Dashboard Name>" </path/File Export Name.json>` -- экспортировать панель мониторинга в файл JSON (имя панели мониторинга должно быть УНИКАЛЬНЫМ! и используйте ", если в имени есть пробелы)

`-importDash <File Export Name.json>` -- импортировать панель мониторинга в KUMA

`-deleteDash "<Dashboard Name>"` -- удалить панель мониторинга из KUMA (используйте " если в имени есть пробелы)

`-exportPreset "<Preset Name>" </path/File Export Name.json>` -- экспортировать пресет в файл JSON (имя панели мониторинга должно быть УНИКАЛЬНЫМ! и используйте ", если в имени есть пробелы)

`-importPreset <File Export Name.json>` -- импорт пресета в KUMA


Пример импорта:
`./kuma_dash_preset.sh -import /root/CheckPointCEF_EXPORT_CLEAR(kuma2-0).json`

Иногда после импорта требуется зайти в новый дашборд в режиме редактирования и проверить указаны ли во всех виджетах верные хранилища, затем сохранить и снова обновить.