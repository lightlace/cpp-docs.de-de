---
title: "IDBSchemaRowsetImpl::GetRowset | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::IDBSchemaRowsetImpl::GetRowset"
  - "ATL.IDBSchemaRowsetImpl.GetRowset"
  - "IDBSchemaRowsetImpl<SessionClass>::GetRowset"
  - "IDBSchemaRowsetImpl.GetRowset"
  - "IDBSchemaRowsetImpl::GetRowset"
  - "ATL::IDBSchemaRowsetImpl<SessionClass>::GetRowset"
  - "GetRowset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetRowset-Methode"
ms.assetid: 3ae28c22-e186-4a15-8591-b0192e784a6f
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# IDBSchemaRowsetImpl::GetRowset
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt ein Schemarowset zurück.  
  
## Syntax  
  
```  
  
STDMETHOD (GetRowset)(  
   IUnknown *  
pUnkOuter  
,  
   REFGUID   
rguidSchema  
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
   IUnknown **  
ppRowset  
);  
  
```  
  
#### Parameter  
 `pUnkOuter`  
 \[in\] Ein äußeres **IUnknown** beim Aggregieren, andernfalls **NULL**.  
  
 `rguidSchema`  
 \[in\] Ein Verweis auf die angeforderte Schemarowset\-GUID \(z. B. `DBSCHEMA_TABLES`\).  
  
 `cRestrictions`  
 \[in\] Die Anzahl der Einschränkungen, die auf das Schemarowset angewendet werden sollen.  
  
 `rgRestrictions`  
 \[in\] Ein Array von `cRestrictions` **VARIANT**s, die die Einschränkungen darstellen.  
  
 `riid`  
 \[in\] Die anzufordernde IID des neu erstellten Schemarowsets.  
  
 `cPropertySets`  
 \[in\] Die Anzahl der festzulegenden Eigenschaftensätze.  
  
 `rgPropertySets`  
 \[in\/out\] Ein Array von [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx)\-Strukturen, die für das neu erstellte Schemarowset festgelegt werden sollen.  
  
 `ppRowset`  
 \[out\] Ein Zeiger auf die angeforderte Schnittstelle für das neu erstellte Schemarowset.  
  
## Hinweise  
 Für diese Methode muss der Benutzer eine Schemazuordnung in der Sitzungsklasse haben. Mit den Schemazuordnungsinformationen erstellt `GetRowset` ein angegebenes Rowsetobjekt, wenn der `rguidSchema`\-Parameter mit einem der Zuordnungseintrags\-GUIDs identisch ist. Unter [SCHEMA\_ENTRY](../../data/oledb/schema-entry.md) finden Sie eine Beschreibung des Zuordnungseintrags.  
  
 Siehe [IDBSchemaRowset::GetRowset](https://msdn.microsoft.com/en-us/library/ms722634.aspx) im [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [IDBSchemaRowsetImpl\-Klasse](../../data/oledb/idbschemarowsetimpl-class.md)   
 [IDBSchemaRowsetImpl Class Members](assetId:///e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [IDBSchemaRowsetImpl::GetSchemas](../../data/oledb/idbschemarowsetimpl-getschemas.md)   
 [Schemarowset\-Klassen und Typedef\-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)