Для клонування репозиторію я використав команду:
git clone https://github.com/alex-oliynyk/study
Команда першого коміту:
git commit -m "lab1: коміт команди для клонування"
Хеш першого коміту:
5b5e0335300c953c1db27cce3a7668b8145b2a35
Команда для створення гілки:
git branch newbranch
Команда для перемикання на гілку newbranch:
git checkout newbranch
Ми не бачимо змін у файлі README.md тому, що ці змінии зміни ми робили в гілці newbranch.
Проблеми при злитті гілок виникли тому, що у двох гілках був файл вміст якого різнився у двох гілках.
Проблему вирішив шляхом ручного видалення зайвих рядків і добавленням поточного файлу до коміту.
Редагуємо файл у Веб-версії.