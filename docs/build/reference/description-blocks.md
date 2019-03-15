---
title: Beschreibungsblöcke
ms.date: 11/04/2016
helpviewer_keywords:
- description blocks
- NMAKE program, description blocks
- blocks, description
ms.assetid: 1321f228-d389-40ac-b0cd-4f6e9293602b
ms.openlocfilehash: da9265d6b0026bb47496d3aa58847824b5d634d2
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57825958"
---
# <a name="description-blocks"></a>Beschreibungsblöcke

Ein Beschreibungsblock ist eine Abhängigkeit optional gefolgt von einem Befehlsblock:

```
targets... : dependents...
    commands...
```

Eine Abhängigkeit Linie gibt an, ein oder mehrere Ziele und keinem oder mehreren abhängigen Elemente. Ein Ziel muss am Anfang der Zeile sein. Es sind separate Ziele von abhängigen Dateien von einem Doppelpunkt (:), Leerzeichen oder Tabstopps zulässig. Verwenden Sie einen umgekehrten Schrägstrich (\) nach der ein Ziel oder eine abhängige, um die Zeile zu teilen. Wenn ein Ziel nicht vorhanden ist, verfügt über einen früheren Zeitstempel als eine abhängige oder ist eine [Pseudoziel](pseudotargets.md), NMAKE führt die Befehle aus. Wenn ein abhängiges Element ein Ziel an anderer Stelle ist und nicht vorhanden ist oder in Bezug auf seine eigenen Abhängigkeiten veraltet ist, aktualisiert NMAKE die abhängigen vor dem Aktualisieren der aktuellen Abhängigkeit.

## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

[Ziele](targets.md)

[Abhängige Dateien](dependents.md)

## <a name="see-also"></a>Siehe auch

[NMAKE-Referenz](nmake-reference.md)
