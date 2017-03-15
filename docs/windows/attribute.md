---
title: "attribute | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.attribute"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__typeof keyword"
  - "custom attributes, creating"
  - "attribute attribute"
  - "attributes [C++], custom"
ms.assetid: 8cb3489f-65c4-44ea-b0aa-3c3c6b15741d
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# attribute
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ermöglicht es Ihnen, ein benutzerdefiniertes Attribut zu erstellen.  
  
## Syntax  
  
```  
  
      [ attribute(  
   AllowOn,  
   AllowMultiple=boolean,  
   Inherited=boolean  
) ]  
```  
  
#### Parameter  
 *AllowOn*  
 Gibt die Sprachelemente auf, in denen das benutzerdefinierte Attribut angewendet werden kann.  Der Standardwert ist **System::AttributeTargets::Alle** \(siehe [System::AttributeTargets](https://msdn.microsoft.com/en-us/library/system.attributetargets.aspx)\).  
  
 `AllowMultiple`  
 Gibt an, ob das benutzerdefinierte Attribut auf ein Konstrukt mehrfach angewendet werden kann.  Der Standardwert ist **FALSE**.  
  
 `Inherited`  
 Gibt an, ob das Attribut von Unterklassen geerbt werden soll.  Der Compiler unterstützt keine besondere Unterstützung für diese Funktion. Dies entspricht der Reihenfolge der Attribute für die Reflektion \(z. B.\), die Informationen zu berücksichtigen.  Wenn `Inherited`**TRUE**ist, wird das Attribut geerbt.  Wenn `AllowMultiple`**TRUE**ist, akkumuliert das Attribut auf der abgeleiteten Membern. `AllowMultiple` wenn **FALSE**ist, überschreibt das Attribut \(oder ersetzen\) in der Vererbung.  Wenn `Inherited`**FALSE**ist, wird das Attribut nicht vererbt werden.  Der Standardwert ist **TRUE**.  
  
## Hinweise  
  
> [!NOTE]
>  Das `attribute`\-Attribut ist mittlerweile veraltet.  Verwenden des Common Language Runtime\-Attribut System.Attribute direkt zu, um die benutzerdefinierte attirbutes zu erstellen.  Weitere Informationen finden Sie unter [User\-Defined Attributes](../windows/user-defined-attributes-cpp-component-extensions.md).  
  
 Sie definieren [benutzerdefiniertes Attribut](../windows/custom-attributes-cpp.md) , indem Sie das `attribute`\-Attribut in einer verwalteten Klasse oder Strukturdefinition platzieren.  Der Name der Klasse ist das benutzerdefinierte Attribut.  Beispiele:  
  
```  
[ attribute(Parameter) ]  
public ref class MyAttr {};  
```  
  
 definiert ein Attribut, das MyAttr aufgerufen wird, das an den Funktionsparametern angewendet werden kann.  Die Klasse muss öffentlich sein, wenn das Attribut in anderen Assemblys verwendet werden soll.  
  
> [!NOTE]
>  Um zu verhindern, dass Konflikte Namespace, beenden alle Attributnamen implizit mit „Attribut“; In diesem Beispiel ist der Name des Attributs ist und die Klasse MyAttrAttribute, aber tatsächlich MyAttr und MyAttrAttribute kann synonym verwendet werden.  
  
 Die öffentlichen Konstruktoren der Klasse definieren die unbenannten Parameter des Attributs.  Überladene Konstruktoren ermöglichen es mehrere Möglichkeiten zum Bereitstellen des Attributs, sodass ein benutzerdefiniertes Attribut, das die folgende Methode definiert ist:  
  
```  
// cpp_attr_ref_attribute.cpp  
// compile with: /c /clr  
using namespace System;  
[ attribute(AttributeTargets::Class) ]   // apply attribute to classes  
public ref class MyAttr {  
public:  
   MyAttr() {}   // Constructor with no parameters  
   MyAttr(int arg1) {}   // Constructor with one parameter  
};  
  
[MyAttr]  
ref class ClassA {};   // Attribute with no parameters  
  
[MyAttr(123)]  
ref class ClassB {};   // Attribute with one parameter  
```  
  
 Durch die öffentlichen Datenmember und Eigenschaften Klasse sind die optionalen benannten Parameter des Attributs:  
  
```  
// cpp_attr_ref_attribute_2.cpp  
// compile with: /c /clr  
using namespace System;  
[ attribute(AttributeTargets::Class) ]  
ref class MyAttr {  
public:  
   // Property Priority becomes attribute's named parameter Priority  
    property int Priority {  
       void set(int value) {}  
       int get() { return 0;}  
   }  
   // Data member Version becomes attribute's named parameter Version  
   int Version;  
   MyAttr() {}   // constructor with no parameters  
   MyAttr(int arg1) {}   // constructor with one parameter  
};  
  
[MyAttr(123, Version=2)]   
ref class ClassC {};  
```  
  
 Eine Liste der möglichen Attribut parametertypen finden Sie unter [Benutzerdefinierte Attribute](../windows/custom-attributes-cpp.md).  
  
 Weitere Informationen finden Sie unter [User\-Defined Attributes](../windows/user-defined-attributes-cpp-component-extensions.md) für eine Diskussion ein Attribut zielen.  
  
 Das `attribute`\-Attribut verfügt über einen `AllowMultiple`\-Parameter, der angibt, ob das custom\-Attribut einzelne Verwendung oder wiederverwendet werden kann \(kann sich in derselben Entität mehrmals angegeben werden\).  
  
```  
// cpp_attr_ref_attribute_3.cpp  
// compile with: /c /clr  
using namespace System;  
[ attribute(AttributeTargets::Class, AllowMultiple = true) ]  
ref struct MyAttr {  
   MyAttr(){}  
};   // MyAttr is a multiuse attribute  
  
[MyAttr, MyAttr()]  
ref class ClassA {};  
```  
  
 Mit benutzerdefinierten Attributklassen sind direkt oder indirekt von <xref:System.ComponentModel.AttributeCollection.#ctor*>abgeleitet, das Attributbeschreibungen in den Metadaten schnell und einfach identifiziert werden können.  Das bedeutet `attribute`\-Attribut vom System::VererbungAttribut, sodass die explizite Ableitungen ist nicht notwendig:  
  
```  
[ attribute(Class) ]  
ref class MyAttr  
```  
  
 der folgenden Syntax:  
  
```  
[ attribute(Class) ]  
ref class MyAttr : System::Attribute   // OK, but redundant.  
```  
  
 `attribute` ist ein Alias für <xref:System.AttributeUsageAttribute?displayProperty=fullName> \(nicht AttributeAttribute. Hierbei handelt es sich um eine Ausnahme von der Attribut\-Benennungs die Regel\).  
  
## Anforderungen  
  
### Attribut\-Kontext  
  
|||  
|-|-|  
|**Betrifft**|`ref` **Klasse**, **ref\-Struktur**|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|None|  
|**Ungültige Attribute**|None|  
  
 Weitere Informationen über das kontexte finden Sie unter [Attribut\-Kontexte](../windows/attribute-contexts.md).  
  
## Beispiel  
  
```  
// cpp_attr_ref_attribute_4.cpp  
// compile with: /c /clr  
using namespace System;  
[attribute(AttributeTargets::Class)]  
ref struct ABC {  
   ABC(Type ^) {}  
};  
  
[ABC(String::typeid)]   // typeid operator yields System::Type ^  
ref class MyClass {};  
```  
  
## Beispiel  
 Das `Inherited` benannten Arguments gibt an, ob ein benutzerdefiniertes Attribut, das auf einer Basisklasse angewendete sich auf die Reflektion einer abgeleiteten Klasse veranschaulicht.  
  
```  
// cpp_attr_ref_attribute_5.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Reflection;  
  
[attribute( AttributeTargets::Method, Inherited=false )]  
ref class BaseOnlyAttribute { };  
  
[attribute( AttributeTargets::Method, Inherited=true )]  
ref class DerivedTooAttribute { };  
  
ref struct IBase {  
public:  
   [BaseOnly, DerivedToo]  
   virtual void meth() {}  
};  
  
// Reflection on Derived::meth will show DerivedTooAttribute   
// but not BaseOnlyAttribute.  
ref class Derived : public IBase {  
public:  
   virtual void meth() override {}  
};  
  
int main() {  
   IBase ^ pIB = gcnew Derived;  
  
   MemberInfo ^ pMI = pIB->GetType( )->GetMethod( "meth" );  
   array<Object ^> ^ pObjs = pMI->GetCustomAttributes( true );  
   Console::WriteLine( pObjs->Length ) ;  
}  
```  
  
  **2**   
## Siehe auch  
 [Attributes Alphabetical Reference](../windows/attributes-alphabetical-reference.md)   
 [Custom Attributes](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)