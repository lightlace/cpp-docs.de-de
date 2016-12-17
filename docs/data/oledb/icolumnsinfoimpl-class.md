---
title: "IColumnsInfoImpl-Klasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "ATL.IColumnsInfoImpl<T>"
  - "ATL::IColumnsInfoImpl"
  - "IColumnsInfoImpl"
  - "ATL.IColumnsInfoImpl"
  - "ATL::IColumnsInfoImpl<T>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IColumnsInfoImpl-Klasse"
ms.assetid: ba74c1c5-2eda-4452-8b57-84919fa0d066
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# IColumnsInfoImpl-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine Implementierung der [IColumnsInfo](https://msdn.microsoft.com/en-us/library/ms724541.aspx)\-Schnittstelle bereit.  
  
## Syntax  
  
```  
template <class T>  
class ATL_NO_VTABLE IColumnsInfoImpl :   
   public IColumnsInfo,    
   public CDBIDOps  
```  
  
#### Parameter  
 `T`  
 Die Klasse, von `IColumnsInfoImpl` abgeleitet.  
  
## Member  
  
### Methoden  
  
|||  
|-|-|  
|[GetColumnInfo](../../data/oledb/icolumnsinfoimpl-getcolumninfo.md)|Gibt die von den meisten Consumern benötigten Spaltenmetadaten zurück.|  
|[MapColumnIDs](../../data/oledb/icolumnsinfoimpl-mapcolumnids.md)|Gibt ein Array von Ordnungszahlen der Spalten in einem Rowset zurück, die mit den angegebenen Spalten\-IDs gekennzeichnet sind.|  
  
## Hinweise  
 Eine erforderliche Schnittstelle auf Rowsets und Befehlen.  Um das Verhalten der `IColumnsInfo` \- Implementierung des Anbieters zu ändern, müssen Sie die Anbieterspaltenzuordnung ändern.  
  
## Anforderungen  
 **Header:**  atldb.h  
  
## Siehe auch  
 [OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)