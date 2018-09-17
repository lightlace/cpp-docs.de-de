---
title: -STAPEL | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /stack
dev_langs:
- C++
helpviewer_keywords:
- -STACK editbin option
- STACK editbin option
- stack, setting size
- /STACK editbin option
ms.assetid: a39bcff0-c945-4355-80cc-8e4f24a5f142
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d8deb3e3bedcb773aa01ae5f1c3ff66ce9d509f2
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45716662"
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