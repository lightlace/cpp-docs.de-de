---
title: /ALLOWISOLATION
ms.date: 11/04/2016
f1_keywords:
- /ALLOWISOLATION
helpviewer_keywords:
- -ALLOWISOLATION editbin option
- /ALLOWISOLATION editbin option
- ALLOWISOLATION editbin option
ms.assetid: 91430344-f64f-491a-a5a5-7ea3b21cbe68
ms.openlocfilehash: 359a68d5ec0a8c7390b5f0343530864e880a057c
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493118"
---
# <a name="allowisolation"></a>/ALLOWISOLATION

Gibt das Verhalten bei der Manifestsuche an.

## <a name="syntax"></a>Syntax

```

/ALLOWISOLATION[:NO]
```

## <a name="remarks"></a>Hinweise

**/ALLOWISOLATION** bewirkt, dass das Betriebssystem Manifeste suchen und lädt.

**/ALLOWISOLATION** ist die Standardeinstellung.

**/ALLOWISOLATION: No** gibt an, dass ausführbare Dateien geladen werden, als ob kein Manifest vorhanden wäre, und bewirkt, dass der `DllCharacteristics` [EDITBIN-Verweis](editbin-reference.md) das `IMAGE_DLLCHARACTERISTICS_NO_ISOLATION` Bit im Feld des optionalen Headers festgelegt hat.

Wenn die Isolation für eine ausführbare Datei deaktiviert ist, führt das Windows-Ladeprogramm keine Suche nach dem Anwendungsmanifest für den neu erstellen Prozess durch. Der neue Prozess verfügt über keinen Standard Aktivierungs Kontext, auch wenn ein Manifest in der ausführbaren Datei selbst vorhanden ist, oder wenn ein Manifest mit dem Namen " *ausführbare Datei*Name. exe. Manifest" vorhanden ist.

## <a name="see-also"></a>Siehe auch

[EDITBIN-Optionen](editbin-options.md)<br/>
[/ALLOWISOLATION (Manifestsuche)](allowisolation-manifest-lookup.md)<br/>
[Manifest-Dateireferenz](/windows/win32/SbsCs/manifest-files-reference)
