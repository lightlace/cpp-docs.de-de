---
title: Definieren einer Regel
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, inference rules
- defining inference rules
ms.assetid: 071cd092-3f2e-4065-b0fb-36a9d393cfa8
ms.openlocfilehash: 0e8356f57b85d503328bb282e2f9f785ac20fa4c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50431163"
---
# <a name="defining-a-rule"></a>Definieren einer Regel

Die *Fromext* repräsentiert eine abhängige Datei, die Erweiterung und *Toext* stellt die Erweiterung einer Zieldatei dar.

```
.fromext.toext:
   commands
```

## <a name="remarks"></a>Hinweise

Erweiterungen sind nicht in der Groß-/Kleinschreibung beachtet. Makros können aufgerufen werden, um die Darstellung *Fromext* und *Toext*; die Makros, die während der vorverarbeitung erweitert werden. Der Punkt (.) vorherigen *Fromext* müssen am Anfang der Zeile angezeigt werden. Der Doppelpunkt (:) ist NULL oder mehr Leerzeichen oder Tabstopps vorangestellt. Es kann nur Leerzeichen oder Tabstopps, ein Semikolon (;) zur Angabe eines Befehls, ein Nummernzeichen (#), geben Sie einen Kommentar oder ein Zeilenumbruchzeichen folgen. Es sind keine anderen Leerzeichen zulässig. Befehle werden wie Beschreibungsblöcke angegeben.

## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

[Suchpfade in Regeln](../build/search-paths-in-rules.md)

## <a name="see-also"></a>Siehe auch

[Rückschlussregeln](../build/inference-rules.md)