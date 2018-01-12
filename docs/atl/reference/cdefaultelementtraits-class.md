---
title: CDefaultElementTraits Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDefaultElementTraits
- atlcoll/ATL::CDefaultElementTraits
dev_langs: C++
helpviewer_keywords: CDefaultElementTraits class
ms.assetid: ac5ee610-7957-4b7c-92b6-38ff72e4118e
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bb6731913d10402016f2148e1ae7705a73e98944
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cdefaultelementtraits-class"></a>CDefaultElementTraits-Klasse
Diese Klasse stellt die Standardmethoden und Funktionen bereit, damit eine Auflistungsklasse.  
  
## <a name="syntax"></a>Syntax  
  
```
template <typename T>  
class CDefaultElementTraits : public CElementTraitsBase<T>,
    public CDefaultHashTraits<T>,
    public CDefaultCompareTraits<T>
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Typ der Daten in der Auflistung gespeichert werden.  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse bietet statische Standard-Funktionen und-Methoden für verschieben, kopieren, vergleichen und hashing ein Klassenobjekt Auflistung gespeicherten Elemente. Diese Klasse abgeleitet wird, seine Funktionen und Methoden von [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md), [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md), und [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md), und wird durch [ CElementTraits](../../atl/reference/celementtraits-class.md), [CPrimitiveElementTraits](../../atl/reference/cprimitiveelementtraits-class.md), und [CHeapPtrElementTraits](../../atl/reference/cheapptrelementtraits-class.md).  
  
 Weitere Informationen finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcoll.h  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../../atl/atl-class-overview.md)
