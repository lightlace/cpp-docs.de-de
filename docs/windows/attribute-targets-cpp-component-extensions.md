---
title: "Attributziele (Komponentenerweiterungen f&#252;r C++)"
ms.custom: na
ms.date: "12/03/2016"
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
  - "benutzerdefinierte Attribute, Ziele"
ms.assetid: b4e6e224-da77-4520-b6e6-b96846e0ebc1
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Attributziele (Komponentenerweiterungen f&#252;r C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Attribut Nutzung Bezeichner können Sie Attributziele angeben.  Jedes Attribut wird definiert, um für bestimmte Sprachelemente zu übernehmen. Beispielsweise kann ein Attribut definiert werden, um gelten nur für Klassen und Strukturen.  Die folgende Liste zeigt die möglichen syntaktischen Elemente, die auf denen ein benutzerdefiniertes Attribut verwendet werden kann. Kombinationen dieser Werte (mit oder) können verwendet werden.  
  
 Attributziel, um eine oder mehrere übergeben an <xref:System.AttributeTargets> Enumeratoren <xref:System.AttributeUsageAttribute> beim Definieren des Attributs.  
  
 Im folgenden finden eine Liste der gültigen Attributnamen Ziele:  
  
-   `All` (gilt für alle Konstrukte)  
  
    ```  
  
    using namespace System;  
    [AttributeUsage(AttributeTargets::All)]  
    ref class Attr : public Attribute {};  
  
    [assembly:Attr];  
  
    ```  
  
-   `Assembly` (gilt für eine gesamte Assembly)  
  
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
  
 Ein Attribut steht in der Regel das Language-Element wird direkt vor. In einigen Fällen ist jedoch die Position eines Attributs nicht ausreichen, um das beabsichtigte Ziel des Attributs bestimmt. Betrachten Sie das folgende Beispiel:  
  
```  
[Attr] int MyFn(double x)...  
```  
  
 Syntaktisch gesehen besteht keine Möglichkeit, festzustellen, ob das Attribut an die Methode oder auf den Rückgabewert der Methode angewendet werden soll (in diesem Fall wird standardmäßig der Methode). In solchen Fällen kann ein Attribut Nutzung-Bezeichner verwendet werden. Damit wird das Attribut auf den Rückgabewert angewendet, z. B. Verwenden der `returnvalue` -Bezeichner wie folgt:  
  
```  
[returnvalue:Attr] int MyFn(double x)... // applies to return value  
```  
  
 Attribut Nutzung Bezeichner sind in den folgenden Situationen erforderlich:  
  
-   Ein Attribut auf Assemblyebene oder Modul angeben.  
  
-   So geben Sie an, dass ein Attribut für den Rückgabewert einer Methode, nicht die Methode gilt  
  
    ```  
    [method:Attr] int MyFn(double x)...     // Attr applies to method  
    [returnvalue:Attr] int MyFn(double x)...// Attr applies to return value  
    [Attr] int MyFn(double x)...            // default: method  
    ```  
  
-   So geben Sie an, dass ein Attribut auf einen Eigenschaftenaccessor nicht die Eigenschaft angewendet wird  
  
    ```  
    [method:MyAttr(123)] property int Property()    
    [property:MyAttr(123)] property int Property()  
    [MyAttr(123)] property int get_MyPropy() // default: property  
    ```  
  
-   Um anzugeben, dass ein Attribut auf ein Ereignis Accessor, nicht auf das Ereignis angewendet wird:  
  
    ```  
    delegate void MyDel();  
    ref struct X {  
       [field:MyAttr(123)] event MyDel* MyEvent;   //field  
       [event:MyAttr(123)] event MyDel* MyEvent;   //event  
       [MyAttr(123)] event MyDel* MyEvent;   // default: event  
    }  
    ```  
  
 Ein Attribut Nutzung Spezifizierer gilt nur für das Attribut, das unmittelbar auf ihn folgt. Das heißt  
  
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