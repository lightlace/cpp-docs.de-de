---
title: Compilerwarnung C4335
ms.date: 11/04/2016
f1_keywords:
- C4335
helpviewer_keywords:
- C4335
ms.assetid: e66467ad-a10b-4438-8c7c-e8e8d11d39bb
ms.openlocfilehash: 43c2f5d9092cdbad14e429349bd7d04e236b75e4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62151850"
---
# <a name="compiler-warning-c4335"></a>Compilerwarnung C4335

Mac-Dateiformat ermittelt: Konvertieren Sie die Quelldatei in DOS- oder UNIX-Format

Das abschließende Zeichen der ersten Zeile einer Quelldatei ist Macintosh-Systeme ('\r') im Gegensatz zu UNIX ('\n') oder DOS ("\r\n").

Diese Warnung wird immer als Fehler ausgegeben.  Finden Sie unter [Warnung](../../preprocessor/warning.md) Pragma Informationen dazu, wie Sie diese Warnung zu deaktivieren.  Darüber hinaus wird diese Warnung nur einmal pro Kompiliereinheit ausgegeben. Aus diesem Grund gibt es sind mehrere `#include` Anweisungen, die Dateien im Macintosh-Format angeben, C4335 wird nur einmal ausgegeben.

Eine Möglichkeit zum Generieren von Dateien im Macintosh-Format ist die Verwendung der **Erweiterte Speicheroptionen** (auf der **Datei** Menü) in Visual Studio.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4335 generiert.

```
// C4335 expected
#include "c4335.h"   // assume both include files are in Macintosh format
#include "c4335_2.h"
```