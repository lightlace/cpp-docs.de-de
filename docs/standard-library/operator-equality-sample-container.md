---
title: operator== (&lt;Sample Container&gt;)
ms.date: 11/04/2016
f1_keywords:
- std.==
- std::==
- operator==
- std.operator==
- std::operator==
- ==
helpviewer_keywords:
- operator ==, containers
- operator==, containers
- == operator, with specific standard C++ objects
ms.assetid: d3d8754e-5157-4b8b-bf9c-da41856f5eed
ms.openlocfilehash: 168785abb09ca198435c301040d7628a6dd12b26
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68460154"
---
# <a name="operator-ltsample-containergt"></a>operator== (&lt;Sample Container&gt;)

> [!NOTE]
> Dieses Thema ist in der Microsoft C++ -Dokumentation als nicht funktionales Beispiel für Container, die C++ in der Standard Bibliothek verwendet werden. Weitere Informationen finden Sie unter [C++-Standardbibliothekcontainer](../standard-library/stl-containers.md).

Überlädt `operator==`, um zwei Objekte der Vorlagenklasse [Container](../standard-library/sample-container-class.md) zu vergleichen.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
bool operator==(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>Rückgabewert

Gibt `left.`[size](../standard-library/container-class-size.md) ` == right.size && equal(left.`[begin](../standard-library/container-class-begin.md)`, left.`[end](../standard-library/container-class-end.md)`, right.begin)` zurück.

## <a name="see-also"></a>Siehe auch

[\<sample container>](../standard-library/sample-container.md)
