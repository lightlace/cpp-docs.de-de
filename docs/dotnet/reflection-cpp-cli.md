---
title: Reflektion (C + c++ / CLI) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- typeid keyword [C++]
- reflection [C++}, about reflection
- metadata, reflection
- GetType method
- .NET Framework [C++], reflection
- data types [C++], reflection
- reflection [C++}
ms.assetid: 46b6ff4a-e441-4022-8892-78e69422f230
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: fab5bb3c912aeea2598189965d424ba4508cf5c8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="reflection-ccli"></a>Reflektion (C++/CLI)
Die Reflektion ermöglicht die Überprüfung von bekannten Datentypen zur Laufzeit. Sie ermöglicht die Enumeration von Datentypen in einer bestimmten Assembly. Darüber hinaus können Member einer bestimmten Klasse oder eines bestimmten Werttyps erkannt werden. Dies trifft unabhängig davon zu, ob der Typ zur Kompilierungszeit bekannt war bzw. auf ihn verwiesen wurde. Dies macht die Reflektion zu einer nützlichen Funktion für Entwicklungs- und Codeverwaltungstools.  
  
 Beachten Sie, dass der Name der Assembly bereitgestellte den starken Namen (finden Sie unter [erstellen und Verwenden von Assemblys](/dotnet/framework/app-domains/create-and-use-strong-named-assemblies)), die die Assemblyversion, Kultur und Signierungsinformationen enthält. Beachten Sie auch, dass der Name des Namespaces, in dem der Datentyp definiert ist, zusammen mit dem Namen der Basisklasse abgerufen werden kann.  
  
 Am häufigsten wird über die <xref:System.Object.GetType%2A>-Methode auf Reflektionsfunktionen zugegriffen. Diese Methode wird bereitgestellt, indem [System:: Object](https://msdn.microsoft.com/en-us/library/system.object.aspx), aus der alle Garbage Collection-Klassen abgeleitet werden.  
  
 Reflektion einer mit Visual C++-Compiler erstellte .exe ist nur zulässig, wenn die .exe erstellt wird, mit der **/CLR: pure** oder **/CLR: safe** Compileroptionen. Die Compileroptionen **/clr:pure** und **/clr:safe** sind in Visual Studio 2015 veraltet. Finden Sie unter [/CLR (Common Language Runtime-Kompilierung)](../build/reference/clr-common-language-runtime-compilation.md) für Weitere Informationen.  
  
 Themen in diesem Abschnitt:  
  
-   [Vorgehensweise: Implementieren einer Plug-In-Komponentenarchitektur mit Reflektion (C++/CLI)](../dotnet/how-to-implement-a-plug-in-component-architecture-using-reflection-cpp-cli.md)  
  
-   [Vorgehensweise: Auflisten von Datentypen in Assemblys mit Reflektion (C++/CLI)](../dotnet/how-to-enumerate-data-types-in-assemblies-using-reflection-cpp-cli.md)  
  
 Weitere Informationen finden Sie unter [System.Reflection-Namespace](https://msdn.microsoft.com/en-us/library/system.reflection.aspx)  
  
## <a name="example"></a>Beispiel  
 Die `GetType`-Methode gibt einen Zeiger auf ein <xref:System.Type>-Klassenobjekt zurück, das den Typ beschreibt, auf dem das Objekt basiert. (Die **Typ** Objekt enthält keine instanzspezifischen Informationen.) Ein solches Element wäre der vollständige Name des Typs, der wie folgt angezeigt werden kann:  
  
 Der Typname enthält den vollständigen Bereich, in dem der Typ definiert ist, einschließlich Namespace und Darstellung in .NET-Syntax, wobei ein Punkt als Bereichsauflösungsoperator verwendet wird.  
  
```  
// vcpp_reflection.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   String ^ s = "sample string";  
   Console::WriteLine("full type name of '{0}' is '{1}'", s, s->GetType());  
}  
```  
  
```Output  
full type name of 'sample string' is 'System.String'  
```  
  
## <a name="example"></a>Beispiel  
 Werttypen können auch mit der `GetType`-Funktion verwendet werden, müssen jedoch zuerst geschachtelt werden.  
  
```  
// vcpp_reflection_2.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   Int32 i = 100;   
   Object ^ o = i;  
   Console::WriteLine("type of i = '{0}'", o->GetType());  
}  
```  
  
```Output  
type of i = 'System.Int32'  
```  
  
## <a name="example"></a>Beispiel  
 Wie bei der `GetType` -Methode, die [Typeid](../windows/typeid-cpp-component-extensions.md) Operator gibt einen Zeiger auf eine **Typ** Objekt, damit dieser Code den Typnamen, **System. Int32**. Das Anzeigen von Typnamen ist die grundlegendste Funktion der Reflektion, eine möglicherweise hilfreichere Technik besteht jedoch in der Überprüfung oder Erkennung der gültigen Werte für enumerierte Typen. Dies kann geschehen, indem Sie mit der statischen **Enum:: GetNames** -Funktion, die gibt ein Array von Zeichenfolgen, jede einen Enumerationswert in Textform enthält.  Im folgende Beispiel ruft ein Array von Zeichenfolgen, die beschreibt, das die Enumerationswerte für die **Optionen** Enum (CLR) und zeigt sie in einer Schleife.  
  
 Wenn eine vierte Option hinzugefügt wird die **Optionen** Enumeration wird in diesem Code meldet die neue Option ohne erneute Kompilierung aus, selbst wenn die Enumeration in einer separaten Assembly definiert ist.  
  
```  
// vcpp_reflection_3.cpp  
// compile with: /clr  
using namespace System;  
  
enum class Options {   // not a native enum  
   Option1, Option2, Option3  
};  
  
int main() {  
   array<String^>^ names = Enum::GetNames(Options::typeid);  
  
   Console::WriteLine("there are {0} options in enum '{1}'",   
               names->Length, Options::typeid);  
  
   for (int i = 0 ; i < names->Length ; i++)  
      Console::WriteLine("{0}: {1}", i, names[i]);  
  
   Options o = Options::Option2;  
   Console::WriteLine("value of 'o' is {0}", o);  
}  
```  
  
```Output  
there are 3 options in enum 'Options'  
0: Option1  
1: Option2  
2: Option3  
value of 'o' is Option2  
```  
  
## <a name="example"></a>Beispiel  
 Das `GetType`-Objekt unterstützt eine Reihe von Membern und Eigenschaften, die zur Überprüfung eines Typs verwendet werden können. Durch diesen Code werden einige dieser Informationen abgerufen und angezeigt:  
  
```  
// vcpp_reflection_4.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   Console::WriteLine("type information for 'String':");  
   Type ^ t = String::typeid;  
  
   String ^ assemblyName = t->Assembly->FullName;  
   Console::WriteLine("assembly name: {0}", assemblyName);  
  
   String ^ nameSpace = t->Namespace;  
   Console::WriteLine("namespace: {0}", nameSpace);  
  
   String ^ baseType = t->BaseType->FullName;  
   Console::WriteLine("base type: {0}", baseType);  
  
   bool isArray = t->IsArray;  
   Console::WriteLine("is array: {0}", isArray);  
  
   bool isClass = t->IsClass;  
   Console::WriteLine("is class: {0}", isClass);  
}  
```  
  
```Output  
type information for 'String':  
assembly name: mscorlib, Version=1.0.5000.0, Culture=neutral,   
PublicKeyToken=b77a5c561934e089  
namespace: System  
base type: System.Object  
is array: False  
is class: True  
```  
  
## <a name="example"></a>Beispiel  
 Die Reflektion unterstützt auch die Enumeration von Typen innerhalb einer Assembly und die von Membern innerhalb von Klassen. Um diese Funktion zu veranschaulichen, definieren Sie eine einfache Klasse:  
  
```  
// vcpp_reflection_5.cpp  
// compile with: /clr /LD  
using namespace System;  
public ref class TestClass {  
   int m_i;  
public:  
   TestClass() {}  
   void SimpleTestMember1() {}  
   String ^ SimpleMember2(String ^ s) { return s; }   
   int TestMember(int i) { return i; }  
   property int Member {  
      int get() { return m_i; }  
      void set(int i) { m_i = i; }  
   }  
};  
```  
  
## <a name="example"></a>Beispiel  
 Wenn der obige Code in eine DLL mit dem Namen vcpp_reflection_6.dll kompiliert wird, können Sie mithilfe der Reflektion den Inhalt dieser Assembly überprüfen. Dies umfasst die Verwendung der statischen Reflektions-API-Funktion [Reflektions](https://msdn.microsoft.com/en-us/library/system.reflection.assembly.load.aspx) zum Laden der Assembly. Diese Funktion gibt die Adresse des ein **Assembly** -Objekt, das über die Module und Typen abgefragt werden kann.  
  
 Sobald das Reflektionssystem die Assembly, die ein Array von erfolgreich lädt **Typ** Objekten wird abgerufen, mit der [Assembly:: GetTypes](https://msdn.microsoft.com/en-us/library/system.reflection.assembly.gettypes.aspx) Funktion. Jedes Arrayelement enthält Informationen zu einem anderen Typ, obwohl in diesem Fall nur eine Klasse definiert ist. Mithilfe einer Schleife, jede **Typ** in diesem Array wird abgefragt, die Typmember, die mit der **GetMembers** Funktion. Diese Funktion gibt ein Array von **MethodInfo** Objekten, jedes Objekt, das Informationen über die Memberfunktion, Datenmember oder Eigenschaft im Typ enthält.  
  
 Beachten Sie, dass die Liste der Methoden der Funktionen enthält, die explizit definierten **TestClass** und die Funktionen implizit geerbt wird, von der **System:: Object** Klasse. Bedingt dadurch, dass Eigenschaften in .NET- anstatt in Visual C++-Syntax beschrieben sind, werden sie als die zugrunde liegenden Datenmember angezeigt, auf die von den get-/set-Funktionen zugegriffen wird. Die get-/set-Funktionen werden in dieser Liste als reguläre Methoden angezeigt. Die Reflektion wird durch die Common Language Runtime und nicht durch den Visual C++-Compiler unterstützt.  
  
 Obwohl mit diesem Code bereits eine von Ihnen definierte Assembly überprüft wurde, können Sie ihn auch zur Überprüfung von .NET-Assemblys verwenden. Wenn Sie "TestAssembly" beispielsweise in "mscorlib" ändern, wird eine Liste aller in "mscorlib.dll" definierten Typen und Methoden angezeigt.  
  
```  
// vcpp_reflection_6.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::IO;  
using namespace System::Reflection;  
int main() {  
   Assembly ^ a = nullptr;  
   try {  
      // load assembly -- do not use file extension  
      // will look for .dll extension first  
      // then .exe with the filename  
      a = Assembly::Load("vcpp_reflection_5");  
   }  
   catch (FileNotFoundException ^ e) {  
      Console::WriteLine(e->Message);  
      return -1;  
   }  
  
   Console::WriteLine("assembly info:");  
   Console::WriteLine(a->FullName);  
   array<Type^>^ typeArray = a->GetTypes();  
  
   Console::WriteLine("type info ({0} types):", typeArray->Length);  
  
   int totalTypes = 0;  
   int totalMembers = 0;  
   for (int i = 0 ; i < typeArray->Length ; i++) {  
      // retrieve array of member descriptions  
      array<MemberInfo^>^ member = typeArray[i]->GetMembers();  
  
      Console::WriteLine("  members of {0} ({1} members):",   
      typeArray[i]->FullName, member->Length);  
      for (int j = 0 ; j < member->Length ; j++) {  
         Console::Write("       ({0})",   
         member[j]->MemberType.ToString() );  
         Console::Write("{0}  ", member[j]);  
         Console::WriteLine("");  
         totalMembers++;  
      }  
      totalTypes++;  
   }  
   Console::WriteLine("{0} total types, {1} total members",  
   totalTypes, totalMembers);  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [.NET-Programmierung mit C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)