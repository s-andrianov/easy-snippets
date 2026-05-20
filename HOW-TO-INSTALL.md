# Easy Snippets — Build, Install, Publish & Run

## 1. Зависимости (один раз)

```bash
# Bun (https://bun.sh)
curl -fsSL https://bun.sh/install | bash

# vsce — упаковщик/публикатор VS Code расширений
npm install -g @vscode/vsce

# Установить локальные зависимости
bun install
```

## 2. Подготовка контента (если меняли шаблоны)

1. Добавьте/измените шаблоны в `src/templates`.
2. Для иконочных CDN-сниппетов используйте `src/templates/icons/<provider>/`.
3. Перегенерируйте сниппет-файлы:
   ```bash
   bun run generate:snippets
   ```
   Это создаст `snippets/snippets.code-snippets`, `snippets/css.code-snippets`, `snippets/icons.code-snippets`, и обновит таблицу в `README.md`.

## 3. Сборка `.vsix` (локальный пакет расширения)

```bash
bun run compile        # tsc -p ./
vsce package           # создаст easy-snippets-<version>.vsix
```

Файл `easy-snippets-<version>.vsix` появится в корне проекта.

> Если `vsce package` ругается на отсутствующий `publisher` — поправьте поле `publisher` в [package.json](package.json). Для локальной проверки подойдёт любая строка; для публикации — это должен быть ваш реальный publisher из Azure DevOps.

## 4. Локальная установка в VS Code

Любой из способов:

- **GUI:** `Cmd+Shift+P` → `Extensions: Install from VSIX...` → выбрать сгенерированный `.vsix`.
- **CLI:**
  ```bash
  code --install-extension easy-snippets-0.6.0.vsix
  ```

После установки перезагрузите окно (`Cmd+Shift+P` → `Developer: Reload Window`).

## 5. Запуск в режиме разработки (без упаковки)

1. Откройте проект в VS Code.
2. Запустите `bun run watch` — TypeScript будет компилироваться на лету.
3. Нажмите `F5` — откроется **Extension Development Host** с подключённым расширением.
4. Внутри новой копии VS Code откройте HTML-файл и проверьте сниппеты.

## 6. Проверка сниппетов

1. В HTML: `bs5-$`, `icons-fa6-cdn`, `icons-bootstrap-icons-cdn`.
2. В CSS/SCSS/SASS: `css-comment-block`.
3. Подсказки IntelliSense — через `Ctrl+Space`.

## 7. Публикация в VS Code Marketplace

1. Зарегистрируйте publisher: <https://aka.ms/vscode-create-publisher>.
2. Получите Personal Access Token в Azure DevOps (scope: **Marketplace → Manage**).
3. Залогиньтесь в `vsce`:
   ```bash
   vsce login <your-publisher-name>
   ```
4. Поднимите версию в [package.json](package.json) (semver).
5. Опубликуйте:
   ```bash
   vsce publish              # публикует текущую версию
   # или с автоматическим bump:
   vsce publish patch        # 0.6.0 → 0.6.1
   vsce publish minor        # 0.6.0 → 0.7.0
   vsce publish major        # 0.6.0 → 1.0.0
   ```

> После публикации Marketplace индексирует расширение в течение 5–10 минут. Найти его можно по `ext install <publisher>.easy-snippets`.

## 8. Альтернатива — Open VSX (для VSCodium, Cursor, Gitpod)

```bash
npm install -g ovsx
ovsx publish easy-snippets-<version>.vsix -p <open-vsx-token>
```

## Подсказки

- Файл иконки: [icon.png](icon.png) — 256×256, прозрачный фон.
- Игнор-список для `vsce package`: [.vscodeignore](.vscodeignore).
- Чтобы быстро увидеть, что попадёт в `.vsix`: `vsce ls`.
