---
title: Reflektion (C++ / CLI) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- typeid keyword [C++]
- reflection [C++}, about reflection
- metadata, reflection
- GetType method
- .NET Framework [C++], reflection
- data types [C++], reflection
- reflection [C++}
- plug-ins [C++]
- reflection [C++}, plug-ins
- assemblies [C++], enumerating data types in
- public types [C++]
- reflection [C++], external assemblies
- assemblies [C++]
- data types [C++], enumerating
- public members [C++]
ms.assetid: 46b6ff4a-e441-4022-8892-78e69422f230
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 505049d6580f41253a483dfe1c64608d0ea9ed3d
ms.sourcegitcommit: 27be37ae07ee7b657a54d23ed34438220d977fdc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2018
ms.locfileid: "39110007"
---
# <a name="reflection-ccli"></a>Reflektion (C++/CLI)

Die Reflektion ermöglicht die Überprüfung von bekannten Datentypen zur Laufzeit. Sie ermöglicht die Enumeration von Datentypen in einer bestimmten Assembly. Darüber hinaus können Member einer bestimmten Klasse oder eines bestimmten Werttyps erkannt werden. Dies trifft unabhängig davon zu, ob der Typ zur Kompilierungszeit bekannt war bzw. auf ihn verwiesen wurde. Dies macht die Reflektion zu einer nützlichen Funktion für Entwicklungs- und Codeverwaltungstools.

Beachten Sie, dass der angegebene Assemblyname des starken Namens ist (finden Sie unter [erstellen und Assemblys mit starkem Namen](/dotnet/framework/app-domains/create-and-use-strong-named-assemblies)), darunter die Assemblyversion, Kultur und Signierungsinformationen. Beachten Sie auch, dass der Name des Namespaces, in dem der Datentyp definiert ist, zusammen mit dem Namen der Basisklasse abgerufen werden kann.

Am häufigsten wird über die <xref:System.Object.GetType%2A>-Methode auf Reflektionsfunktionen zugegriffen. Diese Methode wird bereitgestellt, indem [System:: Object](https://msdn.microsoft.com/en-us/library/system.object.aspx), aus der alle Garbage Collection-Klassen abgeleitet werden.

> [!NOTE]
> Reflektion einer mit Visual C++-Compiler erstellte .exe ist nur zulässig, wenn die .exe mit erstellt wurde die **/CLR: pure** oder **/CLR: safe** Compileroptionen. Die **/CLR: pure** und **/CLR: safe** Compileroptionen sind in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht verfügbar. Finden Sie unter [/CLR (Common Language Runtime Compilation)](../build/reference/clr-common-language-runtime-compilation.md) für Weitere Informationen.

Weitere Informationen finden Sie unter [System.Reflection-Namespace](https://msdn.microsoft.com/en-us/library/system.reflection.aspx)

## <a name="example-gettype"></a>Beispiel: GetType

Die `GetType`-Methode gibt einen Zeiger auf ein <xref:System.Type>-Klassenobjekt zurück, das den Typ beschreibt, auf dem das Objekt basiert. (Die **Typ** Objekt enthält keine instanzspezifischen Informationen.) Ein solches Element wäre der vollständige Name des Typs, der wie folgt angezeigt werden kann:

Der Typname enthält den vollständigen Bereich, in dem der Typ definiert ist, einschließlich Namespace und Darstellung in .NET-Syntax, wobei ein Punkt als Bereichsauflösungsoperator verwendet wird.

```cpp
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

## <a name="example-boxed-value-types"></a>Beispiel: geschachtelte Werttypen

Werttypen können auch mit der `GetType`-Funktion verwendet werden, müssen jedoch zuerst geschachtelt werden.

```cpp
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

## <a name="example-typeid"></a>Beispiel: Typeid

Wie bei der `GetType` -Methode, die [Typeid](../windows/typeid-cpp-component-extensions.md) Operator gibt einen Zeiger auf eine **Typ** Objekt, damit dieser Code den Typnamen, **System. Int32**. Das Anzeigen von Typnamen ist die grundlegendste Funktion der Reflektion, eine möglicherweise hilfreichere Technik besteht jedoch in der Überprüfung oder Erkennung der gültigen Werte für enumerierte Typen. Dies kann erfolgen mithilfe der statischen **Enum:: GetNames** ordnungsgemäß verwendet werden, womit ein Array von Zeichenfolgen, jeweils einen Enumerationswert in Textform.  Im folgende Beispiel ruft ein Array von Zeichenfolgen, die beschreibt, das die Enumerationswerte für die **Optionen** (CLR)-Enumeration und zeigt sie in einer Schleife.

Wenn eine vierte Option hinzugefügt wird die **Optionen** Enumeration, in diesem Code meldet die neue Option ohne erneute Kompilierung aus, selbst wenn die Enumeration in einer separaten Assembly definiert ist.

```cpp
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

## <a name="example-gettype-members-and-properties"></a>Beispiel: GetType-Elemente und Eigenschaften

Das `GetType`-Objekt unterstützt eine Reihe von Membern und Eigenschaften, die zur Überprüfung eines Typs verwendet werden können. Durch diesen Code werden einige dieser Informationen abgerufen und angezeigt:

```cpp
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

## <a name="example-enumeration-of-types"></a>Beispiel: Enumeration von Typen

Die Reflektion unterstützt auch die Enumeration von Typen innerhalb einer Assembly und die von Membern innerhalb von Klassen. Um diese Funktion zu veranschaulichen, definieren Sie eine einfache Klasse:

```cpp
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

## <a name="example-inspection-of-assemblies"></a>Beispiel: Überprüfung von Assemblys

Wenn der obige Code in eine DLL mit dem Namen vcpp_reflection_6.dll kompiliert wird, können Sie mithilfe der Reflektion den Inhalt dieser Assembly überprüfen. Dies umfasst die statische Reflektions-API-Funktion [Reflektions](https://msdn.microsoft.com/en-us/library/system.reflection.assembly.load.aspx) zum Laden der Assembly. Diese Funktion gibt die Adresse einer **Assembly** -Objekt, das über die Module und Typen abgefragt werden kann.

Sobald das Reflektionssystem die Assembly, ein Array von erfolgreich lädt **Typ** Objekte wird abgerufen, mit der [Assembly:: GetTypes](https://msdn.microsoft.com/en-us/library/system.reflection.assembly.gettypes.aspx) Funktion. Jedes Arrayelement enthält Informationen zu einem anderen Typ, obwohl in diesem Fall nur eine Klasse definiert ist. Mithilfe einer Schleife jeden **Typ** wird in diesem Array die Typmember mit abgefragt der **GetMembers** Funktion. Diese Funktion gibt ein Array von **MethodInfo** Objekten, jedes Objekt, das Informationen über die Memberfunktion, Datenmember oder Eigenschaft im Typ enthält.

Beachten Sie, dass die Liste der Methoden explizit die Funktionen enthält, die in definierten **TestClass** und die Funktionen implizit geerbt wird, von der **System:: Object** Klasse. Bedingt dadurch, dass Eigenschaften in .NET- anstatt in Visual C++-Syntax beschrieben sind, werden sie als die zugrunde liegenden Datenmember angezeigt, auf die von den get-/set-Funktionen zugegriffen wird. Die get-/set-Funktionen werden in dieser Liste als reguläre Methoden angezeigt. Die Reflektion wird durch die Common Language Runtime und nicht durch den Visual C++-Compiler unterstützt.

Obwohl mit diesem Code bereits eine von Ihnen definierte Assembly überprüft wurde, können Sie ihn auch zur Überprüfung von .NET-Assemblys verwenden. Wenn Sie "TestAssembly" beispielsweise in "mscorlib" ändern, wird eine Liste aller in "mscorlib.dll" definierten Typen und Methoden angezeigt.

```cpp
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

## <a name="implement"></a> Gewusst wie: Implementieren einer Plug-In-Komponentenarchitektur mit Reflektion
Die folgenden Codebeispiele veranschaulichen die Verwendung von Reflektion, um eine einfache "plug-in-Architektur zu implementieren. Das erste Codelisting ist der Anwendung, und die zweite ist das plug-in. Die Anwendung ist das Formular in einer multiple-Document an, die sich über alle Form-basierten Klassen finden Sie in der Plug-in-DLL als Befehlszeilenargument auffüllt.  
  
 Die Anwendung versucht, beim Laden der bereitgestellten Assembly, die mit der <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> Methode. Wenn erfolgreich, die Typen in der Assembly aufgelistet werden mithilfe der <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=fullName> Methode. Jeder Typ wird dann für die Verwendung von Kompatibilität überprüft die <xref:System.Type.IsAssignableFrom%2A?displayProperty=fullName> Methode. In diesem Beispiel die Klassen in der angegebenen Assembly abgeleitet werden, aus der <xref:System.Windows.Forms.Form> Klasse, die als plug-in behandelt.  
  
 -Kompatible Klassen werden mit dann instanziiert der <xref:System.Activator.CreateInstance%2A?displayProperty=fullName> -Methode, die akzeptiert eine <xref:System.Type> als Argument und gibt einen Zeiger auf eine neue Instanz. Jede neue Instanz wird dann an das Formular angefügt und angezeigt.  
  
 Beachten Sie, dass die <xref:System.Reflection.Assembly.Load%2A> Methode akzeptiert keine Assemblynamen, die die Dateierweiterung enthalten. Also im folgenden Codebeispiel wird in beiden Fällen funktioniert, werden die main-Funktion in der Anwendung bereitgestellten Erweiterungen, entfernt.  
  
### <a name="example"></a>Beispiel  
 Der folgende Code definiert die Anwendung, die akzeptiert-Plug-ins. Namen einer Assembly muss als erstes Argument angegeben werden. Diese Assembly muss mindestens einen öffentlichen enthalten <xref:System.Windows.Forms.Form> abgeleiteten Typ.  
  
```cpp
// plugin_application.cpp  
// compile with: /clr /c  
#using <system.dll>  
#using <system.drawing.dll>  
#using <system.windows.forms.dll>  
  
using namespace System;  
using namespace System::Windows::Forms;  
using namespace System::Reflection;  
  
ref class PluggableForm : public Form  {  
public:  
   PluggableForm() {}  
   PluggableForm(Assembly^ plugAssembly) {  
      Text = "plug-in example";  
      Size = Drawing::Size(400, 400);  
      IsMdiContainer = true;  
  
      array<Type^>^ types = plugAssembly->GetTypes( );  
      Type^ formType = Form::typeid;  
  
      for (int i = 0 ; i < types->Length ; i++) {  
         if (formType->IsAssignableFrom(types[i])) {  
            // Create an instance given the type description.  
            Form^ f = dynamic_cast<Form^> (Activator::CreateInstance(types[i]));  
            if (f) {  
               f->Text = types[i]->ToString();  
               f->MdiParent = this;  
               f->Show();  
            }  
         }  
      }  
   }  
};  
  
int main() {  
   Assembly^ a = Assembly::LoadFrom("plugin_application.exe");  
   Application::Run(gcnew PluggableForm(a));  
}  
```  
  
### <a name="example"></a>Beispiel  
 Der folgende Code definiert drei Klassen, die von <xref:System.Windows.Forms.Form>. Wenn der Name der resultierenden Assembly, die an die ausführbare Datei, in der vorherigen Liste übergeben wird, wird jede dieser drei Klassen ermittelt und instanziiert, trotz der Tatsache, dass sie die hostanwendung zum Zeitpunkt der Kompilierung nicht bekannt waren.  
  
```cpp  
// plugin_assembly.cpp  
// compile with: /clr /LD  
#using <system.dll>  
#using <system.drawing.dll>  
#using <system.windows.forms.dll>  
  
using namespace System;  
using namespace System::Windows::Forms;  
using namespace System::Reflection;  
using namespace System::Drawing;  
  
public ref class BlueForm : public Form {  
public:  
   BlueForm() {  
      BackColor = Color::Blue;  
   }  
};  
  
public ref class CircleForm : public Form {  
protected:  
   virtual void OnPaint(PaintEventArgs^ args) override {  
      args->Graphics->FillEllipse(Brushes::Green, ClientRectangle);  
   }  
};  
  
public ref class StarburstForm : public Form {  
public:  
   StarburstForm(){  
      BackColor = Color::Black;  
   }  
protected:  
   virtual void OnPaint(PaintEventArgs^ args) override {  
      Pen^ p = gcnew Pen(Color::Red, 2);  
      Random^ r = gcnew Random( );  
      Int32 w = ClientSize.Width;  
      Int32 h = ClientSize.Height;  
      for (int i=0; i<100; i++) {  
         float x1 = w / 2;  
         float y1 = h / 2;  
         float x2 = r->Next(w);  
         float y2 = r->Next(h);  
         args->Graphics->DrawLine(p, x1, y1, x2, y2);  
      }  
   }  
};  
```  

## <a name="enumerate"></a> Gewusst wie: Auflisten von Datentypen in Assemblys mit Reflektion
Der folgende Code veranschaulicht die Enumeration von öffentlichen Typen und Member, die mit <xref:System.Reflection>.  
  
 Wenn den Namen einer Assembly, entweder im lokalen Verzeichnis oder im globalen Assemblycache, versucht, der folgenden Code öffnen Sie die Assembly und Beschreibungen abzurufen. Wenn erfolgreich, wird jeder Typ mit die öffentlichen Member angezeigt.  
  
 Beachten Sie, dass <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> erfordert, dass keine Dateierweiterung verwendet wird. Aus diesem Grund fehl mithilfe von "mscorlib.dll" als Befehlszeilenargument bei Verwendung nur "Mscorlib" die Anzeige von .NET Framework-Typen und. Wenn kein Assemblyname angegeben wird, der Code erkennt und meldet die Typen in der aktuellen Assembly (EXE-Datei durch folgenden Code).  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// self_reflection.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Reflection;  
using namespace System::Collections;  
  
public ref class ExampleType {  
public:  
   ExampleType() {}  
   void Func() {}  
};  
  
int main() {  
   String^ delimStr = " ";  
   array<Char>^ delimiter = delimStr->ToCharArray( );  
   array<String^>^ args = Environment::CommandLine->Split( delimiter );  
  
// replace "self_reflection.exe" with an assembly from either the local  
// directory or the GAC  
   Assembly^ a = Assembly::LoadFrom("self_reflection.exe");  
   Console::WriteLine(a);  
  
   int count = 0;  
   array<Type^>^ types = a->GetTypes();  
   IEnumerator^ typeIter = types->GetEnumerator();  
  
   while ( typeIter->MoveNext() ) {  
      Type^ t = dynamic_cast<Type^>(typeIter->Current);  
      Console::WriteLine("   {0}", t->ToString());  
  
      array<MemberInfo^>^ members = t->GetMembers();  
      IEnumerator^ memberIter = members->GetEnumerator();  
      while ( memberIter->MoveNext() ) {  
         MemberInfo^ mi = dynamic_cast<MemberInfo^>(memberIter->Current);  
         Console::Write("      {0}", mi->ToString( ) );  
         if (mi->MemberType == MemberTypes::Constructor)  
            Console::Write("   (constructor)");  
  
         Console::WriteLine();  
      }  
      count++;  
   }  
   Console::WriteLine("{0} types found", count);  
}  
```  

## <a name="see-also"></a>Siehe auch

- [.NET-Programmierung mit C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
