---
title: Ziele (Komponentenerweiterungen für C++)-Attribut | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- custom attributes, targets
ms.assetid: b4e6e224-da77-4520-b6e6-b96846e0ebc1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0de383c6d97f12a1caecbc8fbc7063513a898f50
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="attribute-targets-c-component-extensions"></a>Attributziele (Komponentenerweiterungen für C++)
Attribut Nutzung Spezifizierer können Sie Attributziele angeben.  Jedes Attribut wird definiert, um auf bestimmte Sprachelemente zu übernehmen. Beispielsweise könnte ein Attribut definiert werden, um gelten nur für Klassen und Strukturen.  Die folgende Liste enthält die möglichen syntaktischen Elemente, die auf denen ein benutzerdefiniertes Attribut verwendet werden kann. Kombinationen dieser Werte (mithilfe von logischen oder) kann verwendet werden.  
  
 An Attributziel, übergeben Sie eine oder mehrere <xref:System.AttributeTargets> Enumeratoren <xref:System.AttributeUsageAttribute> Wenn Sie das Attribut zu definieren.  
  
 Im folgenden finden eine Liste der gültigen Attributtyp Ziele:  
  
-   `All` (gilt für alle Konstrukte)  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::All)]  
    ref class Attr : public Attribute {};  
  
    [assembly:Attr];  
  
    ```  
  
-   `Assembly` (gilt für eine Assembly als Ganzes)  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Assembly)]  
    ref class Attr : public Attribute {};  
  
    [assembly:Attr];  
  
    ```  
  
-   `Module` (gilt für ein Modul als Ganzes)  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Module)]  
    ref class Attr : public Attribute {};  
  
    [module:Attr];  
  
    ```  
  
-   `Class`  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Class)]  
    ref class Attr : public System::Attribute {};  
  
    [Attr]   // same as [class:Attr]  
    ref class MyClass {};  
  
    ```  
  
-   `Struct`  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Struct)]  
    ref class Attr : public Attribute {};  
  
    [Attr]   // same as [struct:Attr]  
    value struct MyStruct{};  
  
    ```  
  
-   `enum`  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Enum)]  
    ref class Attr : public Attribute {};  
  
    [Attr]   // same as [enum:Attr]  
    enum struct MyEnum{e, d};  
  
    ```  
  
-   `Constructor`  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Constructor)]  
    ref class Attr : public Attribute {};  
  
    ref struct MyStruct{  
    [Attr] MyStruct(){}   // same as [constructor:Attr]  
    };  
  
    ```  
  
-   `Method`  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Method)]  
    ref class Attr : public Attribute {};  
  
    ref struct MyStruct{  
    [Attr] void Test(){}   // same as [method:Attr]  
    };  
  
    ```  
  
-   `Property`  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Property)]  
    ref class Attr : public Attribute {};  
  
    ref struct MyStruct{  
    [Attr] property int Test;   // same as [property:Attr]  
    };  
  
    ```  
  
-   `Field`  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Field)]  
    ref class Attr : public Attribute {};  
  
    ref struct MyStruct{  
    [Attr] int Test;   // same as [field:Attr]  
    };  
  
    ```  
  
-   `Event`  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Event)]  
    ref class Attr : public Attribute {};  
  
    delegate void ClickEventHandler(int, double);  
  
    ref struct MyStruct{  
    [Attr] event ClickEventHandler^ OnClick;   // same as [event:Attr]  
    };  
  
    ```  
  
-   `Interface`  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Interface)]  
    ref class Attr : public Attribute {};  
  
    [Attr]   // same as [event:Attr]  
    interface struct MyStruct{};  
  
    ```  
  
-   `Parameter`  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Parameter)]  
    ref class Attr : public Attribute {};  
  
    ref struct MyStruct{  
    void Test([Attr] int i);  
    void Test2([parameter:Attr] int i);  
    };  
  
    ```  
  
-   `Delegate`  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Delegate)]  
    ref class Attr : public Attribute {};  
  
    [Attr] delegate void Test();  
    [delegate:Attr] delegate void Test2();  
  
    ```  
  
-   `ReturnValue`  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::ReturnValue)]  
    ref class Attr : public Attribute {};  
  
    ref struct MyStruct {  
    // Note required specifier  
    [returnvalue:Attr] int Test() { return 0; }  
    };  
  
    ```  
  
 Ein Attribut ist in der Regel das Language-Element, für das er gilt, direkt vorangestellt. In einigen Fällen ist jedoch die Position eines Attributs nicht ausreichend, um das beabsichtigte Ziel für das Attribut zu bestimmen. Betrachten Sie das folgende Beispiel:  
  
```  
[Attr] int MyFn(double x)...  
```  
  
 Syntaktisch, besteht keine Möglichkeit mitteilen, ob das Attribut an die Methode oder Rückgabewert der Methode angewendet werden soll (in diesem Fall wird standardmäßig an die Methode). In solchen Fällen kann eine Verwendung der Attributspezifizierer verwendet werden. Beispielsweise verwenden, um das Attribut für den Rückgabewert gelten zu machen, die `returnvalue` Spezifizierer wie folgt:  
  
```  
[returnvalue:Attr] int MyFn(double x)... // applies to return value  
```  
  
 Attribut Nutzung Spezifizierer sind in den folgenden Situationen erforderlich:  
  
-   Ein Attribut auf Assemblyebene oder Modul angeben.  
  
-   So geben Sie an, dass ein Attribut für den Rückgabewert einer Methode, nicht die Methode gilt:  
  
    ```  
    [method:Attr] int MyFn(double x)...     // Attr applies to method  
    [returnvalue:Attr] int MyFn(double x)...// Attr applies to return value  
    [Attr] int MyFn(double x)...            // default: method  
    ```  
  
-   So geben Sie an, dass ein Attribut für einen Eigenschaftenaccessor nicht die Eigenschaft gilt:  
  
    ```  
    [method:MyAttr(123)] property int Property()    
    [property:MyAttr(123)] property int Property()  
    [MyAttr(123)] property int get_MyPropy() // default: property  
    ```  
  
-   So geben Sie an, dass ein Attribut für ein Ereignis Accessor, nicht auf das Ereignis gilt:  
  
    ```  
    delegate void MyDel();  
    ref struct X {  
       [field:MyAttr(123)] event MyDel* MyEvent;   //field  
       [event:MyAttr(123)] event MyDel* MyEvent;   //event  
       [MyAttr(123)] event MyDel* MyEvent;   // default: event  
    }  
    ```  
  
 Eine Verwendung der Attributspezifizierer gilt nur für das Attribut, das unmittelbar; Das heißt  
  
```  
[returnvalue:Attr1, Attr2]  
```  
  
 unterscheidet sich von  
  
```  
[returnvalue:Attr1, returnvalue:Attr2]  
```  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Dieses Beispiel zeigt, wie Sie mehrere Ziele angeben.  
  
### <a name="code"></a>Code  
  
```  
  
using namespace System;  
[AttributeUsage(AttributeTargets::Class | AttributeTargets::Struct, AllowMultiple = true )]  
ref struct Attr : public Attribute {  
   Attr(bool i){}  
   Attr(){}  
};  
  
[Attr]  
ref class MyClass {};  
  
[Attr]  
[Attr(true)]  
value struct MyStruct {};  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Benutzerdefinierte Attribute](../windows/user-defined-attributes-cpp-component-extensions.md)