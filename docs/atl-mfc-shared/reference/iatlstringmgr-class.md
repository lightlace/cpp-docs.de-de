---
title: "IAtlStringMgr Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IAtlStringMgr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IAtlStringMgr class"
  - "Speicher, Verwalten"
  - "shared classes, IAtlStringMgr"
ms.assetid: 722f0346-a770-4aa7-8f94-177be8dba823
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# IAtlStringMgr Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt die Schnittstelle für einen `CStringT` Speicher\-Manager dar.  
  
## Syntax  
  
```  
  
__interface IAtlStringMgr  
  
```  
  
## Mitglieder  
  
### Methoden  
  
|||  
|-|-|  
|[Ordnen Sie zu](../Topic/IAtlStringMgr::Allocate.md)|Rufen Sie diese Methode auf, um eine neue Zeichenfolgendatenstruktur zuzuordnen.|  
|[Klon](../Topic/IAtlStringMgr::Clone.md)|Rufen Sie diese Methode auf, um einen Zeiger auf einen neuen Zeichenfolgenmanager zur Verwendung mit einer anderen Instanz von `CSimpleStringT` zurückzugeben.|  
|[Frei](../Topic/IAtlStringMgr::Free.md)|Rufen Sie diese Methode auf, um eine Zeichenfolgendatenstruktur freizugeben.|  
|[GetNilString](../Topic/IAtlStringMgr::GetNilString.md)|Gibt einen Zeiger auf `CStringData`\-Objekt zurück, das von Nullketteobjekte verwendet wird.|  
|[Teilen Sie neu zu](../Topic/IAtlStringMgr::Reallocate.md)|Rufen Sie diese Methode auf, um eine Zeichenfolgendatenstruktur neu belegen.|  
  
## Hinweise  
 Diese Schnittstelle verwaltet Speicher, der durch die MFC\-unabhängigen Zeichenfolgenklassen verwendet wird; wie [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md), [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) und [CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md).  
  
 Sie können diese Klasse verwenden, um einen benutzerdefinierten Speicher\-Manager für die benutzerdefinierte Zeichenfolgenklasse zu implementieren.  Weitere Informationen finden Sie unter [Speicherverwaltung und CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
## Anforderungen  
 **Header:** atlsimpstr.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)