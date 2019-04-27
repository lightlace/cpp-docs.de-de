---
title: Compilerwarnung (Stufe 1) C4288
ms.date: 11/04/2016
f1_keywords:
- C4288
helpviewer_keywords:
- C4288
ms.assetid: 6aaeb139-90cd-457a-9d37-65687042736f
ms.openlocfilehash: d8769f5663ca0bde9048e52d4579012dfccab0a1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62207094"
---
# <a name="compiler-warning-level-1-c4288"></a>Compilerwarnung (Stufe 1) C4288

nicht dem Standard entsprechende Erweiterung: 'Var': Loop-Steuerelementvariable, die in der for-Schleife deklariert wurde, wird außerhalb der for-Schleife-Bereich; Es liegen Konflikte mit der Deklaration im äußeren Gültigkeitsbereich

Beim Kompilieren mit [/Ze](../../build/reference/za-ze-disable-language-extensions.md) und **/Zc: forScope**, eine Variable deklariert, die einer **für** Schleife wurde verwendet, nach der [für](../../cpp/for-statement-cpp.md)-Schleife-Bereich. Eine Microsoft-Erweiterung der Programmiersprache C++ ermöglicht dieser Variablen im Gültigkeitsbereich bleibt und C4288 erinnert Sie daran, dass die erste Deklaration der Variablen nicht verwendet wird.

Finden Sie unter [/Zc: forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) Informationen zur Vorgehensweise beim Angeben der Microsoft-Erweiterungs im **für** Schleifen/Ze.

Im folgende Beispiel wird die C4288 generiert:

```
// C4288.cpp
// compile with: /W1 /c /Zc:forScope-
int main() {
   int i = 0;    // not used in this program
   for (int i = 0 ; ; ) ;
   i++;   // C4288 using for-loop declaration of i
}
```