# Holy War

Unity-проект на **6000.3.29f1 (Unity 6.3 LTS)** с Universal Render Pipeline и Input System. Версия редактора записана в `ProjectSettings/ProjectVersion.txt`, версии пакетов закреплены в `Packages/manifest.json` и `Packages/packages-lock.json`.

## Открытие проекта

Добавьте корень репозитория в Unity Hub и откройте его указанной версией редактора. Для Android установите Android Build Support вместе с Android SDK & NDK Tools и OpenJDK. Unity восстановит пакеты и создаст локальный кэш при первом импорте.

В Build Profiles → Scene List включены по порядку `Bootstrap`, `MainMenu` (будущее лобби), `TestRange` и `GreyboxMatch`. Это заготовки без игровой логики. Код размещается в `Assets/Scripts` по системам, тесты в `Assets/Tests`, ресурсы в `Assets/Art` и `Assets/Audio`.

## Android

Для пробной сборки выберите Android в Build Profiles и соберите APK. Настройки проекта используют IL2CPP, ARM64 и Android 8.0 (API 26) как временную базу для MVP. Минимальный Android и список архитектур нужно согласовать перед релизом.

Workflow **Unity** собирает APK через GameCI на внутренних pull request, при изменениях в `main` и при ручном запуске. Для Unity Personal настройте репозиторные или организационные секреты `UNITY_LICENSE`, `UNITY_EMAIL` и `UNITY_PASSWORD`.
