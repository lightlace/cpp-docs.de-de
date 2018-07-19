---
title: Containerklasse::swap | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- swap method
ms.assetid: 898c219c-bc8e-4d14-a149-6240426c693f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f0ac2b3322f7f034c09c86f2307da2e3f3995c0d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33842325"
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
