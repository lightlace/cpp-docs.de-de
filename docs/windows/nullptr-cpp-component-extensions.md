---
title: Nullptr (Komponentenerweiterungen für C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- __nullptr keyword (C++)
- nullptr keyword [C++]
ms.assetid: 594cfbf7-06cb-4366-9ede-c0b703e1d095
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 33a276c383618531103a76b1f20c6ad478d57c10
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33880687"
---
# <a name="nullptr--c-component-extensions"></a>nullptr (Komponentenerweiterungen für C++)
Die `nullptr` Schlüsselwort stellt einen *null-Zeigerwert*. Verwenden Sie einen null-Zeiger-Wert, um anzugeben, dass ein Objekthandle, innerer Zeiger oder ein systemeigener Zeiger nicht auf ein Objekt verweist.  
  
 Verwendung `nullptr` mit verwaltetem oder systemeigenem Code. Der Compiler gibt geeignete, aber unterschiedliche Anweisungen für verwalteten und systemeigenen null-Zeiger-Werte. Informationen zur Verwendung der ISO C++ Standardversion des this-Schlüsselwort finden Sie unter [Nullptr](../cpp/nullptr.md).  
  
 Die `__nullptr` -Schlüsselwort ist ein Microsoft-spezifische-Schlüsselwort, das die gleiche Bedeutung wie hat `nullptr`, sondern gilt für nur nativen Code. Bei Verwendung von `nullptr` mit systemeigenen C/C++-code, und kompilieren Sie mit der ["/ CLR"](../build/reference/clr-common-language-runtime-compilation.md) -Compileroption, der Compiler nicht ermitteln, ob `nullptr` gibt einen Wert für systemeigenen oder verwalteten null-Zeiger. Um Ihre Absicht klar, auf dem Compiler zu machen, verwenden `nullptr` einen verwalteten Wert angeben oder `__nullptr` einen einheitlichen Wert angeben.  
  
 Die `nullptr` -Schlüsselwort ist äquivalent zu `Nothing` in Visual Basic und `null` in C# geschrieben.  
  
## <a name="usage"></a>Verwendung  
 Die `nullptr` -Schlüsselwort kann verwendet werden, ein Handle, systemeigene Zeiger oder Funktionsargument verwendet werden kann.  
  
 Die `nullptr` -Schlüsselwort ist kein Typ und wird nicht unterstützt, für die Verwendung mit:  
  
-   [sizeof](../cpp/sizeof-operator.md)  
  
-   [typeid](../cpp/typeid-operator.md)  
  
-   `throw nullptr` (obwohl `throw (Object^)nullptr;` funktioniert)  
  
 Die `nullptr` -Schlüsselwort kann verwendet werden, bei der Initialisierung des folgenden Zeigertypen:  
  
-   Systemeigener Zeiger  
  
-   Windows-Runtime-handle  
  
-   Verwaltete handle  
  
-   Verwaltete innerer Zeiger  
  
 Die `nullptr` -Schlüsselwort kann verwendet werden, um festzustellen, ob ein Zeiger oder Handle Objektverweis null ist, bevor der Verweis verwendet wird.  
  
 Funktionsaufrufe zwischen Sprachen, die null-Zeiger-Werte für die Überprüfung von Fehlern verwenden, sollten richtig interpretiert werden.  
  
 Sie können nicht initialisiert werden, ein Handle auf 0 (null); nur `nullptr` kann verwendet werden. Zuweisung von Konstanten 0 in ein Objekthandle erzeugt ein geschachtelter `Int32` und eine Umwandlung in den `Object^`.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, dass die `nullptr` -Schlüsselwort kann verwendet werden, wo ein Handle, systemeigene Zeiger oder Funktionsargument genutzt werden. Im Beispiel wird veranschaulicht, die die `nullptr` -Schlüsselwort kann verwendet werden, um einen Verweis zu überprüfen, bevor sie verwendet wird.  
  
```  
// mcpp_nullptr.cpp  
// compile with: /clr  
value class V {};  
ref class G {};  
void f(System::Object ^) {}  
  
int main() {  
// Native pointer.  
   int *pN = nullptr;  
// Managed handle.  
   G ^pG = nullptr;  
   V ^pV1 = nullptr;  
// Managed interior pointer.  
   interior_ptr<V> pV2 = nullptr;  
// Reference checking before using a pointer.  
   if (pN == nullptr) {}  
   if (pG == nullptr) {}  
   if (pV1 == nullptr) {}  
   if (pV2 == nullptr) {}  
// nullptr can be used as a function argument.  
   f(nullptr);   // calls f(System::Object ^)  
}  
```  
  
## <a name="example"></a>Beispiel  
 **Beispiel**  
  
 Das folgende Codebeispiel zeigt, dass `nullptr` und 0 (null) für systemeigenen Zeiger synonym verwendet werden kann.  
  
```  
// mcpp_nullptr_1.cpp  
// compile with: /clr  
class MyClass {  
public:  
   int i;  
};  
  
int main() {  
   MyClass * pMyClass = nullptr;  
   if ( pMyClass == nullptr)  
      System::Console::WriteLine("pMyClass == nullptr");  
  
   if ( pMyClass == 0)  
      System::Console::WriteLine("pMyClass == 0");  
  
   pMyClass = 0;  
   if ( pMyClass == nullptr)  
      System::Console::WriteLine("pMyClass == nullptr");  
  
   if ( pMyClass == 0)  
      System::Console::WriteLine("pMyClass == 0");  
}  
```  
  
 **Ausgabe**  
  
```Output  
pMyClass == nullptr  
  
pMyClass == 0  
  
pMyClass == nullptr  
  
pMyClass == 0  
```  
  
## <a name="example"></a>Beispiel  
 **Beispiel**  
  
 Das folgende Codebeispiel zeigt, dass `nullptr` wird als ein Handle für einen beliebigen Typ oder einen systemeigenen Zeiger auf einen beliebigen Typ interpretiert. Im Falle funktionsüberladung mit Handles für verschiedene Typen, wird ein Mehrdeutigkeitsfehler generiert. Die `nullptr` müsste explizit in einen Typ umgewandelt werden.  
  
```  
// mcpp_nullptr_2.cpp  
// compile with: /clr /LD  
void f(int *){}  
void f(int ^){}  
  
void f_null() {  
   f(nullptr);   // C2668  
   // try one of the following lines instead  
   f((int *) nullptr);  
   f((int ^) nullptr);  
}  
```  
  
## <a name="example"></a>Beispiel  
 **Beispiel**  
  
 Im folgenden Codebeispiel wird veranschaulicht, Umwandlung `nullptr` zulässig ist, und gibt ein Zeiger oder Handle an der Cast-Typ, enthält die `nullptr` Wert.  
  
```  
// mcpp_nullptr_3.cpp  
// compile with: /clr /LD  
using namespace System;  
template <typename T>   
void f(T) {}   // C2036 cannot deduce template type because nullptr can be any type  
  
int main() {  
   f((Object ^) nullptr);   // T = Object^, call f(Object ^)  
  
   // Delete the following line to resolve.  
   f(nullptr);  
  
   f(0);   // T = int, call f(int)  
}  
```  
  
## <a name="example"></a>Beispiel  
 **Beispiel**  
  
 Das folgende Codebeispiel zeigt, dass `nullptr` als Funktionsparameter verwendet werden können.  
  
```  
// mcpp_nullptr_4.cpp  
// compile with: /clr  
using namespace System;  
void f(Object ^ x) {  
   Console::WriteLine("test");  
}  
  
int main() {  
   f(nullptr);  
}  
```  
  
 **Ausgabe**  
  
```Output  
test  
```  
  
## <a name="example"></a>Beispiel  
 **Beispiel**  
  
 Im folgenden Codebeispiel wird veranschaulicht, dass Handles deklariert und nicht explizit initialisiert sind, standardmäßig initialisiert sie sind `nullptr`.  
  
```  
// mcpp_nullptr_5.cpp  
// compile with: /clr  
using namespace System;  
ref class MyClass {  
public:  
   void Test() {  
      MyClass ^pMyClass;   // gc type  
      if (pMyClass == nullptr)  
         Console::WriteLine("NULL");  
   }  
};  
  
int main() {  
   MyClass ^ x = gcnew MyClass();  
   x -> Test();  
}  
```  
  
 **Ausgabe**  
  
```Output  
NULL  
```  
  
## <a name="example"></a>Beispiel  
 **Beispiel**  
  
 Das folgende Codebeispiel zeigt, dass `nullptr` kann an einen systemeigenen Zeiger zugewiesen werden, bei der Kompilierung **"/ CLR"**.  
  
```  
// mcpp_nullptr_6.cpp  
// compile with: /clr  
int main() {  
   int * i = 0;  
   int * j = nullptr;  
}  
```  
  
## <a name="requirements"></a>Anforderungen  
 Compileroption: (nicht erforderlich; unterstützt durch alle Codegenerierungsoptionen, einschließlich **/Zw** und **"/ CLR"**)  
  
## <a name="see-also"></a>Siehe auch  
 [Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md)   
 [nullptr](../cpp/nullptr.md)