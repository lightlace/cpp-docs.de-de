---
title: '&lt;list&gt;'
ms.date: 11/04/2016
f1_keywords:
- <list>
- std::<list>
helpviewer_keywords:
- list header
ms.assetid: 2345823b-5612-44d8-95d3-aa96ed076d17
ms.openlocfilehash: c81990f14c6f9dc2400362015b838df5aed86429
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689426"
---
# <a name="ltlistgt"></a>&lt;list&gt;

Definiert die Containerklassen-Vorlagenliste und mehrere unterstützende Vorlagen.

## <a name="syntax"></a>Syntax

```cpp
#include <list>
```

> [!NOTE]
> Die \<list > Bibliothek verwendet auch die `#include <initializer_list>`-Anweisung.

## <a name="members"></a>Member

### <a name="operators"></a>Operatoren

|||
|-|-|
|[Operator!=](../standard-library/list-operators.md#op_neq)|Testet, ob das Listenobjekt links vom Operator ungleich dem Listenobjekt rechts vom Operator ist.|
|[operator<](../standard-library/list-operators.md#op_lt)|Testet, ob das Listenobjekt links vom Operator kleiner als das Listenobjekt auf der rechten Seite ist.|
|[operator\<=](../standard-library/list-operators.md#op_gt_eq)|Testet, ob das Listenobjekt links vom Operator kleiner als oder gleich dem Listenobjekt rechts vom Operator ist.|
|[operator==](../standard-library/list-operators.md#op_eq_eq)|Testet, ob das Listenobjekt links vom Operator gleich dem Listenobjekt rechts vom Operator ist.|
|[operator>](../standard-library/list-operators.md#op_gt)|Testet, ob das Listenobjekt links vom Operator größer als das Listenobjekt auf der rechten Seite ist.|
|[operator>=](../standard-library/list-operators.md#op_gt_eq)|Testet, ob das Listenobjekt links vom Operator größer als oder gleich dem Listenobjekt rechts vom Operator ist.|

### <a name="functions"></a>Funktionen

|||
|-|-|
|[swap](../standard-library/list-functions.md#swap)|Tauscht die Elemente zweier Listen aus.|

### <a name="classes"></a>Klassen

|||
|-|-|
|[list-Klasse](../standard-library/list-class.md)|Eine Klassen Vorlage von Sequenz Containern, die ihre Elemente in einer linearen Anordnung verwalten und effiziente Einfügungen und Löschungen an einer beliebigen Position innerhalb der Sequenz ermöglichen.|

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)\
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)
