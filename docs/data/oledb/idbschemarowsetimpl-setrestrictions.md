---
title: "IDBSchemaRowsetImpl::SetRestrictions"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "IDBSchemaRowsetImpl::SetRestrictions"
  - "SetRestrictions"
  - "IDBSchemaRowsetImpl.SetRestrictions"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetRestrictions-Methode"
ms.assetid: 707d5065-b853-4d38-9b67-3066b4d3b279
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# IDBSchemaRowsetImpl::SetRestrictions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt an, welche Einschränkungen Sie für ein bestimmtes Schemarowset unterstützen.  
  
## Syntax  
  
```  
  
void SetRestrictions(  
   ULONG   
cRestrictions  
,  
   GUID* /*   
rguidSchema  
*/,  
   ULONG*   
rgRestrictions  
);  
  
```  
  
#### Parameter  
 `cRestrictions`  
 \[in\] Die Anzahl der Einschränkungen im `rgRestrictions`\-Array und die Anzahl von GUIDs im `rguidSchema`\-Array.  
  
 `rguidSchema`  
 \[in\] Ein Array von GUIDs der Schemarowsets, für die Einschränkungen abgerufen werden sollen. Jedes Arrayelement enthält die GUID eines Schemarowsets \(z. B. `DBSCHEMA_TABLES`\).  
  
 `rgRestrictions`  
 \[in\] Ein Längenarray von `cRestrictions` von festzulegenden Einschränkungswerten. Jedes Element entspricht den Einschränkungen für das Schemarowset, das mit der GUID identifiziert wird. Wenn ein Schemarowset nicht vom Anbieter unterstützt wird, wird das Element auf 0 \(null\) festgelegt. Andernfalls enthält der **ULONG**\-Wert eine Bitmaske, die die Einschränkungen darstellt, die für dieses Schemarowset unterstützt werden. Weitere Informationen darüber, welche Einschränkungen einem bestimmten Schemarowset entsprechen, finden Sie in der Tabelle der Schemarowset\-GUIDs in [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) in der *OLE DB\-Programmierreferenz* im [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Hinweise  
 Das **IDBSchemaRowset**\-Objekt ruft `SetRestrictions` auf, um zu bestimmen, welche Einschränkungen Sie für ein bestimmtes Schemarowset unterstützen \(durch Aufruf von [GetSchemas](../../data/oledb/idbschemarowsetimpl-getschemas.md) über einen upcasted Zeiger\). Einschränkungen ermöglichen es Consumern, nur die übereinstimmende Zeilen abzurufen \(z. B. Suche nach allen Spalten in der Tabelle „MyTable“\). Einschränkungen sind optional, und wenn keine unterstützt werden \(Standardeinstellung\), werden immer alle Daten zurückgegeben.  
  
 Die standardmäßige Implementierung dieser Methode legt die `rgRestrictions`\-Arrayelemente auf 0 fest. Überschreiben Sie die Standardeinstellung in Ihrer Sitzungsklasse, um Einschränkungen festzulegen, die vom Standard abweichen.  
  
 Informationen zum Implementieren der Schemarowset\-Unterstützung finden Sie unter [Unterstützen von Schemarowsets](../../data/oledb/supporting-schema-rowsets.md).  
  
 Ein Beispiel für einen Anbieter, der Schemarowsets unterstützt, finden Sie unter dem Beispiel [UpdatePV](../../top/visual-cpp-samples.md).  
  
 Weitere Informationen zu Schemarowsets finden Sie unter [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) in der *OLE DB\-Programmierreferenz* im [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [IDBSchemaRowsetImpl\-Klasse](../../data/oledb/idbschemarowsetimpl-class.md)   
 [IDBSchemaRowsetImpl Class Members](assetId:///e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [Schemarowset\-Klassen und Typedef\-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)   
 [Unterstützen von Schemarowsets](../../data/oledb/supporting-schema-rowsets.md)   
 [UpdatePV](../../top/visual-cpp-samples.md)