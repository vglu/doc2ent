---
title: "Work with Currencies"
date: 2021-01-13
tags:
  - Currency
tables:
  - Currency
Entities: 
  - CurrencyEntity
Relations:
  - ForecastSupplyForecastEntryEntity
  - CustInvoiceJournalLineEntity
  - CurrencyRevaluationAccountV2Entity
  - LedgerReportingCurrencyAdjustmentJournalLineEntity
  - VendInvoiceJournalLineEntity
  - LedgerJournalLineCDSEntity
  - smmProspectEntity
  - CashFlowExternalSourceEntryEntity
  - CustomerPaymentJournalLineEntity
  - VendorPaymentJournalLineEntity
  - PurchPurchaseAgreementConfirmationHeaderEntity 
  - LedgerEntity
  - SalesAgreementConfirmationHeaderEntity 
  - RetailInternalOrganizationProductAttributeValue2Entity
  - VendInvoiceRegisterLineEntity
  - BudgetRegisterEntryLineEntity
  - ProjProjectTransferPriceV2Entity
  - TAMTradeAllowanceAgreementMerchandisingEventBillBackLineEntity 
  - ExchangeRateEntity
  - HcmCompensationMeritIncreaseTargetEntity
  - LedgerJournalLineEntity
  - SystemParametersEntity
  - EcoResProductAttributeValueEntity
  - SalesAgreementHeaderEntity
  - FreeTextInvoiceHeaderEntity
  - PurchPurchaseOrderHeaderChargeEntity
  - HcmCompFixedPlanTableEntity
  - RAssetJournalLineEntity
  - PurchPurchaseOrderLineChargeEntity
  - ExpenseJournalLineEntity
  - MainAccountEntity
  - VendorPaymentJournalFeeEntity
  - VendVendorBankAccountEntity
  - BudgetRegisterEntryEntity
  - TAMTradeAllowanceAgreementHeaderEntity 
  - CustomerPaymentJournalFeeEntity
  - AssetJournalLines
  - RetailCatalogInternalOrganizationProductAttributeValue2Entity
  - ExchangeRateCDSEntity
  - FreeTextInvoiceHeaderCDSEntity
  - HcmCompVarPlanTableEntity
  - BankAccountEntity
  - HcmBenefitPlanEntity
AXPath: Cost accounting\Ledger setup\Currencies
Operations:
  - Read
  - Create
  - Update
  - Delete
weight: 1
---

Navigation path: Cost accounting\Ledger setup\Currencies

| Data entity AOT name | Entity name (DMF) | Public collection name (OData) | Support OData | Support DMF | Category  | ReadOnly |
| -------------------- | ----------------- | ------------------------------ | ------------- | ----------- | --------- | -------- |
| CurrencyEntity       | Currencies        | Currencies                     | Yes           | Yes         | Reference | No       |

`CurrencyEntity` Entity is allowed to operate with warehowses in D365FO.

## Key

- CurrencyCode

## Fields

| Field name                           | Value example | Description |
| ------------------------------------ | ------------- | ----------- |
| (*)**CurrencyCode**                  | "USD"         |             |
| RoundingMethodPurchaseOrders         | "Ordinary"    |             |
| RoundingMethodPrices                 | "Ordinary"    |             |
| Name                                 | "US Dollar"   |             |
| RoundingMethodSalesOrders            | "Ordinary"    |             |
| Symbol                               | "$"           |             |
| RoundingRuleFixedAssetDepreciation   | 0             |             |
| ReferenceCurrencyForTriangulation    | "No"          |             |
| CurrencyGender                       | "Male"        |             |
| RoundingRulePurchaseOrders           | 0             |             |
| GeneralRoundingRule                  | 0             |             |
| RoundingMethodFixedAssetDepreciation | "Ordinary"    |             |
| RoundingRulePrices                   | 0             |             |
| RoundingRuleSalesOrders              | 0             |             |
| DecimalsCount_MX                     | 0             |             |


## Postman

### Request for get data

`GET: https://{{base_url}}/data/Currencies(CurrencyCode='USD')`

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
    "@odata.context": "https://{{base_url}}/data/$metadata#Currencies/$entity",
    "@odata.etag": "W/\"JzAsNTYzNzE0NDczMDswLDU2MzcxNDQ3MzAn\"",
    "CurrencyCode": "USD",
    "RoundingMethodPurchaseOrders": "Ordinary",
    "RoundingMethodPrices": "Ordinary",
    "Name": "US Dollar",
    "RoundingMethodSalesOrders": "Ordinary",
    "Symbol": "$",
    "RoundingRuleFixedAssetDepreciation": 0,
    "ReferenceCurrencyForTriangulation": "No",
    "CurrencyGender": "Male",
    "RoundingRulePurchaseOrders": 0,
    "GeneralRoundingRule": 0,
    "RoundingMethodFixedAssetDepreciation": "Ordinary",
    "RoundingRulePrices": 0,
    "RoundingRuleSalesOrders": 0,
    "DecimalsCount_MX": 0
}
```

</details>

### Request for create data

`POST : https://{{base_url}}/data/Currencies`

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
    "@odata.type":"#Microsoft.Dynamics.DataEntities.Currency",
    "CurrencyCode": "AFN"
}
```

</details>

<details>
    <summary>
    Response:
    </summary>

```json
{
    "@odata.context": "https://{{base_url}}/data/$metadata#Currencies/$entity",
    "@odata.etag": "W/\"JzAsNTYzNzE0NDU3NzswLDU2MzcxNDQ1Nzcn\"",
    "CurrencyCode": "AFN",
    "RoundingMethodPurchaseOrders": "Ordinary",
    "RoundingMethodPrices": "Ordinary",
    "Name": "Afghani",
    "RoundingMethodSalesOrders": "Ordinary",
    "Symbol": "",
    "RoundingRuleFixedAssetDepreciation": 0,
    "ReferenceCurrencyForTriangulation": "No",
    "CurrencyGender": "Male",
    "RoundingRulePurchaseOrders": 0,
    "GeneralRoundingRule": 0,
    "RoundingMethodFixedAssetDepreciation": "Ordinary",
    "RoundingRulePrices": 0,
    "RoundingRuleSalesOrders": 0,
    "DecimalsCount_MX": 0
}
```

</details>

### Request for update data

`PATCH : https://{{base_url}}/data/Currencies(CurrencyCode='AFN')`

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
    "@odata.type":"#Microsoft.Dynamics.DataEntities.Currency",
    "Symbol": "&"
}
```

</details>

<details>
    <summary>
    Response:
    </summary>
    Status: 204
</details>

### Request for delete data

`DELETE : https://{{base_url}}/data/Currencies(CurrencyCode='AFN')`

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

## Relations

| Relation name                                           | Data entity AOT name                                           | Entity name (DMF)                                                  | Public collection name (OData)                           | Support Odata | Support DMF | Category    | ReadOnly | Notes |
| ------------------------------------------------------- | -------------------------------------------------------------- | ------------------------------------------------------------------ | -------------------------------------------------------- | ------------- | ----------- | ----------- | -------- | ----- |
| SupplyForecastEntries                                   | ForecastSupplyForecastEntryEntity                              | Supply forecast entries                                            | SupplyForecastEntries                                    | Yes           | Yes         | Document    | Yes      |       | " |
| CustInvoiceJournalLineCurrency                          | CustInvoiceJournalLineEntity                                   | Customer invoice journal line                                      | GeneralLedgerCustInvoiceJournalLines                     | Yes           | Yes         | Document    | No       |       |
| CurrencyRevaluationAccount                              | CurrencyRevaluationAccountV2Entity                             | Currency ledger revaluation account V2                             | CurrencyRevaluationAccountsV2                            | Yes           | Yes         | Reference   | No       |       |
| LedgerReportingCurrencyAdjustmentJournalLineCurrency    | LedgerReportingCurrencyAdjustmentJournalLineEntity             | Reporting currency adjustment journal line                         | LedgerReportingCurrencyAdjustmentJournalLines            | Yes           | Yes         | Document    | No       |       |
| VendInvoiceJournalLineCurrency                          | VendInvoiceJournalLineEntity                                   | Vendor invoice journal line                                        | VendInvoiceJournalLines                                  | Yes           | Yes         | Document    | No       |       | " |
| LedgerJournalLineCDSCurrency                            | LedgerJournalLineCDSEntity                                     | CDS Ledger journal line entity                                     | LedgerJournalCDSLines                                    | Yes           | Yes         | Document    | No       |       |
| Prospects                                               | smmProspectEntity                                              | Prospects                                                          | Prospects                                                | Yes           | Yes         | Master      | No       |       | " |
| CashFLowExternalSourceEntryCurrencyCode                 | CashFlowExternalSourceEntryEntity                              | Cash flow forecast external source entry                           | CashFlowForecastExternalSourceEntries                    | Yes           | Yes         | Master      | No       |       |
| CustomerPaymentJournalLineCurrentyEntity                | CustomerPaymentJournalLineEntity                               | Customer payment journal line                                      | CustomerPaymentJournalLines                              | Yes           | Yes         | Document    | No       |       |
| VendorPaymentJournalLine                                | VendorPaymentJournalLineEntity                                 | Vendor payment journal line                                        | VendorPaymentJournalLines                                | Yes           | Yes         | Document    | No       |       |
| PurchaseAgreementHeaders                                | PurchPurchaseAgreementConfirmationHeaderEntity                 | Purchase agreement confirmation headers                            | PurchaseAgreementConfirmations                           | Yes           | Yes         | Document    | Yes      |       |
| LedgerReportingCurrency                                 | LedgerEntity                                                   | Ledger                                                             | Ledgers                                                  | Yes           | Yes         | Parameters  | No       |       |
| LedgerAccountingCurrency                                | LedgerEntity                                                   | Ledger                                                             | Ledgers                                                  | Yes           | Yes         | Parameters  | No       |       |
| SalesAgreementConfirmationHeaders                       | SalesAgreementConfirmationHeaderEntity                         | Sales agreement confirmation headers                               | SalesAgreementConfirmations                              | Yes           | Yes         | Document    | No       |       |
| RetailInternalOrganizationProductAttributeValue2        | RetailInternalOrganizationProductAttributeValue2Entity         | Internal organization product attribute values - Version 2         | RetailInternalOrganizationProductAttributeValues2        | Yes           | Yes         | Master      | No       |       |
| VendInvoiceRegisterLineCurrency                         | VendInvoiceRegisterLineEntity                                  | Vendor invoice register line                                       | VendInvoiceRegisterLines                                 | Yes           | Yes         | Document    | No       |       |
| BudgetRegisterEntryLineCurrencyCode                     | BudgetRegisterEntryLineEntity                                  | no entry                                                           | BudgetRegisterEntryLines                                 | Yes           | No          | Document    | No       |       | " |
| TransferPriceCurrency                                   | ProjProjectTransferPriceV2Entity                               | Project transfer price V2                                          | TransferPrices                                           | Yes           | Yes         | Master      | No       |       |
| TradeAllowanceAgreementMerchandisingEventBillBackLines  | TAMTradeAllowanceAgreementMerchandisingEventBillBackLineEntity | Trade allowance agreement merchandising event bill back lines      | TradeAllowanceAgreementMerchandisingEventBillBackLines   | Yes           | Yes         | Master      | Yes      |       |
| ExchangeRate                                            | ExchangeRateEntity                                             | Exchange rates                                                     | ExchangeRates                                            | Yes           | Yes         | Reference   | No       |       | " |
| ExchangeRateFromCurrencies                              |                                                                |                                                                    |                                                          |               |             |             |          |       |
| CompensationFixedIncreaseBudgets                        | HcmCompensationMeritIncreaseTargetEntity                       | Compensation merit increase target                                 | CompensationFixedIncreaseBudgets                         | Yes           | Yes         | Master      | No       |       |
| LedgerJournalLineCurrency                               | LedgerJournalLineEntity                                        | no entry                                                           | LedgerJournalLines                                       | Yes           | No          | Document    | No       |       |
| SystemParameters                                        | SystemParametersEntity                                         | System parameters                                                  | SystemParameters                                         | Yes           | Yes         | Master      | No       |       |
| ProductAttributeValues                                  | EcoResProductAttributeValueEntity                              | Product attribute values                                           | ProductAttributeValues                                   | Yes           | Yes         | Master      | No       |       |
| SalesAgreementHeaders                                   | SalesAgreementHeaderEntity                                     | Sales agreement headers                                            | SalesAgreements                                          | Yes           | Yes         | Document    | No       |       |
| FreeTextInvoiceHeaderCurrency                           | FreeTextInvoiceHeaderEntity                                    | no entry                                                           | FreeTextInvoiceHeaders                                   | Yes           | No          | Document    | No       |       |
| PurchaseOrderHeaderCharges                              | PurchPurchaseOrderHeaderChargeEntity                           | Purchase order charges                                             | PurchaseOrderHeaderCharges                               | Yes           | Yes         | Document    | No       |       |
| CompFixedPlanTables                                     | HcmCompFixedPlanTableEntity                                    | Compensation fixed plan                                            | CompFixedPlanTables                                      | Yes           | Yes         | Reference   | No       |       | " |
| RAssetJournalLineCurrency                               | RAssetJournalLineEntity                                        | Fixed asset journal lines (Russia)                                 | RAssetJournalLines                                       | Yes           | Yes         | Document    | No       |       |
| PurchaseOrderLineCharges                                | PurchPurchaseOrderLineChargeEntity                             | Purchase order line charges                                        | PurchaseOrderLineCharges                                 | Yes           | Yes         | Document    | No       |       |
| ProjectExpenseJournalLineCurrency                       | ExpenseJournalLineEntity                                       | Project expense journal lines                                      | ExpenseJournalLines                                      | Yes           | Yes         | Document    | No       |       |
| MainAccount                                             | MainAccountEntity                                              | Main account                                                       | MainAccounts                                             | Yes           | Yes         | Master      | No       |       | " |
| VendorPaymentJournalFee                                 | VendorPaymentJournalFeeEntity                                  | Vendor payment journal fee                                         | VendorPaymentJournalFees                                 | Yes           | Yes         | Transaction | No       |       |
| VendorBankAccounts                                      | VendVendorBankAccountEntity                                    | Vendor bank accounts                                               | VendorBankAccounts                                       | Yes           | Yes         | Master      | No       |       |
| BudgetRegisterEntry                                     | BudgetRegisterEntryEntity                                      | Budget account entries                                             | BudgetRegisterEntries                                    | Yes           | Yes         | Master      | No       |       |
| TradeAllowanceAgreementHeaders                          | TAMTradeAllowanceAgreementHeaderEntity                         | Trade allowance agreement headers                                  | TradeAllowanceAgreementHeaders                           | Yes           | Yes         | Master      | Yes      |       |
| CustomerPaymentJournalFee                               | CustomerPaymentJournalFeeEntity                                | Customer payment journal fee                                       | CustomerPaymentJournalFees                               | Yes           | Yes         | Transaction | No       |       | " |
| AssetJournalLineCurrency                                | AssetJournalLines                                              | no entry                                                           | AssetJournalLines                                        | Yes           | No          | Document    | No       |       |
| RetailCatalogInternalOrganizationProductAttributeValue2 | RetailCatalogInternalOrganizationProductAttributeValue2Entity  | Catalog internal organization product attribute values - Version 2 | RetailCatalogInternalOrganizationProductAttributeValues2 | Yes           | Yes         | Master      | No       |       |
| ExchangeRateCDSEntity                                   | ExchangeRateCDSEntity                                          | CDS Exchange Rates                                                 | ExchangeRatesCDSEntity                                   | Yes           | Yes         | Document    | No       |       |
| CDSFreeTextInvoiceHeaders                               | FreeTextInvoiceHeaderCDSEntity                                 | CDS customer free text invoice headers                             | CDSFreeTextInvoiceHeaders                                | Yes           | Yes         | Document    | No       |       |
| CompVarPlanTable                                        | HcmCompVarPlanTableEntity                                      | Compensation variable plan                                         | CompVarPlanTables                                        | Yes           | Yes         | Master      | No       |       |
| BankAccount                                             | BankAccountEntity                                              | Bank accounts                                                      | BankAccounts                                             | Yes           | Yes         | Master      | No       |       |
| BenefitPlan                                             | HcmBenefitPlanEntity                                           | Benefit plan                                                       | BenefitPlans                                             | Yes           | Yes         | Reference   | No       |       |

### Relation usecase

Request `GET: https://{{base_url}}/data/Currencies('USD')/VendInvoiceJournalLineCurrency?$top=2` return 2 records from Invoice journal where Currency equals 'USD'

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
    "@odata.context": "https://{{base_url}}/data/$metadata#VendInvoiceJournalLines",
    "value": [
        {
            "@odata.etag": "W/\"JzE4NjA2OTczNjAsNjg3MTk1OTcyOTI7MCwwOzAsMCc=\"",
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
            "DefaultDimensionDisplayValue": "001--",
            "Document": "",
            "CashDiscountAmount": 0,
            "TransactionType": "Vend",
            "ApproverNumber": "000020",
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
            "Debit": 6800,
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
        },
        {
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
            "DefaultDimensionDisplayValue": "001--",
            "Document": "",
            "CashDiscountAmount": 0.75,
            "TransactionType": "Vend",
            "ApproverNumber": "000020",
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
            "RemittanceAddressCity": "",
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
    ]
}
```

</details>
