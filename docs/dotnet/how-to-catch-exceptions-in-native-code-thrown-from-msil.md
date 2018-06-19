---
title: 'Vorgehensweise: Abfangen von Ausnahmen in systemeigenem Code von der MSIL ausgelöst | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- exceptions, catching
- catching exceptions, thrown from MSIL
- MSIL, catching exceptions in native code
ms.assetid: c15afd2b-8505-43bf-8a4a-f1d41532a124
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 3d5c1efde1f98ac3f9fdccb19039373d5cfe6be6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33127876"
---
# <a name="how-to-catch-exceptions-in-native-code-thrown-from-msil"></a>Gewusst wie: Abfangen von Ausnahmen, die von der MSIL ausgelöst wurden, in nativem Code
In systemeigenem Code können Sie systemeigene C++-Ausnahme von MSIL abfangen.  Sie können auch mit CLR-Ausnahmen abfangen `__try` und `__except`.  
  
 Weitere Informationen finden Sie unter [strukturierte Ausnahmebehandlung (C/C++)](../cpp/structured-exception-handling-c-cpp.md) und [C++-Ausnahmebehandlung](../cpp/cpp-exception-handling.md).  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel definiert ein Modul mit zwei Funktionen, eine, die eine systemeigene Ausnahme auslöst und eine andere, die eine MSIL-Ausnahme auslöst.  
  
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
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel definiert ein Modul, das einen einheitlichen und MSIL-Ausnahme abgefangen.  
  
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
  
```Output  
error  
caught an exception  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Ausnahmebehandlung](../windows/exception-handling-cpp-component-extensions.md)