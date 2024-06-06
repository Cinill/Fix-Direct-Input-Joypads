# Вмикаємо вібрацію у вашому джойстику на Windows 10

(На Windows 7/8 це має працювати само собою, але я не перевіряв).

## Підтримувані пристрої

Ці драйвери і міні-посібник підійдуть для таких пристроїв, як:

- ![Bravis Pu-2200](https://github.com/Cinill/My-gamepad-drivers-collection/assets/72980216/5f2791f9-ca25-4f50-8af5-cab8cd117619) Bravis Pu-2200
- ![Bravis Pu-2222](https://github.com/Cinill/My-gamepad-drivers-collection/assets/72980216/ef60a557-1f4c-41f2-916c-ad2de7959ff1) Bravis Pu-2222
- ![PS2 to USB Convertor](https://github.com/Cinill/My-gamepad-drivers-collection/assets/72980216/e5588ecf-fbcb-4687-9252-621667088e3f) Синій PS2 to USB Convertor

Або всі пристрої з VID_0810&PID_0001 і VID_11ff&PID_3341.

## Усунення неполадок

### Вікно властивостей джойпада вилітає на вкладці вібрації

Якщо вікно властивостей джойпада вилітає на вкладці вібрації:

1. Скопіюйте файл `joy.cpl` з папки `C:\Windows\SysWOW64` у папку `C:\Windows\System32` із заміною.

Приклад: [Дивіться відео](https://www.youtube.com/watch?v=Un8nRb6pDBc)

### x360ce вилітає

Якщо ваш x360ce вилітає:

- Використовуйте версію 3. [Детальніше](https://github.com/x360ce/x360ce/discussions/1324)

### xOutput вилітає

Якщо ваш xOutput вилітає:

- Використовуйте версію до v3.23 (я використовую v3.22). [Детальніше](https://github.com/csutorasa/XOutput/issues/216)

### PCSX2 вилітає

Якщо ваш PCSX2 вилітає:

1. вимкніть ваш джойпад.
2. вимкніть SDL Input Source у налаштуваннях PCSX2, використовуйте xInput з 'XOutput'.

### Смиканий правий стік (актуально для Bravis Pu-2222 при низькому заряді)

1. вимкніть ваш джойпад.
2. відкрийте `regedit` і перейдіть до `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\MediaProperties\PrivateProperties\Joystick\OEM\(your OEM gamepad)`.
3 Клацніть правою кнопкою миші на папці 'gamepad OEM', створіть новий ключ із назвою 'Axes'.
4 Клацніть правою кнопкою миші на папці 'Axes', створіть ключ із назвою '2'.
5. Усередині '2' клацніть правою кнопкою миші і створіть бінарне значення з ім'ям 'Attributes', встановіть його значення на '00 00 00 00 01 00 00 35 00'.
6. Потім створіть в 'Axes' другий ключ: '5', створіть двійкове значення з ім'ям 'Attributes', встановіть його значення на '00 00 00 00 01 00 00 32 00'.

Це може допомогти, але мені не помогло. [Обговорення на Tom's Hardware](https://forums.tomshardware.com/threads/right-analog-stick-problem.98492/post-9929592)

## Додаткові поради

Ви також можете спробувати відновити свої драйвери, додавши `EZFRD64.dll` (іноді потрібно додати `FCVAP64.dll`) у папку:

`C:\Windows\USB Vibration{PID вашого пристрою}`

Робіть це на свій страх і ризик.

---
