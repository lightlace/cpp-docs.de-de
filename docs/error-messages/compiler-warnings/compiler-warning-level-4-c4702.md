---
title: Compilerwarnung (Stufe 4) C4702
ms.date: 11/04/2016
f1_keywords:
- C4702
helpviewer_keywords:
- C4702
ms.assetid: d8198c1e-8762-42a6-9e6b-cb568b7a1686
ms.openlocfilehash: 5e46bfef925f999ed7f04b5bbe7c88800209ed14
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74990645"
---
# <a name="compiler-warning-level-4-c4702"></a>Compilerwarnung (Stufe 4) C4702

nicht erreichbarer Code

Diese Warnung ist das Ergebnis der compilerübereinstimmungs-Arbeit, die für Visual Studio .NET 2003: nicht erreichbarer Code ausgeführt wurde. Wenn der Compiler (Back-End) nicht erreichbaren Code erkennt, generiert er C4702, eine Warnung der Stufe 4.

Entfernen Sie für Code, der in Visual Studio .NET 2003-und Visual Studio .NET-Versionen von C++Visual Studio gültig ist, den nicht erreichbaren Code, oder stellen Sie sicher, dass der gesamte Quellcode durch einen bestimmten Ausführungs Verlauf erreichbar ist.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4702 generiert.

```cpp
// C4702.cpp
// compile with: /W4
#include <stdio.h>

int main() {
   return 1;
   printf_s("I won't print.\n");   // C4702 unreachable
}
```

## <a name="example"></a>Beispiel

Beim Kompilieren mit **/GX**, **/EHC**, **/EHsc**oder **/EHac** und der Verwendung externer c-Funktionen kann der Code nicht erreichbar sein, da externe c-Funktionen nicht ausgelöst werden, sodass der catch-Block nicht erreichbar ist.  Wenn Sie der Meinung sind, dass diese Warnung ungültig ist, weil eine Funktion eine Ausnahme auslösen kann, kompilieren Sie mit **/EHa** oder **/EHS**, abhängig von der ausgelösten Ausnahme.

Weitere Informationen finden Sie unter [/eh (Ausnahme Behandlungsmodell)](../../build/reference/eh-exception-handling-model.md) .

Im folgenden Beispiel wird C4702 generiert.

```cpp
// C4702b.cpp
// compile with: /W4 /EHsc
#include <iostream>

using namespace std;
extern "C" __declspec(dllexport) void Function2(){}

int main() {
   try {
      Function2();
   }
   catch (...) {
      cout << "Exp: Function2!" << endl;   // C4702
   }
}
```
