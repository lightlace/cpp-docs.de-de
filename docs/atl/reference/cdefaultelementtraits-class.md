---
title: "CDefaultElementTraits Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CDefaultElementTraits<T>"
  - "ATL.CDefaultElementTraits"
  - "ATL::CDefaultElementTraits"
  - "ATL.CDefaultElementTraits<T>"
  - "CDefaultElementTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDefaultElementTraits class"
ms.assetid: ac5ee610-7957-4b7c-92b6-38ff72e4118e
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# CDefaultElementTraits Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt Standardmethoden und Funktionen für eine Auflistungsklasse bereit.  
  
## Syntax  
  
```  
  
      template<  
   typename T  
>  
class CDefaultElementTraits : public CElementTraitsBase< T >,  
   public CDefaultHashTraits< T >,  
   public CDefaultCompareTraits< T >  
```  
  
#### Parameter  
 `T`  
 Der Typ von den in der Auflistung gespeichert werden, Daten.  
  
## Hinweise  
 Diese Klasse bietet Standardverhalten statische Funktionen und Methoden zum Verschieben, Kopieren, Vergleichen und die hackenden Elemente, die in einer Auflistungsklasse gespeichert werden, ein Objekt.  Diese Klasse wird die Funktionen und Methoden von [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md), von [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md) und von [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md) und von [CElementTraits](../../atl/reference/celementtraits-class.md), [CPrimitiveElementTraits](../../atl/reference/cprimitiveelementtraits-class.md) und [CHeapPtrElementTraits](../../atl/reference/cheapptrelementtraits-class.md) verwendet.  
  
 Weitere Informationen finden Sie unter [ATL\-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## Anforderungen  
 **Header:** atlcoll.h  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)