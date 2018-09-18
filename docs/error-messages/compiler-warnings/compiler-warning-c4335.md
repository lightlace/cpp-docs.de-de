---
title: Compilerwarnung C4335 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4335
dev_langs:
- C++
helpviewer_keywords:
- C4335
ms.assetid: e66467ad-a10b-4438-8c7c-e8e8d11d39bb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d2b28909d0c4b663fffeacbec58ad694131bb008
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46036578"
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