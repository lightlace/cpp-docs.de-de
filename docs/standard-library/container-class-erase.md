---
title: Containerklasse::erase | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- erase method
ms.assetid: abc091c5-5a80-4bd8-93a8-a2d9bde2efec
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d5a817ed259f5bd264d82fc948afa4cdcd70be2e
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
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
