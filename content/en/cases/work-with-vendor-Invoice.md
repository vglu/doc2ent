---
title: Work with Vendor invoice
date: 2021-01-20
tags:
  - Vendor invoice
tables:
  - 1
  - 2
Entities: 
  - VendInvoiceJournalHeaderEntity
  - VendInvoiceJournalLineEntity
AXPath: Accounts payable\Invoices\Invoice journal
Operations:
  - Read
  - Create
  - Update
  - Delete
weight: 1
---

Entities is allowed to operate with Vendor invoice in D365FO.

## Header VendorInvoiceHeaderEntity

| Data entity AOT name           | Entity name (DMF)             | Public collection name (OData) | Support OData | Support DMF | Category | ReadOnly |
| ------------------------------ | ----------------------------- | ------------------------------ | ------------- | ----------- | -------- | -------- |
| VendInvoiceJournalHeaderEntity | Vendor invoice journal header | VendInvoiceJournalHeaders      | Yes           | Yes         | Document | No       |

[comment]: < FIXME: To works with `` we want to use `` entity >

### Key

- dataAreaId
- JournalBatchNumber

### Fields

| Field name         | Value example | Description |
| ------------------ | ------------- | ----------- |
| dataAreaId         | "usmf"        |             |
| JournalBatchNumber | "00461"       |             |
| (*)**JournalName** | "APInvoice"   |             |
| Description        | "AP Invoice"  |             |
| IsPosted           | "Yes"         |             |
| SalesTaxIncluded   | "No"          |             |

### Postman

#### Request for get data

`GET: https://{{base_url}}/data/VendInvoiceJournalHeaders(dataAreaId='usmf',JournalBatchNumber='00461')`

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
Authorization:Bearer {{token}}
Host:{{base_url}}
```

</details>

<details>
<summary>
Response:
</summary>

```json
{
    "@odata.context": "https://dev10plus15065719449a0027478devaos.cloudax.dynamics.com/data/$metadata#VendInvoiceJournalHeaders/$entity",
    "@odata.etag": "W/\"JzAsMjI1NjU0ODg4NzAn\"",
    "dataAreaId": "usmf",
    "JournalBatchNumber": "00461",
    "JournalName": "APInvoice",
    "Description": "AP Invoice",
    "IsPosted": "Yes",
    "SalesTaxIncluded": "No"
}
```

</details>

#### Request for create data

`POST : https://{{base_url}}/data/VendInvoiceJournalHeaders`

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
Authorization:Bearer {{token}}
Host:{{base_url}}
```

</details>

<details>
    <summary>
    body:
    </summary>

```json
{
    "@odata.type":"#Microsoft.Dynamics.DataEntities.VendInvoiceJournalHeader",
    "JournalName": "APInvoice"
}
```

</details>

<details>
<summary>
Response:

</summary>

```json
{
    "@odata.context": "https://dev10plus15065719449a0027478devaos.cloudax.dynamics.com/data/$metadata#VendInvoiceJournalHeaders/$entity",
    "@odata.etag": "W/\"JzEsNjg3MTk1MTIyNjEn\"",
    "dataAreaId": "usmf",
    "JournalBatchNumber": "00631",
    "JournalName": "APInvoice",
    "Description": "AP Invoice",
    "IsPosted": "No",
    "SalesTaxIncluded": "No"
}
```

</details>

#### Request for update data

`PATCH : https://{{base_url}}/data/VendInvoiceJournalHeaders(dataAreaId='usmf',JournalBatchNumber='00631')`

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
Authorization:Bearer {{token}}
Host:{{base_url}}
```

</details>

<details>
    <summary>
    body:
    </summary>

```json
{
    "@odata.type":"#Microsoft.Dynamics.DataEntities.VendInvoiceJournalHeader",
    "Description": "AP Invoice upd"
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

`DELETE : https://{{base_url}}/data/VendorPaymentJournalHeaders(dataAreaId='usmf',JournalBatchNumber='00629')`

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
Authorization:Bearer {{token}}
Host:{{base_url}}
```

</details>

<details>
<summary>
Response:
</summary>
Status: 204
</details>

## Lines VendInvoiceJournalLineEntity

| Data entity AOT name           | Entity name (DMF)           | Public collection name (OData) | Support OData | Support DMF | Category | ReadOnly |
| ------------------------------ | --------------------------- | ------------------------------ | ------------- | ----------- | -------- | -------- |
| VendInvoiceJournalLineEntity | Vendor invoice journal line | VendInvoiceJournalLines      | Yes           | Yes         | Document | No       |

To works with `` we want to use `` entity

### Key

- dataAreaId
- JournalBatchNumber
- LineNumber

### Fields

| Field name                                    | Value example                              | Description |
| --------------------------------------------- | ------------------------------------------ | ----------- |
| dataAreaId                                    | "usmf"                                     |             |
| (*)**JournalBatchNumber**                     | "00282"                                    |             |
| (*)**LineNumber**                             | 1                                          |             |
| InstructionKey1                               | "NotUsed"                                  |             |
| InstructionKey2                               | "NotUsed"                                  |             |
| UseSalesTaxDirectionFromMainAccount           | "No"                                       |             |
| InstructionKey3                               | "NotUsed"                                  |             |
| MarkedInvoice                                 | ""                                         |             |
| Voucher                                       | "APPM000001"                               |             |
| ServiceLevel                                  | 0                                          |             |
| OffsetAccountType                             | "Bank"                                     |             |
| FeeAccount                                    | ""                                         |             |
| PostdatedCheckCashierDisplayValue             | ""                                         |             |
| ErrorCodePayment                              | ""                                         |             |
| PostdatedCheckMaturityDate                    | "1900-01-01T12:00:00Z"                     |             |
| CheckNumber                                   | "2"                                        |             |
| LocalInstrument                               | 0                                          |             |
| NewJournalBatchNumber                         | ""                                         |             |
| SettleVoucher                                 | "SelectedTransact"                         |             |
| RemittanceAddressDistrictName                 | ""                                         |             |
| RemittanceAddressCountryISOCode               | "US"                                       |             |
| RemittanceAddressCounty                       | ""                                         |             |
| TransactionDate                               | "2015-02-03T12:00:00Z"                     |             |
| NACHAIATOFACScreeningIndicator                | "Zero"                                     |             |
| RemittanceAddressLongitude                    | 0                                          |             |
| BankTransactionType                           | "03"                                       |             |
| PaymentReference                              | "2"                                        |             |
| ChineseVoucherType                            | ""                                         |             |
| PostdatedCheckSalespersonDisplayValue         | ""                                         |             |
| NACHAIATForeignExchangeIndicator              | "None"                                     |             |
| NACHAIATForeignExchangeReferenceIndicator     | "One"                                      |             |
| RemittanceAddressZipCode                      | "94588"                                    |             |
| DebitAmount                                   | 6800                                       |             |
| RemittanceAddressStreet                       | "4 Main Street"                            |             |
| TaxItemGroup                                  | ""                                         |             |
| NACHAIATOFACSecondaryScreeningIndicator       | "Zero"                                     |             |
| ThirdPartyBankAccountId                       | ""                                         |             |
| TransactionText                               | ""                                         |             |
| FullPrimaryRemittanceAddress                  | "4 Main Street\nPleasanton CA 94588 \nUSA" |             |
| RemittanceAddressValidTo                      | "2154-12-31T23:59:59Z"                     |             |
| PostdatedCheckNumber                          | ""                                         |             |
| OffsetAccountDisplayValue                     | "USMF OPER"                                |             |
| AccountDisplayValue                           | "US\\-108"                                 |             |
| ChargeBearer                                  | 0                                          |             |
| DefaultDimensionsForAccountDisplayValue       | "001--"                                    |             |
| PostdatedCheckOriginalCheckNumber             | ""                                         |             |
| PaymentMethodName                             | "CHECK"                                    |             |
| RemittanceAddressCity                         | "Pleasanton CA"                            |             |
| RemittanceAddressLatitude                     | 0                                          |             |
| CentralBankImportDate                         | "1900-01-01T12:00:00Z"                     |             |
| NACHAIATReceivingDFIQualifier                 | "One"                                      |             |
| OffsetTransactionText                         | ""                                         |             |
| MarkedInvoiceCompany                          | ""                                         |             |
| PaymentSpecification                          | ""                                         |             |
| PostdatedCheckIsReplacementCheck              | "No"                                       |             |
| NACHAIATOriginatingDFIQualifier               | "One"                                      |             |
| AccountType                                   | "Vend"                                     |             |
| TaxGroup                                      | ""                                         |             |
| ContactPerson                                 | ""                                         |             |
| RemittanceAddressState                        | ""                                         |             |
| RemittanceAddressDescription                  | "Reception"                                |             |
| ExchangeRate                                  | 100                                        |             |
| ReportingCurrencyExchRate                     | 0                                          |             |
| RemittanceAddressValidFrom                    | "2012-05-09T17:27:02Z"                     |             |
| RemittanceAddressCountry                      | "USA"                                      |             |
| PaymentId                                     | ""                                         |             |
| RemittanceAddressTimeZone                     | null                                       |             |
| RemittanceLocationId                          | "000000013"                                |             |
| PostingProfile                                | "GEN"                                      |             |
| CalculateWithholdingTax                       | "No"                                       |             |
| PostdatedCheckReasonForStop                   | ""                                         |             |
| VendorName                                    | "City Power & Light"                       |             |
| CategoryPurpose                               | 0                                          |             |
| CreditAmount                                  | 0                                          |             |
| RestrictedForwarding                          | "No"                                       |             |
| OffsetCompany                                 | "usmf"                                     |             |
| IsPrepayment                                  | "No"                                       |             |
| NACHAIATForeignExchangeReference              | ""                                         |             |
| ItemWithholdingTaxGroupCode                   | ""                                         |             |
| DefaultDimensionsForOffsetAccountDisplayValue | "001--"                                    |             |
| ReportingCurrencyExchRateSecondary            | 0                                          |             |
| (*)**CurrencyCode**                           | "USD"                                      |             |
| Company                                       | "usmf"                                     |             |
| SecondaryExchangeRate                         | 0                                          |             |
| PostdatedCheckReceivedDate                    | "1900-01-01T12:00:00Z"                     |             |
| PostdatedCheckBankBranch                      | ""                                         |             |
| CentralBankPurposeCode                        | ""                                         |             |
| PostdatedCheckReplacementComments             | ""                                         |             |
| PostdatedCheckStopPayment                     | "No"                                       |             |
| ChineseVoucher                                | ""                                         |             |
| PostdatedCheckBankName                        | ""                                         |             |
| InstructionKey4                               | "NotUsed"                                  |             |
| CentralBankPurposeText                        | ""                                         |             |

### Postman

#### Request for get data

`GET: https://{{base_url}}/data/VendorPaymentJournalLines(dataAreaId='usmf',JournalBatchNumber='00282',LineNumber=1)`

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
Authorization:Bearer {{token}}
Host:{{base_url}}
```

</details>

<details>
<summary>
Response:
</summary>

```json
{
    "@odata.context": "https://{{base_url}}/data/$metadata#VendorPaymentJournalLines/$entity",
    "@odata.etag": "W/\"JzAsNTYzNzE3MTUyODswLDA7MCwwOzAsMDswLDA7MCwwJw==\"",
    "dataAreaId": "usmf",
    "JournalBatchNumber": "00282",
    "LineNumber": 1,
    "InstructionKey1": "NotUsed",
    "InstructionKey2": "NotUsed",
    "UseSalesTaxDirectionFromMainAccount": "No",
    "InstructionKey3": "NotUsed",
    "MarkedInvoice": "",
    "Voucher": "APPM000001",
    "ServiceLevel": 0,
    "OffsetAccountType": "Bank",
    "FeeAccount": "",
    "PostdatedCheckCashierDisplayValue": "",
    "ErrorCodePayment": "",
    "PostdatedCheckMaturityDate": "1900-01-01T12:00:00Z",
    "CheckNumber": "2",
    "LocalInstrument": 0,
    "NewJournalBatchNumber": "",
    "SettleVoucher": "SelectedTransact",
    "RemittanceAddressDistrictName": "",
    "RemittanceAddressCountryISOCode": "US",
    "RemittanceAddressCounty": "",
    "TransactionDate": "2015-02-03T12:00:00Z",
    "NACHAIATOFACScreeningIndicator": "Zero",
    "RemittanceAddressLongitude": 0,
    "BankTransactionType": "03",
    "PaymentReference": "2",
    "ChineseVoucherType": "",
    "PostdatedCheckSalespersonDisplayValue": "",
    "NACHAIATForeignExchangeIndicator": "None",
    "NACHAIATForeignExchangeReferenceIndicator": "One",
    "RemittanceAddressZipCode": "94588",
    "DebitAmount": 6800,
    "RemittanceAddressStreet": "4 Main Street",
    "TaxItemGroup": "",
    "NACHAIATOFACSecondaryScreeningIndicator": "Zero",
    "ThirdPartyBankAccountId": "",
    "TransactionText": "",
    "FullPrimaryRemittanceAddress": "4 Main Street\nPleasanton, CA, 94588 \nUSA",
    "RemittanceAddressValidTo": "2154-12-31T23:59:59Z",
    "PostdatedCheckNumber": "",
    "OffsetAccountDisplayValue": "USMF OPER",
    "AccountDisplayValue": "US\\-108",
    "ChargeBearer": 0,
    "DefaultDimensionsForAccountDisplayValue": "001--",
    "PostdatedCheckOriginalCheckNumber": "",
    "PaymentMethodName": "CHECK",
    "RemittanceAddressCity": "Pleasanton, CA",
    "RemittanceAddressLatitude": 0,
    "CentralBankImportDate": "1900-01-01T12:00:00Z",
    "NACHAIATReceivingDFIQualifier": "One",
    "OffsetTransactionText": "",
    "MarkedInvoiceCompany": "",
    "PaymentSpecification": "",
    "PostdatedCheckIsReplacementCheck": "No",
    "NACHAIATOriginatingDFIQualifier": "One",
    "AccountType": "Vend",
    "TaxGroup": "",
    "ContactPerson": "",
    "RemittanceAddressState": "",
    "RemittanceAddressDescription": "Reception",
    "ExchangeRate": 100,
    "ReportingCurrencyExchRate": 0,
    "RemittanceAddressValidFrom": "2012-05-09T17:27:02Z",
    "RemittanceAddressCountry": "USA",
    "PaymentId": "",
    "RemittanceAddressTimeZone": null,
    "RemittanceLocationId": "000000013",
    "PostingProfile": "GEN",
    "CalculateWithholdingTax": "No",
    "PostdatedCheckReasonForStop": "",
    "VendorName": "City Power & Light",
    "CategoryPurpose": 0,
    "CreditAmount": 0,
    "RestrictedForwarding": "No",
    "OffsetCompany": "usmf",
    "IsPrepayment": "No",
    "NACHAIATForeignExchangeReference": "",
    "ItemWithholdingTaxGroupCode": "",
    "DefaultDimensionsForOffsetAccountDisplayValue": "001--",
    "ReportingCurrencyExchRateSecondary": 0,
    "CurrencyCode": "USD",
    "Company": "usmf",
    "SecondaryExchangeRate": 0,
    "PostdatedCheckReceivedDate": "1900-01-01T12:00:00Z",
    "PostdatedCheckBankBranch": "",
    "CentralBankPurposeCode": "",
    "PostdatedCheckReplacementComments": "",
    "PostdatedCheckStopPayment": "No",
    "ChineseVoucher": "",
    "PostdatedCheckBankName": "",
    "InstructionKey4": "NotUsed",
    "CentralBankPurposeText": ""
}
```

</details>

#### Request for create data

`POST: https://{{base_url}}/data/VendorPaymentJournalLines`

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
Authorization:Bearer {{token}}
Host:{{base_url}}
```

</details>

<details>
    <summary>
    body:
    </summary>

```json
{
    "@odata.type":"#Microsoft.Dynamics.DataEntities.VendorPaymentJournalLine",
    "CurrencyCode": "USD",
    "LineNumber": 1,
    "JournalBatchNumber": "00630"
}
```

</details>

<details>
<summary>
Response:

</summary>

```json
{
    "@odata.context": "https://{{base_url}}/data/$metadata#VendorPaymentJournalLines/$entity",
    "@odata.etag": "W/\"JzEsNjg3MTk1ODM3OTI7MCwwOzAsMDswLDA7MCwwOzAsMCc=\"",
    "dataAreaId": "usmf",
    "JournalBatchNumber": "00630",
    "LineNumber": 1,
    "InstructionKey1": "NotUsed",
    "InstructionKey2": "NotUsed",
    "UseSalesTaxDirectionFromMainAccount": "No",
    "InstructionKey3": "NotUsed",
    "MarkedInvoice": "",
    "Voucher": "APPM001210",
    "ServiceLevel": 0,
    "OffsetAccountType": "Ledger",
    "FeeAccount": "",
    "PostdatedCheckCashierDisplayValue": "",
    "ErrorCodePayment": "",
    "PostdatedCheckMaturityDate": "1900-01-01T12:00:00Z",
    "CheckNumber": "",
    "LocalInstrument": 0,
    "NewJournalBatchNumber": "",
    "SettleVoucher": "None",
    "RemittanceAddressDistrictName": "",
    "RemittanceAddressCountryISOCode": "",
    "RemittanceAddressCounty": "",
    "TransactionDate": "2021-01-15T12:00:00Z",
    "NACHAIATOFACScreeningIndicator": "Zero",
    "RemittanceAddressLongitude": 0,
    "BankTransactionType": "",
    "PaymentReference": "",
    "ChineseVoucherType": "",
    "PostdatedCheckSalespersonDisplayValue": "",
    "NACHAIATForeignExchangeIndicator": "None",
    "NACHAIATForeignExchangeReferenceIndicator": "One",
    "RemittanceAddressZipCode": "",
    "DebitAmount": 0,
    "RemittanceAddressStreet": "",
    "TaxItemGroup": "",
    "NACHAIATOFACSecondaryScreeningIndicator": "Zero",
    "ThirdPartyBankAccountId": "",
    "TransactionText": "",
    "FullPrimaryRemittanceAddress": "",
    "RemittanceAddressValidTo": "1900-01-01T00:00:00Z",
    "PostdatedCheckNumber": "",
    "OffsetAccountDisplayValue": "",
    "AccountDisplayValue": "",
    "ChargeBearer": 0,
    "DefaultDimensionsForAccountDisplayValue": "",
    "PostdatedCheckOriginalCheckNumber": "",
    "PaymentMethodName": "",
    "RemittanceAddressCity": "",
    "RemittanceAddressLatitude": 0,
    "CentralBankImportDate": "1900-01-01T12:00:00Z",
    "NACHAIATReceivingDFIQualifier": "One",
    "OffsetTransactionText": "",
    "MarkedInvoiceCompany": "",
    "PaymentSpecification": "",
    "PostdatedCheckIsReplacementCheck": "No",
    "NACHAIATOriginatingDFIQualifier": "One",
    "AccountType": "Vend",
    "TaxGroup": "",
    "ContactPerson": "",
    "RemittanceAddressState": "",
    "RemittanceAddressDescription": "",
    "ExchangeRate": 100,
    "ReportingCurrencyExchRate": 100,
    "RemittanceAddressValidFrom": "1900-01-01T00:00:00Z",
    "RemittanceAddressCountry": "",
    "PaymentId": "",
    "RemittanceAddressTimeZone": null,
    "RemittanceLocationId": "",
    "PostingProfile": "",
    "CalculateWithholdingTax": "No",
    "PostdatedCheckReasonForStop": "",
    "VendorName": "",
    "CategoryPurpose": 0,
    "CreditAmount": 0,
    "RestrictedForwarding": "No",
    "OffsetCompany": "USMF",
    "IsPrepayment": "No",
    "NACHAIATForeignExchangeReference": "",
    "ItemWithholdingTaxGroupCode": "",
    "DefaultDimensionsForOffsetAccountDisplayValue": "",
    "ReportingCurrencyExchRateSecondary": 0,
    "CurrencyCode": "USD",
    "Company": "USMF",
    "SecondaryExchangeRate": 0,
    "PostdatedCheckReceivedDate": "1900-01-01T12:00:00Z",
    "PostdatedCheckBankBranch": "",
    "CentralBankPurposeCode": "",
    "PostdatedCheckReplacementComments": "",
    "PostdatedCheckStopPayment": "No",
    "ChineseVoucher": "",
    "PostdatedCheckBankName": "",
    "InstructionKey4": "NotUsed",
    "CentralBankPurposeText": ""
}
```

</details>

#### Request for update data

`PATCH : https://{{base_url}}/data/VendorPaymentJournalLines(dataAreaId='usmf',JournalBatchNumber='00630',LineNumber=1)`

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
Authorization:Bearer {{token}}
Host:{{base_url}}
```

</details>

<details>
    <summary>
    body:
    </summary>

```json
{
    "@odata.type":"#Microsoft.Dynamics.DataEntities.VendorPaymentJournalLine",
    "OffsetAccountType": "Bank",
    "DebitAmount": 6800,
    "AccountDisplayValue": "US\\-108"
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

`DELETE : https://{{base_url}}/data/VendorPaymentJournalLines(dataAreaId='usmf',JournalBatchNumber='00630',LineNumber=1)`

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
Authorization:Bearer {{token}}
Host:{{base_url}}
```

</details>

<details>
<summary>
Response:
</summary>
Status: 204
</details>

## Create Document Vendor Payment Journal

Need to allowed `General ledger\Journal batch number` number sequence be changed by user

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

POST https://{{base_url}}/data/VendorPaymentJournalHeaders HTTP/1.1
OData-Version: 4.0
OData-MaxVersion: 4.0
Content-Type: application/json;odata.metadata=minimal
Accept: application/json;odata.metadata=minimal
Accept-Charset: UTF-8

{
    "@odata.type":"#Microsoft.Dynamics.DataEntities.VendorPaymentJournalHeader",
    "JournalName": "VendPay",
    "JournalBatchNumber": "A0001"
}

--changeset_boundary
Content-Type: application/http
Content-Transfer-Encoding: binary
Content-ID: 2

POST https://{{base_url}}/data/VendorPaymentJournalLines HTTP/1.1
OData-Version: 4.0
OData-MaxVersion: 4.0
Content-Type: application/json;odata.metadata=minimal
Accept: application/json;odata.metadata=minimal
Accept-Charset: UTF-8

{
    "@odata.type":"#Microsoft.Dynamics.DataEntities.VendorPaymentJournalLine",
    "JournalBatchNumber": "A0001",
    "LineNumber": 1,
    "OffsetAccountType": "Bank",
    "TransactionDate": "2021-01-11T12:00:00Z",
    "BankTransactionType": "03",
    "DebitAmount": 150,
    "OffsetAccountDisplayValue": "USMF OPER",
    "AccountDisplayValue": "1001",
    "DefaultDimensionsForAccountDisplayValue": "001--",
    "PaymentMethodName": "CHECK",
    "RemittanceAddressCity": "Houston",
    "NACHAIATReceivingDFIQualifier": "One",
    "NACHAIATOriginatingDFIQualifier": "One",
    "AccountType": "Vend",
    "ExchangeRate": 100,
    "OffsetCompany": "usmf",
    "DefaultDimensionsForOffsetAccountDisplayValue": "001--",
    "CurrencyCode": "USD"
}

--changeset_boundary
Content-Type: application/http
Content-Transfer-Encoding: binary
Content-ID: 3

POST https://{{base_url}}/data/VendorPaymentJournalLines HTTP/1.1
OData-Version: 4.0
OData-MaxVersion: 4.0
Content-Type: application/json;odata.metadata=minimal
Accept: application/json;odata.metadata=minimal
Accept-Charset: UTF-8

{
    "@odata.type":"#Microsoft.Dynamics.DataEntities.VendorPaymentJournalLine",
    "JournalBatchNumber": "A0001",
    "LineNumber": 2,
    "OffsetAccountType": "Bank",
    "TransactionDate": "2021-01-11T12:00:00Z",
    "BankTransactionType": "03",
    "DebitAmount": 250,
    "OffsetAccountDisplayValue": "USMF OPER",
    "AccountDisplayValue": "1001",
    "DefaultDimensionsForAccountDisplayValue": "001--",
    "PaymentMethodName": "CHECK",
    "RemittanceAddressCity": "Houston",
    "NACHAIATReceivingDFIQualifier": "One",
    "NACHAIATOriginatingDFIQualifier": "One",
    "AccountType": "Vend",
    "ExchangeRate": 100,
    "OffsetCompany": "usmf",
    "DefaultDimensionsForOffsetAccountDisplayValue": "001--",
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
--batchresponse_bb3ca9af-d6f3-4ac0-ae82-a7d771b3ff62
Content-Type: multipart/mixed; boundary=changesetresponse_5ebc7bfd-667e-4a34-934f-89bd3cb25feb

--changesetresponse_5ebc7bfd-667e-4a34-934f-89bd3cb25feb
Content-Type: application/http
Content-Transfer-Encoding: binary
Content-ID: 1

HTTP/1.1 201 Created
ETag: W/"JzEsNjg3MTk1MTE1MjA7MCwwJw=="
Location: https://{{base_url}}/data/VendorPaymentJournalHeaders(dataAreaId='usmf',JournalBatchNumber='A0001')
Content-Type: application/json; odata.metadata=minimal
OData-Version: 4.0

{
    "@odata.context": "https://{{base_url}}/data/$metadata#VendorPaymentJournalHeaders/$entity",
    "@odata.etag": "W/\"JzEsNjg3MTk1MTE1MjA7MCwwJw==\"",
    "dataAreaId": "usmf",
    "JournalBatchNumber": "A0001",
    "JournalName": "VendPay",
    "ChargeBearer": 0,
    "Description": "Vendor Payment",
    "CategoryPurpose": 0,
    "IsPosted": "No",
    "LocalInstrument": 0,
    "ServiceLevel": 0
}
--changesetresponse_5ebc7bfd-667e-4a34-934f-89bd3cb25feb
Content-Type: application/http
Content-Transfer-Encoding: binary
Content-ID: 2

HTTP/1.1 201 Created
ETag: W/"JzEsNjg3MTk1ODM3OTY7MCwwOzAsMDswLDA7MCwwOzAsMCc="
Location: https://{{base_url}}/data/VendorPaymentJournalLines(dataAreaId='usmf',JournalBatchNumber='A0001',LineNumber=1)
Content-Type: application/json; odata.metadata=minimal
OData-Version: 4.0

{
    "@odata.context": "https://{{base_url}}/data/$metadata#VendorPaymentJournalLines/$entity",
    "@odata.etag": "W/\"JzEsNjg3MTk1ODM3OTY7MCwwOzAsMDswLDA7MCwwOzAsMCc=\"",
    "dataAreaId": "usmf",
    "JournalBatchNumber": "A0001",
    "LineNumber": 1,
    "InstructionKey1": "NotUsed",
    "InstructionKey2": "NotUsed",
    "UseSalesTaxDirectionFromMainAccount": "No",
    "InstructionKey3": "NotUsed",
    "MarkedInvoice": "",
    "Voucher": "APPM001214",
    "ServiceLevel": 0,
    "OffsetAccountType": "Bank",
    "FeeAccount": "",
    "PostdatedCheckCashierDisplayValue": "",
    "ErrorCodePayment": "",
    "PostdatedCheckMaturityDate": "1900-01-01T12:00:00Z",
    "CheckNumber": "",
    "LocalInstrument": 0,
    "NewJournalBatchNumber": "",
    "SettleVoucher": "None",
    "RemittanceAddressDistrictName": "",
    "RemittanceAddressCountryISOCode": "",
    "RemittanceAddressCounty": "",
    "TransactionDate": "2021-01-11T12:00:00Z",
    "NACHAIATOFACScreeningIndicator": "Zero",
    "RemittanceAddressLongitude": 0,
    "BankTransactionType": "03",
    "PaymentReference": "",
    "ChineseVoucherType": "",
    "PostdatedCheckSalespersonDisplayValue": "",
    "NACHAIATForeignExchangeIndicator": "None",
    "NACHAIATForeignExchangeReferenceIndicator": "One",
    "RemittanceAddressZipCode": "",
    "DebitAmount": 150,
    "RemittanceAddressStreet": "",
    "TaxItemGroup": "",
    "NACHAIATOFACSecondaryScreeningIndicator": "Zero",
    "ThirdPartyBankAccountId": "",
    "TransactionText": "",
    "FullPrimaryRemittanceAddress": "",
    "RemittanceAddressValidTo": "1900-01-01T00:00:00Z",
    "PostdatedCheckNumber": "",
    "OffsetAccountDisplayValue": "USMF OPER",
    "AccountDisplayValue": "1001",
    "ChargeBearer": 0,
    "DefaultDimensionsForAccountDisplayValue": "001--",
    "PostdatedCheckOriginalCheckNumber": "",
    "PaymentMethodName": "CHECK",
    "RemittanceAddressCity": "Houston",
    "RemittanceAddressLatitude": 0,
    "CentralBankImportDate": "1900-01-01T12:00:00Z",
    "NACHAIATReceivingDFIQualifier": "One",
    "OffsetTransactionText": "",
    "MarkedInvoiceCompany": "",
    "PaymentSpecification": "",
    "PostdatedCheckIsReplacementCheck": "No",
    "NACHAIATOriginatingDFIQualifier": "One",
    "AccountType": "Vend",
    "TaxGroup": "",
    "ContactPerson": "",
    "RemittanceAddressState": "",
    "RemittanceAddressDescription": "",
    "ExchangeRate": 100,
    "ReportingCurrencyExchRate": 100,
    "RemittanceAddressValidFrom": "1900-01-01T00:00:00Z",
    "RemittanceAddressCountry": "",
    "PaymentId": "",
    "RemittanceAddressTimeZone": null,
    "RemittanceLocationId": "",
    "PostingProfile": "",
    "CalculateWithholdingTax": "No",
    "PostdatedCheckReasonForStop": "",
    "VendorName": "Acme Office Supplies",
    "CategoryPurpose": 0,
    "CreditAmount": 0,
    "RestrictedForwarding": "No",
    "OffsetCompany": "USMF",
    "IsPrepayment": "No",
    "NACHAIATForeignExchangeReference": "",
    "ItemWithholdingTaxGroupCode": "",
    "DefaultDimensionsForOffsetAccountDisplayValue": "001--",
    "ReportingCurrencyExchRateSecondary": 0,
    "CurrencyCode": "USD",
    "Company": "USMF",
    "SecondaryExchangeRate": 0,
    "PostdatedCheckReceivedDate": "1900-01-01T12:00:00Z",
    "PostdatedCheckBankBranch": "",
    "CentralBankPurposeCode": "",
    "PostdatedCheckReplacementComments": "",
    "PostdatedCheckStopPayment": "No",
    "ChineseVoucher": "",
    "PostdatedCheckBankName": "",
    "InstructionKey4": "NotUsed",
    "CentralBankPurposeText": ""
}
--changesetresponse_5ebc7bfd-667e-4a34-934f-89bd3cb25feb
Content-Type: application/http
Content-Transfer-Encoding: binary
Content-ID: 3

HTTP/1.1 201 Created
ETag: W/"JzEsNjg3MTk1ODM3OTc7MCwwOzAsMDswLDA7MCwwOzAsMCc="
Location: https://{{base_url}}/data/VendorPaymentJournalLines(dataAreaId='usmf',JournalBatchNumber='A0001',LineNumber=2)
Content-Type: application/json; odata.metadata=minimal
OData-Version: 4.0

{
    "@odata.context": "https://{{base_url}}/data/$metadata#VendorPaymentJournalLines/$entity",
    "@odata.etag": "W/\"JzEsNjg3MTk1ODM3OTc7MCwwOzAsMDswLDA7MCwwOzAsMCc=\"",
    "dataAreaId": "usmf",
    "JournalBatchNumber": "A0001",
    "LineNumber": 2,
    "InstructionKey1": "NotUsed",
    "InstructionKey2": "NotUsed",
    "UseSalesTaxDirectionFromMainAccount": "No",
    "InstructionKey3": "NotUsed",
    "MarkedInvoice": "",
    "Voucher": "APPM001215",
    "ServiceLevel": 0,
    "OffsetAccountType": "Bank",
    "FeeAccount": "",
    "PostdatedCheckCashierDisplayValue": "",
    "ErrorCodePayment": "",
    "PostdatedCheckMaturityDate": "1900-01-01T12:00:00Z",
    "CheckNumber": "",
    "LocalInstrument": 0,
    "NewJournalBatchNumber": "",
    "SettleVoucher": "None",
    "RemittanceAddressDistrictName": "",
    "RemittanceAddressCountryISOCode": "",
    "RemittanceAddressCounty": "",
    "TransactionDate": "2021-01-11T12:00:00Z",
    "NACHAIATOFACScreeningIndicator": "Zero",
    "RemittanceAddressLongitude": 0,
    "BankTransactionType": "03",
    "PaymentReference": "",
    "ChineseVoucherType": "",
    "PostdatedCheckSalespersonDisplayValue": "",
    "NACHAIATForeignExchangeIndicator": "None",
    "NACHAIATForeignExchangeReferenceIndicator": "One",
    "RemittanceAddressZipCode": "",
    "DebitAmount": 250,
    "RemittanceAddressStreet": "",
    "TaxItemGroup": "",
    "NACHAIATOFACSecondaryScreeningIndicator": "Zero",
    "ThirdPartyBankAccountId": "",
    "TransactionText": "",
    "FullPrimaryRemittanceAddress": "",
    "RemittanceAddressValidTo": "1900-01-01T00:00:00Z",
    "PostdatedCheckNumber": "",
    "OffsetAccountDisplayValue": "USMF OPER",
    "AccountDisplayValue": "1001",
    "ChargeBearer": 0,
    "DefaultDimensionsForAccountDisplayValue": "001--",
    "PostdatedCheckOriginalCheckNumber": "",
    "PaymentMethodName": "CHECK",
    "RemittanceAddressCity": "Houston",
    "RemittanceAddressLatitude": 0,
    "CentralBankImportDate": "1900-01-01T12:00:00Z",
    "NACHAIATReceivingDFIQualifier": "One",
    "OffsetTransactionText": "",
    "MarkedInvoiceCompany": "",
    "PaymentSpecification": "",
    "PostdatedCheckIsReplacementCheck": "No",
    "NACHAIATOriginatingDFIQualifier": "One",
    "AccountType": "Vend",
    "TaxGroup": "",
    "ContactPerson": "",
    "RemittanceAddressState": "",
    "RemittanceAddressDescription": "",
    "ExchangeRate": 100,
    "ReportingCurrencyExchRate": 100,
    "RemittanceAddressValidFrom": "1900-01-01T00:00:00Z",
    "RemittanceAddressCountry": "",
    "PaymentId": "",
    "RemittanceAddressTimeZone": null,
    "RemittanceLocationId": "",
    "PostingProfile": "",
    "CalculateWithholdingTax": "No",
    "PostdatedCheckReasonForStop": "",
    "VendorName": "Acme Office Supplies",
    "CategoryPurpose": 0,
    "CreditAmount": 0,
    "RestrictedForwarding": "No",
    "OffsetCompany": "USMF",
    "IsPrepayment": "No",
    "NACHAIATForeignExchangeReference": "",
    "ItemWithholdingTaxGroupCode": "",
    "DefaultDimensionsForOffsetAccountDisplayValue": "001--",
    "ReportingCurrencyExchRateSecondary": 0,
    "CurrencyCode": "USD",
    "Company": "USMF",
    "SecondaryExchangeRate": 0,
    "PostdatedCheckReceivedDate": "1900-01-01T12:00:00Z",
    "PostdatedCheckBankBranch": "",
    "CentralBankPurposeCode": "",
    "PostdatedCheckReplacementComments": "",
    "PostdatedCheckStopPayment": "No",
    "ChineseVoucher": "",
    "PostdatedCheckBankName": "",
    "InstructionKey4": "NotUsed",
    "CentralBankPurposeText": ""
}
--changesetresponse_5ebc7bfd-667e-4a34-934f-89bd3cb25feb--
--batchresponse_bb3ca9af-d6f3-4ac0-ae82-a7d771b3ff62--

```

</details>
