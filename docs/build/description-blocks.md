---
title: Beschreibungsblöcke
ms.date: 11/04/2016
helpviewer_keywords:
- description blocks
- NMAKE program, description blocks
- blocks, description
ms.assetid: 1321f228-d389-40ac-b0cd-4f6e9293602b
ms.openlocfilehash: c7469a59c88e9dfb44cf1bf32926aa336b6e46c9
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57420465"
---
# <a name="description-blocks"></a>Beschreibungsblöcke

Ein Beschreibungsblock ist eine Abhängigkeit optional gefolgt von einem Befehlsblock:

```
targets... : dependents...
    commands...
```

Eine Abhängigkeit Linie gibt an, ein oder mehrere Ziele und keinem oder mehreren abhängigen Elemente. Ein Ziel muss am Anfang der Zeile sein. Es sind separate Ziele von abhängigen Dateien von einem Doppelpunkt (:), Leerzeichen oder Tabstopps zulässig. Verwenden Sie einen umgekehrten Schrägstrich (\) nach der ein Ziel oder eine abhängige, um die Zeile zu teilen. Wenn ein Ziel nicht vorhanden ist, verfügt über einen früheren Zeitstempel als eine abhängige oder ist eine [Pseudoziel](../build/pseudotargets.md), NMAKE führt die Befehle aus. Wenn ein abhängiges Element ein Ziel an anderer Stelle ist und nicht vorhanden ist oder in Bezug auf seine eigenen Abhängigkeiten veraltet ist, aktualisiert NMAKE die abhängigen vor dem Aktualisieren der aktuellen Abhängigkeit.

## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

[Ziele](../build/targets.md)

[Abhängige Dateien](../build/dependents.md)

## <a name="see-also"></a>Siehe auch

[NMAKE-Referenz](../build/nmake-reference.md)
