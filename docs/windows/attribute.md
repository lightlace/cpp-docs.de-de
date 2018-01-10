---
title: Attribut | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.attribute
dev_langs: C++
helpviewer_keywords:
- __typeof keyword
- custom attributes, creating
- attribute attribute
- attributes [C++], custom
ms.assetid: 8cb3489f-65c4-44ea-b0aa-3c3c6b15741d
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 42ea9049fdd97691bd139599705856baa8acfee1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="attribute"></a>Attribut
Ermöglicht Ihnen die Erstellung ein benutzerdefiniertes Attributs.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      [ attribute(  
   AllowOn,  
   AllowMultiple=boolean,  
   Inherited=boolean  
) ]  
```  
  
#### <a name="parameters"></a>Parameter  
 *AllowOn*  
 Gibt die Language-Elemente, die zu denen das benutzerdefinierte Attribut angewendet werden kann. Standardmäßig wird **System::AttributeTargets::All** (siehe [System::AttributeTargets](https://msdn.microsoft.com/en-us/library/system.attributetargets.aspx)).  
  
 `AllowMultiple`  
 Gibt an, ob das benutzerdefinierte Attribut wiederholt auf ein Konstrukt angewendet werden kann. Standardmäßig wird **"false"**.  
  
 `Inherited`  
 Gibt an, ob das Attribut von Unterklassen geerbt werden. Der Compiler bietet keine spezielle Unterstützung für diese Funktionalität; Es ist die Aufgabe Consumer Attribut (z. B. Reflektion), um diese Informationen zu berücksichtigen. Wenn `Inherited` ist **"true"**, das Attribut geerbt wird. Wenn `AllowMultiple` ist **"true"**, wird das Attribut für das abgeleitete Element; ansammeln, wenn `AllowMultiple` ist **"false"**, das Attribut wird außer Kraft setzen (oder ersetzen) bei der Vererbung. Wenn `Inherited` ist **"false"**, das Attribut nicht geerbt werden. Standardmäßig wird **"true"**.  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Die `attribute` Attribut ist jetzt veraltet.  Verwenden Sie die common Language Runtime-Attribut System.Attribute direkt, um eine benutzerdefinierte Attirbutes zu erstellen.  Weitere Informationen finden Sie unter [benutzerdefinierte Attribute](../windows/user-defined-attributes-cpp-component-extensions.md).  
  
 Sie definieren eine [benutzerdefiniertes Attribut](../windows/custom-attributes-cpp.md) platziert die `attribute` Attribut auf eine verwaltete Definition der Klasse oder Struktur. Der Name der Klasse ist das benutzerdefinierte Attribut. Zum Beispiel:  
  
```  
[ attribute(Parameter) ]  
public ref class MyAttr {};  
```  
  
 definiert ein Attribut namens MyAttr, der Funktionsparameter übernommen werden kann. Die Klasse muss als öffentlich, wenn das Attribut in anderen Assemblys verwendet werden soll.  
  
> [!NOTE]
>  Um zu verhindern, dass die Namespacekonflikte enden Attributnamen implizit mit "Attribut" In diesem Beispiel der Namen des Attributs und der Klasse wird tatsächlich MyAttrAttribute allerdings MyAttr und MyAttrAttribute austauschbar.  
  
 Öffentliche Konstruktoren für die Klasse definieren unbenannte Parameter des Attributs. Überladene Konstruktoren gestatten es mehrere Möglichkeiten, das Attribut anzugeben, damit ein benutzerdefiniertes Attribut, das wie folgt definiert:  
  
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
  
 Öffentliche Datenmember und Eigenschaften der Klasse sind optionale benannte Parameter für das Attribut:  
  
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
  
 Eine Liste der möglichen Attributparametertypen, finden Sie unter [benutzerdefinierte Attribute](../windows/custom-attributes-cpp.md).  
  
 Finden Sie unter [benutzerdefinierte Attribute](../windows/user-defined-attributes-cpp-component-extensions.md) eine Diskussion zur Attributziele.  
  
 Die `attribute` Attribut hat einen `AllowMultiple` Parameter, der angibt, ob das benutzerdefinierte Attribut einzelne verwendet wird oder Multiuse (stehen mehr als einmal auf die gleiche Entität).  
  
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
  
 Benutzerdefinierte Attributklassen abgeleitet sind direkt oder indirekt <xref:System.ComponentModel.AttributeCollection.%23ctor%2A>, welche macht Attributdefinitionen in Metadaten schnell und einfach zu identifizieren. Die `attribute` -Attributs impliziert Vererbung von System:: Attribute, damit explizite Ableitung nicht erforderlich ist:  
  
```  
[ attribute(Class) ]  
ref class MyAttr  
```  
  
 für die folgende Syntax:  
  
```  
[ attribute(Class) ]  
ref class MyAttr : System::Attribute   // OK, but redundant.  
```  
  
 `attribute`ist ein Alias für <xref:System.AttributeUsageAttribute?displayProperty=fullName> (nicht AttributeAttribute; Dies ist eine Ausnahme aus, um das Attribut Benennungsregel).  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|`ref`**Klasse**, **Referenzstruktur**|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keiner|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="example"></a>Beispiel  
  
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
  
## <a name="example"></a>Beispiel  
 Die `Inherited` benanntes Argument gibt an, ob ein benutzerdefiniertes Attribut in einer Basisklasse angewendet werden, auf Reflektion einer abgeleiteten Klasse angezeigt wird.  
  
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
  
```Output  
2  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Alphabetische Attributreferenz](../windows/attributes-alphabetical-reference.md)   
 [Benutzerdefinierte Attribute](http://msdn.microsoft.com/en-us/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)