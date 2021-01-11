---
title: "Works with Purchase requisitions"
date: 2021-01-10
tags:
  - Purchase requisitions
tables:
  - PurchReqTable
  - PurchReqLine
Entitys: 
  - PurchaseRequisitionHeaderV2Entity
  - PurchaseRequisitionLineEntity
AXPath: Procurement and soursing\Purchase orders\Purchase requisitions
Operations:
  - Read
  - Create
  - Update
  - Delete
weight: 1
---

Entity is allowed to operate with Purchase requisitions in D365FO.

Need to be sure, that integration person should be in list who can create this document otherwise we have got error.

## Header PurchReqTable/PurchaseRequisitionHeaderV2Entity

To works with PurchReqTable we want to use PurchaseRequisitionHeaderV2Entity entity

### Key

- RequisitionNumber

### Fields

| Field name                          | Value example          | Description           |
| ----------------------------------- | ---------------------- | --------------------- |
| RequisitionNumber                   | "000021"               |                       |
| RequisitionStatus                   | "Closed"               | Default "Draft"       |
| DefaultAccountingDate               | "2017-01-23T12:00:00Z" | Default now           |
| DefaultBusinessJustificationDetails | ""                     |                       |
| DefaultProjectId                    | ""                     |                       |
| DefaultRequestedDate                | "2017-01-23T12:00:00Z" | Default now           |
| ProjectBuyingLegalEntityId          | "USMF"                 |                       |
| PreparerPersonnelNumber             | "000007"               |                       |
| DefaultBusinessJustificationCode    | "General"              |                       |
| (*)__RequisitionName__              | "Sara Thomas"          | Any text              |
| OnHoldExplanation                   | ""                     |                       |
| IsPurchaseRequisitionOnHold         | "No"                   |                       |
| RequisitionPurpose                  | "Consumption"          | Default "Consumption" |

### Postman

#### Request for get data

`GET: https://{{base_url}}/data/PurchaseRequisitionHeaders(RequisitionNumber='000021')`

<details>
    <summary>
    Header:
    </summary>

```json
OData-Version:4.0
OData-MaxVersion:4.0
Content-Type:application/json;odata.metadata=minimal
Accept:application/json;odata.metadata=minimal
Accept-Charset:UTF-8
Authorization:Bearer *
Host:{{base_url}}
```

</details>

<details>
<summary>
Response:
</summary>

```json
{
    "@odata.context": "https://{{base_url}}/data/$metadata#PurchaseRequisitionHeaders/$entity",
    "@odata.etag": "W/\"JzAsNTYzNzE1MzYwMjswLDU2MzcxNTM3NzUn\"",
    "RequisitionNumber": "000021",
    "RequisitionStatus": "Closed",
    "DefaultAccountingDate": "2017-01-23T12:00:00Z",
    "DefaultBusinessJustificationDetails": "",
    "DefaultProjectId": "",
    "DefaultRequestedDate": "2017-01-23T12:00:00Z",
    "ProjectBuyingLegalEntityId": "USMF",
    "PreparerPersonnelNumber": "000007",
    "DefaultBusinessJustificationCode": "General",
    "RequisitionName": "Sara Thomas",
    "OnHoldExplanation": "",
    "IsPurchaseRequisitionOnHold": "No",
    "RequisitionPurpose": "Consumption"
}
```

</details>

#### Request for create data

`POST : https://{{base_url}}/data/PurchaseRequisitionHeaders`

<details>
    <summary>
    Header:
    </summary>

```json
OData-Version:4.0
OData-MaxVersion:4.0
Content-Type:application/json;odata.metadata=minimal
Accept:application/json;odata.metadata=minimal
Accept-Charset:UTF-8
Authorization:Bearer *
Host:{{base_url}}
```

</details>

<details>
    <summary>
    body:
    </summary>

```json
{
    "@odata.type":"#Microsoft.Dynamics.DataEntities.PurchaseRequisitionHeader",
    "RequisitionName": "Sara Thomas"
}
```

</details>

<details>
<summary>
Response:

</summary>

```json
{
    "@odata.context": "https://{{base_url}}/data/$metadata#PurchaseRequisitionHeaders/$entity",
    "@odata.etag": "W/\"JzEsNjg3MTk0NzY4OTM7MSw2ODcxOTQ3ODA0NSc=\"",
    "RequisitionNumber": "000032",
    "RequisitionStatus": "Draft",
    "DefaultAccountingDate": "2021-01-11T12:00:00Z",
    "DefaultBusinessJustificationDetails": "",
    "DefaultProjectId": "",
    "DefaultRequestedDate": "2021-01-11T12:00:00Z",
    "ProjectBuyingLegalEntityId": "",
    "PreparerPersonnelNumber": "",
    "DefaultBusinessJustificationCode": "",
    "RequisitionName": "Sara Thomas",
    "OnHoldExplanation": "",
    "IsPurchaseRequisitionOnHold": "No",
    "RequisitionPurpose": "Consumption"
}
```

</details>

#### Request for update data

`PATCH : https://{{base_url}}/data/PurchaseRequisitionHeaders(RequisitionNumber='000021')`

<details>
    <summary>
    Header:
    </summary>

```json
OData-Version:4.0
OData-MaxVersion:4.0
Content-Type:application/json;odata.metadata=minimal
Accept:application/json;odata.metadata=minimal
Accept-Charset:UTF-8
Authorization:Bearer *
Host:{{base_url}}
```

</details>

<details>
    <summary>
    body:
    </summary>

```json
{
    "@odata.type":"#Microsoft.Dynamics.DataEntities.PurchaseRequisitionHeader",
    "RequisitionName": "Sara Thomas2",
    "DefaultRequestedDate": "2021-01-12T12:00:00Z"
}
```

</details>

<details>
    <summary>
    Response:
    </summary>
    Status: 204
</details>

#### Request for delete data

`DELETE : https://{{base_url}}/data/PurchaseRequisitionHeaders(RequisitionNumber='000032')`

<details>
    <summary>
    Header:
    </summary>

```json
OData-Version:4.0
OData-MaxVersion:4.0
Content-Type:application/json;odata.metadata=minimal
Accept:application/json;odata.metadata=minimal
Accept-Charset:UTF-8
Authorization:Bearer *
Host:{{base_url}}
```

</details>

<details>
<summary>
Response:
</summary>
Status: 204
</details>

## Header PurchReqLine/PurchaseRequisitionLineEntity

To works with PurchReqTable we want to use PurchaseRequisitionLines entity

### Key

- RequisitionNumber
- RequisitionLineNumber

### Fields

| Field name                          | Value example                                                                                | Description |
| ----------------------------------- | -------------------------------------------------------------------------------------------- | ----------- |
| (*)__RequisitionNumber__            | "000021"                                                                                     |             |
| (*)__RequisitionLineNumber__        | 1                                                                                            |             |
| FixedAssetRuleQualifierOptionName   | ""                                                                                           |             |
| (*)__BuyingLegalEntityId__          | "USMF"                                                                                       |             |
| VendorAccountNumber                 | "US-111"                                                                                     |             |
| BusinessJustificationDetails        | ""                                                                                           |             |
| ProductStyleId                      | ""                                                                                           |             |
| LineStatus                          | "Closed"                                                                                     |             |
| DeliveryAddressLocationId           | "000001098"                                                                                  |             |
| IsPrepaymentRequired                | "No"                                                                                         |             |
| DeliveryAddressCountyId             | "ASOTIN"                                                                                     |             |
| PrePaymentDetails                   | ""                                                                                           |             |
| RequisitionerPersonnelNumber        | "000007"                                                                                     |             |
| ReceivingSiteId                     | "1"                                                                                          |             |
| DeliveryAddressCountryRegionISOCode | "US"                                                                                         |             |
| LineDiscountAmount                  | 0                                                                                            |             |
| DeliveryAddressBuildingCompliment   | ""                                                                                           |             |
| IsPartialDeliveryPrevented          | "No"                                                                                         |             |
| LineDescription                     | "Share each moment as it happens, in High Definition (720p or 1080p), with this stylish,..." |             |
| (*)__ItemNumber__                   | "C0004"                                                                                      |             |
| DeliveryAddressZipCode              | "98544"                                                                                      |             |
| DeliveryAttentionInformation        | ""                                                                                           |             |
| DeliveryAddressDistrictName         | ""                                                                                           |             |
| DeliveryCityInKana                  | ""                                                                                           |             |
| DeliveryAddressDunsNumber           | ""                                                                                           |             |
| LineAmount                          | 39.95                                                                                        |             |
| ProductSizeId                       | ""                                                                                           |             |
| LineDiscountPercentage              | 0                                                                                            |             |
| RFQRequirementLevel                 | "None"                                                                                       |             |
| FixedPriceCharges                   | 0,                                                                                           |             |
| ProjectSalesPrice                   | 0,                                                                                           |             |
| SalesTaxGroupCode                   | "No-Tax"                                                                                     |             |
| ProductName                         | ""                                                                                           |             |
| DeliveryAddressStreet               | "213 South Street, Gate 1"                                                                   |             |
| PurchasePriceQuantity               | 1                                                                                            |             |
| IsDeliveryAddressPrivate            | "No"                                                                                         |             |
| PurchasePrice                       | 39.95                                                                                        |             |
| DeliveryAddressCity                 | "Galvin"                                                                                     |             |
| LineType                            | "Item"                                                                                       |             |
| AccountingDate                      | "2017-01-23T12:00:00Z"                                                                       |             |
| ProjectSalesCurrencyCode            | ""                                                                                           |             |
| ProductConfigurationId              | ""                                                                                           |             |
| DeliveryAddressCountryRegionId      | "USA"                                                                                        |             |
| BudgetReservationDocumentNumber     | ""                                                                                           |             |
| BudgetReservationLineNumber         | 0                                                                                            |             |
| ProjectActivityNumber               | ""                                                                                           |             |
| (*)__PurchaseUnitSymbol__           | "ea"                                                                                         |             |
| RequestedDate                       | "2017-01-23T12:00:00Z"                                                                       |             |
| URL                                 | ""                                                                                           |             |
| DeliveryAddressPostBox              | ""                                                                                           |             |
| DeliveryAddressDescription          | "Site 1"                                                                                     |             |
| DeliveryStreetInKana                | ""                                                                                           |             |
| SalesTaxItemGroupCode               | "ALL"                                                                                        |             |
| ProductVersionId                    | ""                                                                                           |             |
| DeliveryAddressLatitude             | 0                                                                                            |             |
| ProjectId                           | ""                                                                                           |             |
| RequestedPurchaseQuantity           | 1                                                                                            |             |
| DeliveryAddressTimeZone             | null                                                                                         |             |
| ProjectSalesUnitSymbol              | ""                                                                                           |             |
| FormattedDeliveryAddress            | "213 South Street, Gate 1\nGalvin, WA 98544 \nUSA"                                           |             |
| ExternalItemNumber                  | ""                                                                                           |             |
| ItemBatchNumber                     | ""                                                                                           |             |
| DeliveryAddressName                 | "Contoso Entertainment System USA"                                                           |             |
| ProductColorId                      | ""                                                                                           |             |
| ProjectCategoryId                   | ""                                                                                           |             |
| FixedAssetReasonCode                | ""                                                                                           |             |
| DeliveryAddressStateId              | "WA"                                                                                         |             |
| ProjectLinePropertyId               | ""                                                                                           |             |
| ProjectTaxGroupCode                 | ""                                                                                           |             |
| ProjectTaxItemGroupCode             | ""                                                                                           |             |
| BusinessJustificationCode           | "General"                                                                                    |             |
| ProcurementProductCategoryName      | "Computers"                                                                                  |             |
| DeliveryAddressStreetNumber         | ""                                                                                           |             |
| (*)__CurrencyCode__                        | "USD"                                                                                        |             |
| DeliveryAddressLongitude            | 0                                                                                            |             |
| FixedAssetGroupId                   | ""                                                                                           |             |
| DefaultLedgerDimensionDisplayValue  | "001--"                                                                                      |             |
| IsDeliveryAddressOrderSpecific      | "No"                                                                                         |             |
| AccountingDistributionTemplateName  | ""                                                                                           |             |
| ReceivingWarehouseId                | "13"                                                                                         |             |
| ReceivingOperatingUnitNumber        | "024"                                                                                        |             |

### Postman

#### Request for get data

`GET: https://{{base_url}}/data/PurchaseRequisitionLines(RequisitionNumber='000021',RequisitionLineNumber=1)`

<details>
    <summary>
    Header:
    </summary>

```json
OData-Version:4.0
OData-MaxVersion:4.0
Content-Type:application/json;odata.metadata=minimal
Accept:application/json;odata.metadata=minimal
Accept-Charset:UTF-8
Authorization:Bearer *
Host:{{base_url}}
```

</details>

<details>
<summary>
Response:
</summary>

```json
{
    "@odata.context": "https://{{base_url}}/data/$metadata#PurchaseRequisitionLines/$entity",
    "@odata.etag": "W/\"JzAsNTYzNzE1Mzc0OTswLDU2MzcxNTM3NzY7MCwyMjU2NTQyNjk4OTswLDA7MCwwJw==\"",
    "RequisitionNumber": "000021",
    "RequisitionLineNumber": 1,
    "FixedAssetRuleQualifierOptionName": "",
    "BuyingLegalEntityId": "USMF",
    "VendorAccountNumber": "US-111",
    "BusinessJustificationDetails": "",
    "ProductStyleId": "",
    "LineStatus": "Closed",
    "DeliveryAddressLocationId": "000001098",
    "IsPrepaymentRequired": "No",
    "DeliveryAddressCountyId": "ASOTIN",
    "PrePaymentDetails": "",
    "RequisitionerPersonnelNumber": "000007",
    "ReceivingSiteId": "1",
    "DeliveryAddressCountryRegionISOCode": "US",
    "LineDiscountAmount": 0,
    "DeliveryAddressBuildingCompliment": "",
    "IsPartialDeliveryPrevented": "No",
    "LineDescription": "Share each moment as it happens, in High Definition (720p or 1080p), with this stylish,...",
    "ItemNumber": "C0004",
    "DeliveryAddressZipCode": "98544",
    "DeliveryAttentionInformation": "",
    "DeliveryAddressDistrictName": "",
    "DeliveryCityInKana": "",
    "DeliveryAddressDunsNumber": "",
    "LineAmount": 39.95,
    "ProductSizeId": "",
    "LineDiscountPercentage": 0,
    "RFQRequirementLevel": "None",
    "FixedPriceCharges": 0,
    "ProjectSalesPrice": 0,
    "SalesTaxGroupCode": "No-Tax",
    "ProductName": "",
    "DeliveryAddressStreet": "213 South Street, Gate 1",
    "PurchasePriceQuantity": 1,
    "IsDeliveryAddressPrivate": "No",
    "PurchasePrice": 39.95,
    "DeliveryAddressCity": "Galvin",
    "LineType": "Item",
    "AccountingDate": "2017-01-23T12:00:00Z",
    "ProjectSalesCurrencyCode": "",
    "ProductConfigurationId": "",
    "DeliveryAddressCountryRegionId": "USA",
    "BudgetReservationDocumentNumber": "",
    "BudgetReservationLineNumber": 0,
    "ProjectActivityNumber": "",
    "PurchaseUnitSymbol": "ea",
    "RequestedDate": "2017-01-23T12:00:00Z",
    "URL": "",
    "DeliveryAddressPostBox": "",
    "DeliveryAddressDescription": "Site 1",
    "DeliveryStreetInKana": "",
    "SalesTaxItemGroupCode": "ALL",
    "ProductVersionId": "",
    "DeliveryAddressLatitude": 0,
    "ProjectId": "",
    "RequestedPurchaseQuantity": 1,
    "DeliveryAddressTimeZone": null,
    "ProjectSalesUnitSymbol": "",
    "FormattedDeliveryAddress": "213 South Street, Gate 1\nGalvin, WA 98544 \nUSA",
    "ExternalItemNumber": "",
    "ItemBatchNumber": "",
    "DeliveryAddressName": "Contoso Entertainment System USA",
    "ProductColorId": "",
    "ProjectCategoryId": "",
    "FixedAssetReasonCode": "",
    "DeliveryAddressStateId": "WA",
    "ProjectLinePropertyId": "",
    "ProjectTaxGroupCode": "",
    "ProjectTaxItemGroupCode": "",
    "BusinessJustificationCode": "General",
    "ProcurementProductCategoryName": "Computers",
    "DeliveryAddressStreetNumber": "",
    "CurrencyCode": "USD",
    "DeliveryAddressLongitude": 0,
    "FixedAssetGroupId": "",
    "DefaultLedgerDimensionDisplayValue": "001--",
    "IsDeliveryAddressOrderSpecific": "No",
    "AccountingDistributionTemplateName": "",
    "ReceivingWarehouseId": "13",
    "ReceivingOperatingUnitNumber": "024"
}
```

</details>

#### Request for create data

`POST: https://{{base_url}}/data/PurchaseRequisitionLines`

<details>
    <summary>
    Header:
    </summary>

```json
OData-Version:4.0
OData-MaxVersion:4.0
Content-Type:application/json;odata.metadata=minimal
Accept:application/json;odata.metadata=minimal
Accept-Charset:UTF-8
Authorization:Bearer *
Host:{{base_url}}
```

</details>

<details>
    <summary>
    body:
    </summary>

```json
{
    "@odata.type" : "#Microsoft.Dynamics.DataEntities.PurchaseRequisitionLine",
    "BuyingLegalEntityId" : "USMF",
    "RequisitionNumber" : "000034",
    "RequisitionLineNumber" : 1,
    "PurchaseUnitSymbol": "ea",
    "ItemNumber": "C0004",
    "CurrencyCode": "USD"
}
```

</details>

<details>
<summary>
Response:

</summary>

```json
{
    "@odata.context": "https://{{base_url}}/data/$metadata#PurchaseRequisitionLines/$entity",
    "@odata.etag": "W/\"JzEsNjg3MTk0Nzc4ODM7MSw2ODcxOTQ3ODA0NzswLDIyNTY1NDI2OTg5OzAsMDswLDAn\"",
    "RequisitionNumber": "000034",
    "RequisitionLineNumber": 1,
    "FixedAssetRuleQualifierOptionName": "",
    "BuyingLegalEntityId": "USMF",
    "VendorAccountNumber": "US-111",
    "BusinessJustificationDetails": "",
    "ProductStyleId": "",
    "LineStatus": "Draft",
    "DeliveryAddressLocationId": "000001098",
    "IsPrepaymentRequired": "No",
    "DeliveryAddressCountyId": "ASOTIN",
    "PrePaymentDetails": "",
    "RequisitionerPersonnelNumber": "",
    "ReceivingSiteId": "1",
    "DeliveryAddressCountryRegionISOCode": "US",
    "LineDiscountAmount": 0,
    "DeliveryAddressBuildingCompliment": "",
    "IsPartialDeliveryPrevented": "No",
    "LineDescription": "Lifecam HD 5000\nShare each moment as it happens, in High Definition (720p or 1080p), with this stylish, feature-packed webcam. It fits any monitor – desktop or notebook – and is surprisingly affordable.",
    "ItemNumber": "C0004",
    "DeliveryAddressZipCode": "98544",
    "DeliveryAttentionInformation": "Building B - 5053",
    "DeliveryAddressDistrictName": "",
    "DeliveryCityInKana": "",
    "DeliveryAddressDunsNumber": "",
    "LineAmount": 39.95,
    "ProductSizeId": "",
    "LineDiscountPercentage": 0,
    "RFQRequirementLevel": "None",
    "FixedPriceCharges": 0,
    "ProjectSalesPrice": 0,
    "SalesTaxGroupCode": "No-Tax",
    "ProductName": "",
    "DeliveryAddressStreet": "213 South Street, Gate 1",
    "PurchasePriceQuantity": 1,
    "IsDeliveryAddressPrivate": "No",
    "PurchasePrice": 39.95,
    "DeliveryAddressCity": "Galvin",
    "LineType": "Item",
    "AccountingDate": "2021-01-11T12:00:00Z",
    "ProjectSalesCurrencyCode": "",
    "ProductConfigurationId": "",
    "DeliveryAddressCountryRegionId": "USA",
    "BudgetReservationDocumentNumber": "",
    "BudgetReservationLineNumber": 0,
    "ProjectActivityNumber": "",
    "PurchaseUnitSymbol": "ea",
    "RequestedDate": "2021-01-11T12:00:00Z",
    "URL": "",
    "DeliveryAddressPostBox": "",
    "DeliveryAddressDescription": "Site 1",
    "DeliveryStreetInKana": "",
    "SalesTaxItemGroupCode": "ALL",
    "ProductVersionId": "",
    "DeliveryAddressLatitude": 0,
    "ProjectId": "",
    "RequestedPurchaseQuantity": 1,
    "DeliveryAddressTimeZone": null,
    "ProjectSalesUnitSymbol": "",
    "FormattedDeliveryAddress": "213 South Street, Gate 1\nGalvin, WA 98544 \nUSA",
    "ExternalItemNumber": "",
    "ItemBatchNumber": "",
    "DeliveryAddressName": "Site 1",
    "ProductColorId": "",
    "ProjectCategoryId": "",
    "FixedAssetReasonCode": "",
    "DeliveryAddressStateId": "WA",
    "ProjectLinePropertyId": "",
    "ProjectTaxGroupCode": "",
    "ProjectTaxItemGroupCode": "",
    "BusinessJustificationCode": "",
    "ProcurementProductCategoryName": "Computers",
    "DeliveryAddressStreetNumber": "",
    "CurrencyCode": "USD",
    "DeliveryAddressLongitude": 0,
    "FixedAssetGroupId": "",
    "DefaultLedgerDimensionDisplayValue": "",
    "IsDeliveryAddressOrderSpecific": "No",
    "AccountingDistributionTemplateName": "",
    "ReceivingWarehouseId": "13",
    "ReceivingOperatingUnitNumber": ""
}
```

</details>

#### Request for update data

`PATCH : https://{{base_url}}/data/PurchaseRequisitionLines(RequisitionNumber='000034',RequisitionLineNumber=1)`

<details>
    <summary>
    Header:
    </summary>

```json
OData-Version:4.0
OData-MaxVersion:4.0
Content-Type:application/json;odata.metadata=minimal
Accept:application/json;odata.metadata=minimal
Accept-Charset:UTF-8
Authorization:Bearer *
Host:{{base_url}}
```

</details>

<details>
    <summary>
    body:
    </summary>

```json
{
    "@odata.type":"#Microsoft.Dynamics.DataEntities.PurchaseRequisitionLine",
    "RequestedPurchaseQuantity": 10
}
```

</details>

<details>
    <summary>
    Response:
    </summary>
    Status: 204
</details>

#### Request for delete data

`DELETE : https://{{base_url}}/data/PurchaseRequisitionLines(RequisitionNumber='000034',RequisitionLineNumber=1)`

<details>
    <summary>
    Header:
    </summary>

```json
OData-Version:4.0
OData-MaxVersion:4.0
Content-Type:application/json;odata.metadata=minimal
Accept:application/json;odata.metadata=minimal
Accept-Charset:UTF-8
Authorization:Bearer *
Host:{{base_url}}
```

</details>

<details>
<summary>
Response:
</summary>
Status: 204
</details>

## Create Document Purchase requisitions

Need to allow Purchase requsition number sequence be changed by user

ALLOW USER CHANGES
- To a lower number = YES
- To a higher number = YES

`POST : https://{{base_url}}/data/$batch`

<details>
    <summary>
    Header:
    </summary>

```json
OData-Version:4.0
OData-MaxVersion:4.0
Content-Type:multipart/mixed; boundary=batch_boundary
Accept:multipart/mixed
Accept-Charset:UTF-8
Authorization:Bearer {{token}}
Host:{{base_url}}
```

</details>

<details>
    <summary>
    body:
    </summary>

```json
--batch_boundary
Content-Type: multipart/mixed; boundary=changeset_boundary

--changeset_boundary
Content-Type: application/http
Content-Transfer-Encoding: binary
Content-ID: 1

POST https://{{base_url}}/data/PurchaseRequisitionHeaders HTTP/1.1
OData-Version: 4.0
OData-MaxVersion: 4.0
Content-Type: application/json;odata.metadata=minimal
Accept: application/json;odata.metadata=minimal
Accept-Charset: UTF-8

{
    "@odata.type":"#Microsoft.Dynamics.DataEntities.PurchaseRequisitionHeader",
    "RequisitionName":     "Sara Thomas",
    "RequisitionNumber": "A00001"
}

--changeset_boundary
Content-Type: application/http
Content-Transfer-Encoding: binary
Content-ID: 2

POST https://{{base_url}}/data/PurchaseRequisitionLines HTTP/1.1
OData-Version: 4.0
OData-MaxVersion: 4.0
Content-Type: application/json;odata.metadata=minimal
Accept: application/json;odata.metadata=minimal
Accept-Charset: UTF-8

{
    "@odata.type" : "#Microsoft.Dynamics.DataEntities.PurchaseRequisitionLine",
    "BuyingLegalEntityId" : "USMF",
    "RequisitionNumber" : "A00001",
    "RequisitionLineNumber" : 1,
    "PurchaseUnitSymbol": "ea",
    "ItemNumber": "C0004",
    "CurrencyCode": "USD"
}

--changeset_boundary
Content-Type: application/http
Content-Transfer-Encoding: binary
Content-ID: 3

POST https://{{base_url}}/data/PurchaseRequisitionLines HTTP/1.1
OData-Version: 4.0
OData-MaxVersion: 4.0
Content-Type: application/json;odata.metadata=minimal
Accept: application/json;odata.metadata=minimal
Accept-Charset: UTF-8

{
    "@odata.type" : "#Microsoft.Dynamics.DataEntities.PurchaseRequisitionLine",
    "BuyingLegalEntityId" : "USMF",
    "RequisitionNumber" : "A00001",
    "RequisitionLineNumber" : 2,
    "PurchaseUnitSymbol": "ea",
    "ItemNumber": "C0004",
    "CurrencyCode": "USD"
}
--batch_boundary--

```

</details>

<details>
    <summary>
    Response:
    </summary>

```json
--batchresponse_deb96745-806f-47c0-8db3-b20bca8eacd2
Content-Type: multipart/mixed; boundary=changesetresponse_5a9702a1-e597-437f-b610-0ffb8e2df2f3

--changesetresponse_5a9702a1-e597-437f-b610-0ffb8e2df2f3
Content-Type: application/http
Content-Transfer-Encoding: binary
Content-ID: 1

HTTP/1.1 201 Created
ETag: W/"JzEsNjg3MTk0NzY4OTk7MSw2ODcxOTQ3ODA1Myc="
Location: https://{{base_url}}/data/PurchaseRequisitionHeaders('A00002')
Content-Type: application/json; odata.metadata=minimal
OData-Version: 4.0

{
    "@odata.context": "https://{{base_url}}/data/$metadata#PurchaseRequisitionHeaders/$entity",
    "@odata.etag": "W/\"JzEsNjg3MTk0NzY4OTk7MSw2ODcxOTQ3ODA1Myc=\"",
    "RequisitionNumber": "A00002",
    "RequisitionStatus": "Draft",
    "DefaultAccountingDate": "2021-01-11T12:00:00Z",
    "DefaultBusinessJustificationDetails": "",
    "DefaultProjectId": "",
    "DefaultRequestedDate": "2021-01-11T12:00:00Z",
    "ProjectBuyingLegalEntityId": "",
    "PreparerPersonnelNumber": "",
    "DefaultBusinessJustificationCode": "",
    "RequisitionName": "Sara Thomas",
    "OnHoldExplanation": "",
    "IsPurchaseRequisitionOnHold": "No",
    "RequisitionPurpose": "Consumption"
}
--changesetresponse_5a9702a1-e597-437f-b610-0ffb8e2df2f3
Content-Type: application/http
Content-Transfer-Encoding: binary
Content-ID: 2

HTTP/1.1 201 Created
ETag: W/"JzEsNjg3MTk0Nzc4ODY7MSw2ODcxOTQ3ODA1NDswLDIyNTY1NDI2OTg5OzAsMDswLDAn"
Location: https://{{base_url}}/data/PurchaseRequisitionLines(RequisitionNumber='A00002',RequisitionLineNumber=1)
Content-Type: application/json; odata.metadata=minimal
OData-Version: 4.0

{
    "@odata.context": "https://{{base_url}}/data/$metadata#PurchaseRequisitionLines/$entity",
    "@odata.etag": "W/\"JzEsNjg3MTk0Nzc4ODY7MSw2ODcxOTQ3ODA1NDswLDIyNTY1NDI2OTg5OzAsMDswLDAn\"",
    "RequisitionNumber": "A00002",
    "RequisitionLineNumber": 1,
    "FixedAssetRuleQualifierOptionName": "",
    "BuyingLegalEntityId": "USMF",
    "VendorAccountNumber": "US-111",
    "BusinessJustificationDetails": "",
    "ProductStyleId": "",
    "LineStatus": "Draft",
    "DeliveryAddressLocationId": "000001098",
    "IsPrepaymentRequired": "No",
    "DeliveryAddressCountyId": "ASOTIN",
    "PrePaymentDetails": "",
    "RequisitionerPersonnelNumber": "",
    "ReceivingSiteId": "1",
    "DeliveryAddressCountryRegionISOCode": "US",
    "LineDiscountAmount": 0,
    "DeliveryAddressBuildingCompliment": "",
    "IsPartialDeliveryPrevented": "No",
    "LineDescription": "Lifecam HD 5000\nShare each moment as it happens, in High Definition (720p or 1080p), with this stylish, feature-packed webcam. It fits any monitor \u2013 desktop or notebook \u2013 and is surprisingly affordable.",
    "ItemNumber": "C0004",
    "DeliveryAddressZipCode": "98544",
    "DeliveryAttentionInformation": "Building B - 5053",
    "DeliveryAddressDistrictName": "",
    "DeliveryCityInKana": "",
    "DeliveryAddressDunsNumber": "",
    "LineAmount": 39.95,
    "ProductSizeId": "",
    "LineDiscountPercentage": 0,
    "RFQRequirementLevel": "None",
    "FixedPriceCharges": 0,
    "ProjectSalesPrice": 0,
    "SalesTaxGroupCode": "No-Tax",
    "ProductName": "",
    "DeliveryAddressStreet": "213 South Street, Gate 1",
    "PurchasePriceQuantity": 1,
    "IsDeliveryAddressPrivate": "No",
    "PurchasePrice": 39.95,
    "DeliveryAddressCity": "Galvin",
    "LineType": "Item",
    "AccountingDate": "2021-01-11T12:00:00Z",
    "ProjectSalesCurrencyCode": "",
    "ProductConfigurationId": "",
    "DeliveryAddressCountryRegionId": "USA",
    "BudgetReservationDocumentNumber": "",
    "BudgetReservationLineNumber": 0,
    "ProjectActivityNumber": "",
    "PurchaseUnitSymbol": "ea",
    "RequestedDate": "2021-01-11T12:00:00Z",
    "URL": "",
    "DeliveryAddressPostBox": "",
    "DeliveryAddressDescription": "Site 1",
    "DeliveryStreetInKana": "",
    "SalesTaxItemGroupCode": "ALL",
    "ProductVersionId": "",
    "DeliveryAddressLatitude": 0,
    "ProjectId": "",
    "RequestedPurchaseQuantity": 1,
    "DeliveryAddressTimeZone": null,
    "ProjectSalesUnitSymbol": "",
    "FormattedDeliveryAddress": "213 South Street, Gate 1\nGalvin, WA 98544 \nUSA",
    "ExternalItemNumber": "",
    "ItemBatchNumber": "",
    "DeliveryAddressName": "Site 1",
    "ProductColorId": "",
    "ProjectCategoryId": "",
    "FixedAssetReasonCode": "",
    "DeliveryAddressStateId": "WA",
    "ProjectLinePropertyId": "",
    "ProjectTaxGroupCode": "",
    "ProjectTaxItemGroupCode": "",
    "BusinessJustificationCode": "",
    "ProcurementProductCategoryName": "Computers",
    "DeliveryAddressStreetNumber": "",
    "CurrencyCode": "USD",
    "DeliveryAddressLongitude": 0,
    "FixedAssetGroupId": "",
    "DefaultLedgerDimensionDisplayValue": "",
    "IsDeliveryAddressOrderSpecific": "No",
    "AccountingDistributionTemplateName": "",
    "ReceivingWarehouseId": "13",
    "ReceivingOperatingUnitNumber": ""
}
--changesetresponse_5a9702a1-e597-437f-b610-0ffb8e2df2f3
Content-Type: application/http
Content-Transfer-Encoding: binary
Content-ID: 3

HTTP/1.1 201 Created
ETag: W/"JzEsNjg3MTk0Nzc4ODc7MSw2ODcxOTQ3ODA1NTswLDIyNTY1NDI2OTg5OzAsMDswLDAn"
Location: https://{{base_url}}/data/PurchaseRequisitionLines(RequisitionNumber='A00002',RequisitionLineNumber=2)
Content-Type: application/json; odata.metadata=minimal
OData-Version: 4.0

{
    "@odata.context": "https://{{base_url}}/data/$metadata#PurchaseRequisitionLines/$entity",
    "@odata.etag": "W/\"JzEsNjg3MTk0Nzc4ODc7MSw2ODcxOTQ3ODA1NTswLDIyNTY1NDI2OTg5OzAsMDswLDAn\"",
    "RequisitionNumber": "A00002",
    "RequisitionLineNumber": 2,
    "FixedAssetRuleQualifierOptionName": "",
    "BuyingLegalEntityId": "USMF",
    "VendorAccountNumber": "US-111",
    "BusinessJustificationDetails": "",
    "ProductStyleId": "",
    "LineStatus": "Draft",
    "DeliveryAddressLocationId": "000001098",
    "IsPrepaymentRequired": "No",
    "DeliveryAddressCountyId": "ASOTIN",
    "PrePaymentDetails": "",
    "RequisitionerPersonnelNumber": "",
    "ReceivingSiteId": "1",
    "DeliveryAddressCountryRegionISOCode": "US",
    "LineDiscountAmount": 0,
    "DeliveryAddressBuildingCompliment": "",
    "IsPartialDeliveryPrevented": "No",
    "LineDescription": "Lifecam HD 5000\nShare each moment as it happens, in High Definition (720p or 1080p), with this stylish, feature-packed webcam. It fits any monitor – desktop or notebook – and is surprisingly affordable.",
    "ItemNumber": "C0004",
    "DeliveryAddressZipCode": "98544",
    "DeliveryAttentionInformation": "Building B - 5053",
    "DeliveryAddressDistrictName": "",
    "DeliveryCityInKana": "",
    "DeliveryAddressDunsNumber": "",
    "LineAmount": 39.95,
    "ProductSizeId": "",
    "LineDiscountPercentage": 0,
    "RFQRequirementLevel": "None",
    "FixedPriceCharges": 0,
    "ProjectSalesPrice": 0,
    "SalesTaxGroupCode": "No-Tax",
    "ProductName": "",
    "DeliveryAddressStreet": "213 South Street, Gate 1",
    "PurchasePriceQuantity": 1,
    "IsDeliveryAddressPrivate": "No",
    "PurchasePrice": 39.95,
    "DeliveryAddressCity": "Galvin",
    "LineType": "Item",
    "AccountingDate": "2021-01-11T12:00:00Z",
    "ProjectSalesCurrencyCode": "",
    "ProductConfigurationId": "",
    "DeliveryAddressCountryRegionId": "USA",
    "BudgetReservationDocumentNumber": "",
    "BudgetReservationLineNumber": 0,
    "ProjectActivityNumber": "",
    "PurchaseUnitSymbol": "ea",
    "RequestedDate": "2021-01-11T12:00:00Z",
    "URL": "",
    "DeliveryAddressPostBox": "",
    "DeliveryAddressDescription": "Site 1",
    "DeliveryStreetInKana": "",
    "SalesTaxItemGroupCode": "ALL",
    "ProductVersionId": "",
    "DeliveryAddressLatitude": 0,
    "ProjectId": "",
    "RequestedPurchaseQuantity": 1,
    "DeliveryAddressTimeZone": null,
    "ProjectSalesUnitSymbol": "",
    "FormattedDeliveryAddress": "213 South Street, Gate 1\nGalvin, WA 98544 \nUSA",
    "ExternalItemNumber": "",
    "ItemBatchNumber": "",
    "DeliveryAddressName": "Site 1",
    "ProductColorId": "",
    "ProjectCategoryId": "",
    "FixedAssetReasonCode": "",
    "DeliveryAddressStateId": "WA",
    "ProjectLinePropertyId": "",
    "ProjectTaxGroupCode": "",
    "ProjectTaxItemGroupCode": "",
    "BusinessJustificationCode": "",
    "ProcurementProductCategoryName": "Computers",
    "DeliveryAddressStreetNumber": "",
    "CurrencyCode": "USD",
    "DeliveryAddressLongitude": 0,
    "FixedAssetGroupId": "",
    "DefaultLedgerDimensionDisplayValue": "",
    "IsDeliveryAddressOrderSpecific": "No",
    "AccountingDistributionTemplateName": "",
    "ReceivingWarehouseId": "13",
    "ReceivingOperatingUnitNumber": ""
}
--changesetresponse_5a9702a1-e597-437f-b610-0ffb8e2df2f3--
--batchresponse_deb96745-806f-47c0-8db3-b20bca8eacd2--

```

</details>

