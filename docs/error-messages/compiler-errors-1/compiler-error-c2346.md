---
title: "Compilerfehler C2346"
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
  - "C2346"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2346"
ms.assetid: 246145be-5645-4cd6-867c-e3bc39e33dca
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2346
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion' kann nicht als systemeigen kompiliert werden: Grund  
  
 Der Compiler konnte keine Funktion zu MSIL kompilieren.  
  
 Weitere Informationen finden Sie unter [managed, unmanaged](../../preprocessor/managed-unmanaged.md) und [\/clr \(Common Language Runtime\-Kompilierung\)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
### So beheben Sie diesen Fehler  
  
1.  Entfernen Sie den Code in der Funktion, der nicht zu MSIL kompiliert werden kann.  
  
2.  Kompilieren Sie das Modul nicht mit **\/clr**, und kennzeichnen Sie die Funktion nicht mit dem unmanaged\-Pragma als nicht verwaltet.  
  
## Beispiel  
 Im folgenden Beispiel wird C2346 generiert.  
  
```  
// C2346.cpp  
// processor: x86  
// compile with: /clr   
// C2346 expected  
struct S  
{  
   S()  
   {  
      { __asm { nop } }  
   }  
   virtual __clrcall ~S() { }  
};  
  
void main()  
{  
   S s;  
}  
```