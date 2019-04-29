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
ms.openlocfilehash: c49c58bdc168385d421cf942735b7473de70925f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62371528"
---
# <a name="operator-ltsample-containergt"></a>operator== (&lt;Sample Container&gt;)

> [!NOTE]
> Dieses Thema ist in der Dokumentation zu Visual C++ als nicht funktionierendes Beispiel für Container aufgeführt, die in der C++-Standardbibliothek verwendet werden. Weitere Informationen finden Sie unter [C++-Standardbibliothekcontainer](../standard-library/stl-containers.md).

Überlädt `operator==`, um zwei Objekte der Vorlagenklasse [Container](../standard-library/sample-container-class.md) zu vergleichen.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
bool operator==(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>Rückgabewert

Gibt `left.` [Größe](../standard-library/container-class-size.md) ` == right.size && equal(left.` [beginnen](../standard-library/container-class-begin.md)`, left.`[End](../standard-library/container-class-end.md)`, right.begin)`.

## <a name="see-also"></a>Siehe auch

[\<sample container>](../standard-library/sample-container.md)<br/>
