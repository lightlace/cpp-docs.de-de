---
title: Attribut-Ziele (Komponentenerweiterungen für C++) | Microsoft-Dokumentation
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
ms.openlocfilehash: f89eb3fcc48d8341190ceb5fe74a25570543e0cd
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39645590"
---
# <a name="attribute-targets-c-component-extensions"></a>Attributziele (Komponentenerweiterungen für C++)
Attribut Nutzung Bezeichner können Sie die Attributziele angeben.  Jedes Attribut wird definiert, um für die bestimmte Sprachelemente zu übernehmen. Beispielsweise kann ein Attribut definiert werden, um nur für Klassen und Strukturen zu übernehmen.  Die folgende Liste enthält die möglichen syntaktische Elemente, die auf denen ein benutzerdefiniertes Attribut verwendet werden kann. Kombinationen dieser Werte (Verwendung eines logischen oder) kann verwendet werden.  
  
 Attributziel, um eine oder mehrere übergeben an <xref:System.AttributeTargets> Enumeratoren zur <xref:System.AttributeUsageAttribute> , wenn das Attribut zu definieren.  
  
 Im folgenden finden eine Liste der Ziele, gültiges Attribut:  
  
-   `All` (gilt für alle Konstrukte)  
  
    ```cpp  
    using namespace System;  
    [AttributeUsage(AttributeTargets::All)]  
    ref class Attr : public Attribute {};  
  
    [assembly:Attr];  
    ```  
  
-   `Assembly` (gilt für eine gesamte Assembly)  
  
    ```cpp  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Assembly)]  
    ref class Attr : public Attribute {};  
  
    [assembly:Attr];  
    ```  
  
-   `Module` (gilt für ein Modul als Ganzes)  
  
    ```cpp  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Module)]  
    ref class Attr : public Attribute {};  
  
    [module:Attr];  
    ```  
  
-   `Class`  
  
    ```cpp  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Class)]  
    ref class Attr : public System::Attribute {};  
  
    [Attr]   // same as [class:Attr]  
    ref class MyClass {};  
    ```  
  
-   `Struct`  
  
    ```cpp  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Struct)]  
    ref class Attr : public Attribute {};  
  
    [Attr]   // same as [struct:Attr]  
    value struct MyStruct{};  
    ```  
  
-   `enum`  
  
    ```cpp  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Enum)]  
    ref class Attr : public Attribute {};  
  
    [Attr]   // same as [enum:Attr]  
    enum struct MyEnum{e, d};  
    ```  
  
-   `Constructor`  
  
    ```cpp  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Constructor)]  
    ref class Attr : public Attribute {};  
  
    ref struct MyStruct{  
    [Attr] MyStruct(){}   // same as [constructor:Attr]  
    };  
    ```  
  
-   `Method`  
  
    ```cpp  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Method)]  
    ref class Attr : public Attribute {};  
  
    ref struct MyStruct{  
    [Attr] void Test(){}   // same as [method:Attr]  
    };  
    ```  
  
-   `Property`  
  
    ```cpp  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Property)]  
    ref class Attr : public Attribute {};  
  
    ref struct MyStruct{  
    [Attr] property int Test;   // same as [property:Attr]  
    };  
    ```  
  
-   `Field`  
  
    ```cpp  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Field)]  
    ref class Attr : public Attribute {};  
  
    ref struct MyStruct{  
    [Attr] int Test;   // same as [field:Attr]  
    };  
    ```  
  
-   `Event`  
  
    ```cpp  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Event)]  
    ref class Attr : public Attribute {};  
  
    delegate void ClickEventHandler(int, double);  
  
    ref struct MyStruct{  
    [Attr] event ClickEventHandler^ OnClick;   // same as [event:Attr]  
    };  
    ```  
  
-   `Interface`  
  
    ```cpp  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Interface)]  
    ref class Attr : public Attribute {};  
  
    [Attr]   // same as [event:Attr]  
    interface struct MyStruct{};  
    ```  
  
-   `Parameter`  
  
    ```cpp  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Parameter)]  
    ref class Attr : public Attribute {};  
  
    ref struct MyStruct{  
    void Test([Attr] int i);  
    void Test2([parameter:Attr] int i);  
    };  
    ```  
  
-   `Delegate`  
  
    ```cpp  
    using namespace System;  
    [AttributeUsage(AttributeTargets::Delegate)]  
    ref class Attr : public Attribute {};  
  
    [Attr] delegate void Test();  
    [delegate:Attr] delegate void Test2();  
    ```  
  
-   `ReturnValue`  
  
    ```cpp  
    using namespace System;  
    [AttributeUsage(AttributeTargets::ReturnValue)]  
    ref class Attr : public Attribute {};  
  
    ref struct MyStruct {  
    // Note required specifier  
    [returnvalue:Attr] int Test() { return 0; }  
    };  
    ```  
  
 Ein Attribut steht in der Regel direkt das Language-Element, das auf dem es angewendet. In einigen Fällen ist jedoch die Position eines Attributs nicht ausreichen, um das beabsichtigte Ziel des Attributs bestimmt. Betrachten Sie das folgende Beispiel:  
  
```cpp  
[Attr] int MyFn(double x)...  
```  
  
 Syntaktisch gesehen besteht keine Möglichkeit, festzustellen, ob das Attribut an die Methode oder Rückgabewert der Methode angewendet werden soll (in diesem Fall wird standardmäßig an die Methode). In solchen Fällen kann einem Nutzung Attributspezifizierer verwendet werden. Damit wird das Attribut auf den zurückgegebenen Wert anwenden, verwenden Sie z. B. die `returnvalue` Spezifizierer wie folgt:  
  
```cpp  
[returnvalue:Attr] int MyFn(double x)... // applies to return value  
```  
  
 Attribut Nutzung Bezeichner sind in den folgenden Situationen erforderlich:  
  
-   Um ein Attribut auf Assemblyebene oder Modul anzugeben.  
  
-   So geben Sie an, dass ein Attribut für den Rückgabewert einer Methode, nicht die Methode gilt:  
  
    ```cpp  
    [method:Attr] int MyFn(double x)...     // Attr applies to method  
    [returnvalue:Attr] int MyFn(double x)...// Attr applies to return value  
    [Attr] int MyFn(double x)...            // default: method  
    ```  
  
-   So geben Sie an, dass ein Attribut für einen Eigenschaftenaccessor nicht die Eigenschaft gilt:  
  
    ```cpp  
    [method:MyAttr(123)] property int Property()    
    [property:MyAttr(123)] property int Property()  
    [MyAttr(123)] property int get_MyPropy() // default: property  
    ```  
  
-   So geben Sie an, dass ein Attribut eines Ereignisses Accessor, nicht das Ereignis für die gilt:  
  
    ```cpp  
    delegate void MyDel();  
    ref struct X {  
       [field:MyAttr(123)] event MyDel* MyEvent;   //field  
       [event:MyAttr(123)] event MyDel* MyEvent;   //event  
       [MyAttr(123)] event MyDel* MyEvent;   // default: event  
    }  
    ```  
  
 Ein Attributspezifizierer-Nutzung gilt nur für das Attribut, das unmittelbar. Das heißt  
  
```cpp  
[returnvalue:Attr1, Attr2]  
```  
  
 unterscheidet sich von  
  
```cpp  
[returnvalue:Attr1, returnvalue:Attr2]  
```  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Dieses Beispiel zeigt, wie Sie mehrere Ziele angeben.  
  
### <a name="code"></a>Code  
  
```cpp  
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