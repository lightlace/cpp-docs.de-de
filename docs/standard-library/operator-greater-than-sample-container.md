---
title: operator&gt; (&lt;Sample Container&gt;)
ms.date: 11/04/2016
f1_keywords:
- std::operator>
- operator>
- std::>
- '>'
helpviewer_keywords:
- '> operator, comparing specific objects'
- operator >
ms.assetid: 49bd417a-3305-4ffa-9884-39d3904ed87d
ms.openlocfilehash: 80bcc6b81ec7d6771895f711d61a507f057eae2a
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689185"
---
# <a name="operatorgt-ltsample-containergt"></a>operator&gt; (&lt;Sample Container&gt;)

> [!NOTE]
> Dieses Thema ist in der Microsoft C++ -Dokumentation als nicht funktionales Beispiel für Container, die C++ in der Standard Bibliothek verwendet werden. Weitere Informationen finden Sie unter [C++-Standardbibliothekscontainer](../standard-library/stl-containers.md).

Über lädt **Operator >** , um zwei Objekte des Klassen Vorlagen [Containers](../standard-library/sample-container-class.md)zu vergleichen.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
bool operator*gt;(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>Rückgabewert

Gibt `right < left`zurück.

## <a name="see-also"></a>Siehe auch

[\<sample container>](../standard-library/sample-container.md)
