---
title: CDefaultElementTraits-Klasse
ms.date: 11/04/2016
f1_keywords:
- CDefaultElementTraits
- atlcoll/ATL::CDefaultElementTraits
helpviewer_keywords:
- CDefaultElementTraits class
ms.assetid: ac5ee610-7957-4b7c-92b6-38ff72e4118e
ms.openlocfilehash: 2cf93adc5b78a8fa31a603d58f0e4dbe1efb0d6d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50494687"
---
# <a name="cdefaultelementtraits-class"></a>CDefaultElementTraits-Klasse

Diese Klasse stellt die Standardmethoden und -Funktionen, damit eine Auflistungsklasse.

## <a name="syntax"></a>Syntax

```
template <typename T>
class CDefaultElementTraits : public CElementTraitsBase<T>,
    public CDefaultHashTraits<T>,
    public CDefaultCompareTraits<T>
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Der Typ der Daten in der Auflistung gespeichert werden.

## <a name="remarks"></a>Hinweise

Diese Klasse stellt statische Standard-Funktionen und Methoden für das Verschieben, kopieren, vergleichen und hashing in ein Klassenobjekt Auflistung gespeicherten Elementen an. Diese Klasse abgeleitet wird, seine Funktionen und Methoden aus [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md), [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md), und [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md), und wird verwendet, indem [ CElementTraits](../../atl/reference/celementtraits-class.md), [CPrimitiveElementTraits](../../atl/reference/cprimitiveelementtraits-class.md), und [CHeapPtrElementTraits](../../atl/reference/cheapptrelementtraits-class.md).

Weitere Informationen finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Anforderungen

**Header:** atlcoll.h

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)
