---
title: Definieren einer Regel | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, inference rules
- defining inference rules
ms.assetid: 071cd092-3f2e-4065-b0fb-36a9d393cfa8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a8a5cb7a0285f7abf8bcf476141451eae1b10f85
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45705574"
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