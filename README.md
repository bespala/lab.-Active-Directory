Лабораторна робота "Створення серверу Active directory з введенням в домен однієї віртуальної машини"
Для створення вітруальних машин використовувася гіпервізор Proxmox

1. Створення віртальної машини для серверу

Визначаємо ІД віртуальної машини та його назву і нажимаємо далі
<img width="1904" height="746" alt="Screenshot 2026-03-16 212810" src="https://github.com/user-attachments/assets/fce78d0b-c1af-4103-b6dd-2d2fd74d4481" />

Далі визначаємо місце розташування нашої віртуальної машини
Для серверу ми будемо використовувати Windows Server 2022
Обов'язково в полі "Тип" визначити що це саме продукт Microsoft, та версію, яка вказана на слайді і нажимаємо далі
<img width="1908" height="731" alt="Screenshot 2026-03-16 212935" src="https://github.com/user-attachments/assets/5ef9e92f-a7ef-44f2-99a4-014ac52abe73" />

Налаштування системи вибираємо як показано на наступних слайдах
<img width="1915" height="733" alt="Screenshot 2026-03-16 212958" src="https://github.com/user-attachments/assets/0444874a-9e7b-4f8d-8722-4fa5bc3cb997" />

<img width="1913" height="737" alt="Screenshot 2026-03-16 213037" src="https://github.com/user-attachments/assets/64f327be-31b7-417a-b99a-ec257321bf35" />

<img width="1914" height="735" alt="Screenshot 2026-03-16 213054" src="https://github.com/user-attachments/assets/f1e0b7a2-1b7b-40a9-92fc-2bccc9bdd55c" />

<img width="1907" height="732" alt="Screenshot 2026-03-17 001532" src="https://github.com/user-attachments/assets/f607ae48-ce0d-40c8-87db-06708ad2048f" />

<img width="1364" height="637" alt="Screenshot 2026-03-17 001630" src="https://github.com/user-attachments/assets/e720fdba-5c7e-48c5-ac7d-d198355a0458" />

Для правильної роботи серверу на базі операційної системи Windows, треба додатково на віртуальну машину додати файл з драйверами на систему Як показано на слайді

<img width="1914" height="730" alt="Screenshot 2026-03-16 213148" src="https://github.com/user-attachments/assets/be6cc170-8d40-42fc-b60e-29f7a50b8a9c" />

2. Запуст та установка серверу
Далі йде стандартна процедура встановлення серверу. Вона не відрізняється від встановлення її на фізичний сервер
Встановлення серверу показано на наступних слайдах

<img width="1722" height="1073" alt="Screenshot 2026-03-16 213350" src="https://github.com/user-attachments/assets/5961f2db-e96d-4270-8055-153f7625f6ee" />
<img width="1727" height="989" alt="Screenshot 2026-03-16 213407" src="https://github.com/user-attachments/assets/51adc031-0f1a-47e9-8f97-53d91e1e2bfb" />
<img width="1721" height="991" alt="Screenshot 2026-03-16 213421" src="https://github.com/user-attachments/assets/be53af3f-e05c-49c2-b49c-850e9d5b5c70" />
<img width="1721" height="988" alt="Screenshot 2026-03-16 213433" src="https://github.com/user-attachments/assets/e6607691-325e-41b8-9cd7-e70b97c5fab9" />

На цьому етапі ми маємо вказати шлях до драйверів, які ми доставляли на вуртуальну машину раніше
<img width="1721" height="985" alt="Screenshot 2026-03-16 213442" src="https://github.com/user-attachments/assets/bdc743ba-dad9-4357-9425-429d044cfb6d" />
<img width="1723" height="986" alt="Screenshot 2026-03-16 213840" src="https://github.com/user-attachments/assets/d2b852a4-4881-4de6-aeef-c5c02c307d52" />

<img width="1723" height="990" alt="Screenshot 2026-03-16 213856" src="https://github.com/user-attachments/assets/8fddeb97-9a79-4d40-92d6-a3f2fc43bdf8" />

Як драйвери встановлені, продовжуємо налаштування віртуальної машини по стандарту 

<img width="1731" height="989" alt="Screenshot 2026-03-16 213916" src="https://github.com/user-attachments/assets/36375496-8f84-424e-ba31-9ee2a0df0cce" />
<img width="1721" height="985" alt="Screenshot 2026-03-16 213930" src="https://github.com/user-attachments/assets/6656b392-57da-43be-b76d-7575e1536124" />

Після того як наша віртуальна машина встановлена, створюємо пароль адміністратора та заходимо в систему

<img width="1721" height="1076" alt="Screenshot 2026-03-16 214134" src="https://github.com/user-attachments/assets/2e146279-e1dd-4e80-bd9e-59766c4eedcd" />

<img width="1722" height="1079" alt="Screenshot 2026-03-16 215346" src="https://github.com/user-attachments/assets/5035f4f8-0b60-4a8c-ae0e-7da164788360" />

3. Внутрішні налаштування серверу перед тим, як він стане Домен Контроллером.
Критичними вимогами для Контроллеру домену є налаштування на ньому статичної ІР адреси та налаштування правильного часу в системі. Без них корректно працювати він не буде

Тому заходимо в налаштування мережі, вибираємо Properties (властивості) та змінюємо налаштування ІР адреси з динамічної на статична як показано на слайдах

<img width="1726" height="1027" alt="Screenshot 2026-03-16 215402" src="https://github.com/user-attachments/assets/38c3d3b1-aa7f-41a9-852f-7025a026e0e6" />
<img width="1722" height="1079" alt="Screenshot 2026-03-16 215454" src="https://github.com/user-attachments/assets/d8bc3a08-0ea3-478e-bdae-eee4b0cc732a" />

Переконуємось що часовий пояс встановлений правильно
<img width="1719" height="1076" alt="Screenshot 2026-03-16 232448" src="https://github.com/user-attachments/assets/c0161a4e-86e3-406b-a169-9d6903d6afd9" />

4. Налаштування домен контроллеру на сервері

На даному етапі ми починаємо встановлювати сервіс домен контролеру на сервері, як показано на слайдах
Заходимо в Server Manager (керування сервером) та вибираємо Add roles and Features (додати ролі і можливоті)

<img width="1722" height="1079" alt="Screenshot 2026-03-16 221629" src="https://github.com/user-attachments/assets/66bb8fd4-0fe5-47c5-b5a4-1ae3d302e3af" />

Далі вибираємо стандартні налаштування. нічого не міняємо і видираємо Далі
<img width="1724" height="1079" alt="Screenshot 2026-03-16 221641" src="https://github.com/user-attachments/assets/15857e66-40fd-40ff-b021-f4d028045543" />
<img width="1722" height="1078" alt="Screenshot 2026-03-16 221652" src="https://github.com/user-attachments/assets/5eda852c-7883-4277-9525-bb272665391b" />


На цьому етапі ми вибираємо які функціі наш сервер буде виконувати. В нашому випадку це Служба контролеру домену та також служба DNS.

<img width="1724" height="1079" alt="Screenshot 2026-03-16 221726" src="https://github.com/user-attachments/assets/abd2d512-8447-42c8-bb13-26ed7ee30871" />

<img width="1724" height="1078" alt="Screenshot 2026-03-16 221800" src="https://github.com/user-attachments/assets/79f7ae39-c2fa-48b0-be64-5ab042395b60" />
<img width="1722" height="1078" alt="Screenshot 2026-03-16 221807" src="https://github.com/user-attachments/assets/19d41f8d-11bd-4f6a-86f7-ec0cdc4a3dd3" />

Встановлюємо наші служби
<img width="1723" height="1079" alt="Screenshot 2026-03-16 221821" src="https://github.com/user-attachments/assets/f74dac34-219d-4432-b1ac-b8e1d806a5c2" />

