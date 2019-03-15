---
title: Definieren einer Regel
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, inference rules
- defining inference rules
ms.assetid: 071cd092-3f2e-4065-b0fb-36a9d393cfa8
ms.openlocfilehash: cd82dc5b0693e563fd3d75a0215265089ff57913
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57825653"
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

[Suchpfade in Regeln](search-paths-in-rules.md)

## <a name="see-also"></a>Siehe auch

[Rückschlussregeln](inference-rules.md)
