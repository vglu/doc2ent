---
weight: 1
title: "SalesTable"
---

# SalesTable description

@Label

@Help

@DeveloperDocumentation

@HumanDescription

## Table properties

| Property name | Property value |
| ------------- | -------------- |
| Label         | @sys222124     |
| Description   | @sys1112221    |

## Field list

| Field name               | Field type | EDT/Enum                  | Label                              | Help text                      | Mandatory |
| ------------------------ | ---------- | ------------------------- | ---------------------------------- | ------------------------------ | --------- |
| SalesId (link to field)  | String(20) | SalesIdBase (link to EDT) | Sales id (link to label file)      | Help text (link to label file) | yes       |
| CustId (link to field)   | String(20) | CustAccount (link to EDT) | Customer code (link to label file) | Help text (link to label file) | yes       |
| Currency (link to field) | String(20) | Currency (link to EDT)    | Currency code (link to label file) | Help text (link to label file) | yes       |
| ........................ | .......... | ......................... | .................................. | .............................. | ......... |

## Fields

SalesId

| Property | Value                     |
| -------- | ------------------------- |
| Label    | Sales id (link to label)  |
| EDT      | SalesIdBase (link to EDT) |
| ........ | ......................... |

CustId

| Property | Value                         |
| -------- | ----------------------------- |
| Label    | Customer code (link to label) |
| EDT      | CustAccount (link to EDT)     |
| ........ | .........................     |

## Field group

### Identifications

| Field                           |
| ------------------------------- |
| SalesId (link to field SalesId) |

### AutoLookup

| Field                            |
| -------------------------------- |
| SalesId (link to field SalesId)  |
| CustId (link to field SalesId)   |
| Currency (link to field SalesId) |

## Delete actions

Action name

| Property      | Value   |
| ------------- | ------- |
| Delete action | Cascade |

## Indexes

### SalesLineIdx

| Property        | Value |
| --------------- | ----- |
| AllowDuplicates | No    |

Fields

| Field   | IncludedColumn | Tags |
| ------- | -------------- | ---- |
| SalesId | No             |
