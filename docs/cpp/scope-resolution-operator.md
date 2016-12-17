---
title: "Bereichsaufl&#246;sungsoperator: ::"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "::"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "::-Operator"
  - "Operatoren [C++], Bereichsauflösung"
  - "Bereichsauflösungsoperator"
  - "Gültigkeitsbereich, Bereichsauflösungsoperator"
ms.assetid: fd5de9d3-c716-4e12-bae9-03a16fd79a50
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Bereichsaufl&#246;sungsoperator: ::
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Bereichsauflösungsoperator `::` wird zur Identifikation und eindeutigen Angabe von Bezeichnern in unterschiedlichen Geltungsbereichen verwendet.  Weitere Informationen zu Geltungsbereichen finden Sie unter [Bereich](../cpp/scope-visual-cpp.md).  
  
## Syntax  
  
```  
:: identifier class-name :: identifier namespace :: identifier enum class :: identifier enum struct :: identifier  
```  
  
## Hinweise  
 `identifier` kann eine Variable, eine Funktion oder ein Enumerationswert sein.  
  
## Mit Klassen und Namespaces  
 Das folgende Beispiel zeigt die Verwendung des Bereichsauflösungsoperators mit Namespaces und Klassen:  
  
```cpp  
namespace NamespaceA{  
    int x;  
    class ClassA {  
    public:  
        int x;  
    };  
}  
  
int main() {  
  
    // A namespace name used to disambiguate  
    NamespaceA::x = 1;  
  
    // A class name used to disambiguate  
    NamespaceA::ClassA a1;  
    a1.x = 2;  
  
}  
  
```  
  
 Ein Bereichsauflösungsoperator ohne Bereichsqualifizierer verweist auf den globalen Namespace.  
  
```cpp  
namespace NamespaceA{  
    int x;  
}  
  
int x;   
  
int main() {  
    int x;  
  
    // the x in main()  
    x = 0;   
    // The x in the global namespace  
    ::x = 1;   
  
    // The x in the A namespace  
    NamespaceA::x = 2;   
}  
```  
  
 Mit dem Bereichsauflösungsoperator können Sie ein Mitglied eines Namespaces oder einen Namespace, der den Namespace des Mitglieds benennt, in einer using\-Anweisung identifizieren.  Im folgenden Beispiel können Sie `NamespaceC` zum Qualifizieren von `ClassB` verwenden, obwohl `ClassB` im Namespace `NamespaceB` deklariert wurde, da `NamespaceB` in `NamespaceC` durch eine using\-Anweisung benannt wurde.  
  
```cpp  
namespace NamespaceB {  
    class ClassB {  
    public:  
        int x;  
    };  
}  
  
namespace NamespaceC{  
    using namespace B;  
  
}  
int main() {  
    NamespaceB::ClassB c_b;  
    NamespaceC::ClassB c_c;  
  
    c_b.x = 3;  
    c_c.x = 4;  
}  
  
```  
  
 Bereichsauflösungsoperatoren können verkettet werden.  Im folgenden Beispiel identifiziert `NamespaceD::NamespaceD1` den geschachtelten Namespace `NamespaceD1`, und `NamespaceE::ClassE::ClassE1` identifiziert die geschachtelte Klasse `ClassE1`.  
  
```cpp  
namespace NamespaceD{  
    namespace NamespaceD1{  
        int x;  
    }  
}  
  
namespace NamespaceE{  
  
    class ClassE{  
    public:  
        class ClassE1{  
        public:  
            int x;  
        };  
    };  
}  
  
int main() {  
    NamespaceD:: NamespaceD1::x = 6;  
    NamespaceE::ClassE::ClassE1 e1;  
    e1.x = 7  ;  
}  
  
```  
  
## Mit statischen Members  
 Sie müssen den Bereichsauflösungsoperator verwenden, um statische Member von Klassen aufzurufen.  
  
```cpp  
class ClassG {  
public:  
    static int get_x() { return x;}  
    static int x;  
};  
  
int ClassG::x = 6;  
  
int main() {  
  
    int gx1 = ClassG::x;  
    int gx2 = ClassG::get_x();   
}  
  
```  
  
## Mit bereichsbezogenen Enumerationen  
 Der Bereichsauflösungsoperator wird außerdem mit den Werten einer bereichsbezogenen Enumeration in [Enumerationsdeklarationen](../cpp/enumerations-cpp.md) verwendet, wie im folgenden Beispiel gezeigt:  
  
```cpp  
enum class EnumA{  
    First,  
    Second,  
    Third  
};  
  
int main() {  
  
    EnumA enum_value = EnumA::First;  
}  
  
```  
  
## Siehe auch  
 [C\+\+\-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Namespaces](../cpp/namespaces-cpp.md)   
 [Namen und qualifizierte Namen](../misc/names-and-qualified-names.md)