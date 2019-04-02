---
title: 'Vorgehensweise: Abfangen von Ausnahmen in nativem Code, die von der MSIL ausgelöst'
ms.date: 11/04/2016
helpviewer_keywords:
- exceptions, catching
- catching exceptions, thrown from MSIL
- MSIL, catching exceptions in native code
ms.assetid: c15afd2b-8505-43bf-8a4a-f1d41532a124
ms.openlocfilehash: 95ce7a2afabc34ea78376b12da61f419dab4af34
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58776556"
---
# <a name="how-to-catch-exceptions-in-native-code-thrown-from-msil"></a>Vorgehensweise: Abfangen von Ausnahmen in nativem Code, die von der MSIL ausgelöst

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

[Ausnahmebehandlung](../extensions/exception-handling-cpp-component-extensions.md)
