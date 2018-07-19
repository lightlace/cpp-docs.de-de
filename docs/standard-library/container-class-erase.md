---
title: Containerklasse::erase | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- erase method
ms.assetid: abc091c5-5a80-4bd8-93a8-a2d9bde2efec
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 368b722f03a68445ddd016705aa8bebc6f33e6f5
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33842611"
---
# <a name="container-classerase"></a>Container-Klasse::erase

> [!NOTE]
> Dieses Thema ist in der Dokumentation zu Visual C++ als nicht funktionierendes Beispiel für Container aufgeführt, die in der C++-Standardbibliothek verwendet werden. Weitere Informationen finden Sie unter [C++-Standardbibliothekcontainer](../standard-library/stl-containers.md).

Löscht ein Element

## <a name="syntax"></a>Syntax

```

    iterator erase(
    iterator _Where);

iterator erase(
    iterator first,
    iterator last);
```

## <a name="remarks"></a>Hinweise

Die erste Memberfunktion entfernt das Element der kontrollierten Sequenz verweist *_Where*. Die zweite Memberfunktion entfernt die Elemente der gesteuerten Sequenz im Bereich [`first`, `last`). Beide Memberfunktionen geben einen Iterator zurück, der das erste Element festlegt, das länger als alle anderen entfernten Elementen verbleibt, oder sie geben [end](../standard-library/container-class-end.md) zurück, wenn kein solches Element vorhanden ist.

Die Memberfunktion löst nur dann eine Ausnahme aus, wenn ein Kopiervorgang eine Ausnahme auslöst.

## <a name="see-also"></a>Siehe auch

[Sample Container-Klasse](../standard-library/sample-container-class.md)<br/>
