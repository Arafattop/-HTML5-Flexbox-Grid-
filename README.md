# React + Vite

This template provides a minimal setup to get React working in Vite with HMR and some Oxlint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react) uses [Oxc](https://oxc.rs)
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react-swc) uses [SWC](https://swc.rs/)

## React Compiler

The React Compiler is not enabled on this template because of its impact on dev & build performances. To add it, see [this documentation](https://react.dev/learn/react-compiler/installation).

## Expanding the Oxlint configuration

If you are developing a production application, we recommend using TypeScript with type-aware lint rules enabled. Check out the [TS template](https://github.com/vitejs/vite/tree/main/packages/create-vite/template-react-ts) for information on how to integrate TypeScript and Oxlint's TypeScript related rules in your project.
## Лабораторная 4 — вёрстка
 
### Box model карточки (часть 1)
- content: включает в себя картинку (100% ширины, высота 160px), заголовки h3 и абзацы текста p.
- padding: внутренние отступы составляют 16px со всех сторон для создания пустого пространства вокруг контента.
- border: тонкая сплошная серая рамка толщиной 1px со скруглением углов border-radius: 10px.
- margin: внешние отступы регулируются сеткой Grid (свойство gap: 20px), а у кнопки задан отступ margin-top: auto.
- с box-sizing: border-box ширина стала включать в себя внутренние отступы (padding) и рамку (border), благодаря чему карточки перестали раздуваться сверх заданных размеров и ломать структуру рядов.
 
### repeat(4, 1fr) на узком экране (часть 4)
При сужении окна браузера до ~500px с фиксированной сеткой repeat(4, 1fr) карточки начинают сильно деформироваться, сжиматься в неестественно узкие столбцы, а текст и кнопки вылезают за пределы границ, так как 4 колонки физически не способны поместиться на экране мобильного телефона.
 
### auto-fit vs auto-fill (часть 4)
Разница заключается в поведении при малом количестве элементов: auto-fit растягивает имеющиеся карточки товаров на всю доступную ширину ряда, распределяя свободное пространство, в то время как auto-fill сохраняет фиксированную минимальную ширину карточек (220px) и оставляет пустые невидимые колонки в правой части контейнера. (Для проекта был выбран вариант auto-fit, так как он обеспечивает более гардуальное заполнение каталога).
 
### Адаптивность (часть 5)

| Ширина | Колонок | Где «Доставка» | Шапка |
|--------|---------|----------------|-------|
| 375 px | 1       | Под каталогом  | Столбик (flex-direction: column) |
| 768 px | 2 - 3   | Под каталогом  | Ряд (flex-direction: row) |
| 1280 px| 4       | Справа         | Ряд (flex-direction: row) |
