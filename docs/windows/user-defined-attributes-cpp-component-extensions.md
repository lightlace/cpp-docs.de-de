---
title: "User-Defined Attributes  (C++ Component Extensions)"
ms.custom: na
ms.date: "12/15/2016"
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
  - "metadata, extending"
  - "custom attributes, extending metadata"
ms.assetid: 98b29048-a3ea-4698-8441-f149cdaec9fb
caps.latest.revision: 27
caps.handback.revision: "25"
ms.author: "mblome"
manager: "ghogen"
---
# User-Defined Attributes  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Benutzerdefinierte Attribute ermöglichen Sie, um die Metadaten einer Schnittstelle, der Klasse oder der Struktur, Methode, des Parameters oder Enumeration zu erweitern.  
  
## Alle Laufzeiten  
 Alle Laufzeiten unterstützen benutzerdefinierte Attribute.  
  
## Windows\-Runtime  
 C\+\+\/CX\-Attribute unterstützen nur Eigenschaften, sondern nicht schreiben Konstruktoren oder Methoden zu.  
  
### Hinweise  
  
### Voraussetzungen  
 Compileroption: **\/ZW**  
  
## Common Language Runtime  
 Benutzerdefinierte Attribute können die Metadaten eines verwalteten Element erweitern.  Weitere Informationen finden Sie unter [Attribute](../Topic/Extending%20Metadata%20Using%20Attributes.md).  
  
### Hinweise  
 Die Informationen und die Syntax, die in diesem Thema dargestellt wird, ist implizit, um die Informationen abzulösen, die in [attribute](../windows/attribute.md) dargestellt werden.  
  
 Sie können ein benutzerdefiniertes Attribut definieren, indem Sie einen Typ definieren und <xref:System.Attribute> eine Basisklasse für den Typ ausführen und optional <xref:System.AttributeUsageAttribute> das Attribut anwenden.  
  
 Beispielsweise in Microsoft Transaction Server \(MTS\) 1,0, Verhalten in Bezug auf Transaktionen, Synchronisierung, Lastenausgleich, z. B wurde von der benutzerdefinierten GUIDs angegeben, die in die Typbibliothek eingefügt wurden, indem das benutzerdefinierte Attribut ODL verwendet.  Daher kann ein Client eines MTS\-Servers die Eigenschaften durch Lesen der Typbibliothek bestimmen.  In .NET Framework ist die Entsprechung der Typbibliothek und Metadaten, die Entsprechung der benutzerdefinierten Attribute ODL ist benutzerdefinierte Attribute.  Auch der Typbibliothek zu lesen ist die Verwendung der Reflektion auf Typen analog.  
  
 Weitere Informationen finden Sie unter  
  
-   [Attribute Targets](../windows/attribute-targets-cpp-component-extensions.md)  
  
-   [Attribute Parameter Types](../windows/attribute-parameter-types-cpp-component-extensions.md)  
  
 Informationen zum Signieren von Assemblys in Visual C\+\+, finden Sie unter [Assemblys mit starken Namen \(Assemblysignierung\)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md).  
  
### Voraussetzungen  
 Compileroption: **\/clr**  
  
### Beispiele  
 **Beispiel**  
  
 Das folgende Beispiel zeigt, wie ein benutzerdefiniertes Attribut definiert.  
  
```cpp  
// user_defined_attributes.cpp  
// compile with: /clr /c  
using namespace System;  
  
[AttributeUsage(AttributeTargets::All)]  
ref struct Attr : public Attribute {  
   Attr(bool i){}  
   Attr(){}  
};  
  
[Attr]  
ref class MyClass {};  
```  
  
 **Beispiel**  
  
 Im folgenden Beispiel werden einige wichtige Funktionen von benutzerdefinierten Attributen.  Beispielsweise zeigt dieses Beispiel eine allgemeine Verwendung benutzerdefinierter Attribute an: einen Server instanziieren, der zu den Clients sich vollständig beschrieben werden kann.  
  
```cpp  
// extending_metadata_b.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Reflection;  
  
public enum class Access { Read, Write, Execute };  
  
// Defining the Job attribute:  
[AttributeUsage(AttributeTargets::Class, AllowMultiple=true )]  
public ref class Job : Attribute {  
public:  
   property int Priority {  
      void set( int value ) { m_Priority = value; }  
      int get() { return m_Priority; }  
   }  
  
   // You can overload constructors to specify Job attribute in different ways  
   Job() { m_Access = Access::Read; }  
   Job( Access a ) { m_Access = a; }  
   Access m_Access;  
  
protected:  
   int m_Priority;  
};  
  
interface struct IService {  
   void Run();  
};  
  
   // Using the Job attribute:  
   // Here we specify that QueryService is to be read only with a priority of 2.  
   // To prevent namespace collisions, all custom attributes implicitly   
   // end with "Attribute".   
  
[Job( Access::Read, Priority=2 )]  
ref struct QueryService : public IService {  
   virtual void Run() {}  
};  
  
// Because we said AllowMultiple=true, we can add multiple attributes   
[Job(Access::Read, Priority=1)]  
[Job(Access::Write, Priority=3)]  
ref struct StatsGenerator : public IService {  
   virtual void Run( ) {}  
};  
  
int main() {  
   IService ^ pIS;  
   QueryService ^ pQS = gcnew QueryService;  
   StatsGenerator ^ pSG = gcnew StatsGenerator;  
  
   //  use QueryService  
   pIS = safe_cast<IService ^>( pQS );  
  
   // use StatsGenerator  
   pIS = safe_cast<IService ^>( pSG );  
  
   // Reflection  
   MemberInfo ^ pMI = pIS->GetType();  
   array <Object ^ > ^ pObjs = pMI->GetCustomAttributes(false);  
  
   // We can now quickly and easily view custom attributes for an   
   // Object through Reflection */  
   for( int i = 0; i < pObjs->Length; i++ ) {  
      Console::Write("Service Priority = ");  
      Console::WriteLine(static_cast<Job^>(pObjs[i])->Priority);  
      Console::Write("Service Access = ");  
      Console::WriteLine(static_cast<Job^>(pObjs[i])->m_Access);  
   }  
}  
```  
  
 **Ausgabe**  
  
  **Dienst\-Priorität \= 0**  
 **Dienst\-Zugriff \= schreiben**  
 **Dienst\-Priorität \= 3**  
 **Dienst\-Zugriff \= schreiben**  
 **Dienst\-Priorität \= 1**  
 **Dienst\-Zugriff \= gelesen** **Beispiel**  
  
 Der Object^\-Typ ersetzt den Variant\-Datentyps.  Das folgende Beispiel definiert ein benutzerdefiniertes Attribut, das ein Array aus Object^ als Parameter akzeptiert.  
  
 Attributargumente müssen Kompilierzeitkonstanten sein; in den meisten Fällen sollten sie konstante Literale sein.  
  
 Siehe [typeid](../windows/typeid-cpp-component-extensions.md) zu Informationen darüber, wie Sie einen Wert von System::Type von einem benutzerdefinierten Attributblock zurückgibt.  
  
```cpp  
// extending_metadata_e.cpp  
// compile with: /clr /c  
using namespace System;  
[AttributeUsage(AttributeTargets::Class | AttributeTargets::Method)]  
public ref class AnotherAttr : public Attribute {  
public:  
   AnotherAttr(array<Object^>^) {}  
   array<Object^>^ var1;  
};  
  
// applying the attribute  
[ AnotherAttr( gcnew array<Object ^> { 3.14159, "pi" }, var1 = gcnew array<Object ^> { "a", "b" } ) ]  
public ref class SomeClass {};  
```  
  
 **Beispiel**  
  
 Die Laufzeit erfordert, dass der öffentliche Teil der benutzerdefinierten Attributklasse serialisierbar sein muss.  Wenn die Verwendung benutzerdefinierter Attribute erstellt, werden benannte Argumente des benutzerdefinierten Attributs auf Konstanten zur Kompilierungszeit beschränkt.  \(Denken Sie an es als Sequenz von Bits, die auf das Klassenlayout in den Metadaten. angefügt werden\)  
  
```cpp  
// extending_metadata_f.cpp  
// compile with: /clr /c  
using namespace System;  
ref struct abc {};  
  
[AttributeUsage( AttributeTargets::All )]  
ref struct A : Attribute {  
   A( Type^ ) {}  
   A( String ^ ) {}  
   A( int ) {}  
};  
  
[A( abc::typeid )]  
ref struct B {};  
```  
  
## Siehe auch  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)