---
title: "CAccessor-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CAccessor<T>"
  - "ATL::CAccessor"
  - "CAccessor"
  - "ATL::CAccessor<T>"
  - "ATL.CAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAccessor-Klasse"
ms.assetid: b2ba959f-a686-46f3-8837-176248aef748
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CAccessor-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt einen der Accessortypen dar.  
  
## Syntax  
  
```  
  
      template < class   
      T  
       >  
class CAccessor : public CAccessorBase, public T  
```  
  
#### Parameter  
 `T`  
 Die Benutzerdatensatz\-Klasse.  
  
## Hinweise  
 Sie wird verwendet, wenn ein Datensatz statisch an eine Datenquelle gebunden ist.  Der Datensatz enthält den Puffer.  Diese Klasse unterstützt mehrere Accessoren in einem Rowset.  
  
 Verwenden Sie diesen Accessortyp, wenn Ihnen die Struktur und den Typ der Datenbank zu kennen.  
  
 Wenn der Accessor Felder enthält, die auf Arbeitsspeicher zeigen \(wie `BSTR` oder einer Schnittstelle\) die freigegeben werden müssen, rufen Sie die Memberfunktion [CAccessorRowset::FreeRecordMemory](../../data/oledb/caccessorrowset-freerecordmemory.md) auf, bevor der nächste Datensatz gelesen wird.  
  
## Anforderungen  
 **Header:**  atldbcli.h  
  
## Siehe auch  
 [OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)