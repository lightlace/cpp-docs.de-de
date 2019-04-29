---
title: Linkertoolfehler LNK2011
ms.date: 11/04/2016
f1_keywords:
- LNK2011
helpviewer_keywords:
- LNK2011
ms.assetid: 04991ef5-49d5-46c7-8eee-a9d1d3fc541e
ms.openlocfilehash: c8c62da6c1b4ea856f7a0854b998946893f2be63
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62299089"
---
# <a name="linker-tools-error-lnk2011"></a>Linkertoolfehler LNK2011

Vorkompiliertes Objekt nicht verknüpft; Image kann möglicherweise nicht ausgeführt.

Bei Verwendung vorkompilierter Header erfordert LINK an, dass die Objektdateien mit vorkompilierten Header erstellt alle verknüpft sein muss. Wenn Sie eine Quelldatei, die Sie verwenden verfügen, um einen vorkompilierten Header für die Verwendung mit anderen Quelldateien zu generieren, müssen Sie jetzt die Objektdatei, die erstellt werden, zusammen mit der vorkompilierten Headerdatei einschließen.

Z. B. Wenn Sie eine Datei namens STUB.cpp zum Erstellen des vorkompilierten Headers für die Verwendung mit anderen Quelldateien kompilieren, müssen Sie eine Verknüpfung mit STUB.obj, oder Sie erhalten diesen Fehler. In den folgenden Befehlszeilen dient Zeile aus, den vorkompilierten Header COMMON.pch zu erstellen, die in die zweite und dritte PROG1.cpp und PROG2.cpp verwendet wird. Die Datei STUB.cpp nur enthält `#include` Zeilen (das gleiche `#include` wie in PROG1.cpp und PROG2.cpp) und dient nur zum Generieren von vorkompilierten Headern. In der letzten Zeile müssen STUB.obj verknüpft werden, um LNK2011 zu vermeiden.

```
cl /c /Yccommon.h stub.cpp
cl /c /Yucommon.h prog1.cpp
cl /c /Yucommon.h prog2.cpp
link /out:prog.exe stub.obj prog1.obj prog2.obj
```