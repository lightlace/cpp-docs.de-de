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
ms.openlocfilehash: ac9d1f067259b092a261702b51f2355d4f908469
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57417436"
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

**/ALLOWISOLATION:No** gibt an, dass ausführbare Dateien geladen werden, als gäbe es kein Manifest und bewirkt, dass [EDITBIN-Referenz](../../build/reference/editbin-reference.md) Festlegen der `IMAGE_DLLCHARACTERISTICS_NO_ISOLATION` bit im des optionalen Headers `DllCharacteristics` Feld.

Wenn die Isolation für eine ausführbare Datei deaktiviert ist, führt das Windows-Ladeprogramm keine Suche nach dem Anwendungsmanifest für den neu erstellen Prozess durch. Der neue Prozess verfügt nicht über eine Standard-Aktivierungskontext, auch wenn ein Manifest in der ausführbaren Datei vorhanden ist oder wenn ein Manifest, die den Namen verfügt *Name der ausführbaren Datei*. exe.manifest.

## <a name="see-also"></a>Siehe auch

[EDITBIN-Optionen](../../build/reference/editbin-options.md)<br/>
[/ALLOWISOLATION (Manifestsuche)](../../build/reference/allowisolation-manifest-lookup.md)<br/>
[Manifestdateienreferenz](/windows/desktop/SbsCs/manifest-files-reference)
