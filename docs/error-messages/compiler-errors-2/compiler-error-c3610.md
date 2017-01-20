---
title: "Compilerfehler C3610"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C3610"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3610"
ms.assetid: 9349a348-9d37-4a00-9eab-481039268d31
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3610
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Werttyp': Der Werttyp muss geschachtelt werden, bevor die 'Methode'\-Methode aufgerufen werden kann  
  
 Ein Werttyp befindet sich standardmäßig nicht auf dem verwalteten Heap.  Bevor Sie Methoden aus .NET Runtime\-Klassen, z. B. `Object`, aufrufen können, müssen Sie den Werttyp auf den verwalteten Heap verschieben.  
  
 C3610 ist nur mit **\/clr:oldSyntax** erreichbar.  
  
 Im folgenden Beispiel wird C3610 generiert:  
  
```  
// C3610.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
  
__value class A {};  
  
int main() {  
   A a;  
   a.GetType(); // C3610  
  
   // OK  
   __box A* ovar = __box(a);  
   ovar->GetType();  
}  
```