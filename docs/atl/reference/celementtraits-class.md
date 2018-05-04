---
title: CElementTraits Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CElementTraits
- atlcoll/ATL::CElementTraits
dev_langs:
- C++
helpviewer_keywords:
- CElementTraits class
ms.assetid: 496528e5-7f80-4b45-be0c-6f646feb43c5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c530622f096ef14d4eb3de56e5219e8f7df4f082
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="celementtraits-class"></a>CElementTraits-Klasse
Diese Klasse wird von Auflistungsklassen verschieben, kopieren, Vergleichsoperatoren und Hashvorgängen Methoden und Funktionen bereit.  
  
## <a name="syntax"></a>Syntax  
  
```
template<typename T>  
class CElementTraits : public CDefaultElementTraits<T>
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Typ der Daten in der Auflistung gespeichert werden.  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse bietet statische Standard-Funktionen und-Methoden für verschieben, kopieren, vergleichen und hashing ein Klassenobjekt Auflistung gespeicherten Elemente. `CElementTraits` wird als Standardanbieter dieser Vorgänge angegeben, indem die Auflistungsklassen [CAtlArray](../../atl/reference/catlarray-class.md), [CAtlList](../../atl/reference/catllist-class.md), [CRBMap](../../atl/reference/crbmap-class.md), [CRBMultiMap](../../atl/reference/crbmultimap-class.md), und [CRBTree](../../atl/reference/crbtree-class.md).  
  
 Die standardimplementierungen für einfache Datentypen reicht aus, aber wenn die Auflistungsklassen verwendet werden, um komplexere Objekte zu speichern, die Funktionen und Methoden müssen überschrieben werden vom Benutzer bereitgestellte Implementierungen.  
  
 Weitere Informationen finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcoll.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDefaultElementTraits-Klasse](../../atl/reference/cdefaultelementtraits-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
