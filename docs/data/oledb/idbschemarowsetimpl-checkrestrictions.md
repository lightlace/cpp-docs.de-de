---
title: "IDBSchemaRowsetImpl::CheckRestrictions | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CheckRestrictions"
  - "IDBSchemaRowsetImpl::CheckRestrictions"
  - "IDBSchemaRowsetImpl.CheckRestrictions"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CheckRestrictions-Methode"
ms.assetid: 3c9d77d2-0e4b-48fa-80db-d735da19f1cf
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# IDBSchemaRowsetImpl::CheckRestrictions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Überprüft die Gültigkeit von Einschränkungen für ein Schemarowset.  
  
## Syntax  
  
```  
  
HRESULT CheckRestrictions(  
   REFGUID   
rguidSchema  
,  
   ULONG   
cRestrictions  
,  
   const VARIANT   
rgRestrictions  
[]  
);  
  
```  
  
#### Parameter  
 `rguidSchema`  
 \[in\] Ein Verweis auf die angeforderte Schemarowset\-GUID \(z. B. `DBSCHEMA_TABLES`\).  
  
 `cRestrictions`  
 \[in\] Die Anzahl der Einschränkungen, die der Consumer für das Schemarowset übergeben hat.  
  
 `rgRestrictions`  
 \[in\] Ein Längenarray von *cRestrictions* von festzulegenden Einschränkungswerten. Weitere Informationen finden Sie in der Beschreibung des `rgRestrictions`\-Parameters in [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md).  
  
## Hinweise  
 Verwenden Sie `CheckRestrictions`, um die Gültigkeit von Einschränkungen für ein Schemarowset zu überprüfen. Es überprüft die Einschränkungen für `DBSCHEMA_TABLES`\-, **DBSCHEMA\_COLUMNS**\- und **DBSCHEMA\_PROVIDER\_TYPES** \-Schemarowsets. Rufen Sie es auf, um zu ermitteln, ob der Aufruf eines Consumers von **IDBSchemaRowset::GetRowset** richtig ist. Wenn Sie andere als die oben aufgeführten Schemarowsets unterstützen möchten, sollten Sie Ihre eigene Funktion zum Ausführen dieser Aufgabe erstellen.  
  
 `CheckRestrictions` bestimmt, ob der Consumer [GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md) mit der richtigen Einschränkung und dem richtigen Einschränkungstyp aufruft \(z. B. `VT_BSTR` für eine Zeichenfolge\), die der Anbieter unterstützt. Es bestimmt außerdem, ob die richtige Anzahl von Einschränkungen unterstützt werden. Standardmäßig fragt `CheckRestrictions` den Anbieter mittels des Aufrufs von [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md), welche Einschränkungen für ein angegebenes Rowset unterstützt werden. Es vergleicht dann die Einschränkungen vom Consumer mit den vom Anbieter unterstützten, wobei der Vergleich entweder erfolgreich ist oder fehlschlägt.  
  
 Weitere Informationen zu Schemarowsets finden Sie unter [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) in der *OLE DB\-Programmierreferenz* im [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [IDBSchemaRowsetImpl\-Klasse](../../data/oledb/idbschemarowsetimpl-class.md)   
 [IDBSchemaRowsetImpl Class Members](assetId:///e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [Schemarowset\-Klassen und Typedef\-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)