# AMDNR RX 9070 — профили

Набор пользовательских профилей AMDNR / OptiScaler, протестированных на Radeon RX 9070.

В репозитории **нет чужих DLL/PAK/runtime-файлов**. Сначала устанавливается актуальный AMDNR из оригинального проекта, затем применяется только профиль.

## Assassin's Creed Black Flag Resynced — финальный профиль

Проверено на:

- RX 9070
- 2560x1440
- Ultra + тяжёлый RT
- FSR Quality
- AMDNR 0.3.4.1
- Runtime: lmxxf
- рабочий размер NR: точный размер рендера, около 1712x960
- TierSnap: OFF
- Fast: OFF
- Interleave: 2
- Interleave preset: 10 / Edit accumulation
- AmdLmxxfEditDetail: 0.75

Готовый файл:

`profiles/assassins-creed-black-flag-resynced/OptiScaler.ini`

### Результат

В тестовой сцене:

- без NR: примерно 73-74 FPS;
- финальный lmxxf-профиль: примерно 44-48 FPS;
- с генерацией кадров: ориентировочно 70-80 FPS.

Главная цель настройки — сохранить выразительность и детализацию NR, но убрать чрезмерно сухую/точечную микротекстуру кожи в тени.

### Установка

1. Установить актуальную версию AMDNR из оригинального репозитория.
2. Один раз запустить игру и убедиться, что AMDNR работает.
3. Сделать резервную копию своего `OptiScaler.ini`.
4. Скопировать `profiles/assassins-creed-black-flag-resynced/OptiScaler.ini` в папку игры.
5. Перезапустить игру.
6. Убедиться, что выбран runtime `lmxxf`.

Профиль не является универсальным и рассчитан прежде всего на RX 9070.

## Авторы исходных проектов

AMDNR / OptiScaler:
https://github.com/3zwr1/AMD-NR---OptiScaler

lmxxf:
https://github.com/lmxxf/dlss5-on-amd-9070xt-porting

DLSS-NR-on-AMD / Daniel Blanco:
https://github.com/danielblnc/DLSS-NR-on-AMD

Все права на исходные проекты, код и бинарные файлы принадлежат их авторам. Этот репозиторий содержит только пользовательский конфигурационный профиль и документацию по результатам тестирования.
