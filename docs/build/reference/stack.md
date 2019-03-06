---
title: /STACK
ms.date: 11/04/2016
f1_keywords:
- /stack
helpviewer_keywords:
- -STACK editbin option
- STACK editbin option
- stack, setting size
- /STACK editbin option
ms.assetid: a39bcff0-c945-4355-80cc-8e4f24a5f142
ms.openlocfilehash: 1d583a7259e1aecef0a638743fb0b6271ff09330
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57417748"
---
# <a name="stack"></a>/STACK

```
/STACK:reserve[,commit]
```

## <a name="remarks"></a>Hinweise

Diese Option legt die Stapelgröße in Bytes fest und akzeptiert Argumente in der Schreibweise von "decimal" oder C-Sprachen. Die Stapelgröße-Option gilt nur für eine ausführbare Datei.

Die *reservieren* Argument gibt die gesamte stapelzuordnung im virtuellen Speicher. EDITBIN rundet den angegebenen Wert in die nächsten 4 Bytes ab.

Der optionale `commit` -Argument interpretiert, die vom Betriebssystem wird. In Windows NT, Windows 95 und Windows 98 `commit` gibt die Menge an physikalischem Arbeitsspeicher, zu einem Zeitpunkt zuordnen. Die Zusicherung von virtuellem Speicher bewirkt die Belegung von Speicher in der Auslagerungsdatei. Eine höhere `commit` -Wert spart Zeit, wenn die Anwendung mehr Stapelspeicher benötigt, erhöht aber die arbeitsspeicheranforderungen und möglicherweise die Startzeit.

## <a name="see-also"></a>Siehe auch

[EDITBIN-Optionen](../../build/reference/editbin-options.md)
