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
    "@odata.context": "https://{{base_url}}/data/$metadata#VendInvoiceJournalHeaders/$entity",
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
    "@odata.context": "https://{{base_url}}/data/$metadata#VendInvoiceJournalHeaders/$entity",
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

| Data entity AOT name         | Entity name (DMF)           | Public collection name (OData) | Support OData | Support DMF | Category | ReadOnly |
| ---------------------------- | --------------------------- | ------------------------------ | ------------- | ----------- | -------- | -------- |
| VendInvoiceJournalLineEntity | Vendor invoice journal line | VendInvoiceJournalLines        | Yes           | Yes         | Document | No       |

To works with `` we want to use `` entity

### Key

- dataAreaId
- JournalBatchNumber
- LineNumber

### Fields

| Field name                      | Value example                            | Description |
| ------------------------------- | ---------------------------------------- | ----------- |
| dataAreaId                      | "usmf"                                   |             |
| (*)**JournalBatchNumber**       | "00461"                                  |             |
| (*)**LineNumber**               | 1                                        |             |
| ItemSalesTaxGroup               | "AU/VI"                                  |             |
| CashDiscountDate                | "2016-11-01T12:00:00Z"                   |             |
| Voucher                         | "APIN000001"                             |             |
| TermsOfPayment                  | "Net30"                                  |             |
| Credit                          | 1200                                     |             |
| OffsetAccountType               | "Ledger"                                 |             |
| BookId                          | ""                                       |             |
| Listcode                        | "IncludeNot"                             |             |
| MethodOfPayment                 | "CHECK"                                  |             |
| RemittanceAddressDistrictName   | ""                                       |             |
| RemittanceAddressCountryISOCode | "MX"                                     |             |
| RemittanceAddressCounty         | ""                                       |             |
| GSTHSTTaxType                   | "None"                                   |             |
| RemittanceAddressLongitude      | 0                                        |             |
| DefaultDimensionDisplayValue    | "001--"                                  |             |
| Document                        | ""                                       |             |
| CashDiscountAmount              | -24                                      |             |
| TransactionType                 | "Vend"                                   |             |
| ApproverNumber                  | "000007"                                 |             |
| ExchRate                        | 100                                      |             |
| ChineseVoucherType              | ""                                       |             |
| UUID                            | ""                                       |             |
| RemittanceAddressZipCode        | "44190"                                  |             |
| AssetTransType                  | "None"                                   |             |
| RemittanceAddressStreet         | "Cindy Road"                             |             |
| InvoiceDate                     | "1900-01-01T12:00:00Z"                   |             |
| FullPrimaryRemittanceAddress    | "Cindy Road456\nGuadaljara JAL 44190MEX" |             |
| RemittanceAddressValidTo        | "2154-12-31T23:59:59Z"                   |             |
| PaymId                          | ""                                       |             |
| AccountDisplayValue             | "US\\-101"                               |             |
| OffsetAccountDisplayValue       | "600150-001-007-022"                     |             |
| CashDiscount                    | "2%D10"                                  |             |
| AssetId                         | ""                                       |             |
| RemittanceAddressCity           | "Guadaljara"                             |             |
| Debit                           | 0                                        |             |
| RemittanceAddressLatitude       | 0                                        |             |
| Description                     | "Taxable Expense"                        |             |
| OffsetTransactionText           | ""                                       |             |
| PaymentSpecification            | ""                                       |             |
| SalesTaxGroup                   | "No-Tax"                                 |             |
| RemittanceAddressLocationId     | "000001246"                              |             |
| AccountType                     | "Vend"                                   |             |
| Invoice                         | "48399"                                  |             |
| Tax1099Fields                   | 5637144672                               |             |
| DueDate                         | 2016-11-21T12:00:00Z                     |             |
| RemittanceAddressState          | "JAL"                                    |             |
| ReportingCurrencyExchRate       | 0                                        |             |
| RemittanceAddressDescription    | "Fabrikam Electronics"                   |             |
| RemittanceAddressValidFrom      | "2009-01-04T10:18:40Z"                   |             |
| RemittanceAddressCountry        | "MEX"                                    |             |
| RemittanceAddressTimeZone       | null                                     |             |
| InvoiceDeclarationId            | ""                                       |             |
| PostingProfile                  | "GEN"                                    |             |
| IsWithholdingTaxCalculate       | "No"                                     |             |
| ExchRateSecond                  | 0                                        |             |
| CustVendBankAccountId           | ""                                       |             |
| BankAccountId                   | ""                                       |             |
| OffsetCompany                   | "usmf"                                   |             |
| ItemWithholdingTaxGroupCode     | ""                                       |             |
| TaxExemptNumber                 | ""                                       |             |
| (*)**Currency**                 | "USD"                                    |             |
| Company                         | "usmf"                                   |             |
| TypeOfOperation                 | "Blank"                                  |             |
| DeliveryDate                    | "1900-01-01T12:00:00Z"                   |             |
| Approved                        | "Yes"                                    |             |
| ChineseVoucher                  | ""                                       |             |
| Date                            | "2016-10-22T12:00:00Z"                   |             |

### Postman

#### Request for get data

`GET: https://{{base_url}}/data/VendInvoiceJournalLines(dataAreaId='usmf',JournalBatchNumber='00461',LineNumber=1)`

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
    "@odata.context": "https://{{base_url}}/data/$metadata#VendInvoiceJournalLines/$entity",
    "@odata.etag": "W/\"JzAsNTYzNzMwMDYwMDswLDA7MCwwJw==\"",
    "dataAreaId": "usmf",
    "JournalBatchNumber": "00461",
    "LineNumber": 1,
    "ItemSalesTaxGroup": "AU/VI",
    "CashDiscountDate": "2016-11-01T12:00:00Z",
    "Voucher": "APIN000001",
    "TermsOfPayment": "Net30",
    "Credit": 1200,
    "OffsetAccountType": "Ledger",
    "BookId": "",
    "Listcode": "IncludeNot",
    "MethodOfPayment": "CHECK",
    "RemittanceAddressDistrictName": "",
    "RemittanceAddressCountryISOCode": "MX",
    "RemittanceAddressCounty": "",
    "GSTHSTTaxType": "None",
    "RemittanceAddressLongitude": 0,
    "DefaultDimensionDisplayValue": "001--",
    "Document": "",
    "CashDiscountAmount": -24,
    "TransactionType": "Vend",
    "ApproverNumber": "000007",
    "ExchRate": 100,
    "ChineseVoucherType": "",
    "UUID": "",
    "RemittanceAddressZipCode": "44190",
    "AssetTransType": "None",
    "RemittanceAddressStreet": "Cindy Road",
    "InvoiceDate": "1900-01-01T12:00:00Z",
    "FullPrimaryRemittanceAddress": "Cindy Road456\nGuadaljara, JAL, 44190MEX",
    "RemittanceAddressValidTo": "2154-12-31T23:59:59Z",
    "PaymId": "",
    "AccountDisplayValue": "US\\-101",
    "OffsetAccountDisplayValue": "600150-001-007-022",
    "CashDiscount": "2%D10",
    "AssetId": "",
    "RemittanceAddressCity": "Guadaljara",
    "Debit": 0,
    "RemittanceAddressLatitude": 0,
    "Description": "Taxable Expense",
    "OffsetTransactionText": "",
    "PaymentSpecification": "",
    "SalesTaxGroup": "No-Tax",
    "RemittanceAddressLocationId": "000001246",
    "AccountType": "Vend",
    "Invoice": "48399",
    "Tax1099Fields": 5637144672,
    "DueDate": "2016-11-21T12:00:00Z",
    "RemittanceAddressState": "JAL",
    "ReportingCurrencyExchRate": 0,
    "RemittanceAddressDescription": "Fabrikam Electronics",
    "RemittanceAddressValidFrom": "2009-01-04T10:18:40Z",
    "RemittanceAddressCountry": "MEX",
    "RemittanceAddressTimeZone": null,
    "InvoiceDeclarationId": "",
    "PostingProfile": "GEN",
    "IsWithholdingTaxCalculate": "No",
    "ExchRateSecond": 0,
    "CustVendBankAccountId": "",
    "BankAccountId": "",
    "OffsetCompany": "usmf",
    "ItemWithholdingTaxGroupCode": "",
    "TaxExemptNumber": "",
    "Currency": "USD",
    "Company": "usmf",
    "TypeOfOperation": "Blank",
    "DeliveryDate": "1900-01-01T12:00:00Z",
    "Approved": "Yes",
    "ChineseVoucher": "",
    "Date": "2016-10-22T12:00:00Z"
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
    "@odata.context": "https://{{base_url}}/data/$metadata#VendInvoiceJournalLines/$entity",
    "@odata.etag": "W/\"JzEsNjg3MTk1OTcyOTI7MCwwOzAsMCc=\"",
    "dataAreaId": "usmf",
    "JournalBatchNumber": "00631",
    "LineNumber": 1,
    "ItemSalesTaxGroup": "",
    "CashDiscountDate": "1900-01-01T12:00:00Z",
    "Voucher": "APIN000052",
    "TermsOfPayment": "",
    "Credit": 0,
    "OffsetAccountType": "Ledger",
    "BookId": "",
    "Listcode": "IncludeNot",
    "MethodOfPayment": "",
    "RemittanceAddressDistrictName": "",
    "RemittanceAddressCountryISOCode": "",
    "RemittanceAddressCounty": "",
    "GSTHSTTaxType": "None",
    "RemittanceAddressLongitude": 0,
    "DefaultDimensionDisplayValue": "",
    "Document": "",
    "CashDiscountAmount": 0,
    "TransactionType": "Vend",
    "ApproverNumber": "",
    "ExchRate": 100,
    "ChineseVoucherType": "",
    "UUID": "",
    "RemittanceAddressZipCode": "",
    "AssetTransType": "None",
    "RemittanceAddressStreet": "",
    "InvoiceDate": "1900-01-01T12:00:00Z",
    "FullPrimaryRemittanceAddress": "",
    "RemittanceAddressValidTo": "1900-01-01T00:00:00Z",
    "PaymId": "",
    "AccountDisplayValue": "",
    "OffsetAccountDisplayValue": "",
    "CashDiscount": "",
    "AssetId": "",
    "RemittanceAddressCity": "",
    "Debit": 0,
    "RemittanceAddressLatitude": 0,
    "Description": "",
    "OffsetTransactionText": "",
    "PaymentSpecification": "",
    "SalesTaxGroup": "",
    "RemittanceAddressLocationId": "",
    "AccountType": "Ledger",
    "Invoice": "",
    "Tax1099Fields": 0,
    "DueDate": "2021-04-04T12:00:00Z",
    "RemittanceAddressState": "",
    "ReportingCurrencyExchRate": 100,
    "RemittanceAddressDescription": "",
    "RemittanceAddressValidFrom": "1900-01-01T00:00:00Z",
    "RemittanceAddressCountry": "",
    "RemittanceAddressTimeZone": null,
    "InvoiceDeclarationId": "",
    "PostingProfile": "",
    "IsWithholdingTaxCalculate": "No",
    "ExchRateSecond": 0,
    "CustVendBankAccountId": "",
    "BankAccountId": "",
    "OffsetCompany": "USMF",
    "ItemWithholdingTaxGroupCode": "",
    "TaxExemptNumber": "",
    "Currency": "USD",
    "Company": "USMF",
    "TypeOfOperation": "Blank",
    "DeliveryDate": "1900-01-01T12:00:00Z",
    "Approved": "Yes",
    "ChineseVoucher": "",
    "Date": "2021-04-04T12:00:00Z"
}
```

</details>

#### Request for update data

`PATCH : https://{{base_url}}/data/VendorPaymentJournalLines(dataAreaId='usmf',JournalBatchNumber='00631',LineNumber=1)`

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
    "@odata.type":"#Microsoft.Dynamics.DataEntities.VendInvoiceJournalLine",
    "DefaultDimensionDisplayValue": "001--",
    "Debit": 6800
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

`DELETE : https://{{base_url}}/data/VendorPaymentJournalLines(dataAreaId='usmf',JournalBatchNumber='00631',LineNumber=1)`

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

POST https://{{base_url}}/data/VendInvoiceJournalHeaders HTTP/1.1
OData-Version: 4.0
OData-MaxVersion: 4.0
Content-Type: application/json;odata.metadata=minimal
Accept: application/json;odata.metadata=minimal
Accept-Charset: UTF-8

{
    "@odata.type":"#Microsoft.Dynamics.DataEntities.VendInvoiceJournalHeader",
    "JournalName": "APInvoice",
    "JournalBatchNumber": "B0002"
}

--changeset_boundary
Content-Type: application/http
Content-Transfer-Encoding: binary
Content-ID: 2

POST https://{{base_url}}/data/VendInvoiceJournalLines HTTP/1.1
OData-Version: 4.0
OData-MaxVersion: 4.0
Content-Type: application/json;odata.metadata=minimal
Accept: application/json;odata.metadata=minimal
Accept-Charset: UTF-8

{
    "@odata.type":"#Microsoft.Dynamics.DataEntities.VendInvoiceJournalLine",
    "JournalBatchNumber": "B0002",
    "LineNumber": 1,
    "OffsetAccountType": "Bank",
    "Date": "2021-01-11T12:00:00Z",
    "Debit": 150,
    "OffsetAccountDisplayValue": "USMF OPER",
    "AccountDisplayValue": "1001",
    "RemittanceAddressCity": "Houston",
    "AccountType": "Vend",
    "OffsetCompany": "usmf",
    "Currency": "USD"
}

--changeset_boundary
Content-Type: application/http
Content-Transfer-Encoding: binary
Content-ID: 3

POST https://{{base_url}}/data/VendInvoiceJournalLines HTTP/1.1
OData-Version: 4.0
OData-MaxVersion: 4.0
Content-Type: application/json;odata.metadata=minimal
Accept: application/json;odata.metadata=minimal
Accept-Charset: UTF-8

{
    "@odata.type":"#Microsoft.Dynamics.DataEntities.VendInvoiceJournalLine",
    "JournalBatchNumber": "B0002",
    "LineNumber": 2,
    "OffsetAccountType": "Bank",
    "Date": "2021-01-11T12:00:00Z",
    "Debit": 250,
    "OffsetAccountDisplayValue": "USMF OPER",
    "AccountDisplayValue": "1001",
    "RemittanceAddressCity": "Houston",
    "AccountType": "Vend",
    "OffsetCompany": "usmf",
    "Currency": "USD"
}
--batch_boundary--
```

</details>

<details>
    <summary>
    Response:
    </summary>

```json
--batchresponse_ea261495-d7f4-4336-ac3a-af1ad8462955
Content-Type: multipart/mixed; boundary=changesetresponse_3669d3bc-6169-4ede-a7ae-20a914b4d5c0

--changesetresponse_3669d3bc-6169-4ede-a7ae-20a914b4d5c0
Content-Type: application/http
Content-Transfer-Encoding: binary
Content-ID: 1

HTTP/1.1 201 Created
ETag: W/"JzEsNjg3MTk1MjU3NjEn"
Location: https://{{base_url}}/data/VendInvoiceJournalHeaders(dataAreaId='usmf',JournalBatchNumber='B0002')
Content-Type: application/json; odata.metadata=minimal
OData-Version: 4.0

{
    "@odata.context": "https://{{base_url}}/data/$metadata#VendInvoiceJournalHeaders/$entity",
    "@odata.etag": "W/\"JzEsNjg3MTk1MjU3NjEn\"",
    "dataAreaId": "usmf",
    "JournalBatchNumber": "B0002",
    "JournalName": "APInvoice",
    "Description": "AP Invoice",
    "IsPosted": "No",
    "SalesTaxIncluded": "No"
}
--changesetresponse_3669d3bc-6169-4ede-a7ae-20a914b4d5c0
Content-Type: application/http
Content-Transfer-Encoding: binary
Content-ID: 2

HTTP/1.1 201 Created
ETag: W/"JzEsNjg3MTk1OTgwNDI7MCwwOzAsMCc="
Location: https://{{base_url}}/data/VendInvoiceJournalLines(dataAreaId='usmf',JournalBatchNumber='B0002',LineNumber=1)
Content-Type: application/json; odata.metadata=minimal
OData-Version: 4.0

{
    "@odata.context": "https://{{base_url}}/data/$metadata#VendInvoiceJournalLines/$entity",
    "@odata.etag": "W/\"JzEsNjg3MTk1OTgwNDI7MCwwOzAsMCc=\"",
    "dataAreaId": "usmf",
    "JournalBatchNumber": "B0002",
    "LineNumber": 1,
    "ItemSalesTaxGroup": "",
    "CashDiscountDate": "2021-01-21T12:00:00Z",
    "Voucher": "APIN000053",
    "TermsOfPayment": "Net30",
    "Credit": 0,
    "OffsetAccountType": "Bank",
    "BookId": "",
    "Listcode": "IncludeNot",
    "MethodOfPayment": "CHECK",
    "RemittanceAddressDistrictName": "",
    "RemittanceAddressCountryISOCode": "",
    "RemittanceAddressCounty": "",
    "GSTHSTTaxType": "None",
    "RemittanceAddressLongitude": 0,
    "DefaultDimensionDisplayValue": "",
    "Document": "",
    "CashDiscountAmount": 0.75,
    "TransactionType": "Vend",
    "ApproverNumber": "",
    "ExchRate": 100,
    "ChineseVoucherType": "",
    "UUID": "",
    "RemittanceAddressZipCode": "",
    "AssetTransType": "None",
    "RemittanceAddressStreet": "",
    "InvoiceDate": "1900-01-01T12:00:00Z",
    "FullPrimaryRemittanceAddress": "",
    "RemittanceAddressValidTo": "1900-01-01T00:00:00Z",
    "PaymId": "",
    "AccountDisplayValue": "1001",
    "OffsetAccountDisplayValue": "USMF OPER",
    "CashDiscount": "0.5%D10",
    "AssetId": "",
    "RemittanceAddressCity": "Houston",
    "Debit": 150,
    "RemittanceAddressLatitude": 0,
    "Description": "",
    "OffsetTransactionText": "",
    "PaymentSpecification": "",
    "SalesTaxGroup": "",
    "RemittanceAddressLocationId": "",
    "AccountType": "Vend",
    "Invoice": "",
    "Tax1099Fields": 0,
    "DueDate": "2021-02-10T12:00:00Z",
    "RemittanceAddressState": "",
    "ReportingCurrencyExchRate": 100,
    "RemittanceAddressDescription": "",
    "RemittanceAddressValidFrom": "1900-01-01T00:00:00Z",
    "RemittanceAddressCountry": "",
    "RemittanceAddressTimeZone": null,
    "InvoiceDeclarationId": "",
    "PostingProfile": "GEN",
    "IsWithholdingTaxCalculate": "No",
    "ExchRateSecond": 0,
    "CustVendBankAccountId": "",
    "BankAccountId": "",
    "OffsetCompany": "USMF",
    "ItemWithholdingTaxGroupCode": "",
    "TaxExemptNumber": "",
    "Currency": "USD",
    "Company": "USMF",
    "TypeOfOperation": "Blank",
    "DeliveryDate": "1900-01-01T12:00:00Z",
    "Approved": "Yes",
    "ChineseVoucher": "",
    "Date": "2021-01-11T12:00:00Z"
}
--changesetresponse_3669d3bc-6169-4ede-a7ae-20a914b4d5c0
Content-Type: application/http
Content-Transfer-Encoding: binary
Content-ID: 3

HTTP/1.1 201 Created
ETag: W/"JzEsNjg3MTk1OTgwNDM7MCwwOzAsMCc="
Location: https://{{base_url}}/data/VendInvoiceJournalLines(dataAreaId='usmf',JournalBatchNumber='B0002',LineNumber=2)
Content-Type: application/json; odata.metadata=minimal
OData-Version: 4.0

{
    "@odata.context": "https://{{base_url}}/data/$metadata#VendInvoiceJournalLines/$entity",
    "@odata.etag": "W/\"JzEsNjg3MTk1OTgwNDM7MCwwOzAsMCc=\"",
    "dataAreaId": "usmf",
    "JournalBatchNumber": "B0002",
    "LineNumber": 2,
    "ItemSalesTaxGroup": "",
    "CashDiscountDate": "2021-01-21T12:00:00Z",
    "Voucher": "APIN000054",
    "TermsOfPayment": "Net30",
    "Credit": 0,
    "OffsetAccountType": "Bank",
    "BookId": "",
    "Listcode": "IncludeNot",
    "MethodOfPayment": "CHECK",
    "RemittanceAddressDistrictName": "",
    "RemittanceAddressCountryISOCode": "",
    "RemittanceAddressCounty": "",
    "GSTHSTTaxType": "None",
    "RemittanceAddressLongitude": 0,
    "DefaultDimensionDisplayValue": "",
    "Document": "",
    "CashDiscountAmount": 1.25,
    "TransactionType": "Vend",
    "ApproverNumber": "",
    "ExchRate": 100,
    "ChineseVoucherType": "",
    "UUID": "",
    "RemittanceAddressZipCode": "",
    "AssetTransType": "None",
    "RemittanceAddressStreet": "",
    "InvoiceDate": "1900-01-01T12:00:00Z",
    "FullPrimaryRemittanceAddress": "",
    "RemittanceAddressValidTo": "1900-01-01T00:00:00Z",
    "PaymId": "",
    "AccountDisplayValue": "1001",
    "OffsetAccountDisplayValue": "USMF OPER",
    "CashDiscount": "0.5%D10",
    "AssetId": "",
    "RemittanceAddressCity": "Houston",
    "Debit": 250,
    "RemittanceAddressLatitude": 0,
    "Description": "",
    "OffsetTransactionText": "",
    "PaymentSpecification": "",
    "SalesTaxGroup": "",
    "RemittanceAddressLocationId": "",
    "AccountType": "Vend",
    "Invoice": "",
    "Tax1099Fields": 0,
    "DueDate": "2021-02-10T12:00:00Z",
    "RemittanceAddressState": "",
    "ReportingCurrencyExchRate": 100,
    "RemittanceAddressDescription": "",
    "RemittanceAddressValidFrom": "1900-01-01T00:00:00Z",
    "RemittanceAddressCountry": "",
    "RemittanceAddressTimeZone": null,
    "InvoiceDeclarationId": "",
    "PostingProfile": "GEN",
    "IsWithholdingTaxCalculate": "No",
    "ExchRateSecond": 0,
    "CustVendBankAccountId": "",
    "BankAccountId": "",
    "OffsetCompany": "USMF",
    "ItemWithholdingTaxGroupCode": "",
    "TaxExemptNumber": "",
    "Currency": "USD",
    "Company": "USMF",
    "TypeOfOperation": "Blank",
    "DeliveryDate": "1900-01-01T12:00:00Z",
    "Approved": "Yes",
    "ChineseVoucher": "",
    "Date": "2021-01-11T12:00:00Z"
}
--changesetresponse_3669d3bc-6169-4ede-a7ae-20a914b4d5c0--
--batchresponse_ea261495-d7f4-4336-ac3a-af1ad8462955--
```

</details>
