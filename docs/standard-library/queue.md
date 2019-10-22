---
title: '&lt;Warteschlange&gt;'
ms.date: 11/04/2016
f1_keywords:
- <queue>
helpviewer_keywords:
- queue header
ms.assetid: 24fcf350-eb0e-48cf-9fef-978be1aeda1f
ms.openlocfilehash: ee35f880ddf40561cacb5c4d519f2e6291ad77a8
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689114"
---
# <a name="ltqueuegt"></a>&lt;Warteschlange&gt;

Definiert die Klassen Vorlagen Priority_queue und Queue sowie mehrere unterstützende Vorlagen.

## <a name="requirements"></a>Anforderungen

**Header:** \<queue>

**Namespace:** std

> [!NOTE]
> Die \<queue > Bibliothek verwendet auch die `#include <initializer_list>`-Anweisung.

## <a name="members"></a>Member

### <a name="operators"></a>Operatoren

|||
|-|-|
|[Operator!=](../standard-library/queue-operators.md#op_neq)|Testet, ob das queue-Objekt links vom Operator ungleich dem queue-Objekt rechts vom Operator ist.|
|[operator<](../standard-library/queue-operators.md#op_lt)|Testet, ob das queue-Objekt links vom Operator kleiner ist als das queue-Objekt rechts vom Operator.|
|[operator\<=](../standard-library/queue-operators.md#op_gt_eq)|Testet, ob das queue-Objekt links vom Operator kleiner gleich dem queue-Objekt rechts vom Operator ist.|
|[operator==](../standard-library/queue-operators.md#op_eq_eq)|Testet, ob das queue-Objekt links vom Operator gleich dem queue-Objekt rechts vom Operator ist.|
|[operator>](../standard-library/queue-operators.md#op_gt)|Testet, ob das queue-Objekt links vom Operator größer ist als das queue-Objekt rechts vom Operator.|
|[operator>=](../standard-library/queue-operators.md#op_gt_eq)|Testet, ob das queue-Objekt links vom Operator größer gleich dem queue-Objekt rechts vom Operator ist.|

### <a name="classes"></a>Klassen

|||
|-|-|
|[queue-Klasse](../standard-library/queue-class.md)|Eine Vorlagencontainer-Adapterklasse, die die Funktionalität einschränkt, indem sie den Zugriff auf die vorderen und hinteren Elemente eines zugrunde liegenden Containertyps beschränkt.|
|[priority_queue-Klasse](../standard-library/priority-queue-class.md)|Eine Vorlagencontainer-Adapterklasse, die die Funktionalität einschränkt, indem sie den Zugriff auf das oberste Element eines zugrunde liegenden Containertyps beschränkt, das immer das größte Element ist.|

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)\
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)
