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
ms.openlocfilehash: a286833d96e913a66240d25798e1cc230adf58b0
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68458722"
---
# <a name="operatorlt-ltsample-containergt"></a>operator&lt; (&lt;Sample Container&gt;)

> [!NOTE]
> Dieses Thema ist in der Microsoft C++ -Dokumentation als nicht funktionales Beispiel für Container, die C++ in der Standard Bibliothek verwendet werden. Weitere Informationen finden Sie unter [C++-Standardbibliothekcontainer](../standard-library/stl-containers.md).

Überlädt **operator<** , um zwei Objekte der Vorlagenklasse [Container](../standard-library/sample-container-class.md) zu vergleichen.

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

[\<Sample Container>](../standard-library/sample-container.md)\
[beginnen](../standard-library/container-class-begin.md)\
[end](../standard-library/container-class-end.md)