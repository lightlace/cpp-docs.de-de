---
title: Container-Klasse::erase
ms.date: 11/04/2016
helpviewer_keywords:
- erase method
ms.assetid: abc091c5-5a80-4bd8-93a8-a2d9bde2efec
ms.openlocfilehash: 1fa3fe7dee10f3033b84a671fdc35c193cd6ec3c
ms.sourcegitcommit: 8414cd91297dea88c480e208c7b5301db9972f19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77257896"
---
# <a name="container-classerase"></a>Container-Klasse::erase

> [!NOTE]
> Dieses Thema ist in der Microsoft C++ -Dokumentation als nicht funktionales Beispiel für Container, die C++ in der Standard Bibliothek verwendet werden. Weitere Informationen finden Sie unter [C++ Standard Library Containers (C++-Standardbibliothekcontainer)](../standard-library/stl-containers.md).

Löscht ein Element.

## <a name="syntax"></a>Syntax

```cpp
iterator erase(
    iterator _Where);

iterator erase(
    iterator first,
    iterator last);
```

## <a name="remarks"></a>Bemerkungen

Die erste Member-Funktion entfernt das Element der kontrollierten Sequenz, auf das *_Where*zeigt. Die zweite Memberfunktion entfernt die Elemente der gesteuerten Sequenz im Bereich [`first`, `last`). Beide Memberfunktionen geben einen Iterator zurück, der das erste Element festlegt, das länger als alle anderen entfernten Elementen verbleibt, oder sie geben [end](../standard-library/container-class-end.md) zurück, wenn kein solches Element vorhanden ist.

Die Memberfunktion löst nur dann eine Ausnahme aus, wenn ein Kopiervorgang eine Ausnahme auslöst.

## <a name="see-also"></a>Weitere Informationen

[Sample Container Class (Beispielcontainerklasse)](../standard-library/sample-container-class.md)
