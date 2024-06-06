# Включаем вибрацию в вашем джойстике на Windows 10

(На Windows 7/8 это должно работать само по себе, но я не проверял).

## Поддерживаемые устройства

Эти драйверы и мини-руководство подойдут для таких устройств, как:

- ![Bravis Pu-2200](https://github.com/Cinill/My-gamepad-drivers-collection/assets/72980216/5f2791f9-ca25-4f50-8af5-cab8cd117619) Bravis Pu-2200
- ![Bravis Pu-2222](https://github.com/Cinill/My-gamepad-drivers-collection/assets/72980216/ef60a557-1f4c-41f2-916c-ad2de7959ff1) Bravis Pu-2222
- ![PS2 to USB Convertor](https://github.com/Cinill/My-gamepad-drivers-collection/assets/72980216/e5588ecf-fbcb-4687-9252-621667088e3f) Синий PS2 to USB Convertor

Или все устройства с VID_0810&PID_0001 и VID_11ff&PID_3341.

## Устранение неполадок

### Окно свойств джойпада вылетает на вкладке вибрации

Если окно свойств джойпада вылетает на вкладке вибрации:

1. Скопируйте файл `joy.cpl` из папки `C:\Windows\SysWOW64` в папку `C:\Windows\System32` с заменой.

Пример: [Смотрите видео](https://www.youtube.com/watch?v=Un8nRb6pDBc)

### x360ce вылетает

Если ваш x360ce вылетает:

- Используйте версию 3. [Подробнее](https://github.com/x360ce/x360ce/discussions/1324)

### xOutput вылетает

Если ваш xOutput вылетает:

- Используйте версию до v3.23 (я использую v3.22). [Подробнее](https://github.com/csutorasa/XOutput/issues/216)

### PCSX2 вылетает

Если ваш PCSX2 вылетает:

1. Отключите ваш джойпад.
2. Отключите SDL Input Source в настройках PCSX2, используйте xInput из ‘XOutput’.

### Дёрганый правый стик (актуально для Bravis Pu-2222 при низком заряде)

1. Отключите ваш джойпад.
2. Откройте `regedit` и перейдите к `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\MediaProperties\PrivateProperties\Joystick\OEM\(your OEM gamepad)`.
3. Щелкните правой кнопкой мыши на папке ‘gamepad OEM’, создайте новый ключ с названием ‘Axes’.
4. Щелкните правой кнопкой мыши на папке ‘Axes’, создайте ключ с названием ‘2’.
5. Внутри ‘2’ щелкните правой кнопкой мыши и создайте бинарное значение с именем ‘Attributes’, установите его значение на ‘00 00 00 00 01 00 35 00’.
6. Затем создайте в ‘Axes’ второй ключ: ‘5’, создайте бинарное значение с именем ‘Attributes’, установите его значение на ‘00 00 00 00 01 00 32 00’.

Это может помочь, но мне не помогло. [Обсуждение на Tom's Hardware](https://forums.tomshardware.com/threads/right-analog-stick-problem.98492/post-9929592)

## Дополнительные советы

Вы также можете восстановить свои драйверы, добавив `EZFRD64.dll` (иногда нужно добавить `FCVAP64.dll`) в папку:

`C:\Windows\USB Vibration{PID вашего устройства}`

Делайте это на свой страх и риск.

---
