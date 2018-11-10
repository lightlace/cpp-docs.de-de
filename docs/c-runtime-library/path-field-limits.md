---
title: Begrenzungen für Pfadfelder
ms.date: 11/04/2016
f1_keywords:
- _MAX_EXT
- _MAX_DIR
- _MAX_PATH
- _MAX_FNAME
- _MAX_DRIVE
helpviewer_keywords:
- path field constants
- MAX_FNAME constant
- _MAX_DIR constant
- _MAX_DRIVE constant
- paths, maximum limit
- _MAX_PATH constant
- MAX_DRIVE constant
- _MAX_FNAME constant
- _MAX_EXT constant
- MAX_DIR constant
- MAX_EXT constant
ms.assetid: 2b5d0e43-1347-45b4-8397-24a8a45c444e
ms.openlocfilehash: 89609de3fc5584a960480bff83566f5e38c8be1f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50477531"
---
# <a name="path-field-limits"></a>Begrenzungen für Pfadfelder

## <a name="syntax"></a>Syntax

```cpp
#include <stdlib.h>
```

## <a name="remarks"></a>Hinweise

Diese Konstanten definieren die maximale Länge für den Pfad und die einzelnen Felder in diesem Pfad.

|Konstante|Bedeutung|
|--------------|-------------|
|`_MAX_DIR`|Maximale Länge der Verzeichniskomponente|
|`_MAX_DRIVE`|Maximale Länge der Laufwerkskomponente|
|`_MAX_EXT`|Maximale Länge der Erweiterungskomponente|
|`_MAX_FNAME`|Maximale Länge der Dateinamenkomponente|
|`_MAX_PATH`|Maximale Länge des vollständigen Pfads|

> [!NOTE]
> Die C-Laufzeit unterstützt Pfadlängen bis zu 32.768 Zeichen, aber es hängt vom Betriebssystem, insbesondere vom Dateisystem ab, ob diese längeren Pfade unterstützt werden. Zur vollständigen Abwärtskompatibilität mit FAT32-Dateisystemen sollte die Summe der Felder `_MAX_PATH` nicht überschreiten. Das Windows-NTFS-Dateisystem unterstützt Pfadlängen bis zu 32768 Zeichen, aber nur bei Verwendung von Unicode-APIs. Wenn Sie lange Pfadnamen verwenden, stellen Sie dem Pfad die Zeichen „\\\\?\“ als Präfix voran, und verwenden Sie die Unicode-Versionen der C-Laufzeit-Funktionen.

## <a name="see-also"></a>Siehe auch

[Globale Konstanten](../c-runtime-library/global-constants.md)