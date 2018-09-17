---
title: Ziele | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- targets, specifying in NMAKE
ms.assetid: 826ee849-4278-4c6e-97c3-79a2b5fe6463
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: edb75258c548526c68ed33f7f8037656750f6855
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45713797"
---
# <a name="targets"></a>Ziele

Geben Sie in einer Abhängigkeitszeile ein oder mehrere Ziele, die über alle gültigen Dateinamen, Verzeichnisnamen oder [Pseudoziel](../build/pseudotargets.md). Trennen Sie mehrere Ziele mit ein oder mehrere Leerzeichen oder Tabstopps. Ziele sind nicht in der Groß-/Kleinschreibung beachtet. Pfade sind mit Dateinamen zulässig. Ein Ziel darf 256 Zeichen nicht überschreiten. Wenn das Ziel, die vor dem Doppelpunkt stehenden ein einzelnes Zeichen ist, verwenden Sie ein Leerzeichen getrennt; Andernfalls wird die NMAKE die Buchstaben-Doppelpunkt-Kombination als eine Laufwerksangabe interpretiert.

## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

[Pseudoziele](../build/pseudotargets.md)

[Mehrere Ziele](../build/multiple-targets.md)

[Kumulative Abhängigkeiten](../build/cumulative-dependencies.md)

[Ziele in mehreren Beschreibungsblöcken](../build/targets-in-multiple-description-blocks.md)

[Seiteneffekte bei Abhängigkeiten](../build/dependency-side-effects.md)

## <a name="see-also"></a>Siehe auch

[Beschreibungsblöcke](../build/description-blocks.md)