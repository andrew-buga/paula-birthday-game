# Справа №13 — гра-привітання для Паули

## Структура проєкту
```
paula-birthday-game/
├── index.html      ← вся гра (HTML+CSS+JS в одному файлі)
├── assets/         ← сюди покладеш фото (paula.png, vika.png, andrii.png)
└── README.md
```

## Як додати фото персонажів
1. Створи папку `assets/` поруч з `index.html`.
2. Поклади туди квадратні/портретні фото: `paula.png`, `vika.png`, `andrii.png`
   (найкраще — вирізані фігурки на прозорому фоні, PNG).
3. У кінці файлу `index.html` знайди блок `PHOTO SWAP` і розкоментуй три рядки
   (прибери `//` на початку).

## Локальний перегляд у VS Code
1. Встанови розширення **Live Server** (Ritwick Dey) з маркетплейсу VS Code.
2. Клацни правою кнопкою на `index.html` → **Open with Live Server**.
3. Гра відкриється в браузері на `localhost`.

## Деплой на Vercel — покроково

### Варіант A: через сайт Vercel (найпростіше, без командного рядка)
1. Зайди на **vercel.com** → Sign Up → увійди через GitHub.
2. Завантаж проєкт на GitHub:
   - Створи новий репозиторій на github.com (наприклад `paula-birthday-game`).
   - У VS Code відкрий термінал (`Ctrl+`` `) і виконай:
     ```
     git init
     git add .
     git commit -m "Детективна гра для Паули"
     git branch -M main
     git remote add origin https://github.com/ТВІЙ_НІК/paula-birthday-game.git
     git push -u origin main
     ```
3. У Vercel натисни **Add New → Project**, обери свій репозиторій.
4. Framework Preset — залиш **Other** (це звичайний статичний сайт).
5. Натисни **Deploy**. Через ~30 секунд отримаєш посилання типу
   `https://paula-birthday-game.vercel.app`.

### Варіант B: через Vercel CLI (швидше, якщо звик до термінала)
1. Встанови CLI:
   ```
   npm install -g vercel
   ```
2. У терміналі VS Code, знаходячись у папці проєкту:
   ```
   vercel login
   vercel
   ```
3. Відповідай на питання Enter-ом (стандартні налаштування підходять).
4. Для фінального продакшн-деплою:
   ```
   vercel --prod
   ```
5. Отримаєш посилання — надішли його Паулі.

## Що можна легко змінити
- **Текст привітання** — у `index.html`, шукай `id="finale-post"`.
- **Улики та підказки** — рядки з `onclick="findClue(...)"` у кожній сцені.
- **Колір/шрифт** — блок `:root{...}` на початку файлу (змінні `--amber`, `--ink` тощо).
- **Код замка** — змінна `const CODE = [...]` у скрипті (зараз `7,1,9,3,1,3`).
