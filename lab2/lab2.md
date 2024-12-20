University: [ITMO University](https://itmo.ru/ru/)

Faculty: [FTMI](https://ftmi.itmo.ru/)

Course: [Cloud platforms as the basis of technology entrepreneurship](https://itmo-ict-faculty.github.io/cloud-platforms-as-the-basis-of-technology-entrepreneurship/) 

Year: 2024/2025

Group: U4225

Author: Gurev Danil Sergeevich

Lab: Lab2

Date of create: 28.10.2024

Date of finished: 05.11.2024
</div>

## Описание
Это вторая лабораторная работа "Исследование Cloud Run"

## Цель работы
Ознакомиться с работой Cloud Run.

## Ход работы
Cloud Run - это управляемая вычислительная платформа, которая позволяет запускать контейнеры (изолированная среда для приложения) непосредственно поверх масштабируемой инфраструктуры Google.

1. Создал Cloud Run из представленного дефолтного сервиса.
![image](https://github.com/user-attachments/assets/1a90e606-fd1c-48bf-8959-fdff57559fd9)

Первая версия была создана на порту 8080.

![image](https://github.com/user-attachments/assets/39b7b180-e5eb-43de-b085-7d15e88d810a)


2. Проанализировал логи:

![image](https://github.com/user-attachments/assets/354c4f21-04ec-44f4-914e-c24f15dcabd6)

В логах можно увидеть, что Cloud Run с именем «hello-gurev-danil» был создан в регионе «us-central1». Служба была создана пользователем « danilguriev456@gmail.com » с помощью Cloud Console. Служба была настроена с максимальным масштабом 100 экземпляров, параллель контейнеров 80 и тайм-аут 300 секунд. Далее можно по логам можно увидеть, что служба Cloud Run «hello-gurev-danil» принимает запросы на порту 8080, а также можно увидеть информацию об успешно принятых HTTP GET-запросах.

3. Проанализировал метрики:

Среди метрик представлены следующие: количество запросов, задержка запросов, количество экзмепляров контейнера, оплачиваемое время экземпляра контейнера, загрузка ЦП контейнера, использование памяти котнейнера, количество отправленных и полученных байтов, максимальное количество одновременных запросов и задержка запуска контейнера.

Активность на отображаемых графиках метрик происходила за счет того, что я обращался к странице с информацией о запуске образа контейнера (см.выше).

![image](https://github.com/user-attachments/assets/a2e911c2-2bf5-4b9e-998a-219ad1f2c36e)

![image](https://github.com/user-attachments/assets/b5b3be04-0350-4bab-90c5-83920402780e)

![image](https://github.com/user-attachments/assets/394fd272-6276-42f8-a1ee-bc7fb59ae46d)

4. На базе существующего контейнера поменял порт с 8080 на 8090
![image](https://github.com/user-attachments/assets/bcdf754c-f888-489f-bfeb-ce06dde00964)

5. Проанализировал логи:

![image](https://github.com/user-attachments/assets/2a1fe063-ebf0-4e7e-8e3b-7910829121c7)

В логах можно отметить, что произошло успешное обновление сервиса Cloud Run "hello-gurev-danil" в регионе "us-central1", и что служба Cloud Run начала принимать запросы на порту 8090.

6. Проанализировал метрики:
![image](https://github.com/user-attachments/assets/a47ca016-92aa-4f41-88ec-d03038513113)

![image](https://github.com/user-attachments/assets/1797a3de-6bdd-4726-a73d-0490ed26c3c8)

Анализ метрик, представленных на графиках, помогает понять производительность контейнера и состояние приложения. 

7. Протестировал переключения трафика между версиями:
50%/50%:

![image](https://github.com/user-attachments/assets/2e34e672-33d9-45a8-bf9f-f316c7f7f508)

Сравнение метрик показало, что обе версии обрабатывают запросы одинаково, без значительных различий в производительности.

9. Удалил за собой все созданные сервисы

## Выводы

- В ходе выполнения задания был успешно развернут сервис на Cloud Run.
- Проведено тестирование работы сервиса, настройка минимального уровня ресурсов и тестирование между разными видами портов.
- Проанализированы логи и метрики, что дало представление о производительности и нагрузке на сервис.
- Проведен эксперимент с переключением трафика между версиями.
