---
title: 'Шаблони: найголовніше!'
date: 2017-06-14 12:03:00 Z
---

Мабуть, основна фішка у всіх генераторах статичних сайтів - шаблони. Тому що нема чого копіювати один і той же код в кілька різних місць, якщо комп'ютер може зробити це за вас. Вся система шаблонів в Jekyll влаштована просто, майже примітивно. Шаблон є просто HTML-сторінкою (в папці _layouts), в якому є Liquid-тег (про них далі) {{content}}. А назвою шаблону вважається ім'я файлу без розширення: наприклад, шаблон foo потрібно описувати в файлі foo.html.
Будь-яка сторінка сайту може посилатися на шаблон (в тому числі інший шаблон):


Коли Jekyll збирає сторінку, перевіряється, чи не зазначений в шапці параметр layout, як вище. Якщо вказано, то спочатку збирається сторінка із зазначеного в ньому шаблону, а з отриманої сторінки тег {{content}} замінюється на вміст тієї сторінки, над якою йде робота. Наведу приклад.

У себе на сайті я використовую в основному два шаблони: list і post, але вони не самодостатні, а є розширеннями шаблону default. В останньому знаходиться сама зовнішня оболонка, яка використовується майже на всіх сторінках. post виводить пост, його теги і форму коментарів. list використовується для всіляких списків посад, і містить JavaScript, що виводить кількість коментарів для всіх постів в списку. При складанні поста у мене в блозі Jekyll спочатку бачить в шапці layout: post, звертається в post.html і бачить там. У default.html ніяких шаблонів не вказано, тому він завантажує цей файл, на місце {{content}} записує post.html (а це шаблон, в ньому {{content}} теж є) і в отриманий гібрид замість {{content} } записує мій пост.

Теоретично, ви можете робити пости різних видів і форматів: повноцінна стаття, замітка, цитата, картинка. Доведеться напружитися, щоб пости виводилися в списках по-різному, в залежності від формату, але це, напевно, єдиний неочевидний момент.
