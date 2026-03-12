---
# FileClass для ресурсов каталога.
# Привязка к папке: в интерфейсе Metadata Menu откройте настройки этого fileClass
# (кнопка рядом с названием) → "Files paths option" → добавьте путь: Resources/items
#
# Тогда при редактировании type, category, subcategory_1, subcategory_2
# в заметках из Resources/items будут предлагаться только заметки из нужных папок таксономии.
paths:
  - Resources/items
fields:
  - name: type
    type: File
    id: typeTax
    path: ""
    options:
      dvQueryString: "dv.pages('\"Resources/taxonomy/types\"')"
  - name: category
    type: File
    id: catTax
    path: ""
    options:
      dvQueryString: "dv.pages('\"Resources/taxonomy/categories\"')"
  - name: subcategory_1
    type: File
    id: sub1Tax
    path: ""
    options:
      dvQueryString: "dv.pages('\"Resources/taxonomy/subcategories1\"')"
  - name: subcategory_2
    type: File
    id: sub2Tax
    path: ""
    options:
      dvQueryString: "dv.pages('\"Resources/taxonomy/subcategories2\"')"
  - name: status
    type: Select
    id: statusSel
    path: ""
    options:
      "0": "new"
      "1": "checked"
      "2": "uploaded"
      "3": "archived"
  - name: language
    type: Select
    id: langSel
    path: ""
    options:
      "0": "ru"
      "1": "en"
      "2": "ar"
---

# fileClass: resource

Этот файл определяет для плагина **Metadata Menu** поля и подсказки для заметок-ресурсов.

- **type**, **category**, **subcategory_1**, **subcategory_2** — в выпадающем списке показываются только заметки из соответствующих папок таксономии.
- **status** — только значения: new, checked, uploaded, archived.
- **language** — только: ru, en, ar.

В настройках fileClass обязательно укажите **Files paths option** → `Resources/items`, чтобы все заметки в этой папке использовали данные поля.
