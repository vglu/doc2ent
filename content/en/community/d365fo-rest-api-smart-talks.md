---
title: "D365fo Rest Api Smart Talks"
date: 2020-06-05T13:14:07+03:00
lastmod: 2020-06-05T13:14:07+03:00
publishdate: 2020-06-05T13:14:07+03:00
description: "D365fo Rest Api Start Talks испоользование технологии. Примеры для консультантов"
weight: 10
draft: false
---

## Вступление

Данная статья поможет разобраться в базовых различиях в техниках ти технологиях одного из механизмов обмена данными в современной Аксапте. Многие моменты упрощены для более легкого понимания. Все точные формулировки, вызовы и спецификации, сложные примеры использования есть в открытом доступе.

Практически все материалы показаны в [SMART TALKS 203](https://www.youtube.com/watch?v=yuJx6J4edio)

{{< youtube yuJx6J4edio >}}

### Что такое XML

XML это текстовый формат представления данных. У него есть заголовок, и произвольный набор тегов. Теги должны быть парными. Внутри тегов может быть представлены различные типы данных как простые (текст, число, дата), так и более сложных - например список элементов.

XML выглядит приблизительно так

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SalesOrder>
    <OrderId>"SO-00023"</OrderId>
    <CustomerId>"Very impotant customer"</CustomerId>
    <OrderLines>
        <SalesOrderLine>
            <OrderId>"SO-00023"</OrderId>
            <ItemId>"It00123-5"</ItemId>
            <Qty>5</Qty>
            <Price>10</Price>
            <Amount>50</Amount>
        </SalesOrderLine>
        <SalesOrderLine>
            <OrderId>"SO-00023"</OrderId>
            <ItemId>"It00123-6"</ItemId>
            <Qty>1</Qty>
            <Price>15</Price>
            <Amount>15</Amount>
        </SalesOrderLine>
    </OrderLines>
</SalesOrder>
```

### Что такое JSON

Так же как и XML - текстовый формат для передачи данных, очень похож на XML только нотация чуть-чуть другая. Рассмотрим как выглядят эти же данные в формате JSON

```json
{
  "SalesOrder": {
    "OrderId": "SO-00023",
    "CustomerId": "Very impotant customer",
    "OrderLines": {
      "SalesOrderLine": [
        {
          "OrderId": "SO-00023",
          "ItemId": "It00123-5",
          "Qty": 5,
          "Price": 10,
          "Amount": 50
        },
        {
          "OrderId": "SO-00023",
          "ItemId": "It00123-6",
          "Qty": 1,
          "Price": 15,
          "Amount": 15
        }
      ]
    }
  }
}
```

В чем разница или почему используют один или другой формат? Исторически сложилось, так что сначала был XML и он позволял описывать необходимые данные. К недостаткам можно отнести большую громоздкость (на больших объемах данных это становится важным). JSON (JavaScript object notation) - был взят из JavaScript где он имеет нативную поддержку и получил распространение для обмена данными как более легковесная альтернатива XML. С точки зрения Enterprise - есть протокол SOAP - с использованием XML, есть протокол Rest API - с использованием XML. SOAP дает возможность получить схему документа, REST API - нет. SOAP - тяжелый, REST легковесный. В D365FO\* можно применять любой из подходов либо их комбинацию. Мы заглянем в схему XML но в основном будем рассматривать JSON.

### Получение ключей

```html
Если Вы консультант, то лучше всего попросить ключи у системного аржитектора,
тим лида проекта, ближайшего разработчика ... и не заниматься их генерацией
самостоятельно!
```

Авторизация дело не хитрое и у него есть свои особенности. Предположим наше приложение живет по какому-то адресу ... например `https://devboxa5adevaos.cloudax.dynamics.com/?cmp=USMF&mi=DefaultDashboard` - это точка входа в приложение. Значит наш базовый URL = `devboxa5adevaos.cloudax.dynamics.com`

Для того что бы мы получили доступ к приложению как пользователи - необходимо что бы администратор нас добавил как пользователь и назначил некоторые права в системе.

С точки зрения интеграции все в принципе работает так же. Мы специальным образом подключаем интеграцию к пользователю системы. Пользователю системы даем права на объекты системы. Подробная инструкция [тут](https://www.d365ug.com/blogs/nandita-nityanandam/2018/11/20/third-party-integration-in-d365fo-using-odata), а короткое описание ниже ...
Мы должны в Azure portal создать новую регастрацию для нашего приложения. При этом мы получим пару значений : `clientId`, `client secret`. Эти значения нужно запомнить!
Переходим в D365FO, `System administration\setup\Azure Active Directory application` и создаем новую запись

![IMG](/usefull/d365fo-rest-api-smart-talks/st203restapi01.png)

1 - вносим `client Id`
2 - описание записи (обычно назначение канала или название системы)
3 - пользователь Акс

Таким образом мы связали `clientId`, с пользователем Акс. Осталось передать `clientId`, `client secret внешней системе.

### Отступление. Что такое запрос, какие они бывают, что такое Postman

Давайте попробуем разобраться что такое запрос. Опять же, все упрощаем, главное сейчас - уловить суть.
Если мы откроем любую страницу в браузере, это и будет обычный запрос GET. Можно даже посмотреть что это GET и что он отправляет, получает.
Google chrome, правой клавишей на странице в любом месте в сплывающем контекстном меню выбрать Inspect (Ctrl+Shift+I), и переходим на закладку Network

Мы увидим, вот такую картину

![IMG](/usefull/d365fo-rest-api-smart-talks/st203restapi02.png)

Номер 5- показывает запрос GET, куда он был сделан, что он получил ответ сервера (Status code) 200. Сам ответ - на закладке Response

Какие еще могут быть запросы - может быть ([взято отсюда](https://restfulapi.net/http-methods/))

| HTTP Method | CRUD                  | Entire Collection (e.g. /users)                                                                          | Specific Item (e.g. /users/123)                                                |
| ----------- | --------------------- | -------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| POST        | Create                | 201 (Created), ‘Location’ header with link to /users/{id} containing new ID.                             | Avoid using POST on single resource                                            |
| GET         | Read                  | 200 (OK), list of users. Use pagination, sorting and filtering to navigate big lists.                    | 200 (OK), single user. 404 (Not Found), if ID not found or invalid.            |
| PUT         | Update/Replace        | 405 (Method not allowed), unless you want to update every resource in the entire collection of resource. | 200 (OK) or 204 (No Content). Use 404 (Not Found), if ID not found or invalid. |
| PATCH       | Partial Update/Modify | 405 (Method not allowed), unless you want to modify the collection itself.                               | 200 (OK) or 204 (No Content). Use 404 (Not Found), if ID not found or invalid. |
| DELETE      | Delete                | 405 (Method not allowed), unless you want to delete the whole collection — use with caution.             | 200 (OK). 404 (Not Found), if ID not found or invalid.                         |

Что бы увидеть как отдает данные D365FO давайте попробуем выполнить такой запрос в адресной строке браузера

`https://devboxa5adevaos.cloudax.dynamics.com/data/CustomerGroups(dataAreaId='usmf',CustomerGroupId='10')`

И посмотрим на свойства в окошке `Inspect`

![IMG](/usefull/d365fo-rest-api-smart-talks/st203restapi03.png)

если данных на закладке Network нет - нажмите F5, если страница не открывается вовсе - выполните авторизацию в D365FO

Мы выполнили Rest API запрос GET к CustomersGroups отобрав данные только по полям `DataAreaId = 'usmf'` и `CustomerGroupId = '10'`

К сожалению, возможности в браузере ограничены и нам будет проще в дальнейшем использовать другие инструменты, например `CURL`, `Fiddler`, `Postman`.

### Postman

Позволяет выполнять запросы из пользовательского окружения, удобный механизм сохранения и передачи запросов от человека к человеку, есть механизм автоматического тестирования запросов! Итак, шаг за шагом.

Где его взять ... - [тут](https://www.postman.com/)

![IMG](/usefull/d365fo-rest-api-smart-talks/st203restapi04.png)

1. Коллекции - тут создаем для себя папочку с текущим нашим проектом. Здесь будут размещаться наши сохраненные запросы (создали, описали)
2. Запросы - создаются плюсиком - основная рабочая область
3. Окружение - сюда можно будет заносить значения переменных. Об этом позже, но в двух словах, мы можем базовый URL записать в переменную и один и тот же запрос выполнять для разных окружений - в каждом окружении значение этой переменной базовый URL может быть свое ...

Что бы создать запрос - нажимаем + из 2)

![IMG](/usefull/d365fo-rest-api-smart-talks/st203restapi05.png)

1. можно запросу дать имя
2. тип запроса GET, POST ...
3. к чему запрос
4. заголовки - рассмотрим дальше отдельно. В двух словах - мы говорим сервису что мы от него хотим - например мы ему можем сообщить что хотим получить результат в формате xml или json. Другой пример - здесь задается токен авторизации
5. тело запроса. Если мы хотим получить данные от сервиса - тело пустое. А если хотим вставить данные - то в этой секции описываем что хотим вставить
6. отправить запрос на выполнение

Пример запроса, который мы использовали в браузере

![IMG](/usefull/d365fo-rest-api-smart-talks/st203restapi06.png)

Результат - внизу - на закладке Body

#### Браузер таблиц

Мы можем просмотреть записи таблицы если введем ссылку в виде

`https://BASEURL/?mi=SysTableBrowser&TableName=CustGroup&cmp=USMF&lng=en-us&limitednav=true`

где

- TableName=Имя Таблицы или представления (View) - CustGroup
- cmp - имя компании - USMF
- lng - язык - un-us

В результате получим

![IMG](/usefull/d365fo-rest-api-smart-talks/st203restapi07.png)

### Список Entity

Чтобы получить список энтитей - необходимо ввести

`https://BASEURL/data/`

![IMG](/usefull/d365fo-rest-api-smart-talks/st203restapi08.png)

### Table and Entity Chrome extension

![IMG](/usefull/d365fo-rest-api-smart-talks/st203restapi09.png)

Просто необходимый инструмент. Вводится BASEURL, есть возможность получить список всех таблиц, View, Entity с возможностью найти по названию, просмотреть свойства ...

Однако, вернемся к запросам .....

## Получение токена авторизации

Авторизация производится при помощи протокола OAuth 2.0

Для этого выполняется запрос

POST https://login.windows.net/<tenant>/oauth2/token HTTP/1.1
Content-Type: application/x-www-form-urlencoded
Host: login.windows.net

resource=https%3A%2F%2FBASEURL&client_id=f78fe522-29b3-4acf-a61b-f5581e121496&client_secret=bZGMw90F7SwVyBCuIllJH7umNu2SutM0qOczMPUOzOg%3D&grant_type=client_credentials

где
<tenant> - это значение нужно уточнить у технических специалистов D365 знак вопроса, About/в секци **This product is licensed to:**
`BASEURL`- значение описано выше
`client_id`, `client_secret` - значения которые мы запомнили выше

Запустим этот запрос в `Postman` - в результате мы получим ответ типа

![IMG](/usefull/d365fo-rest-api-smart-talks/st203restapi10.png)

В красном квадрате `access_token` - который будет использован для авторизации. Этот токен который будет использоваться в каждом запросе.

Обратите внимание на использование переменных в секции `body`. Эти переменные установлены в окружении

![IMG](/usefull/d365fo-rest-api-smart-talks/st203restapi11.png)

Если в запросе на авторизацию на закладке Tests этот код
`pm.environment.set("token", pm.response.json().access_token);`

![IMG](/usefull/d365fo-rest-api-smart-talks/st203restapi12.png)

и выполнить запрос еще раз - то в переменную token будет записано вот это значение и мы сможем дальше ее использовать в запросах.

## Запрос на чтение данных

Чтение данных происходит запросом `GET`

Запрос к Entity `CustomerGroups` вернет 7 записей

![IMG](/usefull/d365fo-rest-api-smart-talks/st203restapi13.png)

### \$top

`$top` - параметр - вернет первых несколько записей

Например в этом же запросе `GET https://{{base_url}}/data/CustomerGroups?$top=1`

Вернет только одну запись (первую запись)

```json
{
  "@odata.context": "https://devaos.cloudax.dynamics.com/data/$metadata#CustomerGroups",
  "value": [
    {
      "@odata.etag": "W/\"JzAsMjI1NjU0MjExNzYn\"",
      "dataAreaId": "usmf",
      "CustomerGroupId": "10",
      "ClearingPeriodPaymentTermName": "Net30",
      "CustomerAccountNumberSequence": "",
      "DefaultDimensionDisplayValue": "",
      "Description": "Wholesales customers",
      "IsSalesTaxIncludedInPrice": "No",
      "WriteOffReason": "",
      "PaymentTermId": "Net30",
      "TaxGroupId": ""
    }
  ]
}
```

### \$skip

`$skip` - параметр - пропустит первых несколько записей

В этом запросе `GET https://{{base_url}}/data/CustomerGroups?$top=1&$skip=1`

Вернет только вторую запись

```json
{
  "@odata.context": "https://devaos.cloudax.dynamics.com/data/$metadata#CustomerGroups",
  "value": [
    {
      "@odata.etag": "W/\"Jzc1MDAwNDY4LDIyNTY1NDIxMTc3Jw==\"",
      "dataAreaId": "usmf",
      "CustomerGroupId": "20",
      "ClearingPeriodPaymentTermName": "Net30",
      "CustomerAccountNumberSequence": "",
      "DefaultDimensionDisplayValue": "",
      "Description": "Major customers new",
      "IsSalesTaxIncludedInPrice": "No",
      "WriteOffReason": "GOODWILL",
      "PaymentTermId": "Net30",
      "TaxGroupId": ""
    }
  ]
}
```

### \$count

Возвращает кол-во записей запроса

В этом виде `GET https://{{base_url}}/data/CustomerGroups/$count`

Получаем сколько записей у нас сейчас в системе

![IMG](/usefull/d365fo-rest-api-smart-talks/st203restapi14.png)

Запрос `GET https://{{base_url}}/data/CustomerGroups?$count=true`

Вернет

```json
{
  "@odata.context": "https://devaos.cloudax.dynamics.com/data/$metadata#CustomerGroups",
  "@odata.count": 9,
  "value": [
    {
      "@odata.etag": "W/\"JzAsMjI1NjU0MjExNzYn\"",
      "dataAreaId": "usmf",
      "CustomerGroupId": "10",
      "ClearingPeriodPaymentTermName": "Net30",
      "CustomerAccountNumberSequence": "",
      "DefaultDimensionDisplayValue": "",
      "Description": "Wholesales customers",
      "IsSalesTaxIncludedInPrice": "No",
      "WriteOffReason": "",
      "PaymentTermId": "Net30",
      "TaxGroupId": ""
    },
    {
        ...
    }
```

и т.д. ...

Запрос GET `https://{{base_url}}/data/CustomerGroups?$count=true&$top=1`

Вернет все равно 9 записей

```json
{
  "@odata.context": "https://devaos.cloudax.dynamics.com/data/$metadata#CustomerGroups",
  "@odata.count": 9,
  "value": [
    {
      "@odata.etag": "W/\"JzAsMjI1NjU0MjExNzYn\"",
      "dataAreaId": "usmf",
      "CustomerGroupId": "10",
      "ClearingPeriodPaymentTermName": "Net30",
      "CustomerAccountNumberSequence": "",
      "DefaultDimensionDisplayValue": "",
      "Description": "Wholesales customers",
      "IsSalesTaxIncludedInPrice": "No",
      "WriteOffReason": "",
      "PaymentTermId": "Net30",
      "TaxGroupId": ""
    }
  ]
}
```

### \$select

Указываем список полей для выборки

`GET https://{{base_url}}/data/CustomerGroups?$top=2&$select=dataAreaId,CustomerGroupId`

Получим

```json
{
  "@odata.context": "https://devaos.cloudax.dynamics.com/data/$metadata#CustomerGroups(dataAreaId,CustomerGroupId)",
  "value": [
    {
      "@odata.etag": "W/\"JzAsMjI1NjU0MjExNzYn\"",
      "dataAreaId": "usmf",
      "CustomerGroupId": "10"
    },
    {
      "@odata.etag": "W/\"Jzc1MDAwNDY4LDIyNTY1NDIxMTc3Jw==\"",
      "dataAreaId": "usmf",
      "CustomerGroupId": "20"
    }
  ]
}
```

### \$filter

фильтруем записи

`GET https://{{base_url}}/data/CustomerGroups?$count=true&$filter=PaymentTermId eq 'Net30'`

```json
{
  "@odata.context": "https://devaos.cloudax.dynamics.com/data/$metadata#CustomerGroups",
  "@odata.count": 2,
  "value": [
    {
      "@odata.etag": "W/\"JzAsMjI1NjU0MjExNzYn\"",
      "dataAreaId": "usmf",
      "CustomerGroupId": "10",
      "ClearingPeriodPaymentTermName": "Net30",
      "CustomerAccountNumberSequence": "",
      "DefaultDimensionDisplayValue": "",
      "Description": "Wholesales customers",
      "IsSalesTaxIncludedInPrice": "No",
      "WriteOffReason": "",
      "PaymentTermId": "Net30",
      "TaxGroupId": ""
    },
    {
      "@odata.etag": "W/\"Jzc1MDAwNDY4LDIyNTY1NDIxMTc3Jw==\"",
      "dataAreaId": "usmf",
      "CustomerGroupId": "20",
      "ClearingPeriodPaymentTermName": "Net30",
      "CustomerAccountNumberSequence": "",
      "DefaultDimensionDisplayValue": "",
      "Description": "Major customers new",
      "IsSalesTaxIncludedInPrice": "No",
      "WriteOffReason": "GOODWILL",
      "PaymentTermId": "Net30",
      "TaxGroupId": ""
    }
  ]
}
```

Допускается использовать `AND`, `OR` и ...

### \$orderby

сортируем записи, по умолчанию ASK, доступно использование DESC

`GET https://{{base_url}}/data/CustomerGroups?$count=true&$filter=PaymentTermId eq 'Net30'&$orderby=Description`

```json
{
  "@odata.context": "https://devaos.cloudax.dynamics.com/data/$metadata#CustomerGroups",
  "@odata.count": 2,
  "value": [
    {
      "@odata.etag": "W/\"Jzc1MDAwNDY4LDIyNTY1NDIxMTc3Jw==\"",
      "dataAreaId": "usmf",
      "CustomerGroupId": "20",
      "ClearingPeriodPaymentTermName": "Net30",
      "CustomerAccountNumberSequence": "",
      "DefaultDimensionDisplayValue": "",
      "Description": "Major customers new",
      "IsSalesTaxIncludedInPrice": "No",
      "WriteOffReason": "GOODWILL",
      "PaymentTermId": "Net30",
      "TaxGroupId": ""
    },
    {
      "@odata.etag": "W/\"JzAsMjI1NjU0MjExNzYn\"",
      "dataAreaId": "usmf",
      "CustomerGroupId": "10",
      "ClearingPeriodPaymentTermName": "Net30",
      "CustomerAccountNumberSequence": "",
      "DefaultDimensionDisplayValue": "",
      "Description": "Wholesales customers",
      "IsSalesTaxIncludedInPrice": "No",
      "WriteOffReason": "",
      "PaymentTermId": "Net30",
      "TaxGroupId": ""
    }
  ]
}
```

### KEY

Возможность выбирать данные по ключу - одну запись. Очень важное свойство в операциях `PATCH`, `PUT`, `DELETE`

`GET https://{{base_url}}/data/CustomerGroups(dataAreaId='usmf',CustomerGroupId='10')`

Ответ

```json
{
  "@odata.context": "https://devaos.cloudax.dynamics.com/data/$metadata#CustomerGroups/$entity",
  "@odata.etag": "W/\"JzAsMjI1NjU0MjExNzYn\"",
  "dataAreaId": "usmf",
  "CustomerGroupId": "10",
  "ClearingPeriodPaymentTermName": "Net30",
  "CustomerAccountNumberSequence": "",
  "DefaultDimensionDisplayValue": "",
  "Description": "Wholesales customers",
  "IsSalesTaxIncludedInPrice": "No",
  "WriteOffReason": "",
  "PaymentTermId": "Net30",
  "TaxGroupId": ""
}
```

как узнать ключ

`Accept: odata.metadata=minimal, odata.metadata=full`
Ключ `Accept` говорит о том, как мы ожидаем получить данные от сервиса
В случае `odata.metadata=minimal` - сервис выдаст минимальный набор данных - все запросы до этого момента были выполенены с этим параметром
Как выглядит ответ `odata.metadata=full` вернет такой ответ

`GET https://{{base_url}}/data/CustomerGroups?$count=true&$filter=CustomerGroupId eq '10'`

```json
{
  "@odata.context": "https://devaos.cloudax.dynamics.com/data/$metadata#CustomerGroups",
  "@odata.count": 1,
  "value": [
    {
      "@odata.type": "#Microsoft.Dynamics.DataEntities.CustomerGroup",
      "@odata.id": "https://devaos.cloudax.dynamics.com/data/CustomerGroups(dataAreaId='usmf',CustomerGroupId='10')",
      "@odata.etag": "W/\"JzAsMjI1NjU0MjExNzYn\"",
      "@odata.editLink": "CustomerGroups(dataAreaId='usmf',CustomerGroupId='10')",
      "dataAreaId": "usmf",
      "CustomerGroupId": "10",
      "ClearingPeriodPaymentTermName": "Net30",
      "CustomerAccountNumberSequence": "",
      "DefaultDimensionDisplayValue": "",
      "Description": "Wholesales customers",
      "IsSalesTaxIncludedInPrice@odata.type": "#Microsoft.Dynamics.DataEntities.NoYes",
      "IsSalesTaxIncludedInPrice": "No",
      "WriteOffReason": "",
      "PaymentTermId": "Net30",
      "TaxGroupId": "",
      "DimensionSet@odata.associationLink": "https://devaos.cloudax.dynamics.com/data/CustomerGroups(dataAreaId='usmf',CustomerGroupId='10')/DimensionSet/$ref",
      "DimensionSet@odata.navigationLink": "https://devaos.cloudax.dynamics.com/data/CustomerGroups(dataAreaId='usmf',CustomerGroupId='10')/DimensionSet",
      "Prospects@odata.associationLink": "https://devaos.cloudax.dynamics.com/data/CustomerGroups(dataAreaId='usmf',CustomerGroupId='10')/Prospects/$ref",
      "Prospects@odata.navigationLink": "https://devaos.cloudax.dynamics.com/data/CustomerGroups(dataAreaId='usmf',CustomerGroupId='10')/Prospects"
    }
  ]
}
```

где
`@odata.type` - название Entity
`@odata.id` - ссылка на получение уникальной текущей записи - в скобках - ключи
`@odata.nextLink` - ссылка на следующую страницу

### Ограничения

Максимальная выборка ограничена только 1000 записями. Если в результирующей выборке записей больше - включается постраничное отображение. Постраничное отображение реализовано при помощи `$top` и `$skip`. Дополнительно появляется тег `@odata.nextLink` со ссылкой на следующий набор записей.

### \$expand

Позволяет присоединить один набор данных в другому

Возмем другой набор данных - `GET https://{{base_url}}/data/SalesOrderHeadersV2?$top=1`

```json
{
  "@odata.context": "https://devaos.cloudax.dynamics.com/data/$metadata#SalesOrderHeadersV2/$entity",
  "@odata.type": "#Microsoft.Dynamics.DataEntities.SalesOrderHeaderV2",
  "@odata.id": "https://adevaos.cloudax.dynamics.com/data/SalesOrderHeadersV2(dataAreaId='usmf',SalesOrderNumber='000002')",
  "@odata.etag": "W/\"JzAsNTYzNzE0NDU3NjswLDA7MCwwOzAsMDswLDA7MCwwJw==\"",
  "@odata.editLink": "SalesOrderHeadersV2(dataAreaId='usmf',SalesOrderNumber='000002')",
  "dataAreaId": "usmf",
  "SalesOrderNumber": "000002",
  "OrderTotalChargesAmount@odata.type": "#Decimal",
......
  "RevRecContractStartDate": "1900-01-01T12:00:00Z",
  "SalesOrderOrigin@odata.associationLink": "https://devaos.cloudax.dynamics.com/data/SalesOrderHeadersV2(dataAreaId='usmf',SalesOrderNumber='000002')/SalesOrderOrigin/$ref",
  "SalesOrderOrigin@odata.navigationLink": "https://devaos.cloudax.dynamics.com/data/SalesOrderHeadersV2(dataAreaId='usmf',SalesOrderNumber='000002')/SalesOrderOrigin",
  "Project@odata.associationLink": "https://devaos.cloudax.dynamics.com/data/SalesOrderHeadersV2(dataAreaId='usmf',SalesOrderNumber='000002')/Project/$ref",
  "Project@odata.navigationLink": "https://devaos.cloudax.dynamics.com/data/SalesOrderHeadersV2(dataAreaId='usmf',SalesOrderNumber='000002')/Project",
  "DimensionSet@odata.associationLink": "https://devaos.cloudax.dynamics.com/data/SalesOrderHeadersV2(dataAreaId='usmf',SalesOrderNumber='000002')/DimensionSet/$ref",
  "DimensionSet@odata.navigationLink": "https://devaos.cloudax.dynamics.com/data/SalesOrderHeadersV2(dataAreaId='usmf',SalesOrderNumber='000002')/DimensionSet",
  "SalesOrderLines@odata.associationLink": "https://devaos.cloudax.dynamics.com/data/SalesOrderHeadersV2(dataAreaId='usmf',SalesOrderNumber='000002')/SalesOrderLines/$ref",
  "SalesOrderLines@odata.navigationLink": "https://devaos.cloudax.dynamics.com/data/SalesOrderHeadersV2(dataAreaId='usmf',SalesOrderNumber='000002')/SalesOrderLines",
  "QualityOrderHeaders@odata.associationLink": "https://devaos.cloudax.dynamics.com/data/SalesOrderHeadersV2(dataAreaId='usmf',SalesOrderNumber='000002')/QualityOrderHeaders/$ref",
  "QualityOrderHeaders@odata.navigationLink": "https://devaos.cloudax.dynamics.com/data/SalesOrderHeadersV2(dataAreaId='usmf',SalesOrderNumber='000002')/QualityOrderHeaders"
}
```

Теперь его расширим за счет expand

Запрос `GET https://{{base_url}}/data/SalesOrderHeadersV2(dataAreaId='usmf',SalesOrderNumber='000002')?$expand=SalesOrderLines`

Ответ

```json
{
  "@odata.context": "https://devaos.cloudax.dynamics.com/data/$metadata#SalesOrderHeadersV2/$entity",
  "@odata.type": "#Microsoft.Dynamics.DataEntities.SalesOrderHeaderV2",
  "@odata.id": "https://devaos.cloudax.dynamics.com/data/SalesOrderHeadersV2(dataAreaId='usmf',SalesOrderNumber='000002')",
  "@odata.etag": "W/\"JzAsNTYzNzE0NDU3NjswLDA7MCwwOzAsMDswLDA7MCwwJw==\"",
  "@odata.editLink": "SalesOrderHeadersV2(dataAreaId='usmf',SalesOrderNumber='000002')",
  "dataAreaId": "usmf",
  "SalesOrderNumber": "000002",
  "OrderTotalChargesAmount@odata.type": "#Decimal",
  "OrderTotalChargesAmount": 0,
 ...
  "RevRecLatestReverseJournal": 0,
  "RevRecContractStartDate@odata.type": "#DateTimeOffset",
  "RevRecContractStartDate": "1900-01-01T12:00:00Z",
  "SalesOrderOrigin@odata.associationLink": "https://devaos.cloudax.dynamics.com/data/SalesOrderHeadersV2(dataAreaId='usmf',SalesOrderNumber='000002')/SalesOrderOrigin/$ref",
  "SalesOrderOrigin@odata.navigationLink": "https://devaos.cloudax.dynamics.com/data/SalesOrderHeadersV2(dataAreaId='usmf',SalesOrderNumber='000002')/SalesOrderOrigin",
  "Project@odata.associationLink": "https://devaos.cloudax.dynamics.com/data/SalesOrderHeadersV2(dataAreaId='usmf',SalesOrderNumber='000002')/Project/$ref",
  "Project@odata.navigationLink": "https://devaos.cloudax.dynamics.com/data/SalesOrderHeadersV2(dataAreaId='usmf',SalesOrderNumber='000002')/Project",
  "DimensionSet@odata.associationLink": "https://devaos.cloudax.dynamics.com/data/SalesOrderHeadersV2(dataAreaId='usmf',SalesOrderNumber='000002')/DimensionSet/$ref",
  "DimensionSet@odata.navigationLink": "https://devaos.cloudax.dynamics.com/data/SalesOrderHeadersV2(dataAreaId='usmf',SalesOrderNumber='000002')/DimensionSet",
  "QualityOrderHeaders@odata.associationLink": "https://devaos.cloudax.dynamics.com/data/SalesOrderHeadersV2(dataAreaId='usmf',SalesOrderNumber='000002')/QualityOrderHeaders/$ref",
  "QualityOrderHeaders@odata.navigationLink": "https://devaos.cloudax.dynamics.com/data/SalesOrderHeadersV2(dataAreaId='usmf',SalesOrderNumber='000002')/QualityOrderHeaders",
  "SalesOrderLines@odata.associationLink": "https://devaos.cloudax.dynamics.com/data/SalesOrderHeadersV2(dataAreaId='usmf',SalesOrderNumber='000002')/SalesOrderLines/$ref",
  "SalesOrderLines@odata.navigationLink": "https://devaos.cloudax.dynamics.com/data/SalesOrderHeadersV2(dataAreaId='usmf',SalesOrderNumber='000002')/SalesOrderLines",
  "SalesOrderLines": [
    {
      "@odata.type": "#Microsoft.Dynamics.DataEntities.SalesOrderLine",
      "@odata.id": "https://devaos.cloudax.dynamics.com/data/SalesOrderLines(dataAreaId='usmf',InventoryLotId='000221')",
      "@odata.etag": "W/\"JzAsNTYzNzE0NDU3NjswLDA7MCwwOzAsMDswLDA7MCwwJw==\"",
      "@odata.editLink": "SalesOrderLines(dataAreaId='usmf',InventoryLotId='000221')",
      "dataAreaId": "usmf",
      "InventoryLotId": "000221",
    ...
      "SalesOrderLineStatus": "Invoiced",
      "ProjectCategoryId": "",
      "ItemNumber": "D0001",
      "DeliveryAddressDescription": "",
...
      "SalesOrderNumber": "000002",
...
      "RevRecContractStartDate@odata.type": "#DateTimeOffset",
      "RevRecContractStartDate": "1900-01-01T12:00:00Z",
      "SalesOrderHeaderV2@odata.associationLink": "https://devaos.cloudax.dynamics.com/data/SalesOrderLines(dataAreaId='usmf',InventoryLotId='000221')/SalesOrderHeaderV2/$ref",
      "SalesOrderHeaderV2@odata.navigationLink": "https://devaos.cloudax.dynamics.com/data/SalesOrderLines(dataAreaId='usmf',InventoryLotId='000221')/SalesOrderHeaderV2",
      "SalesOrderHeader@odata.associationLink": "https://devaos.cloudax.dynamics.com/data/SalesOrderLines(dataAreaId='usmf',InventoryLotId='000221')/SalesOrderHeader/$ref",
      "SalesOrderHeader@odata.navigationLink": "https://devaos.cloudax.dynamics.com/data/SalesOrderLines(dataAreaId='usmf',InventoryLotId='000221')/SalesOrderHeader",
      "DimensionSet@odata.associationLink": "https://devaos.cloudax.dynamics.com/data/SalesOrderLines(dataAreaId='usmf',InventoryLotId='000221')/DimensionSet/$ref",
      "DimensionSet@odata.navigationLink": "https://devaos.cloudax.dynamics.com/data/SalesOrderLines(dataAreaId='usmf',InventoryLotId='000221')/DimensionSet",
      "DimensionCombination@odata.associationLink": "https://devaos.cloudax.dynamics.com/data/SalesOrderLines(dataAreaId='usmf',InventoryLotId='000221')/DimensionCombination/$ref",
      "DimensionCombination@odata.navigationLink": "https://devaos.cloudax.dynamics.com/data/SalesOrderLines(dataAreaId='usmf',InventoryLotId='000221')/DimensionCombination"
    },
    {
      "@odata.type": "#Microsoft.Dynamics.DataEntities.SalesOrderLine",
      "@odata.id": "https://devaos.cloudax.dynamics.com/data/SalesOrderLines(dataAreaId='usmf',InventoryLotId='000222')",
      "@odata.etag": "W/\"JzAsNTYzNzE0NDU3NzswLDA7MCwwOzAsMDswLDA7MCwwJw==\"",
      "@odata.editLink": "SalesOrderLines(dataAreaId='usmf',InventoryLotId='000222')",
      "dataAreaId": "usmf",
      "InventoryLotId": "000222",
...
    },
    {
      "@odata.type": "#Microsoft.Dynamics.DataEntities.SalesOrderLine",
      "@odata.id": "https://devaos.cloudax.dynamics.com/data/SalesOrderLines(dataAreaId='usmf',InventoryLotId='000223')",
      "@odata.etag": "W/\"JzAsNTYzNzE0NDU3ODswLDA7MCwwOzAsMDswLDA7MCwwJw==\"",
      "@odata.editLink": "SalesOrderLines(dataAreaId='usmf',InventoryLotId='000223')",
      "dataAreaId": "usmf",
      "InventoryLotId": "000223",
   ...
    },
    {
      "@odata.type": "#Microsoft.Dynamics.DataEntities.SalesOrderLine",
      "@odata.id": "https://devaos.cloudax.dynamics.com/data/SalesOrderLines(dataAreaId='usmf',InventoryLotId='000224')",
      "@odata.etag": "W/\"JzAsNTYzNzE0NDU3OTswLDA7MCwwOzAsMDswLDA7MCwwJw==\"",
      "@odata.editLink": "SalesOrderLines(dataAreaId='usmf',InventoryLotId='000224')",
      "dataAreaId": "usmf",
      "InventoryLotId": "000224",
...
    },
    {
      "@odata.type": "#Microsoft.Dynamics.DataEntities.SalesOrderLine",
      "@odata.id": "https://devaos.cloudax.dynamics.com/data/SalesOrderLines(dataAreaId='usmf',InventoryLotId='000225')",
      "@odata.etag": "W/\"JzAsNTYzNzE0NDU4MDswLDA7MCwwOzAsMDswLDA7MCwwJw==\"",
      "@odata.editLink": "SalesOrderLines(dataAreaId='usmf',InventoryLotId='000225')",
      "dataAreaId": "usmf",
      "InventoryLotId": "000225",
 ...
    }
  ]
}
```

мы можем использовать дополнительные параметры в \$expand запросе
`GET https://{{base_url}}/data/SalesOrderHeadersV2?$top=1&$select=SalesOrderNumber&$expand=SalesOrderLines($select=InventoryLotId,ItemNumber,SalesOrderNumber)`

вернет

```json
{
  "@odata.context": "https://devaos.cloudax.dynamics.com/data/$metadata#SalesOrderHeadersV2(SalesOrderNumber,SalesOrderLines,SalesOrderLines(InventoryLotId,ItemNumber,SalesOrderNumber))",
  "value": [
    {
      "@odata.etag": "W/\"JzAsNTYzNzE0NDU3NjswLDA7MCwwOzAsMDswLDA7MCwwJw==\"",
      "SalesOrderNumber": "000002",
      "SalesOrderLines": [
        {
          "@odata.etag": "W/\"JzAsNTYzNzE0NDU3NjswLDA7MCwwOzAsMDswLDA7MCwwJw==\"",
          "InventoryLotId": "000221",
          "ItemNumber": "D0001",
          "SalesOrderNumber": "000002"
        },
        {
          "@odata.etag": "W/\"JzAsNTYzNzE0NDU3NzswLDA7MCwwOzAsMDswLDA7MCwwJw==\"",
          "InventoryLotId": "000222",
          "ItemNumber": "L0001",
          "SalesOrderNumber": "000002"
        },
        {
          "@odata.etag": "W/\"JzAsNTYzNzE0NDU3ODswLDA7MCwwOzAsMDswLDA7MCwwJw==\"",
          "InventoryLotId": "000223",
          "ItemNumber": "P0001",
          "SalesOrderNumber": "000002"
        },
        {
          "@odata.etag": "W/\"JzAsNTYzNzE0NDU3OTswLDA7MCwwOzAsMDswLDA7MCwwJw==\"",
          "InventoryLotId": "000224",
          "ItemNumber": "D0003",
          "SalesOrderNumber": "000002"
        },
        {
          "@odata.etag": "W/\"JzAsNTYzNzE0NDU4MDswLDA7MCwwOzAsMDswLDA7MCwwJw==\"",
          "InventoryLotId": "000225",
          "ItemNumber": "D0004",
          "SalesOrderNumber": "000002"
        }
      ]
    }
  ]
}
```

### cross-company=true

По умолчанию запросы выполняются к компании в которой по умолчанию привязан пользователь ассоциированный с парой `clientId`, `secret`
Для того что бы выполнить запрос по всем компаниям компаниям, необходимо добавить параметр `cross-company=true`

## Вставка записей (Insert/POST)

Вставка осуществляется при помощи запроса `POST`

`POST https://{{base_url}}/data/CustomerGroups`

![IMG](/usefull/d365fo-rest-api-smart-talks/st203restapi15.png)

Закладка `Body`

```json
{
  "@odata.type": "#Microsoft.Dynamics.DataEntities.CustomerGroup",
  "CustomerGroupId": "T1",
  "dataAreaId": "usmf",
  "Description": "Test group T1"
}
```

Где
`@odata.type` - тип записи который мы вставляем. Очень грубо говоря - Entity в которую мы осуществляем вставку называется CustomerGroups, мы в нее вставляемзапись типа #Microsoft.Dynamics.DataEntities.CustomerGroup. Внешне энтити и тип помут быть похожи, а могут быть не похожи.
Заполняем поля - поля со звездочной - обязательные для заполнения поля

- `* "CustomerGroupId":"T1",`
- `* "dataAreaId":"usmf",`
- `"Description":"Test group T1"`

Выполняем запрос, получаем ответ

![IMG](/usefull/d365fo-rest-api-smart-talks/st203restapi16.png)

Статус ответа `201 Created` - запись создана

Выполняем запрос с фильтром на выборку и проверяем

`GET https://{{base_url}}/data/CustomerGroups?$filter=CustomerGroupId eq 'T1'`

```json
{
  "@odata.context": "https://devaos.cloudax.dynamics.com/data/$metadata#CustomerGroups",
  "value": [
    {
      "@odata.type": "#Microsoft.Dynamics.DataEntities.CustomerGroup",
      "@odata.id": "https://devaos.cloudax.dynamics.com/data/CustomerGroups(dataAreaId='usmf',CustomerGroupId='T1')",
      "@odata.etag": "W/\"JzEsNjg3MTk0ODI4MzMn\"",
      "@odata.editLink": "CustomerGroups(dataAreaId='usmf',CustomerGroupId='T1')",
      "dataAreaId": "usmf",
      "CustomerGroupId": "T1",
      "ClearingPeriodPaymentTermName": "",
      "CustomerAccountNumberSequence": "",
      "DefaultDimensionDisplayValue": "",
      "Description": "Test group T1",
      "IsSalesTaxIncludedInPrice@odata.type": "#Microsoft.Dynamics.DataEntities.NoYes",
      "IsSalesTaxIncludedInPrice": "No",
      "WriteOffReason": "",
      "PaymentTermId": "",
      "TaxGroupId": "",
      "DimensionSet@odata.associationLink": "https://devaos.cloudax.dynamics.com/data/CustomerGroups(dataAreaId='usmf',CustomerGroupId='T1')/DimensionSet/$ref",
      "DimensionSet@odata.navigationLink": "https://devaos.cloudax.dynamics.com/data/CustomerGroups(dataAreaId='usmf',CustomerGroupId='T1')/DimensionSet",
      "Prospects@odata.associationLink": "https://devaos.cloudax.dynamics.com/data/CustomerGroups(dataAreaId='usmf',CustomerGroupId='T1')/Prospects/$ref",
      "Prospects@odata.navigationLink": "https://devaos.cloudax.dynamics.com/data/CustomerGroups(dataAreaId='usmf',CustomerGroupId='T1')/Prospects"
    }
  ]
}
```

## Обновление записей (Update/PUT)

`PUT https://{{base_url}}/data/CustomerGroups(dataAreaId='usmf',CustomerGroupId='T1')`

Обратите внимание - мы должны четко выбрать одну запись по ключу, и только тогда ее обновить.

`Headers` - такой же

`Body`

```json
{
  "@odata.type": "#Microsoft.Dynamics.DataEntities.CustomerGroup",
  "Description": "Test group T123"
}
```

Ответ `Status 204 No content`

![IMG](/usefull/d365fo-rest-api-smart-talks/st203restapi17.png)

проверяем ззапросом на выборку

`GET https://{{base_url}}/data/CustomerGroups?$filter=CustomerGroupId eq 'T1'`

```json
{
  "@odata.context": "https://devaos.cloudax.dynamics.com/data/$metadata#CustomerGroups",
  "value": [
    {
      "@odata.etag": "W/\"JzM0NjU2NTI5MCw2ODcxOTQ4MjgzMyc=\"",
      "dataAreaId": "usmf",
      "CustomerGroupId": "T1",
      "ClearingPeriodPaymentTermName": "",
      "CustomerAccountNumberSequence": "",
      "DefaultDimensionDisplayValue": "",
      "Description": "Test group T123",
      "IsSalesTaxIncludedInPrice": "No",
      "WriteOffReason": "",
      "PaymentTermId": "",
      "TaxGroupId": ""
    }
  ]
}
```

## Удаление записей (Delete/DELETE)

Заголовок тот же, боди -пустое, запрос `DELETE https://{{base_url}}/data/CustomerGroups(dataAreaId='usmf',CustomerGroupId='T1')`

Ответ

![IMG](/usefull/d365fo-rest-api-smart-talks/st203restapi18.png)

`Статус 204 - No Content`

проверяем `GET https://{{base_url}}/data/CustomerGroups?$filter=CustomerGroupId eq 'T1'`

![IMG](/usefull/d365fo-rest-api-smart-talks/st203restapi19.png)

Нет записей для отображения, мы справились

## Транзакция ttsbegin..ttscommit BATCH

Для того, что бы выполнить вставку многих записей в один раз мы должны выполнить запрос к сервису `batch`

`POST https://{{base_url}}/data/$batch`

В Header:

`Content-Type: multipart/mixed; boundary=batch_boundary`

`Body`:

```json
--batch_boundary
Content-Type: multipart/mixed; boundary=changeset_boundary

--changeset_boundary
Content-Type: application/http
Content-Transfer-Encoding: binary
Content-ID: 1

POST https://{{base_url}}/data/CustomerGroups HTTP/1.1
OData-Version: 4.0
OData-MaxVersion: 4.0
Content-Type: application/json;odata.metadata=minimal
Accept: application/json;odata.metadata=minimal
Accept-Charset: UTF-8

{
"@odata.type":"#Microsoft.Dynamics.DataEntities.CustomerGroup",
"CustomerGroupId":"Batch1",
"dataAreaId":"usmf",
"Description":"Batch 1 Test group T1"
}

--changeset_boundary
Content-Type: application/http
Content-Transfer-Encoding: binary
Content-ID: 2

POST https://{{base_url}}/data/CustomerGroups HTTP/1.1
OData-Version: 4.0
OData-MaxVersion: 4.0
Content-Type: application/json;odata.metadata=minimal
Accept: application/json;odata.metadata=minimal
Accept-Charset: UTF-8

{
"@odata.type":"#Microsoft.Dynamics.DataEntities.CustomerGroup",
"CustomerGroupId":"Batch2",
"dataAreaId":"usmf",
"Description":"Batch 2 Test group T1"
}

--batch_boundary--
```

![IMG](/usefull/d365fo-rest-api-smart-talks/st203restapi20.png)

Если по какой-то причине какая-то запись не вставилась - сервис `batch` вернет **статус 200** - что он отработал нормально. Другое дело, при вызове `multipart` нужно анализировать **все** ответы.

```json
--batchresponse_5a294678-02dd-4b16-94b9-5fd64e297a8e
Content-Type: multipart/mixed; boundary=changesetresponse_1209a811-16fe-40f4-98e9-5519c744549e

--changesetresponse_1209a811-16fe-40f4-98e9-5519c744549e
Content-Type: application/http
Content-Transfer-Encoding: binary
Content-ID: 1

HTTP/1.1 500 Internal Server Error
Content-Type: application/json; odata.metadata=minimal; charset=utf-8
OData-Version: 4.0

{
  "error":{
    "code":"","message":"An error has occurred.","innererror":{
      "message":"Write failed for table row of type 'CustCustomerGroupEntity'. Infolog: Info: Cannot create a record in Customer groups (CustGroup). Customer group: Batch2, Batch 2 Test group T1.\nThe record already exists..","type":"Microsoft.Dynamics.Platform.Integration.Services.OData.AxODataWriteException","stacktrace":"   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.UpdateProcessor.CreateEntity_Save(ChangeOperationContext context, ChangeInfo changeInfo)\r\n   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.UpdateManager.<>c__DisplayClass6_0.<CreateEntity>b__1(ChangeOperationContext context)\r\n   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.ChangeInfo.ExecuteActionsInCompanyContext(IEnumerable`1 actionList, ChangeOperationContext operationContext)\r\n   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.ChangeInfo.TrySave(ChangeOperationContext operationContext)\r\n   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.UpdateManager.SaveChanges()\r\n   at Microsoft.Dynamics.Platform.Integration.Services.OData.AxODataBatchHandler.<ExecuteRequestMessagesAsync>d__8.MoveNext()"
    }
  }
}
--changesetresponse_1209a811-16fe-40f4-98e9-5519c744549e--
--batchresponse_5a294678-02dd-4b16-94b9-5fd64e297a8e--
```

Обратите внимание - внутри по `Cintent-ID: 1` **ошибка!** Т.е. сервис отработал, но запись не вставлена. Попробуйте `multipart` запрсос на вставку запустить два раза-вы увидите такую ошибку

## Номерные серии

Работа с Entity позволяет получать автозаполнение полей стандартным способом. Например при вставке строк заказов на продажу достаточно заполнить всего пару полей в `POST` запросе

```json
{
  "@odata.type": "#Microsoft.Dynamics.DataEntities.SalesOrderLine",
  "ItemNumber": "D0001",
  "SalesOrderNumber": "001261"
}
```

Строка успешно создастся и поля единица измерения, кол-во, цена, сумма ... аналитики - заполнятся по умолчанию.

В случае вставки заказа на продажу (шапка) та же история

```json
{
  "@odata.type": "#Microsoft.Dynamics.DataEntities.SalesOrderHeaderV2",
  "CurrencyCode": "USD",
  "InvoiceCustomerAccountNumber": "US-001",
  "OrderingCustomerAccountNumber": "US-001",
  "dataAreaId": "usmf"
}
```

При этом номер заказа для шапки будет сгенерирован автоматически.

Что нам делать, если мы попробуем сделать вставку Шапки заказа и строк в одной транзакции при помощи `batch`?

Нам нужно что бы шапка и строки были с одним номером. Для этого у нас есть два варианта. Первый - нужно присвоить следующий номер или произвольный( в случае с произвольным номером- номерная серия для номера заказа на продажу должна допускать редактирование).

## Заключение

В принципе мы рассмотрели возможности применения данной технологии. Это не единственная технология интеграции в аксапте, но точно очень полезная. Понимая эти принципы - можно дальше идти с интеграцией в `MS Power Automate`.
