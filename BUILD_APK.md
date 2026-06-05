# Сборка APK — Sky Runner

## Способ 1: Без сборки — Chrome (самый простой!)

1. Откройте `index.html` в **Chrome** на телефоне
2. Нажмите **⋮** (три точки) → **Добавить на главный экран**
3. Введите название → **Добавить**
4. Готово! Иконка появится как у обычного приложения

Это создаёт PWA (Progressive Web App) — работает офлайн, полноэкранный режим.

---

## Способ 2: Android Studio

1. Установите [Android Studio](https://developer.android.com/studio)

2. Скопируйте игру в assets:
   ```bash
   mkdir -p android/app/src/main/assets
   cp index.html android/app/src/main/assets/index.html
   ```

3. Откройте папку `android/` в Android Studio

4. Дождитесь синхронизации Gradle (может занять несколько минут)

5. **Build → Build Bundle(s) / APK(s) → Build APK(s)**

6. APK: `android/app/build/outputs/apk/debug/app-debug.apk`

7. Перекиньте на телефон и установите
   - Включите «Установка из неизвестных источников» в настройках

---

## Способ 3: Командная строка

```bash
# Подготовка
mkdir -p android/app/src/main/assets
cp index.html android/app/src/main/assets/index.html

# Сборка
cd android
./gradlew assembleDebug

# Результат
ls app/build/outputs/apk/debug/app-debug.apk
```

---

## Особенности мобильной версии

- **Управление касанием** — левая/правая половина экрана
- **Обе ориентации** — горизонтальная и вертикальная
- **Полный экран** — скрывает системные кнопки
- **Экран не гаснет** во время игры
