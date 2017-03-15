---
title: "CAccessorRowset-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CAccessorRowset"
  - "ATL.CAccessorRowset"
  - "ATL::CAccessorRowset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAccessorRowset-Klasse"
ms.assetid: bd4f58ed-cebf-4d43-8985-1e5fcbf06953
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# CAccessorRowset-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kapselt ein Rowset und seine zugeordneten Accessoren in einer einzelnen Klasse.  
  
## Syntax  
  
```  
template <   
   class TAccessor = CNoAccessor,    
   template <typename T> class TRowset = CRowset    
>  
class CAccessorRowset :   
   public TAccessor,    
   public TRowset<TAccessor>  
```  
  
#### Parameter  
 `TAccessor`  
 Eine Accessorklasse.  
  
 `TRowset`  
 Eine Rowsetklasse.  
  
## Member  
  
### Methoden  
  
|||  
|-|-|  
|[Binden](../../data/oledb/caccessorrowset-bind.md)|Stellt die Bindungen erstellt \(verwendet, wenn **bBind** als false in [CCommand::Open](../../data/oledb/ccommand-open.md) angegeben\).|  
|[CAccessorRowset](../../data/oledb/caccessorrowset-caccessorrowset.md)|Konstruktor.|  
|[Schließen](../../data/oledb/caccessorrowset-close.md)|Schließt das Rowset und alle Accessoren.|  
|[FreeRecordMemory](../../data/oledb/caccessorrowset-freerecordmemory.md)|Gibt alle Spalten im aktuellen Datensatz frei, die freigegeben werden müssen.|  
|[GetColumnInfo](../../data/oledb/caccessorrowset-getcolumninfo.md)|Implementiert [IColumnsInfo::GetColumnInfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx).|  
  
## Hinweise  
 `TAccessor`\-Klasse verwaltet den Accessor.  *TRowset*\-Klasse verwaltet das Rowset.  
  
## Anforderungen  
 **Header:**  atldbcli.h  
  
## Siehe auch  
 [OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)