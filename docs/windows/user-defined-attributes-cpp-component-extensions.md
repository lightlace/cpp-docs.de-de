---
title: Benutzerdefinierte Attribute (Komponentenerweiterungen für C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- metadata, extending
- custom attributes, extending metadata
ms.assetid: 98b29048-a3ea-4698-8441-f149cdaec9fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 22f8dfa7e78568f100b0c58c881b9e84cb47a149
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="user-defined-attributes--c-component-extensions"></a>Benutzerdefinierte Attribute (Komponentenerweiterungen für C++)
Benutzerdefinierte Attribute können Sie die Metadaten von einer Schnittstelle, Klasse oder Struktur, -Methode, Parameter oder Enumeration zu erweitern.  
  
## <a name="all-runtimes"></a>Alle Laufzeiten  
 Alle Laufzeiten unterstützt benutzerdefinierte Attribute.  
  
## <a name="windows-runtime"></a>Windows-Runtime  
 C + c++ / CX-Attribut nur Eigenschaften unterstützt, aber nicht-Attribut Konstruktoren oder Methoden.  
  
### <a name="remarks"></a>Hinweise  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: **/ZW**  
  
## <a name="common-language-runtime"></a>Common Language Runtime  
 Benutzerdefinierte Attribute können Sie die Metadaten eines verwalteten Elements zu erweitern. Weitere Informationen finden Sie unter [Attribute](/dotnet/standard/attributes/index).  
  
### <a name="remarks"></a>Hinweise  
 Der Informationen und die Syntax, die in diesem Thema vorgestellt wird zum Ablösen der Informationen in voneinander [Attribut](../windows/attribute.md).  
  
 Sie können ein benutzerdefiniertes Attribut definieren, indem Sie einen Typ definieren und vornehmen <xref:System.Attribute> eine Basisklasse für den Typ und optional Anwenden der <xref:System.AttributeUsageAttribute> Attribut.  
  
 Z. B. in Microsoft Transaction Server (MTS) 1.0, Verhalten in Bezug auf Transaktionen, Synchronisierung, Lastenausgleich und So weiter durch benutzerdefinierte GUIDs, die in der Typbibliothek eingefügt werden, mit dem benutzerdefinierten ODL-Attribut angegeben wurde. Daher konnte ein Client eine MTS-Servers Merkmalen ermittelt werden durch Lesen der Typbibliothek. In .NET Framework die Analog der Typbibliothek ist Metadaten und der analogen des benutzerdefinierten ODL-Attribut ist, benutzerdefinierte Attribute. Außerdem ist das Lesen der Typbibliothek analog zur Verwendung von Reflektion auf die Typen.  
  
 Weitere Informationen finden Sie unter  
  
-   [Attributziele](../windows/attribute-targets-cpp-component-extensions.md)  
  
-   [Attributparametertypen](../windows/attribute-parameter-types-cpp-component-extensions.md)  
  
 Informationen zum Signieren von Assemblys in Visual C++ finden Sie unter [Assemblys mit starken Namen (Assembly signieren) (C + c++ / CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md).  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: **/clr**  
  
### <a name="examples"></a>Beispiele  
 **Beispiel**  
  
 Im folgende Beispiel wird gezeigt, wie ein benutzerdefiniertes Attribut definiert.  
  
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
  
 Das folgende Beispiel veranschaulicht einige wichtigen Funktionen von benutzerdefinierten Attributen. Dieses Beispiel zeigt z. B. eine allgemeine Verwendung der benutzerdefinierten Attribute: Instanziieren eines Servers, die selbst an Clients vollständig beschreiben kann.  
  
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
  
```Output  
Service Priority = 0  
  
Service Access = Write  
  
Service Priority = 3  
  
Service Access = Write  
  
Service Priority = 1  
  
Service Access = Read  
```  
  
 **Beispiel**  
  
 Das Objekt ^ Typ ersetzt den variant-Datentyp. Das folgende Beispiel definiert ein benutzerdefiniertes Attribut, das ein Array von Objekt verwendet ^ als Parameter.  
  
 Attributargumente müssen kompilierungszeitskonstanten werden; in den meisten Fällen sollten sie Konstanten Literale sein.  
  
 Finden Sie unter [Typeid](../windows/typeid-cpp-component-extensions.md) Informationen zum System:: Type Wert aus einem benutzerdefinierten Attributblock zurückzugeben.  
  
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
  
 Die Common Language Runtime erfordert, dass der öffentliche Teil der benutzerdefinierten Attributklasse serialisierbar sein muss.  Beim Erstellen von benutzerdefinierter Attributen sind benannte Argumente für das benutzerdefinierte Attribut auf den kompilierungszeitskonstanten beschränkt.  (Sozusagen Sie eine Sequenz von Bits, die das Klassenlayout in den Metadaten hinzugefügt.)  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md)