---
title: Extrahieren eines Bibliothekmembers
ms.date: 11/04/2016
f1_keywords:
- Lib
helpviewer_keywords:
- LIB [C++], extracting library members
- EXTRACT library manager option
- libraries, extracting members
- -EXTRACT library manager option
- extracting library members
- /EXTRACT library manager option
ms.assetid: a2c5c2a1-9b7e-489a-a9a4-1dec694e1fc5
ms.openlocfilehash: 2975ef584b0244a16b556232b6939308d2e1bd14
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50447033"
---
# <a name="extracting-a-library-member"></a>Extrahieren eines Bibliothekmembers

Sie können LIB verwenden, um eine Objektdatei (obj) zu erstellen, die eine Kopie eines Elements aus einer bestehenden Bibliothek enthält. Um eine Kopie eines Elements zu extrahieren, verwenden Sie die folgende Syntax:

```
LIB library /EXTRACT:member /OUT:objectfile
```

Dieser Befehl erstellt eine OBJ-Datei mit dem Namen *Objektdatei* , enthält eine Kopie einer `member` von einer *Bibliothek*. Die `member` Namen wird Groß-/Kleinschreibung beachtet. Sie können nur ein Element in einem einzigen Befehl extrahieren. Die/Out-Option ist erforderlich; Es gibt keine standardausgabename. Wenn eine Datei namens *Objektdatei* bereits im angegebenen Verzeichnis (das aktuelle Verzeichnis, wenn kein Verzeichnis angegeben wird oder *Objektdatei*), die extrahierte *Objektdatei*ersetzt die vorhandene Datei.

## <a name="see-also"></a>Siehe auch

[LIB-Referenz](../../build/reference/lib-reference.md)