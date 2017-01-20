---
title: "CSimpleRow-Klasse"
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
  - "CSimpleRow"
  - "ATL::CSimpleRow"
  - "ATL.CSimpleRow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleRow-Klasse"
ms.assetid: 06d9621d-60cc-4508-8b0c-528d1b1a809b
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# CSimpleRow-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine Standardimplementierung für das Zeilenhandle bereit, das in der [IRowsetImpl](../../data/oledb/irowsetimpl-class.md)\-Klasse verwendet wird.  
  
## Syntax  
  
```  
class CSimpleRow  
```  
  
## Member  
  
### Methoden  
  
|||  
|-|-|  
|[AddRefRow](../../data/oledb/csimplerow-addrefrow.md)|Fügt einem vorhandenen Zeilenhandle einen Verweiszähler hinzu.|  
|[Compare](../../data/oledb/csimplerow-compare.md)|Vergleicht zwei Zeilen, um zu sehen, wenn sie dieselbe Zeile zugreifen.|  
|[CSimpleRow](../../data/oledb/csimplerow-csimplerow.md)|Der \-Konstruktor.|  
|[ReleaseRow](../../data/oledb/csimplerow-releaserow.md)|Gibt Zeilen frei.|  
  
### Datenmember  
  
|||  
|-|-|  
|[m\_dwRef](../../data/oledb/csimplerow-m-dwref.md)|Verweiszähler einem vorhandenen Zeilenhandle.|  
|[m\_iRowset](../../data/oledb/csimplerow-m-irowset.md)|Ein Index in das Rowset, das den Cursor darstellt.|  
  
## Hinweise  
 Ein Zeilenhandle ist logisch ein eindeutiges Tag für eine Ergebniszeile.  `IRowsetImpl` erstellt einen neuen `CSimpleRow` für jede Zeile, die in [IRowsetImpl::GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) angefordert wird.  `CSimpleRow` kann über eine eigene Implementierung des Zeilenhandles ersetzt auch werden, da es ein Standardvorlagenargument zu `IRowsetImpl` ist.  Die einzige Anforderung dem Ersetzen der Klasse ist, die Ersatzklasse einen Konstruktor bereitstellen werden, der einen einzelnen Parameter des Typs **LONG** akzeptiert.  
  
## Anforderungen  
 **Header:**  atldb.h  
  
## Siehe auch  
 [OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)   
 [IRowsetImpl\-Klasse](../../data/oledb/irowsetimpl-class.md)