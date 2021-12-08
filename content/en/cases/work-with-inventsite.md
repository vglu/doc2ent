---
title: "Work with inventory site (Sites)"
date: 2021-01-13
tags:
  - InventSite
tables:
  - InventSite
Entities: 
  - OperationalSites
Relations:
  - RouteCardProductionJournalEntries
  - ItemCoverageSettings
  - SupplyForecastEntries
  - ItemSpecificBillOfMaterialsHeaders
  - ItemSpecificBillOfMaterialsHeadersV3
  - ProductSpecificOrderSettingsV3
  - OpenSalesPriceJournalLine
  - AggregatedCostStatementEntries
  - InventoryCountingJournalLines
  - BillOfMaterialsHeaders
  - PurchaseAgreementLinesV2
  - ProductSpecificOrderSettingsV2
  - ProductDefaultOrderSettings
  - ItemArrivalJournalLinesV2
  - JobCardProductionJournalEntries
  - RebateAndDeductionsAgreementHeaders
  - InventoryTagCountingJournalLines
  - ProductionPickingListJournalEntries
  - BillOfMaterialsVersionsV3
  - SalesAgreementConfirmationLines
  - Warehouses
  - SalesAgreementLines
  - CDSInventoryOnHandEntries
  - OpenPurchasePriceJournalLine
  - QualityOrderHeaders
  - PurchaseAgreementLine
  - CostMontlyStatementEntries
  - OpenSalesLineDiscountJournalLine
  - CostStatementEntries
  - BillOfMaterialsVersionsV2
  - ReceivingSentProductReleaseHeaders
  - ReleasingSentProductReleaseHeaders
  - ItemArrivalJournalHeadersV2
  - ReceivingReceivedProductReleaseHeaders
  - ReleasingReceivedProductReleaseHeaders
  - OpenSalesPostageDiscountJournalLine
  - ServiceAgreementLines
  - PendingRouteCostCategoryUnitCosts
  - ItemSpecificBillOfMaterialsHeadersV2
  - OpenPurchaseLineDiscountJournalLine
  - OperationalSiteCurrentPostalAddresses
  - FiscalEstablishment
  - ReportAsFinishedProductionJournalEntries
AXPath: Warehouse management\Setup\Warehouse\Sites
Operations:
  - Read
  - Create
  - Update
  - Delete
weight: 1
---

Navigation path: Warehouse management\Setup\Warehouse\Sites

| Data entity AOT name        | Entity name (DMF) | Public collection name (OData) | Support OData | Support DMF | Category | ReadOnly |
| --------------------------- | ----------------- | ------------------------------ | ------------- | ----------- | -------- | -------- |
| InventOperationalSiteEntity | Sites             | OperationalSites               | Yes           | Yes         | Master   | No       |

`OperationalSites` Entity is allowed to operate with warehowses in D365FO.

## Key

- dataAreaId
- SiteId

## Fields

| Field name                                             | Value example                                    | Description |
| ------------------------------------------------------ | ------------------------------------------------ | ----------- |
| (*)__dataAreaId__                                      | "usmf"                                           |             |
| (*)**SiteId**                                          | "1"                                              |             |
| IsReceivingWarehouseOverrideAllowed                    | "No"                                             |             |
| PrimaryAddressCountyId                                 | "ASOTIN"                                         |             |
| PrimaryAddressLocationSalesTaxGroupCode                | ""                                               |             |
| PrimaryAddressCity                                     | "Galvin"                                         |             |
| PrimaryAddressStreetNumber                             | ""                                               |             |
| FormattedPrimaryAddress                                | "213 South Street Gate 1\nGalvin WA 98544 \nUSA" |             |
| FiscalEstablishmentId                                  | ""                                               |             |
| PrimaryAddressDescription                              | "Site 1"                                         |             |
| PrimaryAddressZipCode                                  | "98544"                                          |             |
| PrimaryAddressLongitude                                | 0                                                |             |
| PrimaryAddressStateId                                  | "WA"                                             |             |
| DefaultInventoryStatusId                               | ""                                               |             |
| TaxBranchCode                                          | ""                                               |             |
| WillMasterPlannedIntraSiteMovementsUseTransferJournals | "No"                                             |             |
| PrimaryAddressStreet                                   | "213 South Street Gate 1"                        |             |
| IsPrimaryAddressAssigned                               | "Yes"                                            |             |
| SiteTimezone                                           | "GMTMINUS0800PACIFICTIME"                        |             |
| DefaultFinancialDimensionValue                         | ""                                               |             |
| PrimaryAddressBuildingCompliment                       | ""                                               |             |
| PrimaryAddressLocationRoles                            | "Delivery"                                       |             |
| PrimaryAddressDistrictName                             | ""                                               |             |
| PrimaryAddressPostBox                                  | ""                                               |             |
| PrimaryAddressTimeZone                                 | null                                             |             |
| SiteName                                               | "Home speakers production"                       |             |
| PrimaryAddressLatitude                                 | 0                                                |             |
| PrimaryAddressCityInKana                               | ""                                               |             |
| OrderEntryDeadlineGroupId                              | ""                                               |             |
| PrimaryAddressStreetInKana                             | ""                                               |             |
| PrimaryAddressCountryRegionId                          | "USA"                                            |             |

## Postman

### Request for get data

`GET: https://{{base_url}}/data/OperationalSites(dataAreaId='usmf',SiteId='1')`

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
    "@odata.context": "https://{{base_url}}/data/$metadata#OperationalSites/$entity",
    "@odata.etag": "W/\"JzAsMjI1NjU0MjE2NzY7MCwyMjU2NTQyMTQyNjswLDA7MCwyMjU2NTQyNjk4OSc=\"",
    "dataAreaId": "usmf",
    "SiteId": "1",
    "IsReceivingWarehouseOverrideAllowed": "No",
    "PrimaryAddressCountyId": "ASOTIN",
    "PrimaryAddressLocationSalesTaxGroupCode": "",
    "PrimaryAddressCity": "Galvin",
    "PrimaryAddressStreetNumber": "",
    "FormattedPrimaryAddress": "213 South Street, Gate 1\nGalvin, WA 98544 \nUSA",
    "FiscalEstablishmentId": "",
    "PrimaryAddressDescription": "Site 1",
    "PrimaryAddressZipCode": "98544",
    "PrimaryAddressLongitude": 0,
    "PrimaryAddressStateId": "WA",
    "DefaultInventoryStatusId": "",
    "TaxBranchCode": "",
    "WillMasterPlannedIntraSiteMovementsUseTransferJournals": "No",
    "PrimaryAddressStreet": "213 South Street, Gate 1",
    "IsPrimaryAddressAssigned": "Yes",
    "SiteTimezone": "GMTMINUS0800PACIFICTIME",
    "DefaultFinancialDimensionValue": "",
    "PrimaryAddressBuildingCompliment": "",
    "PrimaryAddressLocationRoles": "Delivery",
    "PrimaryAddressDistrictName": "",
    "PrimaryAddressPostBox": "",
    "PrimaryAddressTimeZone": null,
    "SiteName": "Home speakers production",
    "PrimaryAddressLatitude": 0,
    "PrimaryAddressCityInKana": "",
    "OrderEntryDeadlineGroupId": "",
    "PrimaryAddressStreetInKana": "",
    "PrimaryAddressCountryRegionId": "USA"
}
```

</details>

### Request for create data

`POST : https://{{base_url}}/data/OperationalSites`

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
    "@odata.type":"#Microsoft.Dynamics.DataEntities.OperationalSite",
    "dataAreaId": "usmf",
    "SiteId": "A2"
}
```

</details>

<details>
    <summary>
    Response:
    </summary>

```json
{
    "@odata.context": "https://{{base_url}}/data/$metadata#OperationalSites/$entity",
    "@odata.etag": "W/\"JzEsNjg3MTk0NzkwMjg7MSw2ODcxOTQ3OTAyOTswLDA7MCwwJw==\"",
    "dataAreaId": "usmf",
    "SiteId": "A2",
    "IsReceivingWarehouseOverrideAllowed": "No",
    "PrimaryAddressCountyId": "",
    "PrimaryAddressLocationSalesTaxGroupCode": "",
    "PrimaryAddressCity": "",
    "PrimaryAddressStreetNumber": "",
    "FormattedPrimaryAddress": "",
    "FiscalEstablishmentId": "",
    "PrimaryAddressDescription": "",
    "PrimaryAddressZipCode": "",
    "PrimaryAddressLongitude": 0,
    "PrimaryAddressStateId": "",
    "DefaultInventoryStatusId": "",
    "TaxBranchCode": "",
    "WillMasterPlannedIntraSiteMovementsUseTransferJournals": "No",
    "PrimaryAddressStreet": "",
    "IsPrimaryAddressAssigned": "No",
    "SiteTimezone": "GMTMINUS0800PACIFICTIME",
    "DefaultFinancialDimensionValue": "",
    "PrimaryAddressBuildingCompliment": "",
    "PrimaryAddressLocationRoles": "",
    "PrimaryAddressDistrictName": "",
    "PrimaryAddressPostBox": "",
    "PrimaryAddressTimeZone": null,
    "SiteName": "",
    "PrimaryAddressLatitude": 0,
    "PrimaryAddressCityInKana": "",
    "OrderEntryDeadlineGroupId": "",
    "PrimaryAddressStreetInKana": "",
    "PrimaryAddressCountryRegionId": ""
}
```

</details>

### Request for update data

`PATCH : https://{{base_url}}/data/OperationalSites(dataAreaId='usmf',SiteId='A2')`

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
    "@odata.type":"#Microsoft.Dynamics.DataEntities.OperationalSite",
    "SiteName": "New site name"
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

`DELETE : https://{{base_url}}/data/OperationalSites(dataAreaId='usmf',SiteId='A2')`

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

## Relation

| Relation name                                   | Data entity AOT name                             | Entity name (DMF)                             | Public collection name (OData)           | Support Odata | Support DMF | Category     | ReadOnly | Notes |
| ----------------------------------------------- | ------------------------------------------------ | --------------------------------------------- | ---------------------------------------- | ------------- | ----------- | ------------ | -------- | ----- |

### Relation usecase

Request `GET: https://{{base_url}}/data/OperationalSites(dataAreaId='usmf',SiteId='1')/ItemCoverageSettings?$filter=ItemNumber eq 'D0001'&$count=true` return 1 records from Item Coverage Settings where Site = '1' and Item number = 'D0001'

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
    "@odata.context": "https://{{base_url}}/data/$metadata#ItemCoverageSettings",
    "@odata.count": 1,
    "value": [
        {
            "@odata.etag": "W/\"JzAsMjI1NjU0MjE5NDQn\"",
            "dataAreaId": "usmf",
            "ItemNumber": "D0001",
            "CoverageWarehouseLocationId": "",
            "CoverageItemBatchNumber": "",
            "CoverageProductColorId": "",
            "CoverageProductSizeId": "",
            "CoverageProductStyleId": "",
            "CoverageWarehouseId": "",
            "CoverageItemSerialNumber": "",
            "CoverageSiteId": "1",
            "CoverageInventoryStatusId": "",
            "CoverageProductConfigurationId": "",
            "CoveragePeriodDays": 1,
            "VendorAccountNumber": "US-101",
            "ApprovedRequisitionTimeFenceDays": 0,
            "LastPlanningFormulaPriorityChangedDate": "1900-01-01T12:00:00Z",
            "ProcurementLeadTimeDays": 0,
            "DefaultPlanningFormulaPriority": 99,
            "IsProcurementLeadTimeOverridden": "No",
            "AutomaticFirmingTimeFenceDays": 0,
            "IsConsumeOnHandOverridden": "No",
            "ProductionLeadTimeDays": 0,
            "MinimumOnHandFulfillmentMethod": "TodaysDate",
            "PlanningFormulaItemNumber": "",
            "MaximumOnHandInventoryQuantity": 0,
            "AreTimeFencesOverridden": "No",
            "FreezeTimeFenceDays": 0,
            "IsTransferLeadTimeOverridden": "No",
            "CapacitySchedulingTimeFenceDays": 100,
            "NegativeDays": 2,
            "MinimumOnHandInventoryQuantity": 0,
            "MaximumOnHandInventorySafetyKeyId": "",
            "PositiveDays": 100,
            "CoverageTimeFenceDays": 100,
            "CurrentPlanningFormulaPriority": 99,
            "ProductCoverageGroupId": "Req",
            "MinimumOnHandInventorySafetyKeyId": "",
            "AreCoverageGroupSettingsOverridden": "No",
            "IsTransferLeadTimeUsingWorkingDays": "Yes",
            "IsProcumentLeadTimeUsingWorkingDays": "No",
            "BOMOrFormulaExplosionTimeFenceDays": 100,
            "AreGeneralSettingsOverridden": "No",
            "DefaultPlannedTransferOrderFromWarehouseId": "",
            "CoverageMethod": "Req",
            "ConsumeOnHandInventoryMethod": "BeforeAllOtherSupply",
            "TransferLeadTimeDays": 0,
            "PlannedOrderType": "Production",
            "IsPlannedOrderTypeOverridden": "No",
            "IsProductionLeadTimeOverridden": "No",
            "IsProductionLeadTimeUsingWorkingDays": "No",
            "IsMinimumOnHandSafetyPeriodUsed": "No"
        }
    ]
}
```

</details>
