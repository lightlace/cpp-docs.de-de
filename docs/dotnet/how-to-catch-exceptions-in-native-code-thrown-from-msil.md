---
title: "Gewusst wie: Abfangen von Ausnahmen, die von der MSIL ausgel&#246;st wurden, in systemeigenem Code"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Abfangen von Ausnahmen, ausgelöst von MSIL"
  - "Ausnahmen, Abfangen"
  - "MSIL, Auffangen von Ausnahmen in systemeigenem Code"
ms.assetid: c15afd2b-8505-43bf-8a4a-f1d41532a124
caps.latest.revision: 9
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Abfangen von Ausnahmen, die von der MSIL ausgel&#246;st wurden, in systemeigenem Code
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In systemeigenem Code können Sie die systemeigene C\+\+\-Ausnahme von MSIL abfangen.  Sie können CLR\-Ausnahmen mit `__try` und `__except` abfangen.  
  
 Weitere Informationen finden Sie unter [Strukturierte Ausnahmebehandlung](../cpp/structured-exception-handling-c-cpp.md) und [C\+\+\-Ausnahmebehandlung](../cpp/cpp-exception-handling.md).  
  
## Beispiel  
 Das folgende Beispiel definiert ein Modul mit zwei Features, eine, die eine systemeigene Ausnahme auslöst, und eine weitere, die eine MSIL\-Ausnahme auslöst.  
  
```  
// catch_MSIL_in_native.cpp  
// compile with: /clr /c  
void Test() {  
   throw ("error");  
}  
  
void Test2() {  
   throw (gcnew System::Exception("error2"));  
}  
```  
  
## Beispiel  
 Das folgende Beispiel definiert ein Modul, das einen systemeigenen und MSIL\-Ausnahme abfängt.  
  
```  
// catch_MSIL_in_native_2.cpp  
// compile with: /clr catch_MSIL_in_native.obj  
#include <iostream>  
using namespace std;  
void Test();  
void Test2();  
  
void Func() {  
   // catch any exception from MSIL  
   // should not catch Visual C++ exceptions like this  
   // runtime may not destroy the object thrown  
   __try {  
      Test2();  
   }  
   __except(1) {  
      cout << "caught an exception" << endl;  
   }  
  
}  
  
int main() {  
   // catch native C++ exception from MSIL  
   try {  
      Test();  
   }  
   catch(char * S) {  
      cout << S << endl;  
   }  
   Func();  
}  
```  
  
  **error**  
**fing eine Ausnahme ab**   
## Siehe auch  
 [Exception Handling](../windows/exception-handling-cpp-component-extensions.md)