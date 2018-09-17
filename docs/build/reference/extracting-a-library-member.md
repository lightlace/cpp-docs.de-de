---
title: Extrahieren eines Bibliothekmembers | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- Lib
dev_langs:
- C++
helpviewer_keywords:
- LIB [C++], extracting library members
- EXTRACT library manager option
- libraries, extracting members
- -EXTRACT library manager option
- extracting library members
- /EXTRACT library manager option
ms.assetid: a2c5c2a1-9b7e-489a-a9a4-1dec694e1fc5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9207a77868b3257d09f0d9efe38e4765cb8f4906
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45726517"
---
# <a name="extracting-a-library-member"></a>Extrahieren eines Bibliothekmembers

Sie können LIB verwenden, um eine Objektdatei (obj) zu erstellen, die eine Kopie eines Elements aus einer bestehenden Bibliothek enthält. Um eine Kopie eines Elements zu extrahieren, verwenden Sie die folgende Syntax:

```
LIB library /EXTRACT:member /OUT:objectfile
```

Dieser Befehl erstellt eine OBJ-Datei mit dem Namen *Objektdatei* , enthält eine Kopie einer `member` von einer *Bibliothek*. Die `member` Namen wird Groß-/Kleinschreibung beachtet. Sie können nur ein Element in einem einzigen Befehl extrahieren. Die/Out-Option ist erforderlich; Es gibt keine standardausgabename. Wenn eine Datei namens *Objektdatei* bereits im angegebenen Verzeichnis (das aktuelle Verzeichnis, wenn kein Verzeichnis angegeben wird oder *Objektdatei*), die extrahierte *Objektdatei*ersetzt die vorhandene Datei.

## <a name="see-also"></a>Siehe auch

[LIB-Referenz](../../build/reference/lib-reference.md)