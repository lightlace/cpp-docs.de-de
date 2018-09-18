---
title: CElementTraits-Klasse | Microsoft-Dokumentation
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
ms.openlocfilehash: 61cbd301d01d62c0d24f232703b53cebf411a082
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46021069"
---
# <a name="celementtraits-class"></a>CElementTraits-Klasse

Diese Klasse wird von Auflistungsklassen verwendet, verschieben, kopieren, Vergleich und Hashvorgängen Methoden und Funktionen bereit.

## <a name="syntax"></a>Syntax

```
template<typename T>
class CElementTraits : public CDefaultElementTraits<T>
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Der Typ der Daten in der Auflistung gespeichert werden.

## <a name="remarks"></a>Hinweise

Diese Klasse stellt statische Standard-Funktionen und Methoden für das Verschieben, kopieren, vergleichen und hashing in ein Klassenobjekt Auflistung gespeicherten Elementen an. `CElementTraits` als Standardanbieter dieser Vorgänge angegeben ist, durch die Auflistungsklassen [CAtlArray](../../atl/reference/catlarray-class.md), [CAtlList](../../atl/reference/catllist-class.md), [CRBMap](../../atl/reference/crbmap-class.md), [CRBMultiMap](../../atl/reference/crbmultimap-class.md), und [CRBTree](../../atl/reference/crbtree-class.md).

Die standardimplementierungen ist ausreichend für einfache Datentypen, aber wenn die Auflistungsklassen verwendet werden, um komplexe Objekte speichern, die Funktionen und Methoden müssen überschrieben werden von benutzerdefinierten Implementierungen.

Weitere Informationen finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Anforderungen

**Header:** atlcoll.h

## <a name="see-also"></a>Siehe auch

[CDefaultElementTraits-Klasse](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
