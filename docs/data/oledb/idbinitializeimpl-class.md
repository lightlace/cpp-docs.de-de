---
title: "IDBInitializeImpl-Klasse"
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
  - "ATL.IDBInitializeImpl<T>"
  - "ATL::IDBInitializeImpl<T>"
  - "IDBInitializeImpl"
  - "ATL::IDBInitializeImpl"
  - "ATL.IDBInitializeImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDBInitializeImpl-Klasse"
ms.assetid: e4182f81-0443-44f5-a0d3-e7e075d6f883
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# IDBInitializeImpl-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine Implementierung für die [IDBInitialize](https://msdn.microsoft.com/en-us/library/ms713706.aspx)\-Schnittstelle bereit.  
  
## Syntax  
  
```  
template <class T>  
class ATL_NO_VTABLE IDBInitializeImpl : public IDBInitialize  
```  
  
#### Parameter  
 `T`  
 Die Klasse, von `IDBInitializeImpl` abgeleitet.  
  
## Member  
  
### Methoden  
  
|||  
|-|-|  
|[IDBInitializeImpl](../../data/oledb/idbinitializeimpl-idbinitializeimpl.md)|Der \-Konstruktor.|  
  
### Schnittstellenmethoden  
  
|||  
|-|-|  
|[Initialisieren](../../data/oledb/idbinitializeimpl-initialize.md)|Startet den Anbieter.|  
|[Deinitialisieren Sie](../../data/oledb/idbinitializeimpl-uninitialize.md)|Beendet den Anbieter.|  
  
### Datenmember  
  
|||  
|-|-|  
|[m\_dwStatus](../../data/oledb/idbinitializeimpl-m-dwstatus.md)|Datenquellenflags.|  
|[m\_pCUtlPropInfo](../../data/oledb/idbinitializeimpl-m-pcutlpropinfo.md)|Ein Zeiger zur Implementierung von DB\-Eigenschafteninformationen.|  
  
## Hinweise  
 Eine erforderliche Schnittstelle auf Datenquellenobjekte und optionale Schnittstelle auf Enumeratoren.  
  
## Anforderungen  
 **Header:**  atldb.h  
  
## Siehe auch  
 [OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)