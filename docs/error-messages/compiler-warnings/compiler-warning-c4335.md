---
title: Compilerwarnung C4335
ms.date: 11/04/2016
f1_keywords:
- C4335
helpviewer_keywords:
- C4335
ms.assetid: e66467ad-a10b-4438-8c7c-e8e8d11d39bb
ms.openlocfilehash: ccb00118d0c6895eee84976bb01472ea2f98353d
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73627120"
---
# <a name="compiler-warning-c4335"></a>Compilerwarnung C4335

Mac-Dateiformat erkannt: konvertieren Sie die Quelldatei in das DOS-oder UNIX-Format.

Das Zeilen Beendigungs Zeichen der ersten Zeile einer Quelldatei ist der Macintosh-Stil ("\r") im Gegensatz zu UNIX ("\n") oder DOS ("\r\n").

Diese Warnmeldung wird immer als Fehler ausgegeben.  Informationen dazu, wie Sie diese Warnung deaktivieren, finden Sie unter [Warning](../../preprocessor/warning.md) -Pragma.  Diese Warnung wird auch nur einmal pro Kompilierungen ausgegeben. Wenn mehrere `#include` Direktiven vorhanden sind, die Dateien im Macintosh-Format angeben, wird C4335 nur einmal ausgegeben.

Eine Möglichkeit zum Generieren von Dateien im Macintosh-Format ist die Verwendung der **erweiterten Speicheroptionen** (im Menü **Datei** ) in Visual Studio.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4335 generiert.

```cpp
// C4335 expected
#include "c4335.h"   // assume both include files are in Macintosh format
#include "c4335_2.h"
```
