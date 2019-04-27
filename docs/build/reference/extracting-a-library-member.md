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
ms.openlocfilehash: 6c577300f747d6f546b7caa3c66bddd6a516e16b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62271319"
---
# <a name="extracting-a-library-member"></a>Extrahieren eines Bibliothekmembers

Sie können LIB verwenden, um eine Objektdatei (obj) zu erstellen, die eine Kopie eines Elements aus einer bestehenden Bibliothek enthält. Um eine Kopie eines Elements zu extrahieren, verwenden Sie die folgende Syntax:

```
LIB library /EXTRACT:member /OUT:objectfile
```

Dieser Befehl erstellt eine OBJ-Datei mit dem Namen *Objektdatei* , enthält eine Kopie einer `member` von einer *Bibliothek*. Die `member` Namen wird Groß-/Kleinschreibung beachtet. Sie können nur ein Element in einem einzigen Befehl extrahieren. Die/Out-Option ist erforderlich; Es gibt keine standardausgabename. Wenn eine Datei namens *Objektdatei* bereits im angegebenen Verzeichnis (das aktuelle Verzeichnis, wenn kein Verzeichnis angegeben wird oder *Objektdatei*), die extrahierte *Objektdatei*ersetzt die vorhandene Datei.

## <a name="see-also"></a>Siehe auch

[LIB-Referenz](lib-reference.md)
