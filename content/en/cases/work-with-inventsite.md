---
title: "Works with inventory site (Sites)"
date: 2021-01-13
tags:
  - InventSite
tables:
  - InventSite
Entities: 
  - OperationalSites
AXPath: Warehouse management\Setup\Warehouse\Sites
Operations:
  - Read
  - Create
  - Update
  - Delete
weight: 1
---

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
    "@odata.context": "https://dev10plus15065719449a0027478devaos.cloudax.dynamics.com/data/$metadata#OperationalSites/$entity",
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
    "@odata.context": "https://dev10plus15065719449a0027478devaos.cloudax.dynamics.com/data/$metadata#OperationalSites/$entity",
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
