---
title: Compilerwarnung (Stufe 4) C4289 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4289
dev_langs:
- C++
helpviewer_keywords:
- C4289
ms.assetid: 0dbd2863-4cde-4e16-894b-104a2d5fa724
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 35cb22c767c0ea64a1536bd4d02ad8653bb94250
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46102839"
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