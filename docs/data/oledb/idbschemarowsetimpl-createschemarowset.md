---
title: "IDBSchemaRowsetImpl::CreateSchemaRowset | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDBSchemaRowsetImpl::CreateSchemaRowset"
  - "ATL::IDBSchemaRowsetImpl::CreateSchemaRowset"
  - "CreateSchemaRowset"
  - "IDBSchemaRowsetImpl.CreateSchemaRowset"
  - "ATL.IDBSchemaRowsetImpl.CreateSchemaRowset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateSchemaRowset-Methode"
ms.assetid: ad3e3e4d-45b9-461c-b7b8-3af6843631b1
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IDBSchemaRowsetImpl::CreateSchemaRowset
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert eine COM\-Objekterstellerfunktion für das mit dem Vorlagenparameter angegebene Objekt.  
  
## Syntax  
  
```  
  
template < class   
SchemaRowsetClass  
 >  
HRESULT CreateSchemaRowset(  
   IUnknown *  
pUnkOuter  
,  
   ULONG   
cRestrictions  
,  
   const VARIANT   
rgRestrictions  
[],  
   REFIID   
riid  
,  
   ULONG   
cPropertySets  
,  
   DBPROPSET   
rgPropertySets  
[],  
   IUnknown**   
ppRowset  
,  
   SchemaRowsetClass*&   
pSchemaRowset  
);  
  
```  
  
#### Parameter  
 `pUnkOuter`  
 \[in\] Ein äußeres [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) beim Aggregieren, andernfalls **NULL**.  
  
 `cRestrictions`  
 \[in\] Die Anzahl der Einschränkungen für das Schemarowset.  
  
 `rgRestrictions`  
 \[in\] Ein Array auf das Rowset anzuwendender `cRestrictions`\-**VARIANT**en.  
  
 `riid`  
 \[in\] Die Schnittstelle zu [QueryInterface](../../atl/queryinterface.md) für die **IUnknown**\-Ausgabe.  
  
 `cPropertySets`  
 \[in\] Die Anzahl festzulegender Eigenschaftensätze.  
  
 `rgPropertySets`  
 \[in\] Ein Array von [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx)\-Strukturen, die die festzulegenden Eigenschaften angeben.  
  
 `ppRowset`  
 \[out\] Von `riid` angefordertes ausgehendes **IUnknown**. Dieses **IUnknown** ist eine Schnittstelle des Schemarowsetobjekts.  
  
 `pSchemaRowset`  
 \[out\] Ein Zeiger auf eine Instanz der Schemarowsetklasse. Dieser Parameter wird in der Regel nicht verwendet, kann jedoch verwendet werden, wenn Sie mehr Arbeit in das Schemarowset investieren müssen, bevor Sie es einem COM\-Objekt übergeben. Die Lebensdauer von `pSchemaRowset` ist an `ppRowset` gebunden.  
  
## Rückgabewert  
 Ein Standard `HRESULT`\-Wert.  
  
## Hinweise  
 Diese Funktion implementiert einen generischen Ersteller für alle Typen von Schemarowsets. In der Regel ruft der Benutzer diese Funktion nicht auf. Sie wird durch die Implementierung der Schemazuordnung aufgerufen.  
  
## Anforderungen  
 **Header:** „atldb.h“  
  
## Siehe auch  
 [IDBSchemaRowsetImpl\-Klasse](../../data/oledb/idbschemarowsetimpl-class.md)   
 [IDBSchemaRowsetImpl Class Members](assetId:///e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [SCHEMA\_ENTRY](../../data/oledb/schema-entry.md)   
 [Schemarowset\-Klassen und Typedef\-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)