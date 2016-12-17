---
title: "CElementTraits Class"
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
  - "ATL.CElementTraits<T>"
  - "ATL::CElementTraits"
  - "ATL.CElementTraits"
  - "ATL::CElementTraits<T>"
  - "CElementTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CElementTraits class"
ms.assetid: 496528e5-7f80-4b45-be0c-6f646feb43c5
caps.latest.revision: 17
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# CElementTraits Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse wird von Auflistungsklassen verwendet, um Methoden und Funktionen zum Verschieben, Kopieren, den Vergleich und Hashvorgänge bereitzustellen.  
  
## Syntax  
  
```  
  
      template<  
   typename T  
>  
class CElementTraits : public CDefaultElementTraits< T >  
```  
  
#### Parameter  
 `T`  
 Der Typ von den in der Auflistung gespeichert werden, Daten.  
  
## Hinweise  
 Diese Klasse bietet Standardverhalten statische Funktionen und Methoden zum Verschieben, Kopieren, Vergleichen und die hackenden Elemente, die in einer Auflistungsklasse gespeichert werden, ein Objekt.  `CElementTraits` wird als Standardanbieter dieser Vorgänge von der [CAtlArray](../../atl/reference/catlarray-class.md)\-Auflistungsklassen, [CAtlList](../../atl/reference/catllist-class.md), [CRBMap](../../atl/reference/crbmap-class.md), [CRBMultiMap](../../atl/reference/crbmultimap-class.md) und [CRBTree](../../atl/reference/crbtree-class.md) angegeben.  
  
 Die Standardimplementierungen genügt für einfache Datentypen, jedoch, wenn die Auflistungsklassen verwendet werden, um komplexere Objekte zu speichern, müssen die Funktionen und die Methoden von vom Benutzer bereitgestellte Implementierungen überschrieben werden.  
  
 Weitere Informationen finden Sie unter [ATL\-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## Anforderungen  
 **Header:** atlcoll.h  
  
## Siehe auch  
 [CDefaultElementTraits Class](../../atl/reference/cdefaultelementtraits-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)