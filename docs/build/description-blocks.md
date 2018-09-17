---
title: Beschreibungsblöcke | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- description blocks
- NMAKE program, description blocks
- blocks, description
ms.assetid: 1321f228-d389-40ac-b0cd-4f6e9293602b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d83e010f690f96afa5a57eb89ca1e8f4cf444225
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45699659"
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