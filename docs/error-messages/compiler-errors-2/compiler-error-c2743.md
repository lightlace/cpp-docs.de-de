---
title: "Compilerfehler C2743 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2743"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2743"
ms.assetid: 644cd444-21d2-471d-a176-f5f52c5a0b73
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2743
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Typ': catch von systemeigenem Typ mit \_\_clrcall\-Destruktor oder copy\-Konstruktor nicht möglich  
  
 Ein mit **\/clr** \(nicht mit **\/clr:pure**\) kompiliertes Modul hat versucht, eine Ausnahme systemeigenen Typs aufzufangen, wobei der Destruktor bzw. copy\-Konstruktor des Typs die \_`_clrcall`\-Aufrufkonvention verwendet.  
  
 Von einer mit **\/clr** \(nicht **\/clr:pure**\) kompilierten Ausnahmebehandlung wird erwartet, dass es sich bei den Memberfunktionen in einem systemeigenen Typ um [\_\_cdecl](../../cpp/cdecl.md) und nicht um [\_\_clrcall](../../cpp/clrcall.md) handelt.  Systemeigene Typen mit Memberfunktionen, die die `__clrcall`\-Aufrufkonvention verwenden, können nicht in einem mit **\/clr** kompilierten Modul abgefangen werden.  
  
 Weitere Informationen finden Sie unter [\/clr \(Common Language Runtime\-Kompilierung\)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C2743 generiert.  
  
```  
// C2743.cpp  
// compile with: /clr  
public struct S {  
   __clrcall ~S() {}  
};  
  
public struct T {  
   ~T() {}  
};  
  
int main() {  
   try {}  
   catch(S) {}   // C2743  
   // try the following line instead  
   // catch(T) {}  
  
   try {}  
   catch(S*) {}   // OK  
}  
```