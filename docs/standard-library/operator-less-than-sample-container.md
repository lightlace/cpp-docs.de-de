---
title: operator&lt; (&lt;Sample Container&gt;)
ms.date: 11/04/2016
f1_keywords:
- std::operator<
- operator<
- std.<
- <
- std.operator<
- std::<
helpviewer_keywords:
- < operator, comparing specific objects
- operator<, valarrays
- < operator
- operator <, valarrays
ms.assetid: 31027dd6-53be-428b-b950-1dcb25393597
ms.openlocfilehash: 57796cc69dd734ea4c619db4bd8fedbfa09ce15b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62371310"
---
# <a name="operatorlt-ltsample-containergt"></a>operator&lt; (&lt;Sample Container&gt;)

> [!NOTE]
> Dieses Thema ist in der Dokumentation zu Visual C++ als nicht funktionierendes Beispiel für Container aufgeführt, die in der C++-Standardbibliothek verwendet werden. Weitere Informationen finden Sie unter [C++-Standardbibliothekscontainer](../standard-library/stl-containers.md).

Überlädt **operator<**, um zwei Objekte der Vorlagenklasse [Container](../standard-library/sample-container-class.md) zu vergleichen.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
bool operator<(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>Rückgabewert

Gibt `lexicographical_compare(left.begin, left.end, right.begin, right.end)`zurück.

## <a name="see-also"></a>Siehe auch

[\<sample container>](../standard-library/sample-container.md)<br/>
[begin](../standard-library/container-class-begin.md)<br/>
[end](../standard-library/container-class-end.md)