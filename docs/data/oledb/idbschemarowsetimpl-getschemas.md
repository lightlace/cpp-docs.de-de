---
title: "IDBSchemaRowsetImpl::GetSchemas"
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
  - "ATL::IDBSchemaRowsetImpl::GetSchemas"
  - "GetSchemas"
  - "IDBSchemaRowsetImpl<SessionClass>::GetSchemas"
  - "ATL.IDBSchemaRowsetImpl.GetSchemas"
  - "ATL::IDBSchemaRowsetImpl<SessionClass>::GetSchemas"
  - "IDBSchemaRowsetImpl.GetSchemas"
  - "IDBSchemaRowsetImpl::GetSchemas"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetSchemas-Methode"
ms.assetid: fbe725a6-3acd-45f8-bcaf-10a6c1239cd2
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# IDBSchemaRowsetImpl::GetSchemas
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt eine Liste der Schemarowsets zurück, auf die [IDBSchemaRowsetImpl::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md) zugreifen kann.  
  
## Syntax  
  
```  
  
STDMETHOD  
( GetSchema s )(  
   ULONG *   
pcSchemas  
,  
   GUID **   
prgSchemas  
,  
   ULONG**   
prgRest  
);  
  
```  
  
#### Parameter  
 *pcSchemas*  
 \[out\] Ein Zeiger auf eine **ULONG**, die mit der Anzahl von Schemas gefüllt ist.  
  
 *prgSchemas*  
 \[out\] Ein Zeiger auf ein Array von GUIDs, das mit einem Zeiger auf ein Array von Schemarowset\-GUIDs gefüllt ist.  
  
 *prgRest*  
 \[out\] Ein Zeiger auf ein Array von **ULONG**s, das mit dem Einschränkungsarray gefüllt werden soll.  
  
## Hinweise  
 Diese Methode gibt ein Array aller Schemarowsets zurück, die vom Anbieter unterstützt werden. Siehe [IDBSchemaRowset::GetSchemas](https://msdn.microsoft.com/en-us/library/ms719605.aspx) im [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Für die Implementierung dieser Funktion muss der Benutzer eine Schemazuordnung in der Sitzungsklasse haben. Mithilfe der Schemazuordnungsinformationen antwortet die Funktion dann mit dem Array von GUIDs für die Schemas in der Zuordnung. Dies stellt die Schemas dar, die vom Anbieter unterstützt werden.  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [IDBSchemaRowsetImpl\-Klasse](../../data/oledb/idbschemarowsetimpl-class.md)   
 [IDBSchemaRowsetImpl Class Members](assetId:///e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [IDBSchemaRowsetImpl::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md)   
 [IDBSchemaRowset::GetRowset](https://msdn.microsoft.com/en-us/library/ms722634.aspx)   
 [Schemarowset\-Klassen und Typedef\-Klassen](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)