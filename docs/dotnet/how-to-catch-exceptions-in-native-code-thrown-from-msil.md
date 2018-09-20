---
title: 'Vorgehensweise: Abfangen von Ausnahmen in nativem Code, die von der MSIL ausgelöst | Microsoft-Dokumentation'
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
ms.openlocfilehash: f7022bffa7dd5a8524c614760fa2a36b2884b973
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46379462"
---
# <a name="how-to-catch-exceptions-in-native-code-thrown-from-msil"></a>Gewusst wie: Abfangen von Ausnahmen, die von der MSIL ausgelöst wurden, in nativem Code

In nativem Code können Sie native C++-Ausnahme von der MSIL abfangen.  Sie können auch mit CLR-Ausnahmen abfangen `__try` und `__except`.

Weitere Informationen finden Sie unter [Structured Exception Handling (C/C++)](../cpp/structured-exception-handling-c-cpp.md) und [C++-Ausnahmebehandlung](../cpp/cpp-exception-handling.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel definiert ein Modul mit zwei Funktionen, eine, die von einem systemeigenen Ausnahme ausgelöst und eine, die eine MSIL-Ausnahme auslöst.

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

Im folgende Beispiel definiert ein Modul, das einen einheitlichen und MSIL-Ausnahme abfängt.

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