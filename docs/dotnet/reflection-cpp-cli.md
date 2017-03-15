---
title: "Reflektion (C++/CLI)"
ms.custom: na
ms.date: "12/14/2016"
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
  - ".NET Framework [C++], Reflektion"
  - "Datentypen [C++], Reflektion"
  - "GetType-Methode"
  - "Metadaten, Reflektion"
  - "Reflektion [C++}"
  - "Reflektion [C++}, Informationen über die Reflektion"
  - "typeid-Schlüsselwort [C++]"
ms.assetid: 46b6ff4a-e441-4022-8892-78e69422f230
caps.latest.revision: 24
caps.handback.revision: "22"
ms.author: "mblome"
manager: "ghogen"
---
# Reflektion (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Reflektion ermöglicht die Überprüfung von bekannten Datentypen zur Laufzeit.  Sie ermöglicht die Enumeration von Datentypen in einer bestimmten Assembly. Darüber hinaus können Member einer bestimmten Klasse oder eines bestimmten Werttyps erkannt werden.  Dies trifft unabhängig davon zu, ob der Typ zur Kompilierungszeit bekannt war bzw. auf ihn verwiesen wurde.  Dies macht die Reflektion zu einer nützlichen Funktion für Entwicklungs\- und Codeverwaltungstools.  
  
 Bei dem angegebenen Assemblynamen handelt es sich um den starken Namen \(siehe [Assemblys mit starken Namen](../Topic/Creating%20and%20Using%20Strong-Named%20Assemblies.md)\), der die Assemblyversion, Kultur und Signierungsinformationen enthält.  Beachten Sie auch, dass der Name des Namespaces, in dem der Datentyp definiert ist, zusammen mit dem Namen der Basisklasse abgerufen werden kann.  
  
 Am häufigsten wird über die <xref:System.Object.GetType*>\-Methode auf Reflektionsfunktionen zugegriffen.  Diese Methode wird von der [System::Object](https://msdn.microsoft.com/en-us/library/system.object.aspx)\-Klasse zur Verfügung gestellt, von der alle Garbage Collection\-Klassen abgeleitet sind.  
  
 Die Reflektion einer mit dem Visual C\+\+\-Compiler erstellten EXE\-Datei ist zulässig, wenn die EXE\-Datei mit der Compileroption **\/clr:pure** oder der Compileroption **\/clr:safe** erstellt wurde.  Weitere Informationen finden Sie unter [\/clr \(Common Language Runtime\-Kompilierung\)](../build/reference/clr-common-language-runtime-compilation.md).  
  
 Themen in diesem Abschnitt:  
  
-   [Gewusst wie: Implementieren einer Plug\-In\-Komponentenarchitektur mit Reflektion](../dotnet/how-to-implement-a-plug-in-component-architecture-using-reflection-cpp-cli.md)  
  
-   [Gewusst wie: Auflisten von Datentypen in Assemblys mit Reflektion](../dotnet/how-to-enumerate-data-types-in-assemblies-using-reflection-cpp-cli.md)  
  
 Weitere Informationen hierzu finden Sie unter [System.Reflection\-Namespace](https://msdn.microsoft.com/en-us/library/system.reflection.aspx).  
  
## Beispiel  
 Die `GetType`\-Methode gibt einen Zeiger auf ein <xref:System.Type>\-Klassenobjekt zurück, das den Typ beschreibt, auf dem das Objekt basiert. \(Das **Type**\-Objekt enthält keine instanzspezifischen Informationen.\) Ein solches Element wäre der vollständige Name des Typs, der wie folgt angezeigt werden kann:  
  
 Der Typname enthält den vollständigen Bereich, in dem der Typ definiert ist, einschließlich Namespace und Darstellung in .NET\-Syntax, wobei ein Punkt als Bereichsauflösungsoperator verwendet wird.  
  
```  
// vcpp_reflection.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   String ^ s = "sample string";  
   Console::WriteLine("full type name of '{0}' is '{1}'", s, s->GetType());  
}  
```  
  
  **Der vollständige Typname von "Beispielzeichenfolge" ist "System.String".**   
## Beispiel  
 Werttypen können auch mit der `GetType`\-Funktion verwendet werden, müssen jedoch zuerst geschachtelt werden.  
  
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
  
  **Typ von i \= "System.Int32"**   
## Beispiel  
 Bei der `GetType`\-Methode gibt der Operator [typeid](../windows/typeid-cpp-component-extensions.md) einen Zeiger auf das **Type**\-Objekt zurück, sodass dieser Code den Typnamen **System.Int32** angibt.  Das Anzeigen von Typnamen ist die grundlegendste Funktion der Reflektion, eine möglicherweise hilfreichere Technik besteht jedoch in der Überprüfung oder Erkennung der gültigen Werte für enumerierte Typen.  Dazu verwenden Sie die statische **Enum::GetNames**\-Funktion, die ein Array aus Zeichenfolgen zurückgibt, von denen jede einen Enumerationswert in Textform enthält.  Im folgenden Beispiel wird ein Zeichenfolgenarray abgerufen, das die Enumerationswerte für die Enumeration **Optionen** \(CLR\) beschreibt und sie in einer Schleife anzeigt.  
  
 Falls der Enumeration **Optionen** eine vierte Option hinzugefügt wird, gibt dieser Code die neue Option ohne erneute Kompilierung aus, selbst wenn die Enumeration in einer separaten Assembly definiert ist.  
  
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
  
  **Es gibt drei Optionen in der Enumeration "Optionen".**  
**0: Option1**  
**1: Option2**  
**2: Option3**  
**Wert von "o" ist Option2.**   
## Beispiel  
 Das `GetType`\-Objekt unterstützt eine Reihe von Membern und Eigenschaften, die zur Überprüfung eines Typs verwendet werden können.  Durch diesen Code werden einige dieser Informationen abgerufen und angezeigt:  
  
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
  
  **Typinformationen für "Zeichenfolge":**  
**assembly name: mscorlib, Version\=1.0.5000.0, Culture\=neutral,**   
**PublicKeyToken\=b77a5c561934e089**  
**namespace: System**  
**base type: System.Object**  
**is array: False**  
**is class: True**   
## Beispiel  
 Die Reflektion unterstützt auch die Enumeration von Typen innerhalb einer Assembly und die von Membern innerhalb von Klassen.  Um diese Funktion zu veranschaulichen, definieren Sie eine einfache Klasse:  
  
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
  
## Beispiel  
 Wenn der obige Code in eine DLL mit dem Namen vcpp\_reflection\_6.dll kompiliert wird, können Sie mithilfe der Reflektion den Inhalt dieser Assembly überprüfen.  Dies beinhaltet auch die Verwendung der statischen [Assembly::Load](https://msdn.microsoft.com/en-us/library/system.reflection.assembly.load.aspx)\-Funktion der Reflektions\-API, um die Assembly zu laden.  Diese Funktion gibt die Adresse eines **Assembly**\-Objekts zurück, von dem enthaltene Module und Typen abgefragt werden können.  
  
 Sobald das Reflektionssystem die Assembly erfolgreich lädt, wird ein Array von **Type**\-Objekten mit der [Assembly::GetTypes](https://msdn.microsoft.com/en-us/library/system.reflection.assembly.gettypes.aspx)\-Funktion abgerufen.  Jedes Arrayelement enthält Informationen zu einem anderen Typ, obwohl in diesem Fall nur eine Klasse definiert ist.  In einem Schleifendurchlauf und mithilfe der **Type::GetMembers**\-Funktion werden von jedem **Type** in diesem Array die Typmember abgefragt.  Diese Funktion gibt ein Array von **MethodInfo**\-Objekten zurück, von denen jedes Informationen zu Memberfunktion, Datenmember oder Eigenschaft im Typ enthält.  
  
 Beachten Sie, dass die Methodenliste die in **TestClass** explizit definierten sowie die implizit von der **System::Object**\-Klasse geerbten Funktionen enthält.  Bedingt dadurch, dass Eigenschaften in .NET\- anstatt in Visual C\+\+\-Syntax beschrieben sind, werden sie als die zugrunde liegenden Datenmember angezeigt, auf die von den get\-\/set\-Funktionen zugegriffen wird.  Die get\-\/set\-Funktionen werden in dieser Liste als reguläre Methoden angezeigt.  Die Reflektion wird durch die Common Language Runtime und nicht durch den Visual C\+\+\-Compiler unterstützt.  
  
 Obwohl mit diesem Code bereits eine von Ihnen definierte Assembly überprüft wurde, können Sie ihn auch zur Überprüfung von .NET\-Assemblys verwenden.  Wenn Sie "TestAssembly" beispielsweise in "mscorlib" ändern, wird eine Liste aller in "mscorlib.dll" definierten Typen und Methoden angezeigt.  
  
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
  
## Siehe auch  
 [.NET\-Programmierung mit C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)