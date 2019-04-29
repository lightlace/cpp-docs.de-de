---
title: Compilerwarnung (Stufe 4) C4289
ms.date: 11/04/2016
f1_keywords:
- C4289
helpviewer_keywords:
- C4289
ms.assetid: 0dbd2863-4cde-4e16-894b-104a2d5fa724
ms.openlocfilehash: 3a997af466ddfdaaf4631afeb53d917ce0338c3b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400902"
---
# <a name="compiler-warning-level-4-c4289"></a>Compilerwarnung (Stufe 4) C4289

Nicht dem Standard entsprechende Erweiterung: 'var': Die loop-Steuerelementvariable, die in der for-Schleife deklariert wurde, wird außerhalb des for-Schleifenbereichs verwendet

Beim Kompilieren mit [/Ze](../../build/reference/za-ze-disable-language-extensions.md) und **/Zc: forScope**, eine Variable deklariert, die einer [für](../../cpp/for-statement-cpp.md) Schleife wurde verwendet, nach der **für**-Schleife-Bereich.

Finden Sie unter [/Zc: forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) Informationen zur Vorgehensweise beim Angeben der gemäß dem Standardverhalten in **für** mit Schleifen **/Ze**.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Im folgende Beispiel wird die C4289 generiert:

```
// C4289.cpp
// compile with: /W4 /Zc:forScope-
#pragma warning(default:4289)
int main() {
   for (int i = 0 ; ; )   // C4289
      break;
   i++;
}
```