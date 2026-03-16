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
<img width="1725" height="1079" alt="Screenshot 2026-03-16 221844" src="https://github.com/user-attachments/assets/ea044bbc-742f-4c12-b5bc-3bb516b7f221" />

Після встановлення відповідних служб нам тркба назначити цей сервер як Контролер Домену, як показано на слайдах

<img width="1729" height="1079" alt="Screenshot 2026-03-16 221935" src="https://github.com/user-attachments/assets/900d4e51-b74e-41b8-8286-946aa1e24d9c" />

Визначаємо ім'я нашого домену, в прикладі у нас назва Lab.domain
<img width="1726" height="1079" alt="Screenshot 2026-03-16 222108" src="https://github.com/user-attachments/assets/36940eb5-cc41-40dd-b50a-322dc859a639" />


встановлюємо пароль для відновленя домену (його дуже важливо запам'ятати, без ноього відновлення після збою буде неможливе)

<img width="1723" height="1079" alt="Screenshot 2026-03-16 222143" src="https://github.com/user-attachments/assets/4151cb71-cd19-4ad8-8d30-ea3061be7e51" />

Далі нічого не змінюючи завершуємо налаштування 

<img width="1723" height="1079" alt="Screenshot 2026-03-16 222218" src="https://github.com/user-attachments/assets/6694ecb7-ce81-4304-b0e1-15946612f145" />

На даному слайді нам показано, яку приставку будуть робити користувачі, для того щоб зайти на домен
<img width="1726" height="1079" alt="Screenshot 2026-03-16 222239" src="https://github.com/user-attachments/assets/523d84ca-7539-4aea-8605-97687052589e" />

<img width="1723" height="1079" alt="Screenshot 2026-03-16 222255" src="https://github.com/user-attachments/assets/77d9b87d-f725-402f-9f1a-17ded2192450" />

<img width="1724" height="1079" alt="Screenshot 2026-03-16 222306" src="https://github.com/user-attachments/assets/df843ee5-bf9b-4f6e-bcf0-fd0f4bdff961" />
Встановюємо зміни. Після завершення, сервер автоматично перезавантижиться, і наступний вхід вже буде здійснюватись в створеному нами домені
<img width="1723" height="1079" alt="Screenshot 2026-03-16 222334" src="https://github.com/user-attachments/assets/51160676-47ac-4552-b214-bb121baeb989" />
<img width="1915" height="1079" alt="Screenshot 2026-03-16 222813" src="https://github.com/user-attachments/assets/dd224f33-44a1-4e49-8549-a41bafd3257e" />

5. Створення користувача в домені

Для створення майбутнього користувача в домені,  треба зайти в додаток Active Directory Users and Computers, вибрати наш домер, зайти в папку Користувачі та створити ного користувача як показано на слайді
<img width="1724" height="1079" alt="Screenshot 2026-03-16 232556" src="https://github.com/user-attachments/assets/55cd47c3-40e6-45ad-b21b-050a5366dbcb" />
<img width="1724" height="1075" alt="Screenshot 2026-03-16 232702" src="https://github.com/user-attachments/assets/b27eca8e-44a2-48d6-8751-9696bd8cdd36" />
<img width="1722" height="1076" alt="Screenshot 2026-03-16 232723" src="https://github.com/user-attachments/assets/3da52cd8-8bb7-44d8-a2dd-dfc1ceb872fc" />
<img width="1723" height="1079" alt="Screenshot 2026-03-16 232730" src="https://github.com/user-attachments/assets/d3022608-ef74-48eb-8c5a-0d5d4e30771f" />
<img width="1720" height="1079" alt="Screenshot 2026-03-16 232738" src="https://github.com/user-attachments/assets/bead1e4a-81dc-401c-9f23-fd9a0d449c05" />


6. Встановлення віртуальної машини клієнта
В якості клієнта ми використовуємо віртуальну машину на базі Windows11, тому налаштування самої віртуальної машини відрізняється тільки його назвою, ID та вихідним файлом

<img width="1916" height="735" alt="Screenshot 2026-03-16 223000" src="https://github.com/user-attachments/assets/384fbdf5-42b7-44ca-8a01-91cb9483bb6f" />

Далі іде процес встановлення самої операційної системи, він не відрізняється від встановлення її на фізичний компьютер

<img width="1720" height="1077" alt="Screenshot 2026-03-16 225356" src="https://github.com/user-attachments/assets/9fb18b9c-78cc-4fe7-a701-65cc90e331fb" />
<img width="1720" height="1079" alt="Screenshot 2026-03-16 225410" src="https://github.com/user-attachments/assets/79c26327-e4af-4ab0-a184-6bbac06b8b06" />
<img width="1721" height="1078" alt="Screenshot 2026-03-16 225425" src="https://github.com/user-attachments/assets/5aeb3dd9-8cd0-42ba-a7eb-e7d6331cee21" />

Так само як при встановленні серверу, нам треба завантижити драйвери на систему як показано на слайдах
<img width="1724" height="1079" alt="Screenshot 2026-03-16 225450" src="https://github.com/user-attachments/assets/b642d5d0-956d-48a9-9a99-7549c2f70a81" />

<img width="1719" height="1073" alt="Screenshot 2026-03-16 225507" src="https://github.com/user-attachments/assets/6a06f1c1-65de-43d2-aa4c-f038cd4b500f" />
<img width="1715" height="1079" alt="Screenshot 2026-03-16 225523" src="https://github.com/user-attachments/assets/cdd20c41-9a02-4020-9c0e-9fba36f73e85" />
<img width="1719" height="1079" alt="Screenshot 2026-03-16 225532" src="https://github.com/user-attachments/assets/d9ca39a7-fc0b-4ff0-a903-d7e52bf12620" />

Встановлюємо систему

Після перезавантаження системи, заходимо під локально створенним користувачем
<img width="1725" height="1079" alt="Screenshot 2026-03-16 232943" src="https://github.com/user-attachments/assets/7c0ca017-8093-4387-b36d-0401c2b43458" />

7. Додавання віртуальної машини в домен

Для того щоб додати віртуальну машину в домен мають буди виконані наступні умови
- Комп'ютер має бути в одній мережі з сервером домену, і сервер домену має бути налаштований як DNS для машини клієнта
- Має відповідати час машини клієнта на машини серверу

налаштування мережі показані на наступних слайдах

<img width="1723" height="1079" alt="Screenshot 2026-03-16 233319" src="https://github.com/user-attachments/assets/acec0441-8d1b-4c97-ba2c-645ae319de6e" />

<img width="1720" height="1078" alt="Screenshot 2026-03-16 233604" src="https://github.com/user-attachments/assets/4e12f610-d360-406a-9881-a3e45f99843c" />

Через командний рядок перевіряємо доступність серверу домену
<img width="1723" height="1079" alt="Screenshot 2026-03-16 233638" src="https://github.com/user-attachments/assets/73678fb9-9c95-4c1e-8e03-aae7b1e89eb7" />

Все успішно

Далі йде фінальний етап -додавання машини клієнта в домен, як показано на слайдах

<img width="1723" height="1079" alt="Screenshot 2026-03-16 234114" src="https://github.com/user-attachments/assets/c3b2b406-ff06-439d-ad20-7aa6e8809271" />

<img width="1725" height="1079" alt="Screenshot 2026-03-16 234121" src="https://github.com/user-attachments/assets/da71952d-50da-4a50-b315-7c147340bdec" />

<img width="1718" height="1079" alt="Screenshot 2026-03-16 234136" src="https://github.com/user-attachments/assets/8b9771ca-657f-4d19-a00d-cd3f94e12491" />

В діалоговому вікні вписуємо назву нашого домену, та вводимо обліковий запис адміністратора, для того щоб приєднати машину клієнта

<img width="1721" height="1079" alt="Screenshot 2026-03-16 234428" src="https://github.com/user-attachments/assets/f1e8c096-64ab-4654-b5a9-738aef3d3b8d" />
<img width="1724" height="1079" alt="Screenshot 2026-03-16 234800" src="https://github.com/user-attachments/assets/3632962b-02bb-48ec-98e2-2c8be9a89a54" />

Після цього машина клієнта перезавантажується, і наступний вхід вже буде пропонувати в домені
Використовуємо створений раніше  акаунт користувача
<img width="1719" height="1078" alt="Screenshot 2026-03-16 234836" src="https://github.com/user-attachments/assets/dd75cbc7-fc78-4fc7-abbf-f848e647fb1e" />
На даному слайді ми бачимо що віртуальна машина клієнта успішно підключена в домен

<img width="1720" height="1079" alt="Screenshot 2026-03-16 234937" src="https://github.com/user-attachments/assets/de8b5e60-7b02-48c5-83fd-0b2daa320088" />
