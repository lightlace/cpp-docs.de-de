---
title: Attribut | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.attribute
dev_langs:
- C++
helpviewer_keywords:
- __typeof keyword
- custom attributes, creating
- attribute attribute
- attributes [C++/CLI], custom
ms.assetid: 8cb3489f-65c4-44ea-b0aa-3c3c6b15741d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 54699888fc2988dd9b4ccec2a57b6d9df0d4e79e
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44314772"
---
# <a name="attribute"></a>Attribut

Ermöglicht Ihnen die Erstellung ein benutzerdefiniertes Attributs.

## <a name="syntax"></a>Syntax

```cpp
[ attribute(
   AllowOn,
   AllowMultiple=boolean,
   Inherited=boolean
) ]
```

### <a name="parameters"></a>Parameter

*AllowOn*  
Gibt die Language-Elemente, die auf denen das benutzerdefinierte Attribut angewendet werden kann. Der Standardwert ist `System::AttributeTargets::All` (finden Sie unter [System::AttributeTargets](https://msdn.microsoft.com/library/system.attributetargets.aspx)).

*AllowMultiple*  
Gibt an, ob das benutzerdefinierte Attribut wiederholt für ein Konstrukt angewendet werden kann. Der Standardwert lautet FALSE.

*Geerbt*  
Gibt an, ob das Attribut von Unterklassen geerbt werden. Der Compiler bietet keine spezielle Unterstützung für diese Funktion; Es ist die Aufgabe der Attribut-Consumer (`Reflection`, z. B.), die diese Informationen zu berücksichtigen. Wenn *geerbte* TRUE ist, wird das Attribut geerbt. Wenn *AllowMultiple* ist "true", das Attribut sammeln sich daher auf der abgeleitete Member; Wenn *AllowMultiple* ist "false", das Attribut wird außer Kraft setzen (oder ersetzen) bei der Vererbung. Wenn *geerbte* false festgelegt ist, wird das Attribut nicht geerbt werden. Der Standardwert ist TRUE.

## <a name="remarks"></a>Hinweise

> [!NOTE]
> Die **Attribut** Attribut ist jetzt veraltet.  Verwenden Sie die common Language Runtime-Attribut `System.Attribute` , direkt an eine benutzerdefinierte Attirbutes zu erstellen. Weitere Informationen finden Sie unter [User-Defined Attributes](../windows/user-defined-attributes-cpp-component-extensions.md).

Sie definieren eine [benutzerdefiniertes Attribut](../windows/custom-attributes-cpp.md) durch Platzieren der **Attribut** Attribut für eine verwaltete Definition der Klasse oder Struktur. Der Name der Klasse wird das benutzerdefinierte Attribut. Zum Beispiel:

```cpp
[ attribute(Parameter) ]
public ref class MyAttr {};
```

definiert ein Attribut namens `MyAttr` , das auf Parameter angewendet werden kann. Die Klasse muss öffentlich sein, wenn das Attribut in anderen Assemblys verwendet werden soll.

> [!NOTE]
> Um Konflikte von Namespaces zu verhindern, enden alle Attributnamen implizit "Attribute"; In diesem Beispiel wird der Name des Attributs und Klasse tatsächlich `MyAttrAttribute`, aber `MyAttr` und `MyAttrAttribute` austauschbar verwendet werden.

Die Klasse öffentliche Konstruktoren definieren unbenannte Parameter des Attributs. Überladene Konstruktoren gestatten es mehrere Möglichkeiten, das Attribut angeben, damit ein benutzerdefiniertes Attribut, das ist wie folgt definiert:

```cpp
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

Öffentliche Datenmember und Eigenschaften der Klasse sind optionale benannte Parameter für das Attribut:

```cpp
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

Eine Liste der möglichen Attributparametertypen, finden Sie unter [benutzerdefinierte Attribute](../windows/custom-attributes-cpp.md).

Finden Sie unter [User-Defined Attributes](../windows/user-defined-attributes-cpp-component-extensions.md) eine Erläuterung zum Attribut abzielt.

Die **Attribut** Attribut hat eine *AllowMultiple* Parameter, der angibt, ob das benutzerdefinierte Attribut einzelne verwendet wird oder Multiuse (können werden mehr als einmal auf die gleiche Entität).

```cpp
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

Benutzerdefinierte Attributklassen stammen direkt oder indirekt von <xref:System.ComponentModel.AttributeCollection.%23ctor%2A>, welche macht Attributdefinitionen in Metadaten schnell und einfach zu identifizieren. Die **Attribut** -Attributs impliziert die Vererbung von `System::Attribute`, sodass die explizite Ableitung nicht erforderlich ist:

```cpp
[ attribute(Class) ]
ref class MyAttr
```

für die folgende Syntax:

```cpp
[ attribute(Class) ]
ref class MyAttr : System::Attribute   // OK, but redundant.
```

**Attribut** ist ein Alias für <xref:System.AttributeUsageAttribute?displayProperty=fullName> (keine Attribute-Attribut; Dies ist eine Ausnahme aus, um die Benennungsregel Attribut).

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Verweisklasse**, **Referenzstruktur**|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="example"></a>Beispiel

```cpp
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

## <a name="example"></a>Beispiel

Die `Inherited` das benannte Argument gibt an, ob ein benutzerdefiniertes Attribut auf eine Basisklasse angewendet, bei der Reflektion einer abgeleiteten Klasse angezeigt wird.

```cpp
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

```Output
2
```

## <a name="see-also"></a>Siehe auch

[Alphabetische Attributreferenz](../windows/attributes-alphabetical-reference.md)  
