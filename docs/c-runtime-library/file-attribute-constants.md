---
title: Dateiattributskonstanten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- A_HIDDEN
- _A_NORMAL
- _A_SUBDIR
- _A_RDONLY
- A_NORMAL
- A_SUBDIR
- _A_SYSTEM
- c.constants.file
- _A_HIDDEN
- A_RDONLY
- _A_ARCH
- A_ARCH
dev_langs:
- C++
helpviewer_keywords:
- constants [C++], file attributes
- file attribute constants [C++]
- _A_SYSTEM constant
- files [C++], file attribute constants
- _A_SUBDIR constant
- _A_ARCH constant
- _A_NORMAL constant
- _A_HIDDEN constant
- _A_RDONLY constant
ms.assetid: 8dc8ccb9-99f5-446b-876c-7ebecc2f764f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 42745d25c0f743fa1a11226d5cfe433327c8ff2a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46077047"
---
# <a name="file-attribute-constants"></a>Dateiattributskonstanten

## <a name="syntax"></a>Syntax

```

#include <io.h>
```

## <a name="remarks"></a>Hinweise

Diese Konstanten geben die aktuellen Attribute der Datei oder des Verzeichnisses an, die/das von der Funktion angegeben wird.

Die Attribute werden durch die folgenden Manifestkonstanten dargestellt:

|Konstante|Beschreibung |
|-|-|
|`_A_ARCH`| Archiv. Wird bei jeder Änderung der Datei festgelegt und durch den BACKUP-Befehl gelöscht. Wert: 0x20|
|`_A_HIDDEN`| Versteckte Datei. Normalerweise mithilfe des DIR-Befehls nicht angezeigt, sofern nicht die Option „/AH“ verwendet wird. Gibt Informationen über normale Dateien zurück und über Dateien, die dieses Attribut aufweisen. Wert: 0x02|
|`_A_NORMAL`| Normal. Datei kann ohne Einschränkung gelesen oder geschrieben werden. Wert: 0x00|
|`_A_RDONLY`| Schreibgeschützt. Die Datei kann nicht zum Schreiben geöffnet werden, und eine Datei mit gleichem Namen kann nicht erstellt werden. Wert: 0x01|
|`_A_SUBDIR`| Unterverzeichnis. Wert: 0x10|
|`_A_SYSTEM`| Systemdatei. Normalerweise mithilfe des DIR-Befehls nicht angezeigt, sofern nicht die Option „/AS“ verwendet wird. Wert: 0x04|

Mit dem OR-Operator (& #124;) können mehrere Konstanten kombiniert werden.

## <a name="see-also"></a>Siehe auch

[Dateinamen-Suchfunktionen](../c-runtime-library/filename-search-functions.md)<br/>
[Globale Konstanten](../c-runtime-library/global-constants.md)