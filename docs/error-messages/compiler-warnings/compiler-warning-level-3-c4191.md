---
title: Compilerwarnung (Stufe 3) C4191 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4191
dev_langs:
- C++
helpviewer_keywords:
- C4191
ms.assetid: 576d3bc6-95b7-448a-af31-5d798452df09
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 81240ea085b52f4687c968848d526194bdb66a68
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053777"
---
# <a name="compiler-warning-level-3-c4191"></a>Compilerwarnung (Stufe 3) C4191

'operator/operation': unsichere Konvertierung von 'type of expression' zu 'type required'

Verschiedene Operationen, die Funktionszeiger verwenden, werden als unsicher angesehen:

- Funktionstypen mit unterschiedlichen Aufrufkonventionen.

- Funktionstypen mit unterschiedlichen Rückgabekonventionen.

- Argument- oder Rückgabetypen mit verschiedenen Größen, Typkategorien oder Klassifikationen.

- Verschiedene Länge von Argumentlisten (in `__cdecl`nur bei der Typumwandlung von längerer zu kürzer Liste, auch wenn die kürzere 'varargs' aufweist).

- Zeiger auf Daten (außer **"void"**<strong>\*</strong>) als Alias für einen Zeiger auf Funktion.

- Alle anderen Typunterschiede, die einen Fehler oder eine Warnung bei einem `reinterpret_cast`hervorrufen würden.

Das Aufrufen dieser Funktion über den Ergebniszeiger kann zum Absturz des Programms führen.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Im folgenden Beispiel wird C4191 generiert:

```
// C4191.cpp
// compile with: /W3 /clr
#pragma warning(default: 4191)

void __clrcall f1() { }
void __cdecl   f2() { }

typedef void (__clrcall * fnptr1)();
typedef void (__cdecl   * fnptr2)();

int main() {
   fnptr1 fp1 = static_cast<fnptr1>(&f1);
   fnptr2 fp2 = (fnptr2) &f2;

   fnptr1 fp3 = (fnptr1) &f2;   // C4191
   fnptr2 fp4 = (fnptr2) &f1;   // C4191
};
```