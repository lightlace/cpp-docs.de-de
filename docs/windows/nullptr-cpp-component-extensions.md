---
title: "nullptr  (C++ Component Extensions)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__nullptr keyword (C++)"
  - "nullptr keyword [C++]"
ms.assetid: 594cfbf7-06cb-4366-9ede-c0b703e1d095
caps.latest.revision: 24
caps.handback.revision: "22"
ms.author: "mblome"
manager: "ghogen"
---
# nullptr  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das `nullptr`\-Schlüsselwort stellt einen *NULL\-Zeiger\-Wert dar*.  Verwenden Sie einen NULL\-Zeiger\-Wert, um anzugeben, dass ein Objekthandle innerer Zeiger, oder systemeigener Zeigertyp nicht auf ein Objekt zeigt.  
  
 Verwenden Sie `nullptr` entweder mit verwaltet oder systemeigenen Code.  Die Compiler verwenden aber unterschiedliche Anweisungen für die verwalteten und systemeigenen NULL\-Zeiger\-Werte.  Informationen zum Verwenden der ISO\-Standard\-C\+\+\-Version dieses Schlüsselworts, finden Sie unter [nullptr](../cpp/nullptr.md).  
  
 Das Schlüsselwort `__nullptr` ist ein Microsoft\-Besondereschlüsselwort, das dieselbe Bedeutung wie `nullptr` aufweist, sondern gilt nur für systemeigenen Code.  Wenn Sie systemeigenen C\/C\+\+\-Code mit `nullptr` verwenden und dann mit der [\/clr](../build/reference/clr-common-language-runtime-compilation.md)\-Compileroption kompilieren, kann der Compiler nicht ermitteln, ob `nullptr` einen systemeigenen oder verwalteten einem NULL\-Zeiger\-Wert angibt.  Um dem Compiler Ihre Absicht verständlich zu machen, verwenden Sie `nullptr` um ein verwaltetes Wert oder `__nullptr` anzugeben um einen systemeigenen Wert anzugeben.  
  
 Das Schlüsselwort `nullptr` ist `Nothing` in Visual Basic und `null` in C\# entspricht.  
  
## Verwendung  
 Das `nullptr`\-Schlüsselwort kann verwendet werden, wo ein Handle systemeigener Zeiger, oder Funktionsargument kann verwendet werden.  
  
 Das Schlüsselwort `nullptr` ist kein Typ und nicht für unterstützt:  
  
-   [sizeof](../cpp/sizeof-operator.md)  
  
-   [typeid](../cpp/typeid-operator.md)  
  
-   `throw nullptr` \(wenn `throw (Object^)nullptr;` verwendet wird\)  
  
 Das `nullptr`\-Schlüsselwort kann in der Initialisierung der folgenden Zeigertypen verwendet werden:  
  
-   Systemeigener Zeiger  
  
-   Windows Runtime\-Handle  
  
-   Verwaltetes Handle  
  
-   Verwalteter innerer Zeiger  
  
 Das `nullptr`\-Schlüsselwort kann verwendet werden, um zu testen, wenn ein Handleverweis Zeiger\- oder NULL ist, bevor der Verweis verwendet wird.  
  
 Funktionsaufrufe mit Sprachen, die NULL\-Zeiger\-Werte zur Fehlerprüfung verwenden, sollten korrekt interpretiert werden.  
  
 Sie können einen Handletyp nicht Null initialisieren; nur `nullptr` kann verwendet werden.  Zuweisung der Konstanten 0 zu einem Objekt erzeugt geschachteltes `Int32` und eine Umwandlung in `Object^`.  
  
## Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, dass immer zusammen mit dem `nullptr`\-Schlüsselwort verwendet werden kann, ein Handle oder systemeigener Zeiger Funktionsargument verwendet werden kann.  Und das Beispiel zeigen, dass das `nullptr`\-Schlüsselwort verwendet werden kann, um einen Verweis zu überprüfen, bevor sie verwendet wird.  
  
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
  
## Beispiel  
 **Beispiel**  
  
 Im folgenden Codebeispiel wird dies `nullptr` und kann null auf systemeigene Zeiger synonym verwendet werden.  
  
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
  
  **pMyClass \=\= nullptr**  
 **pMyClass \=\= 0**  
 **pMyClass \=\= nullptr**  
 **pMyClass \=\= 0**   
## Beispiel  
 **Beispiel**  
  
 Das folgende Codebeispiel zeigt, dass `nullptr` während ein Handle zu einem Typ oder einem systemeigenen Zeiger zu einem Typ interpretiert wird.  Im Fall der Funktionsüberladung mit Handles zu den verschiedenen Arten, wird einem Mehrdeutigkeitsfehler generiert.  `nullptr` würde zu explizit einen Typ umgewandelt werden müssen.  
  
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
  
## Beispiel  
 **Beispiel**  
  
 Im folgenden Codebeispiel wird, an, dass das Umwandeln von `nullptr` ermöglicht wird gibt einen Zeiger oder ein Handle für Umwandlungstyp zurück, der den `nullptr`\-Wert enthält.  
  
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
  
## Beispiel  
 **Beispiel**  
  
 Das folgende Codebeispiel zeigt, dass `nullptr` als Funktionsparameter verwendet werden kann.  
  
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
  
  **Testen**   
## Beispiel  
 **Beispiel**  
  
 Im folgenden Codebeispiel ist die, wenn Handles deklariert werden und nicht explizit initialisiert, diese werden standardmäßig dar, der an `nullptr` initialisiert wird.  
  
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
  
  **NULL**   
## Beispiel  
 **Beispiel**  
  
 Das folgende Codebeispiel zeigt, dass `nullptr` an einen systemeigenen Zeiger zugewiesen werden kann, wenn Sie mit **\/clr** kompilieren.  
  
```  
// mcpp_nullptr_6.cpp  
// compile with: /clr  
int main() {  
   int * i = 0;  
   int * j = nullptr;  
}  
```  
  
## Voraussetzungen  
 Compileroption: \(Nicht erforderlich; unterstützt von allen Codegenerierungsoptionen, einschließlich **\/ZW** und **\/clr**\)  
  
## Siehe auch  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)   
 [nullptr](../cpp/nullptr.md)