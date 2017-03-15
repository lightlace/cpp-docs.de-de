---
title: "Compilerwarnung (Stufe 4) C4702 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4702"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4702"
ms.assetid: d8198c1e-8762-42a6-9e6b-cb568b7a1686
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerwarnung (Stufe 4) C4702
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Unerreichbarer Code  
  
 Diese Warnung resultiert aus einer Verbesserung der Compilerkonformität in Visual Studio .NET 2003, die in Bezug auf unerreichbaren Code vorgenommen wurde.  Wenn der Compiler \(Back\-End\) unerreichbaren Code ermittelt, gibt er C4702 aus, eine Warnung der Stufe 4.  
  
 Bei Code, der sowohl in der Visual Studio .NET 2003\-Version als auch in der Visual Studio .NET\-Version von Visual C\+\+ gültig sein soll, entfernen Sie den unerreichbaren Code oder stellen sicher, dass der gesamte Quellcode im Ausführungsfluss berücksichtigt wird.  
  
## Beispiel  
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
  
## Beispiel  
 Wenn Sie mit **\/GX**, **\/EHc**, **\/EHsc** oder  **\/EHac** kompilieren und externe C\-Funktionen verwenden, kann dies zu unerreichbarem Code führen. Dies ist der Fall, da angenommen wird, dass von externen C\-Funktionen keine Ausnahmen ausgelöst werden, sodass der catch\-Block unerreichbar ist.  Wenn Sie glauben, dass diese Warnung ungültig ist, da eine Funktion Ausnahmen auslösen kann, kompilieren Sie abhängig von der ausgelösten Ausnahme mit **\/EHa** oder **\/EHs**.  
  
 Weitere Informationen finden Sie unter [\/EH \(Ausnahmebehandlungsmodell\)](../../build/reference/eh-exception-handling-model.md).  
  
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