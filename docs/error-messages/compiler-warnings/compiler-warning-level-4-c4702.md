---
title: Compilerwarnung (Stufe 4) C4702 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4702
dev_langs:
- C++
helpviewer_keywords:
- C4702
ms.assetid: d8198c1e-8762-42a6-9e6b-cb568b7a1686
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 29c2d6b0328fd8dd4cd6f9a226253036b62d03ab
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4702"></a>Compilerwarnung (Stufe 4) C4702
unerreichbarer code  
  
 Diese Warnung ist das Ergebnis des konformitätsverbesserung für Compiler, die für Visual Studio .NET 2003 durchgeführt wurde: unerreichbarer Code. Wenn der Compiler (Back-End) unerreichbarer Code erkennt, generiert er C4702, eine Warnung der Stufe 4.  
  
 Entfernen Sie für Code, der in der Visual Studio .NET 2003 und die Visual Studio .NET Versionen von Visual C++ gültig ist den Code nicht erreichbaren oder nicht gewährleisten Sie, dass alle Quellcode durch einige Ausführungsablauf erreichbar ist.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4702 generiert.  
  
```  
// C4702.cpp  
// compile with: /W4  
#include <stdio.h>  
  
int main() {  
   return 1;  
   printf_s("I won't print.\n");   // C4702 unreachable  
}  
```  
  
## <a name="example"></a>Beispiel  
 Beim Kompilieren mit **/GX**, **/EHc**, **/EHsc /**, oder **EHac** und Verwenden von "extern" C-Funktionen, Code kann ggf. nicht mehr erreichbar da "extern" C Funktionen sind davon ausgegangen, dass nicht auslösen, der Catch-Block ist daher nicht erreichbar.  Wenn Sie glauben, dass diese Warnung ist ungültig, da eine Funktion Ausnahmen auslösen kann, kompilieren Sie mit **/EHa** oder **/EHs**, je nachdem, auf die Ausnahme ausgelöst wird.  
  
 Weitere Informationen finden Sie unter [/EH (Ausnahmebehandlungsmodell)](../../build/reference/eh-exception-handling-model.md) für Weitere Informationen.  
  
 Im folgenden Beispiel wird C4702 generiert.  
  
```  
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