---
title: "CComObjectRoot Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CComObjectRoot"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComObjectRoot class"
ms.assetid: f8797c38-6e73-4f67-85c2-71654cffa8eb
caps.latest.revision: 17
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# CComObjectRoot Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Typedef von [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) ist auf dem Standard Threadingmodell des Servers auf Vorlagen basierende.  
  
## Syntax  
  
```  
  
typedef CComObjectRootEx<CComObjectThreadModel> CComObjectRoot;  
  
```  
  
## Hinweise  
 `CComObjectRoot` ist `typedef` von [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) vorlagenbasierten auf dem Standard Threadingmodell des Servers.  Daher verweist [CComObjectThreadModel](../Topic/CComObjectThreadModel.md) entweder [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) oder [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md).  
  
 `CComObjectRootEx` Handleobjektverweis\-Anzahlverwaltung für nicht aggregiertes und zusammengesetzte Objekte.  Sie enthält die Objektverweisanzahl, wenn das Objekt nicht aggregiert wird, und enthält den Zeiger des äußeren Unbekannten an, wenn das Objekt aggregiert wird.  Für zusammengesetzte Objekte können `CComObjectRootEx`\-Methoden verwendet werden, um den Fehler des inneren Objekts dem Konstrukt zu behandeln, und das äußere Objekt vom Löschen, wenn innere Schnittstellen freigegeben werden oder das innere Objekt zu schützen wird gelöscht.  
  
## Anforderungen  
 **Header:** atlcom.h  
  
## Siehe auch  
 [CComObjectRootEx Class Members](assetId:///e3ce9c3d-9c8e-4fe5-b682-8e56740a0164)   
 [CComObjectRootEx Class](../../atl/reference/ccomobjectrootex-class.md)   
 [CComAggObject Class](../../atl/reference/ccomaggobject-class.md)   
 [CComObject Class](../../atl/reference/ccomobject-class.md)   
 [CComPolyObject Class](../../atl/reference/ccompolyobject-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)