---
title: CComAutoDeleteCriticalSection-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComAutoDeleteCriticalSection
- atlcore/ATL::CComAutoDeleteCriticalSection
dev_langs:
- C++
helpviewer_keywords:
- CComAutoDeleteCriticalSection class
ms.assetid: 2396dbea-1c60-4841-b50e-c4e18af311a3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8c8ff6141fb5aa58e8de626675e29b46426ed47f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118439"
---
# <a name="ccomautodeletecriticalsection-class"></a>CComAutoDeleteCriticalSection-Klasse

Diese Klasse stellt Methoden zum Abrufen und Freigeben des Besitzes eines kritischen Abschnitts-Objekts.

## <a name="syntax"></a>Syntax

```
class CComAutoDeleteCriticalSection : public CComSafeDeleteCriticalSection
```

## <a name="remarks"></a>Hinweise

`CComAutoDeleteCriticalSection` leitet sich von der Klasse [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md). Allerdings `CComAutoDeleteCriticalSection` überschreibt die [Begriff](ccomsafedeletecriticalsection-class.md#term) Methode, um **private** Zugriff, die erzwingt, internen Speicher Cleanup dass erfolgen nur, wenn Instanzen dieser Klasse verlassen den Gültigkeitsbereich oder explizit gelöscht werden, aus Arbeitsspeicher.  

Diese Klasse führt keine zusätzlichen Methoden über seine Basisklasse. Finden Sie unter [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md) und [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) für Weitere Informationen zu den kritischen Abschnitt-Hilfsklassen.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)

[CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md)

`CComAutoDeleteCriticalSection`

## <a name="requirements"></a>Anforderungen

**Header:** atlcore.h

## <a name="see-also"></a>Siehe auch

[CComSafeDeleteCriticalSection-Klasse](../../atl/reference/ccomsafedeletecriticalsection-class.md)<br/>
[CComCriticalSection-Klasse](../../atl/reference/ccomcriticalsection-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
