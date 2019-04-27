---
title: Container-Klasse::swap
ms.date: 11/04/2016
helpviewer_keywords:
- swap method
ms.assetid: 898c219c-bc8e-4d14-a149-6240426c693f
ms.openlocfilehash: 2c2b87e8cc51248fd3d29df7f361fff92da72957
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62210843"
---
# <a name="container-classswap"></a>Container-Klasse::swap

> [!NOTE]
> Dieses Thema ist in der Dokumentation zu Visual C++ als nicht funktionierendes Beispiel für Container aufgeführt, die in der C++-Standardbibliothek verwendet werden. Weitere Informationen finden Sie unter [C++-Standardbibliothekcontainer](../standard-library/stl-containers.md).

Tauscht die gesteuerten Sequenzen zwischen **\*this** und seinem Argument aus

## <a name="syntax"></a>Syntax

```cpp
void swap(Container& right);
```

## <a name="remarks"></a>Hinweise

Wenn **\*this.get\_allocator ==** _right_**.get_allocator** gilt, erfolgt eine Austausch in konstanter Zeit. Andernfalls führt Sie proportional zur Anzahl der Elemente in den beiden kontrollierten Sequenzen eine Reihe von Elementzuweisungen und Konstruktoraufrufe aus.

## <a name="see-also"></a>Siehe auch

[Sample Container-Klasse](../standard-library/sample-container-class.md)<br/>
