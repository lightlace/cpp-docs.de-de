---
title: Zeichenfolge (Komponentenerweiterungen für C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- string support with /clr
- /clr compiler option [C++], string support
ms.assetid: c695f965-9be0-4e20-9661-373bfee6557e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cfab95c400aad949f06a559fffbdb42993910bb7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="string--c-component-extensions"></a>Zeichenfolge (Komponentenerweiterungen für C++)
Der Visual C++-Compiler unterstützt *Zeichenfolgen*, sind Objekte, die Text als eine Folge von Zeichen darstellen. Visual C++ unterstützt Zeichenfolgenvariablen, deren Wert implizit ist, und Literale, deren Wert eine explizite Zeichenfolge in Anführungszeichen ist.  
  
## <a name="all-runtimes"></a>Alle Laufzeiten  
 Die Windows-Runtime und die Common Language Runtime stellen Zeichenfolgen als Objekte dar, deren belegter Speicher automatisch verwaltet wird. Das heißt, dass es nicht erforderlich ist, den Arbeitsspeicher für eine Zeichenfolge explizit zu verwerfen, wenn die Zeichenfolgenvariable außerhalb des gültigen Bereichs liegt oder die Anwendung beendet wird. Um anzugeben, dass die Lebensdauer eines Zeichenfolgenobjekts automatisch verwaltet werden soll, deklarieren Sie den String-Datentyp mit der [Handle-to-Object (^)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md) Modifizierer.  
  
## <a name="windows-runtime"></a>Windows-Runtime  
 Die Windows-Runtime-Architektur erfordert von Visual C++, den `String`-Datentyp im `Platform`-Namespace zu implementieren. Zur Vereinfachung stellt Visual C++ den `string`-Datentyp, der synonym mit `Platform::String` ist, auch im `default`-Namespace bereit.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
// compile with /ZW  
using namespace Platform;  
using namespace default;  
   Platform::String^ MyString1 = "The quick brown fox";  
   String^ MyString2 = "jumped over the lazy dog.";  
   String^ MyString3 = "Hello, world!";  
  
```  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen und Beispiele zu Zeichenfolgen finden Sie unter [Platform:: String, Std:: wstring und Literale (Plattform)](http://msdn.microsoft.com/en-us/ec92fbc6-edf3-4137-a85e-8e29bdb857a8)  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: **/ZW**  
  
## <a name="common-language-runtime"></a>Common Language Runtime  
 In diesem Thema wird erläutert, wie der Visual C++-Compiler Zeichenfolgenliterale verarbeitet, bei der Ausführung mit der **"/ CLR"** -Compileroption. Mit **"/ CLR"**, müssen Sie auch verwenden, die common Language Runtime (CLR), C + c++ / CLI-Syntax und verwaltete Objekte. Weitere Informationen zu **"/ CLR"**, finden Sie unter [/CLR (Common Language Runtime-Kompilierung)](../build/reference/clr-common-language-runtime-compilation.md).  
  
 Beim Kompilieren mit **"/ CLR"**, konvertiert der Compiler Zeichenfolgenliterale in Zeichenfolgen des Typs <xref:System.String>. Um die Abwärtskompatibilität mit vorhandenem Code beizubehalten, bestehen dabei die folgenden beiden Ausnahmen:  
  
-   Ausnahmebehandlung. Wenn ein Zeichenfolgenliteral ausgelöst wird, fängt der Compiler dieses auch als Zeichenfolgenliteral ab.  
  
-   Vorlagenableitung. Wenn ein Zeichenfolgenliteral als Vorlagenargument übergeben wird, wird es durch den Compiler nicht in <xref:System.String> konvertiert. Hinweis: Zeichenfolgenliterale, die als generisches Argument übergeben werden, werden zu <xref:System.String> höhergestuft.  
  
 Der Compiler verfügt auch über integrierte Unterstützung für drei Operatoren, die Sie überschreiben können, um ihr Verhalten anzupassen:  
  
-   System::String-^ Operator + (System::String, System::String);  
  
-   System::String ^ operator +( System::Object, System::String);  
  
-   System::String ^ operator +( System::String, System::Object);  
  
 Wenn ein <xref:System.String> übergeben wird, wird das Objekt (mit ToString) mit der Zeichenfolge vom Compiler geschachtelt und ggf. verkettet.  
  
> [!NOTE]
>  Das Caretzeichen ("^") gibt an, dass die deklarierte Variable ein Handle zu einem verwalteten C++/CLI-Objekt ist.  
  
 Weitere Informationen finden Sie unter [Zeichenfolgen- und Zeichenliterale](../cpp/string-and-character-literals-cpp.md).  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: **/clr**  
  
### <a name="examples"></a>Beispiele  
 **Beispiel**  
  
 Im folgenden Codebeispiel wird das Verketten und Vergleichen von Zeichenfolgen veranschaulicht.  
  
```cpp  
// string_operators.cpp  
// compile with: /clr  
// In the following code, the caret ("^") indicates that the   
// declared variable is a handle to a C++/CLI managed object.  
using namespace System;  
  
int main() {  
   String ^ a = gcnew String("abc");  
   String ^ b = "def";   // same as gcnew form  
   Object ^ c = gcnew String("ghi");  
  
   char d[100] = "abc";  
  
   // variables of System::String returning a System::String  
   Console::WriteLine(a + b);  
   Console::WriteLine(a + c);  
   Console::WriteLine(c + a);  
  
   // accessing a character in the string  
   Console::WriteLine(a[2]);  
  
   // concatenation of three System::Strings  
   Console::WriteLine(a + b + c);  
  
   // concatenation of a System::String and string literal  
   Console::WriteLine(a + "zzz");  
  
   // you can append to a System::String ^  
   Console::WriteLine(a + 1);  
   Console::WriteLine(a + 'a');  
   Console::WriteLine(a + 3.1);  
  
   // test System::String ^ for equality  
   a += b;  
   Console::WriteLine(a);  
   a = b;  
   if (a == b)  
      Console::WriteLine("a and b are equal");  
  
   a = "abc";  
   if (a != b)  
      Console::WriteLine("a and b are not equal");  
  
   // System:String ^ and tracking reference  
   String^% rstr1 = a;  
   Console::WriteLine(rstr1);  
  
   // testing an empty System::String ^  
   String ^ n;  
   if (n == nullptr)  
      Console::WriteLine("n is empty");  
}  
```  
  
 **Ausgabe**  
  
```Output  
abcdef  
  
abcghi  
  
ghiabc  
  
c  
  
abcdefghi  
  
abczzz  
  
abc1  
  
abc97  
  
abc3.1  
  
abcdef  
  
a and b are equal  
  
a and b are not equal  
  
abc  
  
n is empty  
```  
  
 **Beispiel**  
  
 Im folgenden Beispiel wird gezeigt, dass Sie die vom Compiler bereitgestellten Operatoren überladen können und vom Compiler eine Funktionsüberladung basierend auf dem <xref:System.String>-Typ gefunden wird.  
  
```cpp  
// string_operators_2.cpp  
// compile with: /clr  
using namespace System;  
  
// a string^ overload will be favored when calling with a String  
void Test_Overload(const char * a) {   
   Console::WriteLine("const char * a");   
}  
void Test_Overload(String ^ a) {   
   Console::WriteLine("String ^ a");   
}  
  
// overload will be called instead of compiler defined operator  
String ^ operator +(String ^ a, String ^ b) {  
   return ("overloaded +(String ^ a, String ^ b)");  
}  
  
// overload will be called instead of compiler defined operator  
String ^ operator +(Object ^ a, String ^ b) {  
   return ("overloaded +(Object ^ a, String ^ b)");  
}  
  
// overload will be called instead of compiler defined operator  
String ^ operator +(String ^ a, Object ^ b) {  
   return ("overloaded +(String ^ a, Object ^ b)");  
}  
  
int main() {  
   String ^ a = gcnew String("abc");  
   String ^ b = "def";   // same as gcnew form  
   Object ^ c = gcnew String("ghi");  
  
   char d[100] = "abc";  
  
   Console::WriteLine(a + b);  
   Console::WriteLine(a + c);  
   Console::WriteLine(c + a);  
  
   Test_Overload("hello");  
   Test_Overload(d);  
}  
```  
  
 **Ausgabe**  
  
```Output  
overloaded +(String ^ a, String ^ b)   
  
overloaded +(String ^ a, Object ^ b)   
  
overloaded +(Object ^ a, String ^ b)   
  
String ^ a  
  
const char * a  
```  
  
 **Beispiel**  
  
 Im folgenden Beispiel wird gezeigt, dass der Compiler zwischen systemeigenen Zeichenfolgen und <xref:System.String>-Zeichenfolgen unterscheidet.  
  
```cpp  
// string_operators_3.cpp  
// compile with: /clr  
using namespace System;  
int func() {  
   throw "simple string";   // const char *  
};  
  
int func2() {  
   throw "string" + "string";   // returns System::String  
};  
  
template<typename T>  
void func3(T t) {  
   Console::WriteLine(T::typeid);  
}  
  
int main() {  
   try {  
      func();  
   }  
   catch(char * e) {  
      Console::WriteLine("char *");  
   }  
  
   try {  
      func2();  
   }  
   catch(String^ str) {  
      Console::WriteLine("String^ str");  
   }  
  
   func3("string");   // const char *  
   func3("string" + "string");   // returns System::String  
}  
```  
  
 **Ausgabe**  
  
```Output  
char *  
  
String^ str  
  
System.SByte*  
  
System.String  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md)   
 [Zeichenfolgen- und Zeichenliterale](../cpp/string-and-character-literals-cpp.md)   
 [/clr (Common Language Runtime-Kompilierung)](../build/reference/clr-common-language-runtime-compilation.md)