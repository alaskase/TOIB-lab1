# TOIB-lab1
# Настройка авторизации jupyterhub TLJH через Keycloak

## Настройка сетевого обмена между ВМ1 и ВМ2 ##

### Для обеспечения сетевого обмена и доступа к сети Интернет настроим сетевую среду виртуальных машин в виде сетевого моста###
Сетевой мост на debian12-1:
![01](https://github.com/alaskase/TOIB-lab1/assets/145039541/5d799486-af3d-4443-a1fb-1bff3073f630)

Сетевой мост на debian12-1:
![02](https://github.com/alaskase/TOIB-lab1/assets/145039541/18b0e5f3-dfb5-4aa6-acd0-ac8f02e3de67)

Сетевой адрес debian12-1:
![03](https://github.com/alaskase/TOIB-lab1/assets/145039541/2ba8a9ea-e498-4054-a2dd-2d28f937d411)

Сетевой адрес debian12-2:
![04](https://github.com/alaskase/TOIB-lab1/assets/145039541/217f113b-a656-4dd2-a85d-eafd48a579db)

Доступность debian12-2 c debian12-1:
![05](https://github.com/alaskase/TOIB-lab1/assets/145039541/229143bb-c23e-48cb-89ab-4d88c27ebfb3)

Доступность debian12-1 c debian12-2:
![06](https://github.com/alaskase/TOIB-lab1/assets/145039541/26a94af6-c282-466c-8862-4e9d6c0c2935)

## Установка и настройка Keycloak на ВМ1 ##
На debian12-1 установим Keycloak версии 22.0.5 в каталог /opt и выполним запуск:
![07](https://github.com/alaskase/TOIB-lab1/assets/145039541/97eda111-b0fb-4895-90fd-b5742d01ff31)

Откроем web-интерфейс Keycloak и произведем необходимые настройки:
![08](https://github.com/alaskase/TOIB-lab1/assets/145039541/3df32091-f5fa-4612-bc01-475303bb2cae)

Выполним авторизацию:
![09](https://github.com/alaskase/TOIB-lab1/assets/145039541/212b16c1-df14-47a3-8123-f14ed6b1cca6)

Добавим собственный реалм:
![10](https://github.com/alaskase/TOIB-lab1/assets/145039541/17f07e27-43a5-47a9-8917-2dc2c039a76a)

Создадим пользователя appadmin:
![11](https://github.com/alaskase/TOIB-lab1/assets/145039541/e8c2722b-5cf9-424d-84e1-811bc802fed2)

Создадим пользователя user:
![12](https://github.com/alaskase/TOIB-lab1/assets/145039541/6b9d7f1b-1ed3-4604-b4e4-7e782943c04e)

Пользователи созданы:
![13](https://github.com/alaskase/TOIB-lab1/assets/145039541/800f190a-6cde-4328-910f-9a97775da550)

Создадим клиента для приложения:
![14](https://github.com/alaskase/TOIB-lab1/assets/145039541/c665403f-3403-4010-8927-dbf8cd56ce9c)

Ключ авторизации для клиентского приложения:
![15](https://github.com/alaskase/TOIB-lab1/assets/145039541/406be48e-d025-446f-9115-b835be354c35)

## Установка и настройка приложения jupyterhub TLJH на ВМ2 ##

Проверим наличие необходимых пакетов:
![16](https://github.com/alaskase/TOIB-lab1/assets/145039541/d7435bbe-b3a7-46a6-a88a-2d944bfdfc02)

Установим jupyterhub TLJH:
![17](https://github.com/alaskase/TOIB-lab1/assets/145039541/83d9cf74-3fcf-49a6-b7ef-591eeb3de0c7)

Создадим файл настроек для авторизации jupyterhub через Keycloak:
![18](https://github.com/alaskase/TOIB-lab1/assets/145039541/40344add-c908-4395-a101-9273b59056af)

## Авторизация в приложении через Keycloak ##
Выполнив перезапуск jupyterhub, произведем авторизацию через Keycloak:
![19](https://github.com/alaskase/TOIB-lab1/assets/145039541/3cc318c3-aa86-4edf-b920-5ce1bd7f1bfe)

Приложение произвело перенаправление на страницу авторизации Keycloak:
![20](https://github.com/alaskase/TOIB-lab1/assets/145039541/266f6ac0-aab0-4c6d-a913-2472004244d2)

Выполнив успешную авторизацию мы получили доступ к нашему приложению:
![21](https://github.com/alaskase/TOIB-lab1/assets/145039541/1f692159-4db1-409a-87a5-d47a9eabbd4e)

Настроим 2FA в Keycloak:
![22](https://github.com/alaskase/TOIB-lab1/assets/145039541/3dc07930-09d3-4e40-b485-cedcd9143e66)









