---
title: -HEAP | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /heap
dev_langs:
- C++
helpviewer_keywords:
- heap allocation, setting heap size
- HEAP editbin option
- -HEAP editbin option
- /HEAP editbin option
ms.assetid: 6ce759b5-75b7-44ff-a5fd-3a83a0ba9a48
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 22698760ba23dc60b64002f0f728bb7a036f6731
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45699815"
---
# <a name="heap"></a>/HEAP

Legt die Größe des Heaps in Bytes fest. Diese Option gilt nur für ausführbare Dateien.

```

/HEAP:
reserve[,commit]
```

## <a name="remarks"></a>Hinweise

Die `reserve` Argument gibt die gesamte anfängliche Heapreservierung im virtuellen Speicher. Standardmäßig beträgt die Größe des Heaps 1 MB. [EDITBIN-Referenz](../../build/reference/editbin-reference.md) rundet den angegebenen Wert in das nächste Vielfache von 4 Bytes.

Der optionale `commit` -Argument interpretiert, die vom Betriebssystem wird. Auf einem Windows-Betriebssystem gibt es die Anfangsgröße des physischen Arbeitsspeicher zugeordnet werden soll, und die Menge an zusätzlichem Arbeitsspeicher reserviert werden, wenn der Heap erweitert werden muss. Die Zusicherung von virtuellem Speicher bewirkt die Belegung von Speicher in der Auslagerungsdatei. Eine höhere `commit` Wert kann das System Arbeitsspeicher belegt weniger häufig auf, wenn die app mehr Heapspeicher benötigt, erhöht aber die arbeitsspeicheranforderungen und möglicherweise die app-Start-Dauer. Die `commit` Wert muss kleiner als oder gleich der `reserve` Wert.

Geben Sie die `reserve` und `commit` Werte Dezimal oder Hexadezimal oder Oktal Programmiersprache C-Notation. Beispielsweise kann ein Wert von 1 MB als 1048576 in Dezimal, oder als 0 x 100000 im Hexadezimalformat oder als 04000000 im Oktalformat angegeben werden.

## <a name="see-also"></a>Siehe auch

[EDITBIN-Optionen](../../build/reference/editbin-options.md)