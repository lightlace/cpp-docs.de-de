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
ms.openlocfilehash: 6f30877800d4597054601f7459df88c78193fd3c
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57820649"
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

[EDITBIN-Optionen](editbin-options.md)
