---
title: Compilerwarnung (Stufe 4) C4289
ms.date: 11/04/2016
f1_keywords:
- C4289
helpviewer_keywords:
- C4289
ms.assetid: 0dbd2863-4cde-4e16-894b-104a2d5fa724
ms.openlocfilehash: b9083670465d68493d90a8e96ff7ee5db34c1978
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991327"
---
# <a name="compiler-warning-level-4-c4289"></a>Compilerwarnung (Stufe 4) C4289

Nicht dem Standard entsprechende Erweiterung: 'var': Die loop-Steuerelementvariable, die in der for-Schleife deklariert wurde, wird außerhalb des for-Schleifenbereichs verwendet

Beim Kompilieren mit [/Ze](../../build/reference/za-ze-disable-language-extensions.md) und **/Zc: forScope-** wurde eine in einer [for](../../cpp/for-statement-cpp.md) -Schleife deklarierte Variable nach dem **for**-Schleifen Bereich verwendet.

Weitere Informationen zum Angeben des Standard Verhaltens in **for** -Schleifen mit **/Ze**finden Sie unter [/Zc: forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) .

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Im folgenden Beispiel wird C4289 generiert:

```cpp
// C4289.cpp
// compile with: /W4 /Zc:forScope-
#pragma warning(default:4289)
int main() {
   for (int i = 0 ; ; )   // C4289
      break;
   i++;
}
```
