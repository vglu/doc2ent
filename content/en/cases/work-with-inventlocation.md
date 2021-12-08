---
title: "Work with inventory location (warehouse)"
date: 2021-01-10
tags:
  - InventLocation
tables:
  - InventLocation
Entities: 
  - Warehouses
Relations:
  - SalesAgreementConfirmationLines
  - RebateAndDeductionsAgreementHeaders
  - ReportAsFinishedProductionJournalEntries
  - ItemArrivalJournalLinesV2
  - OpenPurchasePriceJournalLine
  - ProductDefaultOrderSettings
  - ItemArrivalJournalHeadersV2
  - OpenSalesPriceJournalLine
  - WarehouseLocations
  - WarehouseAisles
  - CDSInventoryOnHandEntries
  - PurchaseAgreementLine
  - JobCardProductionJournalEntries
  - AssetMaintenanceFunctionalLocation
  - ProductSpecificOrderSettingsV3
  - SalesAgreementLines
  - ServiceAgreementLines
  - ItemCoverageSettings
  - DefaultPlannedTransferOrderItemCoverageSettings
  - ProductSpecificOrderSettingsV2
  - RetailStore
  - SupplyForecastEntries
  - QualityOrderHeaders
  - RetailCallCenter
  - PurchaseAgreementLinesV2
  - RouteCardProductionJournalEntries
  - OperationalSite
  - ExternallyLocatedWarehouseCustomer
  - ExternallyLocatedWarehouseVendor
  - MainRefillingWarehouse
  - MainRefillingAssignedWarehouses
  - TransitWarehouse
  - TransitAssignedWarehouses
  - QuarantineWarehouse
  - QuarantineAssignedWarehouses
  - InventCountingReasonCodePolicy
  - OpenPurchaseLineDiscountJournalLine
  - OpenSalesPostageDiscountJournalLine
  - RetailServiceCategory
  - OpenSalesLineDiscountJournalLine
  - ProductionPickingListJournalEntries
AXPath: Warehouse management\Setup\Warehouse\Warehouses
Operations:
  - Read
  - Create
  - Update
  - Delete
weight: 1
---

Navigation path: Warehouse management\Setup\Warehouse\Warehouses

| Data entity AOT name  | Entity name (DMF) | Public collection name (OData) | Support OData | Support DMF | Category | ReadOnly |
| --------------------- | ----------------- | ------------------------------ | ------------- | ----------- | -------- | -------- |
| InventWarehouseEntity | Warehouses        | Warehouses                     | Yes           | Yes         | Master   | No       |

`Warehouses` Entity is allowed to operate with warehowses in D365FO.

## Key

- dataAreaId
- WarehouseId

## Fields

| Field name                                              | Value example          | Description    |
| ------------------------------------------------------- | ---------------------- | -------------- |
| dataAreaId                                              | "usmf"                 | Company        |
| (*)__WarehouseId__                                      | "21"                   | WarehouseId    |
| PrimaryAddressLatitude                                  | 0                      |                |
| AreLaborStandardsAllowed                                | "No"                   |                |
| AreAdvancedWarehouseManagementProcessesEnabled          | "No"                   |                |
| WarehouseSpecificDefaultInventoryStatusId               | ""                     |                |
| ArePickingListsShipmentSpecificOnly                     | "No"                   |                |
| RawMaterialPickingInventoryIssueStatus                  | "Pick"                 |                |
| QuarantineWarehouseId                                   | "28"                   |                |
| InventoryCountingReasonCodePolicyName                   | ""                     |                |
| WillWarehouseLocationIdIncludeShelfIdByDefault          | "No"                   |                |
| ArePickingListsDeliveryModeSpecific                     | "No"                   |                |
| FormattedPrimaryAddress                                 | ""                     |                |
| WillManualLoadReleaseReserveInventory                   | "No"                   |                |
| WarehouseLocationIdBinIdFormat                          | ""                     |                |
| AreItemsCoveragePlannedManually                         | "No"                   |                |
| WillShippingCancellationDecrementLoadQuanity            | "No"                   |                |
| AutoUpdateShipmentRule                                  | "OnQuantityDecrease"   |                |
| PrimaryAddressStateId                                   | ""                     |                |
| WarehouseLocationIdRackIdFormat                         | ""                     |                |
| PrimaryAddressBuildingCompliment                        | ""                     |                |
| PrimaryAddressLocationSalesTaxGroupCode                 | ""                     |                |
| IsRefilledFromMainWarehouse                             | "No"                   |                |
| PrimaryAddressCountryRegionId                           | ""                     |                |
| WillWarehouseLocationIdIncludeRackIdByDefault           | "No"                   |                |
| RetailStoreQuantityAllocationReplenismentRuleWeight     | 0                      |                |
| IsPalletMovementDuringCycleCountingAllowed              | "No"                   |                |
| WarehouseLocationIdShelfIdFormat                        | ""                     |                |
| PrimaryAddressCountyId                                  | ""                     |                |
| MasterPlanningWorkCalendardId                           | ""                     |                |
| WarehouseWorkProcessingPolicyName                       | ""                     |                |
| ExternallyLocatedWarehouseVendorAccountNumber           | ""                     |                |
| MainRefillingWarehouseId                                | ""                     |                |
| WillAutomaticLoadReleaseReserveInventory                | "No"                   |                |
| IsPhysicalNegativeRetailStoreInventoryAllowed           | "No"                   |                |
| PrimaryAddressLocationRoles                             | ""                     |                |
| ExternallyLocatedWarehouseCustomerAccountNumber         | ""                     |                |
| PrimaryAddressDistrictName                              | ""                     |                |
| IsRetailStoreWarehouse                                  | "No"                   |                |
| IsBillOfLadingPrintingBeforeShipmentConfirmationEnabled | "No"                   |                |
| WarehouseName                                           | "Site2-Dist.&Shipping" | Warehouse name |
| WillInventoryStatusChangeRemoveBlocking                 | "No"                   |                |
| PrimaryAddressStreet                                    | ""                     |                |
| DefaultContainerTypeId                                  | ""                     |                |
| IdentificationGroup                                     | "OwnStock"             |                |
| PrimaryAddressDescription                               | ""                     |                |
| WillProductionBOMsReserveWarehouseLevelOnly             | "No"                   |                |
| PrimaryAddressCity                                      | ""                     |                |
| PrimaryAddressStreetNumber                              | ""                     |                |
| PrimaryAddressStreetInKana                              | ""                     |                |
| PrimaryAddressZipCode                                   | ""                     |                |
| WillWarehouseLocationIdIncludeBinIdByDefault            | "No"                   |                |
| MaximumBatchPickingListQuantity                         | 0                      |                |
| AreWarehouseLocationCheckDigitsUnique                   | "No"                   |                |
| IsPrimaryAddressAssigned                                | "No"                   |                |
| ShouldWarehouseLocationIdIncludeAisleId                 | "No"                   |                |
| InventoryStatusChangeReservationRemovalLevel            | "None"                 |                |
| PrimaryAddressTimeZone                                  | null                   |                |
| TransitWarehouseId                                      | "29"                   |                |
| PrimaryAddressCityInKana                                | ""                     |                |
| WarehouseType                                           | "Standard"             |                |
| IsFinancialNegativeRetailStoreInventoryAllowed          | "No"                   |                |
| MaximumPickingListLineQuantity                          | 0                      |                |
| WarehouseReleaseReservationRequirementRule              | "NotApplicable"        |                |
| WillOrderReleasingConsolidateShipments                  | "No"                   |                |
| PrimaryAddressPostBox                                   | ""                     |                |
| PrimaryAddressLongitude                                 | 0                      |                |
| (*)__OperationalSiteId__                                | "2"                    | Warehouse site |
| IsFallbackWarehouse                                     | "Yes"                  |                |
| UnderdeliveryWarehouseId                                | ""                     |                |
| GoodsInTransitWarehouseId                               | ""                     |                |

## Postman

### Request for get data

`GET: https://{{base_url}}/data/Warehouses(dataAreaId='usmf',WarehouseId='21')`

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
    "@odata.context": "{{base_url}}/data\$metadata#Warehouses/$entity",
    "@odata.etag": "W/\"JzAsMjI1NjU0MjE0MzA7MCwwOzAsNTYzNzE0NDgyOTswLDA7MCwwJw==\"",
    "dataAreaId": "usmf",
    "WarehouseId": "21",
    "PrimaryAddressLatitude": 0,
    "AreLaborStandardsAllowed": "No",
    "AreAdvancedWarehouseManagementProcessesEnabled": "No",
    "WarehouseSpecificDefaultInventoryStatusId": "",
    "ArePickingListsShipmentSpecificOnly": "No",
    "RawMaterialPickingInventoryIssueStatus": "Pick",
    "QuarantineWarehouseId": "28",
    "InventoryCountingReasonCodePolicyName": "",
    "WillWarehouseLocationIdIncludeShelfIdByDefault": "No",
    "ArePickingListsDeliveryModeSpecific": "No",
    "FormattedPrimaryAddress": "",
    "WillManualLoadReleaseReserveInventory": "No",
    "WarehouseLocationIdBinIdFormat": "",
    "AreItemsCoveragePlannedManually": "No",
    "WillShippingCancellationDecrementLoadQuanity": "No",
    "AutoUpdateShipmentRule": "OnQuantityDecrease",
    "PrimaryAddressStateId": "",
    "WarehouseLocationIdRackIdFormat": "",
    "PrimaryAddressBuildingCompliment": "",
    "PrimaryAddressLocationSalesTaxGroupCode": "",
    "IsRefilledFromMainWarehouse": "No",
    "PrimaryAddressCountryRegionId": "",
    "WillWarehouseLocationIdIncludeRackIdByDefault": "No",
    "RetailStoreQuantityAllocationReplenismentRuleWeight": 0,
    "IsPalletMovementDuringCycleCountingAllowed": "No",
    "WarehouseLocationIdShelfIdFormat": "",
    "PrimaryAddressCountyId": "",
    "MasterPlanningWorkCalendardId": "",
    "WarehouseWorkProcessingPolicyName": "",
    "ExternallyLocatedWarehouseVendorAccountNumber": "",
    "MainRefillingWarehouseId": "",
    "WillAutomaticLoadReleaseReserveInventory": "No",
    "IsPhysicalNegativeRetailStoreInventoryAllowed": "No",
    "PrimaryAddressLocationRoles": "",
    "ExternallyLocatedWarehouseCustomerAccountNumber": "",
    "PrimaryAddressDistrictName": "",
    "IsRetailStoreWarehouse": "No",
    "IsBillOfLadingPrintingBeforeShipmentConfirmationEnabled": "No",
    "WarehouseName": "Site 2 - Dist. & Shipping",
    "WillInventoryStatusChangeRemoveBlocking": "No",
    "PrimaryAddressStreet": "",
    "DefaultContainerTypeId": "",
    "IdentificationGroup": "OwnStock",
    "PrimaryAddressDescription": "",
    "WillProductionBOMsReserveWarehouseLevelOnly": "No",
    "PrimaryAddressCity": "",
    "PrimaryAddressStreetNumber": "",
    "PrimaryAddressStreetInKana": "",
    "PrimaryAddressZipCode": "",
    "WillWarehouseLocationIdIncludeBinIdByDefault": "No",
    "MaximumBatchPickingListQuantity": 0,
    "AreWarehouseLocationCheckDigitsUnique": "No",
    "IsPrimaryAddressAssigned": "No",
    "ShouldWarehouseLocationIdIncludeAisleId": "No",
    "InventoryStatusChangeReservationRemovalLevel": "None",
    "PrimaryAddressTimeZone": null,
    "TransitWarehouseId": "29",
    "PrimaryAddressCityInKana": "",
    "WarehouseType": "Standard",
    "IsFinancialNegativeRetailStoreInventoryAllowed": "No",
    "MaximumPickingListLineQuantity": 0,
    "WarehouseReleaseReservationRequirementRule": "NotApplicable",
    "WillOrderReleasingConsolidateShipments": "No",
    "PrimaryAddressPostBox": "",
    "PrimaryAddressLongitude": 0,
    "OperationalSiteId": "2",
    "IsFallbackWarehouse": "Yes",
    "UnderdeliveryWarehouseId": "",
    "GoodsInTransitWarehouseId": ""
}
```

</details>

### Request for create data

`POST : https://{{base_url}}/data/Warehouses`

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
    "@odata.type":"#Microsoft.Dynamics.DataEntities.Warehouse",
    "WarehouseId": "AAA-01",
    "OperationalSiteId": "2"
}
```

</details>

<details>
<summary>
Response:

</summary>

```json
{
    "@odata.context": "https://{{base_url}}/data/$metadata#Warehouses/$entity",
    "@odata.etag": "W/\"JzEsNjg3MTk0ODI4NzE7MSw2ODcxOTQ4Mjc5NDswLDA7MCwwOzAsMCc=\"",
    "dataAreaId": "usmf",
    "WarehouseId": "AAA-01",
    "PrimaryAddressLatitude": 0,
    "AreLaborStandardsAllowed": "No",
    "AreAdvancedWarehouseManagementProcessesEnabled": "No",
    "WarehouseSpecificDefaultInventoryStatusId": "",
    "ArePickingListsShipmentSpecificOnly": "No",
    "RawMaterialPickingInventoryIssueStatus": "Pick",
    "QuarantineWarehouseId": "",
    "InventoryCountingReasonCodePolicyName": "",
    "WillWarehouseLocationIdIncludeShelfIdByDefault": "No",
    "ArePickingListsDeliveryModeSpecific": "No",
    "FormattedPrimaryAddress": "",
    "WillManualLoadReleaseReserveInventory": "No",
    "WarehouseLocationIdBinIdFormat": "",
    "AreItemsCoveragePlannedManually": "No",
    "WillShippingCancellationDecrementLoadQuanity": "No",
    "AutoUpdateShipmentRule": "OnQuantityDecrease",
    "PrimaryAddressStateId": "",
    "WarehouseLocationIdRackIdFormat": "",
    "PrimaryAddressBuildingCompliment": "",
    "PrimaryAddressLocationSalesTaxGroupCode": "",
    "IsRefilledFromMainWarehouse": "No",
    "PrimaryAddressCountryRegionId": "",
    "WillWarehouseLocationIdIncludeRackIdByDefault": "No",
    "RetailStoreQuantityAllocationReplenismentRuleWeight": 0,
    "IsPalletMovementDuringCycleCountingAllowed": "No",
    "WarehouseLocationIdShelfIdFormat": "",
    "PrimaryAddressCountyId": "",
    "MasterPlanningWorkCalendardId": "",
    "WarehouseWorkProcessingPolicyName": "",
    "ExternallyLocatedWarehouseVendorAccountNumber": "",
    "MainRefillingWarehouseId": "",
    "WillAutomaticLoadReleaseReserveInventory": "No",
    "IsPhysicalNegativeRetailStoreInventoryAllowed": "No",
    "PrimaryAddressLocationRoles": "",
    "ExternallyLocatedWarehouseCustomerAccountNumber": "",
    "PrimaryAddressDistrictName": "",
    "IsRetailStoreWarehouse": "No",
    "IsBillOfLadingPrintingBeforeShipmentConfirmationEnabled": "No",
    "WarehouseName": "",
    "WillInventoryStatusChangeRemoveBlocking": "No",
    "PrimaryAddressStreet": "",
    "DefaultContainerTypeId": "",
    "IdentificationGroup": null,
    "PrimaryAddressDescription": "",
    "WillProductionBOMsReserveWarehouseLevelOnly": "No",
    "PrimaryAddressCity": "",
    "PrimaryAddressStreetNumber": "",
    "PrimaryAddressStreetInKana": "",
    "PrimaryAddressZipCode": "",
    "WillWarehouseLocationIdIncludeBinIdByDefault": "No",
    "MaximumBatchPickingListQuantity": 0,
    "AreWarehouseLocationCheckDigitsUnique": "No",
    "IsPrimaryAddressAssigned": "No",
    "ShouldWarehouseLocationIdIncludeAisleId": "No",
    "InventoryStatusChangeReservationRemovalLevel": "None",
    "PrimaryAddressTimeZone": null,
    "TransitWarehouseId": "",
    "PrimaryAddressCityInKana": "",
    "WarehouseType": "Standard",
    "IsFinancialNegativeRetailStoreInventoryAllowed": "No",
    "MaximumPickingListLineQuantity": 0,
    "WarehouseReleaseReservationRequirementRule": "NotApplicable",
    "WillOrderReleasingConsolidateShipments": "No",
    "PrimaryAddressPostBox": "",
    "PrimaryAddressLongitude": 0,
    "OperationalSiteId": "2",
    "IsFallbackWarehouse": "No",
    "UnderdeliveryWarehouseId": "",
    "GoodsInTransitWarehouseId": ""
}
```

</details>

### Request for update data

`PATCH : https://{{base_url}}/data/Warehouses(dataAreaId='usmf',WarehouseId='AAA-01')`

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
    "@odata.type": "#Microsoft.Dynamics.DataEntities.Warehouse",
    "TransitWarehouseId": "29"
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

`DELETE : https://{{base_url}}/data/Warehouses(dataAreaId='usmf',WarehouseId='AAA-01')`

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
| SalesAgreementConfirmationLines                 | SalesAgreementConfirmationLineEntity             | Sales agreement confirmation lines            | SalesAgreementConfirmationLines          | Yes           | Yes         | Document     | Yes      |       |
| RebateAndDeductionsAgreementHeaders             | TAMRebateAndDeductionsAgreementHeaderEntity      | Rebate and deductions agreement header        | RebateAndDeductionAgreementHeaders       | Yes           | Yes         | Document     | No       |       |
| ReportAsFinishedProductionJournalEntries        | ProdReportAsFinishedProductionJournalEntryEntity | Report as finished production journal entries | ReportAsFinishedProductionJournalEntries | Yes           | Yes         | Document     | No       |       |
| ItemArrivalJournalLinesV2                       | WMSItemArrivalJournalLineV2Entity                | Item arrival journal lines V2                 | ItemArrivalJournalLinesV2                | Yes           | Yes         | Document     | No       |       |
| OpenPurchasePriceJournalLine                    | PurchOpenPurchasePriceJournalLineEntity          | Open purchase price journal lines             | OpenPurchasePriceJournalLines            | Yes           | Yes         | Master       | No       |       |
| ProductDefaultOrderSettings                     | InventProductDefaultOrderSettingsEntity          | Default order settings                        | ProductDefaultOrderSettings              | Yes           | Yes         | Master       | No       |       |
| ItemArrivalJournalHeadersV2                     | WMSItemArrivalJournalHeaderV2Entity              | Item arrival journal headers V2               | ItemArrivalJournalHeadersV2              | Yes           | Yes         | Document     | No       |       |
| OpenSalesPriceJournalLine                       | SalesOpenSalesPriceJournalLineEntity             | Open sales price journal lines                | OpenSalesPriceJournalLines               | Yes           | Yes         | Master       | No       |       |
| WarehouseLocations                              | WMSWarehouseLocationEntity                       | Warehouse locations                           | WarehouseLocations                       | Yes           | Yes         | Master       | No       |       |
| WarehouseAisles                                 | WMSWarehouseAisleEntity                          | Inventory aisle                               | WarehouseAisles                          | Yes           | Yes         | Master       | No       |       |
| CDSInventoryOnHandEntries                       | InventCDSInventoryOnHandEntryEntity              | CDS inventory on-hand entries                 | CDSInventoryOnHandEntries                | Yes           | Yes         | Transactions | No       |       |
| PurchaseAgreementLine                           | PurchPurchaseAgreementLineEntity                 | Purchase agreement lines                      | PurchaseAgreementLines                   | Yes           | Yes         | Document     | No       |       |
| JobCardProductionJournalEntries                 | ProdJobCardProductionJournalEntryEntity          | Job card production journal entries           | JobCardProductionJournalEntries          | Yes           | Yes         | Document     | No       |       |
| AssetMaintenanceFunctionalLocation              | EntAssetMaintenanceFunctionalLocationEntity      | Asset management functional locations         | AssetMaintenanceFunctionalLocations      | Yes           | Yes         | Master       | No       |       |
| ProductSpecificOrderSettingsV3                  | InventProductSpecificOrderSettingsV3Entity       | Product default order settings V3             | ProductSpecificOrderSettingsV3           | Yes           | Yes         | Master       | No       |       |
| SalesAgreementLines                             | SalesAgreementLineEntity                         | Sales agreement lines                         | SalesAgreementLines                      | Yes           | Yes         | Document     | No       |       |
| ServiceAgreementLines                           | SMAServiceAgreementLineEntity                    | Service agreement lines                       | ServiceAgreementLines                    | Yes           | Yes         | Document     | No       |       |
| ItemCoverageSettings                            | ReqItemCoverageSettingsEntity                    | Item coverage                                 | ItemCoverageSettings                     | Yes           | Yes         | Master       | No       |       |
| DefaultPlannedTransferOrderItemCoverageSettings | InventProductSpecificOrderSettingsV2Entity       | Product default order settings V2             | ProductSpecificOrderSettingsV2           | Yes           | Yes         | Master       | No       |       |
| ProductSpecificOrderSettingsV2                  | InventProductSpecificOrderSettingsV2Entity       | Product default order settings V2             | ProductSpecificOrderSettingsV2           | Yes           | Yes         | Master       | No       |       |
| RetailStore                                     | RetailStoreEntity                                | Stores                                        | RetailStores                             | Yes           | Yes         | Master       | No       |       |
| SupplyForecastEntries                           | ForecastSupplyForecastEntryEntity                | Supply forecast entries                       | SupplyForecastEntries                    | Yes           | Yes         | Document     | Yes      |       |
| QualityOrderHeaders                             | InventQualityOrderHeaderEntity                   | Quality orders                                | QualityOrderHeaders                      | Yes           | Yes         | Document     | No       |       |
| RetailCallCenter                                | RetailCallCenterEntity                           | Call center channel                           | RetailCallCenters                        | Yes           | Yes         | Master       | No       |       |
| PurchaseAgreementLinesV2                        | PurchPurchaseAgreementConfirmationLineEntity     | Purchase agreement confirmation lines         | PurchaseAgreementConfirmationLines       | Yes           | Yes         | Document     | Yes      |       |
| RouteCardProductionJournalEntries               | ProdRouteCardProductionJournalEntryEntity        | Route card production journal entries         | RouteCardProductionJournalEntries        | Yes           | Yes         | Document     | No       |       |
| OperationalSite                                 | InventOperationalSiteEntity                      | Sites                                         | OperationalSites                         | Yes           | Yes         | Master       | No       |       |
| ExternallyLocatedWarehouseCustomer              | CustCustomerV3Entity                             | Customers V3                                  | CustomersV3                              | Yes           | Yes         | Master       | No       |       |
| ExternallyLocatedWarehouseVendor                | VendVendorV2Entity                               | Vendors V2                                    | VendorsV2                                | Yes           | Yes         | Master       | No       |       |
| MainRefillingWarehouse                          | InventWarehouseEntity                            | Warehouses                                    | Warehouses                               | Yes           | Yes         | Master       | No       |       |
| MainRefillingAssignedWarehouses                 | InventWarehouseEntity                            | Warehouses                                    | Warehouses                               | Yes           | Yes         | Master       | No       |       |
| TransitWarehouse                                | InventWarehouseEntity                            | Warehouses                                    | Warehouses                               | Yes           | Yes         | Master       | No       |       |
| TransitAssignedWarehouses                       | InventWarehouseEntity                            | Warehouses                                    | Warehouses                               | Yes           | Yes         | Master       | No       |       |
| QuarantineWarehouse                             | InventWarehouseEntity                            | Warehouses                                    | Warehouses                               | Yes           | Yes         | Master       | No       |       |
| QuarantineAssignedWarehouses                    | InventWarehouseEntity                            | Warehouses                                    | Warehouses                               | Yes           | Yes         | Master       | No       |       |
| InventCountingReasonCodePolicy                  | InventInventoryCountingReasonCodePolicyEntity    | Inventory counting reason code policies       | InventCountingReasonCodePolicies         | Yes           | Yes         | Master       | No       |       |
| OpenPurchaseLineDiscountJournalLine             | PurchOpenPurchaseLineDiscountJournalLineEntity   | Open purchase line discount journal lines     | OpenPurchaseLineDiscountJournalLines     | Yes           | Yes         | Master       | No       |       |
| OpenSalesPostageDiscountJournalLine             | MCROpenSalesPostageDiscountJournalLineEntity     | Open sales postage discount journal lines     | OpenSalesPostageDiscountJournalLines     | Yes           | Yes         | Master       | No       |       |
| RetailServiceCategory                           | RetailServiceCategoryEntity                      | Service category                              | RetailServiceCategories                  | Yes           | Yes         | Master       | No       |       |
| OpenSalesLineDiscountJournalLine                | SalesOpenSalesLineDiscountJournalLineEntity      | Open sales line discount journal lines        | OpenSalesLineDiscountJournalLines        | Yes           | Yes         | Master       | No       |       |
| ProductionPickingListJournalEntries             | ProdProductionPickingListJournalEntryEntity      | Production picking list journal entries       | ProductionPickingListJournalEntries      | Yes           | Yes         | Document     | No       |       |

### Relation usecase

Request `GET: https://{{base_url}}/data/Warehouses(dataAreaId='usmf',WarehouseId='21')/ProductSpecificOrderSettingsV2?$count=true` return 7 records from Orders setings where Warehouse equals '21'

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
    "@odata.context": "https://{{base_url}}/data/$metadata#ProductSpecificOrderSettingsV2",
    "@odata.count": 7,
    "value": [
        {
            "@odata.etag": "W/\"JzE5MzY1MDU0MzMsNTI1NjU0NDcwODI7NjYzMjg1NzIsNTI1NjU0NDcwODI7MzgwMDI1MjcxLDUyNTY1NDQ3MDgyJw==\"",
            "dataAreaId": "usmf",
            "ItemNumber": "T0020",
            "OperationalSiteId": "",
            "ProductConfigurationId": "",
            "ProductColorId": "",
            "ProductSizeId": "",
            "ProductStyleId": "",
            "IsInventorySiteMandatory": "No",
            "InventoryATPBackwardDemandTimeFenceDays": 2,
            "IsSalesSiteMandatory": "No",
            "SalesATPBackwardSupplyTimeFenceDays": 2,
            "SalesOrderPromisingMethod": "ATPPlusIssueMargin",
            "ProcurementLeadTimeDays": 0,
            "AreInventoryDefaultOrderSettingsOverridden": "No",
            "IsInventoryWarehouseMandatory": "No",
            "IsSalesWarehouseMandatory": "No",
            "SalesATPBackwardDemandTimeFenceDays": 2,
            "SalesATPDelayedDemandOffsetDays": 1,
            "IsProcurementSiteMandatory": "No",
            "ProcurementWarehouseId": "21",
            "AreSalesDefaultOrderSettingsOverridden": "No",
            "AreProcurementDefaultOrderSettingsOverridden": "No",
            "InventoryATPDelayedSupplyOffsetDays": 1,
            "IsSalesATPIncludingPlannedOrders": true,
            "InventoryWarehouseId": "21",
            "MaximumSalesOrderQuantity": 0,
            "StandardProcurementOrderQuantity": 0,
            "MinimumInventoryOrderQuantity": 0,
            "MinimumSalesOrderQuantity": 0,
            "IsInventoryProcessingStopped": "No",
            "InventoryLeadTimeDays": 0,
            "StandardSalesOrderQuantity": 0,
            "StandardInventoryOrderQuantity": 0,
            "SalesATPTimeFenceDays": 30,
            "InventoryATPBackwardSupplyTimeFenceDays": 2,
            "IsDefaultProcurementStorageDimensionOverridden": "No",
            "ProcurementSiteId": "2",
            "InventoryATPDelayedDemandOffsetDays": 1,
            "SalesLeadTimeDays": 5,
            "IsInventoryUsingWorkingDays": "No",
            "OrderSettingsRank": 0,
            "IsDefaultSalesStorageDimensionOverridden": "No",
            "ProcurementQuantityMultiples": 0,
            "InventorySiteId": "2",
            "MinimumProcurementOrderQuantity": 0,
            "SalesQuantityMultiples": 0,
            "IsSalesLeadTimeOverridden": "No",
            "IsProcurementUsingWorkingDays": "No",
            "MaximumProcurementOrderQuantity": 0,
            "IsProcurementProcessingstopped": "No",
            "MaximumInventoryOrderQuantity": 0,
            "SalesWarehouseId": "21",
            "IsSalesProcessingStopped": "No",
            "InventoryQuantityMultiples": 0,
            "SalesATPDelayedSupplyOffsetDays": 1,
            "IsDefaultInventoryStorageDimensionOverridden": "No",
            "IsProcurementWarehouseMandatory": "No",
            "SalesSiteId": "2",
            "InventoryOrderPromisingMethod": "ATPPlusIssueMargin",
            "IsInventoryATPIncludingPlannedOrders": true,
            "InventoryATPTimeFenceDays": 30
        },
        {
            "@odata.etag": "W/\"JzE4MDQxNjIxODgsMjI1NjU0MjI0MDI7OTkyNjE2MTI2LDIyNTY1NDIyNDAyOzU1MDI3MzU0NSwyMjU2NTQyMjQwMic=\"",
            "dataAreaId": "usmf",
            "ItemNumber": "T0001",
            "OperationalSiteId": "",
            "ProductConfigurationId": "",
            "ProductColorId": "",
            "ProductSizeId": "",
            "ProductStyleId": "",
            "IsInventorySiteMandatory": "No",
            "InventoryATPBackwardDemandTimeFenceDays": 2,
            "IsSalesSiteMandatory": "No",
            "SalesATPBackwardSupplyTimeFenceDays": 5,
            "SalesOrderPromisingMethod": "ATPPlusIssueMargin",
            "ProcurementLeadTimeDays": 1,
            "AreInventoryDefaultOrderSettingsOverridden": "No",
            "IsInventoryWarehouseMandatory": "No",
            "IsSalesWarehouseMandatory": "No",
            "SalesATPBackwardDemandTimeFenceDays": 5,
            "SalesATPDelayedDemandOffsetDays": 1,
            "IsProcurementSiteMandatory": "No",
            "ProcurementWarehouseId": "21",
            "AreSalesDefaultOrderSettingsOverridden": "Yes",
            "AreProcurementDefaultOrderSettingsOverridden": "No",
            "InventoryATPDelayedSupplyOffsetDays": 1,
            "IsSalesATPIncludingPlannedOrders": true,
            "InventoryWarehouseId": "21",
            "MaximumSalesOrderQuantity": 0,
            "StandardProcurementOrderQuantity": 0,
            "MinimumInventoryOrderQuantity": 0,
            "MinimumSalesOrderQuantity": 0,
            "IsInventoryProcessingStopped": "No",
            "InventoryLeadTimeDays": 0,
            "StandardSalesOrderQuantity": 0,
            "StandardInventoryOrderQuantity": 0,
            "SalesATPTimeFenceDays": 1,
            "InventoryATPBackwardSupplyTimeFenceDays": 2,
            "IsDefaultProcurementStorageDimensionOverridden": "No",
            "ProcurementSiteId": "2",
            "InventoryATPDelayedDemandOffsetDays": 1,
            "SalesLeadTimeDays": 0,
            "IsInventoryUsingWorkingDays": "No",
            "OrderSettingsRank": 0,
            "IsDefaultSalesStorageDimensionOverridden": "No",
            "ProcurementQuantityMultiples": 0,
            "InventorySiteId": "2",
            "MinimumProcurementOrderQuantity": 0,
            "SalesQuantityMultiples": 0,
            "IsSalesLeadTimeOverridden": "No",
            "IsProcurementUsingWorkingDays": "No",
            "MaximumProcurementOrderQuantity": 0,
            "IsProcurementProcessingstopped": "No",
            "MaximumInventoryOrderQuantity": 0,
            "SalesWarehouseId": "21",
            "IsSalesProcessingStopped": "No",
            "InventoryQuantityMultiples": 0,
            "SalesATPDelayedSupplyOffsetDays": 1,
            "IsDefaultInventoryStorageDimensionOverridden": "No",
            "IsProcurementWarehouseMandatory": "No",
            "SalesSiteId": "2",
            "InventoryOrderPromisingMethod": "ATPPlusIssueMargin",
            "IsInventoryATPIncludingPlannedOrders": true,
            "InventoryATPTimeFenceDays": 30
        },
        {
            "@odata.etag": "W/\"JzkwNjc0NzA5NiwyMjU2NTQyMjQwNDsxOTEzMDM0Nzg2LDIyNTY1NDIyNDA0OzgyNDg5NzA4OSwyMjU2NTQyMjQwNCc=\"",
            "dataAreaId": "usmf",
            "ItemNumber": "T0002",
            "OperationalSiteId": "",
            "ProductConfigurationId": "",
            "ProductColorId": "",
            "ProductSizeId": "",
            "ProductStyleId": "",
            "IsInventorySiteMandatory": "No",
            "InventoryATPBackwardDemandTimeFenceDays": 2,
            "IsSalesSiteMandatory": "No",
            "SalesATPBackwardSupplyTimeFenceDays": 5,
            "SalesOrderPromisingMethod": "ATPPlusIssueMargin",
            "ProcurementLeadTimeDays": 42,
            "AreInventoryDefaultOrderSettingsOverridden": "No",
            "IsInventoryWarehouseMandatory": "No",
            "IsSalesWarehouseMandatory": "No",
            "SalesATPBackwardDemandTimeFenceDays": 5,
            "SalesATPDelayedDemandOffsetDays": 1,
            "IsProcurementSiteMandatory": "No",
            "ProcurementWarehouseId": "21",
            "AreSalesDefaultOrderSettingsOverridden": "Yes",
            "AreProcurementDefaultOrderSettingsOverridden": "No",
            "InventoryATPDelayedSupplyOffsetDays": 1,
            "IsSalesATPIncludingPlannedOrders": true,
            "InventoryWarehouseId": "21",
            "MaximumSalesOrderQuantity": 0,
            "StandardProcurementOrderQuantity": 0,
            "MinimumInventoryOrderQuantity": 0,
            "MinimumSalesOrderQuantity": 0,
            "IsInventoryProcessingStopped": "No",
            "InventoryLeadTimeDays": 0,
            "StandardSalesOrderQuantity": 0,
            "StandardInventoryOrderQuantity": 0,
            "SalesATPTimeFenceDays": 42,
            "InventoryATPBackwardSupplyTimeFenceDays": 2,
            "IsDefaultProcurementStorageDimensionOverridden": "No",
            "ProcurementSiteId": "2",
            "InventoryATPDelayedDemandOffsetDays": 1,
            "SalesLeadTimeDays": 0,
            "IsInventoryUsingWorkingDays": "No",
            "OrderSettingsRank": 0,
            "IsDefaultSalesStorageDimensionOverridden": "No",
            "ProcurementQuantityMultiples": 0,
            "InventorySiteId": "2",
            "MinimumProcurementOrderQuantity": 0,
            "SalesQuantityMultiples": 0,
            "IsSalesLeadTimeOverridden": "No",
            "IsProcurementUsingWorkingDays": "No",
            "MaximumProcurementOrderQuantity": 0,
            "IsProcurementProcessingstopped": "No",
            "MaximumInventoryOrderQuantity": 0,
            "SalesWarehouseId": "21",
            "IsSalesProcessingStopped": "No",
            "InventoryQuantityMultiples": 0,
            "SalesATPDelayedSupplyOffsetDays": 1,
            "IsDefaultInventoryStorageDimensionOverridden": "No",
            "IsProcurementWarehouseMandatory": "No",
            "SalesSiteId": "2",
            "InventoryOrderPromisingMethod": "ATPPlusIssueMargin",
            "IsInventoryATPIncludingPlannedOrders": true,
            "InventoryATPTimeFenceDays": 30
        },
        {
            "@odata.etag": "W/\"JzE4MzMyNDIwMzksMjI1NjU0MjI0MDY7NDk0MDMwMTc5LDIyNTY1NDIyNDA2OzE0ODQ5OTM4OTksMjI1NjU0MjI0MDYn\"",
            "dataAreaId": "usmf",
            "ItemNumber": "T0003",
            "OperationalSiteId": "",
            "ProductConfigurationId": "",
            "ProductColorId": "",
            "ProductSizeId": "",
            "ProductStyleId": "",
            "IsInventorySiteMandatory": "No",
            "InventoryATPBackwardDemandTimeFenceDays": 2,
            "IsSalesSiteMandatory": "No",
            "SalesATPBackwardSupplyTimeFenceDays": 5,
            "SalesOrderPromisingMethod": "ATPPlusIssueMargin",
            "ProcurementLeadTimeDays": 42,
            "AreInventoryDefaultOrderSettingsOverridden": "No",
            "IsInventoryWarehouseMandatory": "No",
            "IsSalesWarehouseMandatory": "No",
            "SalesATPBackwardDemandTimeFenceDays": 5,
            "SalesATPDelayedDemandOffsetDays": 1,
            "IsProcurementSiteMandatory": "No",
            "ProcurementWarehouseId": "21",
            "AreSalesDefaultOrderSettingsOverridden": "Yes",
            "AreProcurementDefaultOrderSettingsOverridden": "No",
            "InventoryATPDelayedSupplyOffsetDays": 1,
            "IsSalesATPIncludingPlannedOrders": true,
            "InventoryWarehouseId": "21",
            "MaximumSalesOrderQuantity": 0,
            "StandardProcurementOrderQuantity": 0,
            "MinimumInventoryOrderQuantity": 0,
            "MinimumSalesOrderQuantity": 0,
            "IsInventoryProcessingStopped": "No",
            "InventoryLeadTimeDays": 0,
            "StandardSalesOrderQuantity": 0,
            "StandardInventoryOrderQuantity": 0,
            "SalesATPTimeFenceDays": 42,
            "InventoryATPBackwardSupplyTimeFenceDays": 2,
            "IsDefaultProcurementStorageDimensionOverridden": "No",
            "ProcurementSiteId": "2",
            "InventoryATPDelayedDemandOffsetDays": 1,
            "SalesLeadTimeDays": 0,
            "IsInventoryUsingWorkingDays": "No",
            "OrderSettingsRank": 0,
            "IsDefaultSalesStorageDimensionOverridden": "No",
            "ProcurementQuantityMultiples": 0,
            "InventorySiteId": "2",
            "MinimumProcurementOrderQuantity": 0,
            "SalesQuantityMultiples": 0,
            "IsSalesLeadTimeOverridden": "No",
            "IsProcurementUsingWorkingDays": "No",
            "MaximumProcurementOrderQuantity": 0,
            "IsProcurementProcessingstopped": "No",
            "MaximumInventoryOrderQuantity": 0,
            "SalesWarehouseId": "21",
            "IsSalesProcessingStopped": "No",
            "InventoryQuantityMultiples": 0,
            "SalesATPDelayedSupplyOffsetDays": 1,
            "IsDefaultInventoryStorageDimensionOverridden": "No",
            "IsProcurementWarehouseMandatory": "No",
            "SalesSiteId": "2",
            "InventoryOrderPromisingMethod": "ATPPlusIssueMargin",
            "IsInventoryATPIncludingPlannedOrders": true,
            "InventoryATPTimeFenceDays": 30
        },
        {
            "@odata.etag": "W/\"Jzc4OTc1NDM1OCwyMjU2NTQyMTYyODsxNDg3MjAyODczLDIyNTY1NDIxNjI4OzIyNTc4ODgxMCwyMjU2NTQyMTYyOCc=\"",
            "dataAreaId": "usmf",
            "ItemNumber": "T0004",
            "OperationalSiteId": "",
            "ProductConfigurationId": "",
            "ProductColorId": "",
            "ProductSizeId": "",
            "ProductStyleId": "",
            "IsInventorySiteMandatory": "No",
            "InventoryATPBackwardDemandTimeFenceDays": 2,
            "IsSalesSiteMandatory": "No",
            "SalesATPBackwardSupplyTimeFenceDays": 5,
            "SalesOrderPromisingMethod": "ATPPlusIssueMargin",
            "ProcurementLeadTimeDays": 42,
            "AreInventoryDefaultOrderSettingsOverridden": "No",
            "IsInventoryWarehouseMandatory": "No",
            "IsSalesWarehouseMandatory": "No",
            "SalesATPBackwardDemandTimeFenceDays": 5,
            "SalesATPDelayedDemandOffsetDays": 1,
            "IsProcurementSiteMandatory": "No",
            "ProcurementWarehouseId": "21",
            "AreSalesDefaultOrderSettingsOverridden": "Yes",
            "AreProcurementDefaultOrderSettingsOverridden": "No",
            "InventoryATPDelayedSupplyOffsetDays": 1,
            "IsSalesATPIncludingPlannedOrders": true,
            "InventoryWarehouseId": "21",
            "MaximumSalesOrderQuantity": 0,
            "StandardProcurementOrderQuantity": 0,
            "MinimumInventoryOrderQuantity": 0,
            "MinimumSalesOrderQuantity": 0,
            "IsInventoryProcessingStopped": "No",
            "InventoryLeadTimeDays": 0,
            "StandardSalesOrderQuantity": 0,
            "StandardInventoryOrderQuantity": 0,
            "SalesATPTimeFenceDays": 42,
            "InventoryATPBackwardSupplyTimeFenceDays": 2,
            "IsDefaultProcurementStorageDimensionOverridden": "No",
            "ProcurementSiteId": "2",
            "InventoryATPDelayedDemandOffsetDays": 1,
            "SalesLeadTimeDays": 0,
            "IsInventoryUsingWorkingDays": "No",
            "OrderSettingsRank": 0,
            "IsDefaultSalesStorageDimensionOverridden": "No",
            "ProcurementQuantityMultiples": 0,
            "InventorySiteId": "2",
            "MinimumProcurementOrderQuantity": 0,
            "SalesQuantityMultiples": 0,
            "IsSalesLeadTimeOverridden": "No",
            "IsProcurementUsingWorkingDays": "No",
            "MaximumProcurementOrderQuantity": 0,
            "IsProcurementProcessingstopped": "No",
            "MaximumInventoryOrderQuantity": 0,
            "SalesWarehouseId": "21",
            "IsSalesProcessingStopped": "No",
            "InventoryQuantityMultiples": 0,
            "SalesATPDelayedSupplyOffsetDays": 1,
            "IsDefaultInventoryStorageDimensionOverridden": "No",
            "IsProcurementWarehouseMandatory": "No",
            "SalesSiteId": "2",
            "InventoryOrderPromisingMethod": "ATPPlusIssueMargin",
            "IsInventoryATPIncludingPlannedOrders": true,
            "InventoryATPTimeFenceDays": 30
        },
        {
            "@odata.etag": "W/\"JzU2NjkzMzE3MiwyMjU2NTQyMTYzMDs5MzY0MDc2MzYsMjI1NjU0MjE2MzA7MjA1MDcwNTQ4NCwyMjU2NTQyMTYzMCc=\"",
            "dataAreaId": "usmf",
            "ItemNumber": "T0005",
            "OperationalSiteId": "",
            "ProductConfigurationId": "",
            "ProductColorId": "",
            "ProductSizeId": "",
            "ProductStyleId": "",
            "IsInventorySiteMandatory": "No",
            "InventoryATPBackwardDemandTimeFenceDays": 2,
            "IsSalesSiteMandatory": "No",
            "SalesATPBackwardSupplyTimeFenceDays": 5,
            "SalesOrderPromisingMethod": "ATPPlusIssueMargin",
            "ProcurementLeadTimeDays": 42,
            "AreInventoryDefaultOrderSettingsOverridden": "No",
            "IsInventoryWarehouseMandatory": "No",
            "IsSalesWarehouseMandatory": "No",
            "SalesATPBackwardDemandTimeFenceDays": 5,
            "SalesATPDelayedDemandOffsetDays": 1,
            "IsProcurementSiteMandatory": "No",
            "ProcurementWarehouseId": "21",
            "AreSalesDefaultOrderSettingsOverridden": "Yes",
            "AreProcurementDefaultOrderSettingsOverridden": "No",
            "InventoryATPDelayedSupplyOffsetDays": 1,
            "IsSalesATPIncludingPlannedOrders": true,
            "InventoryWarehouseId": "21",
            "MaximumSalesOrderQuantity": 0,
            "StandardProcurementOrderQuantity": 0,
            "MinimumInventoryOrderQuantity": 0,
            "MinimumSalesOrderQuantity": 0,
            "IsInventoryProcessingStopped": "No",
            "InventoryLeadTimeDays": 0,
            "StandardSalesOrderQuantity": 0,
            "StandardInventoryOrderQuantity": 0,
            "SalesATPTimeFenceDays": 42,
            "InventoryATPBackwardSupplyTimeFenceDays": 2,
            "IsDefaultProcurementStorageDimensionOverridden": "No",
            "ProcurementSiteId": "2",
            "InventoryATPDelayedDemandOffsetDays": 1,
            "SalesLeadTimeDays": 0,
            "IsInventoryUsingWorkingDays": "No",
            "OrderSettingsRank": 0,
            "IsDefaultSalesStorageDimensionOverridden": "No",
            "ProcurementQuantityMultiples": 0,
            "InventorySiteId": "2",
            "MinimumProcurementOrderQuantity": 0,
            "SalesQuantityMultiples": 0,
            "IsSalesLeadTimeOverridden": "No",
            "IsProcurementUsingWorkingDays": "No",
            "MaximumProcurementOrderQuantity": 0,
            "IsProcurementProcessingstopped": "No",
            "MaximumInventoryOrderQuantity": 0,
            "SalesWarehouseId": "21",
            "IsSalesProcessingStopped": "No",
            "InventoryQuantityMultiples": 0,
            "SalesATPDelayedSupplyOffsetDays": 1,
            "IsDefaultInventoryStorageDimensionOverridden": "No",
            "IsProcurementWarehouseMandatory": "No",
            "SalesSiteId": "2",
            "InventoryOrderPromisingMethod": "ATPPlusIssueMargin",
            "IsInventoryATPIncludingPlannedOrders": true,
            "InventoryATPTimeFenceDays": 30
        },
        {
            "@odata.etag": "W/\"JzEyMjU5NzI5NzEsNjg3MTk0Nzg1ODM7MTAyMzY0NzE0MCw2ODcxOTQ3ODU4MzsxMjM1NDM4MTYsNjg3MTk0Nzg1ODMn\"",
            "dataAreaId": "usmf",
            "ItemNumber": "D0007",
            "OperationalSiteId": "2",
            "ProductConfigurationId": "",
            "ProductColorId": "",
            "ProductSizeId": "",
            "ProductStyleId": "",
            "IsInventorySiteMandatory": "No",
            "InventoryATPBackwardDemandTimeFenceDays": 2,
            "IsSalesSiteMandatory": "No",
            "SalesATPBackwardSupplyTimeFenceDays": 2,
            "SalesOrderPromisingMethod": "ATPPlusIssueMargin",
            "ProcurementLeadTimeDays": 0,
            "AreInventoryDefaultOrderSettingsOverridden": "No",
            "IsInventoryWarehouseMandatory": "No",
            "IsSalesWarehouseMandatory": "No",
            "SalesATPBackwardDemandTimeFenceDays": 2,
            "SalesATPDelayedDemandOffsetDays": 1,
            "IsProcurementSiteMandatory": "No",
            "ProcurementWarehouseId": "21",
            "AreSalesDefaultOrderSettingsOverridden": "No",
            "AreProcurementDefaultOrderSettingsOverridden": "No",
            "InventoryATPDelayedSupplyOffsetDays": 1,
            "IsSalesATPIncludingPlannedOrders": true,
            "InventoryWarehouseId": "21",
            "MaximumSalesOrderQuantity": 0,
            "StandardProcurementOrderQuantity": 0,
            "MinimumInventoryOrderQuantity": 0,
            "MinimumSalesOrderQuantity": 0,
            "IsInventoryProcessingStopped": "No",
            "InventoryLeadTimeDays": 3,
            "StandardSalesOrderQuantity": 0,
            "StandardInventoryOrderQuantity": 0,
            "SalesATPTimeFenceDays": 30,
            "InventoryATPBackwardSupplyTimeFenceDays": 2,
            "IsDefaultProcurementStorageDimensionOverridden": "Yes",
            "ProcurementSiteId": "",
            "InventoryATPDelayedDemandOffsetDays": 1,
            "SalesLeadTimeDays": 5,
            "IsInventoryUsingWorkingDays": "Yes",
            "OrderSettingsRank": 10,
            "IsDefaultSalesStorageDimensionOverridden": "Yes",
            "ProcurementQuantityMultiples": 0,
            "InventorySiteId": "",
            "MinimumProcurementOrderQuantity": 0,
            "SalesQuantityMultiples": 0,
            "IsSalesLeadTimeOverridden": "No",
            "IsProcurementUsingWorkingDays": "No",
            "MaximumProcurementOrderQuantity": 0,
            "IsProcurementProcessingstopped": "No",
            "MaximumInventoryOrderQuantity": 0,
            "SalesWarehouseId": "21",
            "IsSalesProcessingStopped": "No",
            "InventoryQuantityMultiples": 0,
            "SalesATPDelayedSupplyOffsetDays": 1,
            "IsDefaultInventoryStorageDimensionOverridden": "Yes",
            "IsProcurementWarehouseMandatory": "No",
            "SalesSiteId": "",
            "InventoryOrderPromisingMethod": "ATPPlusIssueMargin",
            "IsInventoryATPIncludingPlannedOrders": true,
            "InventoryATPTimeFenceDays": 30
        }
    ]
}
```

</details>
