---
title: "managed, unmanaged | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.unmanaged"
  - "managed_CPP"
  - "unmanaged_CPP"
  - "vc-pragma.managed"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "managed-Pragma"
  - "Pragmas, Verwaltet"
  - "Pragmas, Nicht verwaltet"
  - "unmanaged-Pragma"
ms.assetid: f072ddcc-e1ec-408a-8ce1-326ddb60e4a4
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# managed, unmanaged
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Aktivieren Sie die Steuerung auf Funktionsebene für Kompilierfunktionen als verwaltet oder nicht verwaltet.  
  
## Syntax  
  
```  
  
        #pragma managed  
#pragma unmanaged  
#pragma managed([push,] on | off)  
#pragma managed(pop)  
```  
  
## Hinweise  
 Die [\/clr](../build/reference/clr-common-language-runtime-compilation.md)\-Compileroption stellt eine Steuerung auf Modulebene für Kompilierfunktionen als verwaltet oder nicht verwaltet bereit.  
  
 Eine nicht verwaltete Funktion wird für die systemeigene Plattform kompiliert, und die Ausführung dieses Teils des Programms wird von der Common Language Runtime an die systemeigene Plattform übergeben.  
  
 Funktionen werden standardmäßig als verwaltet kompiliert, wenn **\/clr** verwendet wird.  
  
 Beim Anwenden dieser Pragmas:  
  
-   Fügen Sie das Pragma hinzu, das einer Funktion vorangeht, sich jedoch nicht innerhalb eines Funktionsrumpfs befindet.  
  
-   Fügen Sie das Pragma nach `#include`\-Anweisungen hinzu.  Verwenden Sie diese Pragmas nicht vor `#include`\-Anweisungen.  
  
 Der Compiler ignoriert die `managed`\- und `unmanaged`\-Pragmas, wenn **\/clr** nicht in der Kompilierung verwendet wird.  
  
 Wenn eine Vorlagenfunktion instanziiert wird, bestimmt der Pragmazustand zum Zeitpunkt der Definition, ob die Vorlage verwaltet oder nicht verwaltet ist.  
  
 Weitere Informationen finden Sie unter [Initialisierung gemischter Assemblys](../dotnet/initialization-of-mixed-assemblies.md).  
  
## Beispiel  
  
```  
// pragma_directives_managed_unmanaged.cpp  
// compile with: /clr  
#include <stdio.h>  
  
// func1 is managed  
void func1() {  
   System::Console::WriteLine("In managed function.");  
}  
  
// #pragma unmanaged  
// push managed state on to stack and set unmanaged state  
#pragma managed(push, off)  
  
// func2 is unmanaged  
void func2() {  
   printf("In unmanaged function.\n");  
}  
  
// #pragma managed  
#pragma managed(pop)  
  
// main is managed  
int main() {  
   func1();  
   func2();  
}  
```  
  
  **In verwalteter Funktion.  In nicht verwalteter Funktion.**    
## Siehe auch  
 [Pragma\-Direktiven und das \_\_Pragma\-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)