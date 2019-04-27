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
ms.openlocfilehash: 02012e7561fe8462f5f25ae13d961c35561666ec
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62273143"
---
# <a name="allowisolation"></a>/ALLOWISOLATION

Gibt das Verhalten bei der Manifestsuche an.

## <a name="syntax"></a>Syntax

```

/ALLOWISOLATION[:NO]
```

## <a name="remarks"></a>Hinweise

**/ ALLOWISOLATION** bewirkt, dass das Betriebssystem manifestsuch- und-Ladevorgänge durchführt.

**/ ALLOWISOLATION** ist die Standardeinstellung.

**/ALLOWISOLATION:No** gibt an, dass ausführbare Dateien geladen werden, als gäbe es kein Manifest und bewirkt, dass [EDITBIN-Referenz](editbin-reference.md) Festlegen der `IMAGE_DLLCHARACTERISTICS_NO_ISOLATION` bit im des optionalen Headers `DllCharacteristics` Feld.

Wenn die Isolation für eine ausführbare Datei deaktiviert ist, führt das Windows-Ladeprogramm keine Suche nach dem Anwendungsmanifest für den neu erstellen Prozess durch. Der neue Prozess verfügt nicht über eine Standard-Aktivierungskontext, auch wenn ein Manifest in der ausführbaren Datei vorhanden ist oder wenn ein Manifest, die den Namen verfügt *Name der ausführbaren Datei*. exe.manifest.

## <a name="see-also"></a>Siehe auch

[EDITBIN-Optionen](editbin-options.md)<br/>
[/ALLOWISOLATION (Manifestsuche)](allowisolation-manifest-lookup.md)<br/>
[Manifestdateienreferenz](/windows/desktop/SbsCs/manifest-files-reference)
