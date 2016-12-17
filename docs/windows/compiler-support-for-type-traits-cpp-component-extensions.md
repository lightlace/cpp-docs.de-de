---
title: "Compilerunterst&#252;tzung f&#252;r Typmerkmale (Komponentenerweiterungen f&#252;r C++)"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "__is_simple_value_class"
  - "__has_trivial_destructor"
  - "__has_assign"
  - "__is_union"
  - "__is_class"
  - "__is_abstract"
  - "__has_trivial_assign"
  - "__has_virtual_destructor"
  - "__is_ref_array"
  - "__is_base_of"
  - "__has_copy"
  - "__is_polymorphic"
  - "__has_nothrow_constructor"
  - "__is_ref_class"
  - "__is_delegate"
  - "__is_convertible_to"
  - "__is_value_class"
  - "__is_interface_class"
  - "__has_nothrow_copy"
  - "__is_sealed"
  - "__has_trivial_constructor"
  - "__has_trivial_copy"
  - "__is_enum"
  - "__has_nothrow_assign"
  - "__has_finalizer"
  - "__is_empty"
  - "__is_pod"
  - "__has_user_destructor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__is_class-Schlüsselwort [C++]"
  - "__is_pod-Schlüsselwort [C++]"
  - "__is_delegate-Schlüsselwort [C++]"
  - "__is_value_class-Schlüsselwort [C++]"
  - "__has_copy-Schlüsselwort [C++]"
  - "__has_nothrow_copy-Schlüsselwort [C++]"
  - "__is_interface_class-Schlüsselwort [C++]"
  - "__is_sealed-Schlüsselwort [C++]"
  - "__is_convertible_to-Schlüsselwort [C++]"
  - "__is_ref_class-Schlüsselwort [C++]"
  - "__has_trivial_copy-Schlüsselwort [C++]"
  - "__has_user_destructor-Schlüsselwort [C++]"
  - "__is_abstract-Schlüsselwort [C++]"
  - "__is_empty-Schlüsselwort [C++]"
  - "__has_trivial_assign-Schlüsselwort [C++]"
  - "__has_nothrow_constructor-Schlüsselwort [C++]"
  - "__is_ref_array-Schlüsselwort [C++]"
  - "__is_base_of-Schlüsselwort [C++]"
  - "__has_nothrow_assign-Schlüsselwort [C++]"
  - "__has_virtual_destructor-Schlüsselwort [C++]"
  - "__has_finalizer-Schlüsselwort [C++]"
  - "__is_union-Schlüsselwort [C++]"
  - "__has_assign-Schlüsselwort [C++]"
  - "__has_trivial_destructor-Schlüsselwort [C++]"
  - "__is_polymorphic-Schlüsselwort [C++]"
  - "__is_enum-Schlüsselwort [C++]"
  - "__is_simple_value_class-Schlüsselwort [C++]"
  - "__has_trivial_constructor-Schlüsselwort [C++]"
ms.assetid: cd440630-0394-48c0-a16b-1580b6ef5844
caps.latest.revision: 27
caps.handback.revision: "27"
ms.author: "mblome"
manager: "ghogen"
---
# Compilerunterst&#252;tzung f&#252;r Typmerkmale (Komponentenerweiterungen f&#252;r C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Compiler unterstützt *Geben Merkmale*, die verschiedene Eigenschaften eines Typs zum Zeitpunkt der Kompilierung angeben.  
  
## <a name="all-runtimes"></a>Alle Laufzeiten  
 **Hinweise**  
  
 Typeigenschaften sind besonders nützlich für Programmierer, die Bibliotheken schreiben.  
  
 Die folgende Liste enthält die Typeigenschaften, die vom Compiler unterstützt werden. Alle Typeigenschaften geben `false` wieder, wenn die durch den Namen der Typeigenschaft angegebene Bedingung nicht erfüllt ist.  
  
 (In der folgenden Liste werden Codebeispiele wurden nur in [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)]. Jedoch wird die entsprechende Typeigenschaft auch in [!INCLUDE[cppwrt](../build/reference/includes/cppwrt_md.md)] unterstützt, sofern nichts anderes angegeben ist. Der Begriff „Plattformtyp“ bezieht sich entweder auf [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]-Typen oder Common Language Runtime-Typen.)  
  
-   `__has_assign(` `type` `)`  
  
     Gibt „true“ zurück, wenn die Plattform oder der systemeigene Typ einen Kopierzuweisungsoperator aufweist.  
  
    ```  
  
    ref struct R {  
    void operator=(R% r) {}  
    };  
  
    int main() {  
    System::Console::WriteLine(__has_assign(R));  
    }  
  
    ```  
  
-   `__has_copy(` `type` `)`  
  
     Gibt „true“ zurück, wenn die Plattform oder der systemeigene Typ einen Kopierkonstruktor aufweist.  
  
    ```  
  
    ref struct R {  
    R(R% r) {}  
    };  
  
    int main() {  
    System::Console::WriteLine(__has_copy(R));  
    }  
  
    ```  
  
-   `__has_finalizer(` `type` `)`  
  
     (Nicht unterstützt in [!INCLUDE[cppwrt](../build/reference/includes/cppwrt_md.md)].) Gibt „true“ zurück, wenn der CLR-Typ einen Finalizer aufweist. Finden Sie unter [Destruktoren und Finalizer in Visual C++](../misc/destructors-and-finalizers-in-visual-cpp.md) Weitere Informationen.  
  
    ```  
  
    using namespace System;  
    ref struct R {  
    ~R() {}  
    protected:  
    !R() {}  
    };  
  
    int main() {  
    Console::WriteLine(__has_finalizer(R));  
    }  
  
    ```  
  
-   `__has_nothrow_assign(` `type` `)`  
  
     Gibt „true“ zurück, wenn ein Kopierzuweisungsoperator eine leere Ausnahmespezifikation aufweist.  
  
    ```  
  
    #include <stdio.h>  
    struct S {  
    void operator=(S& r) throw() {}  
    };  
  
    int main() {  
    __has_nothrow_assign(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__has_nothrow_constructor(` `type` `)`  
  
     Gibt „true“ zurück, wenn ein Standardkonstruktor eine leere Ausnahmespezifikation aufweist.  
  
    ```  
  
    #include <stdio.h>  
    struct S {  
    S() throw() {}  
    };  
  
    int main() {  
    __has_nothrow_constructor(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__has_nothrow_copy(` `type` `)`  
  
     Gibt „true“ zurück, wenn der Kopierkonstruktor eine leere Ausnahmespezifikation aufweist.  
  
    ```  
  
    #include <stdio.h>  
    struct S {  
    S(S& r) throw() {}  
    };  
  
    int main() {  
    __has_nothrow_copy(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__has_trivial_assign(` `type` `)`  
  
     Gibt „true“ zurück, wenn der Typ einen trivialen, vom Compiler generierten Zuweisungsoperator aufweist.  
  
    ```  
  
    #include <stdio.h>  
    struct S {};  
  
    int main() {  
    __has_trivial_assign(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__has_trivial_constructor(` `type` `)`  
  
     Gibt „true“ zurück, wenn der Typ einen trivialen, vom Compiler generierten Konstruktor aufweist.  
  
    ```  
  
    #include <stdio.h>  
    struct S {};  
  
    int main() {  
    __has_trivial_constructor(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__has_trivial_copy(` `type` `)`  
  
     Gibt „true“ zurück, wenn der Typ einen trivialen, vom Compiler generierten Kopierkonstruktor aufweist.  
  
    ```  
  
    #include <stdio.h>  
    struct S {};  
  
    int main() {  
    __has_trivial_copy(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__has_trivial_destructor(` `type` `)`  
  
     Gibt „true“ zurück, wenn der Typ einen trivialen, vom Compiler generierten Destruktor aufweist.  
  
    ```  
  
    // has_trivial_destructor.cpp  
    #include <stdio.h>  
    struct S {};  
  
    int main() {  
    __has_trivial_destructor(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__has_user_destructor(` `type` `)`  
  
     Gibt „true“ zurück, wenn die Plattform oder der systemeigene Typ einen benutzerdeklarierten Destruktor aufweist.  
  
    ```  
  
    // has_user_destructor.cpp  
  
    using namespace System;  
    ref class R {  
    ~R() {}  
    };  
  
    int main() {  
    Console::WriteLine(__has_user_destructor(R));  
    }  
  
    ```  
  
-   `__has_virtual_destructor(` `type` `)`  
  
     Gibt „true“ zurück, wenn der Typ einen virtuellen Destruktor aufweist.  
  
     `__has_virtual_destructor` funktioniert auch für Plattformtypen, und jeder benutzerdefinierte Destruktor in einem Plattformtyp ist ein virtueller Destruktor.  
  
    ```  
  
    // has_virtual_destructor.cpp  
    #include <stdio.h>  
    struct S {  
    virtual ~S() {}  
    };  
  
    int main() {  
    __has_virtual_destructor(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_abstract(` `type` `)`  
  
     Gibt „true“ zurück, wenn der Typ ein abstrakter Typ ist. Weitere Informationen zu systemeigenen abstrakte Typen, finden Sie unter [abstrakte](../windows/abstract-cpp-component-extensions.md).  
  
     `__is_abstract` funktioniert auch für die Plattformtypen. Eine Schnittstelle mit mindestens einem Member ist ein abstrakter Typ, genauso wie ein Verweistyp mit mindestens einem abstrakten Member. Weitere Informationen zu abstrakten Plattformtypen, finden Sie unter [abstrakte Klassen](../cpp/abstract-classes-cpp.md)  
  
    ```  
  
    // is_abstract.cpp  
    #include <stdio.h>  
    struct S {  
    virtual void Test() = 0;  
    };  
  
    int main() {  
    __is_abstract(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_base_of(` `base` `,` `derived` `)`  
  
     Gibt „true“ zurück, wenn der erste Typ eine Basisklasse des zweiten Typs ist, oder wenn beide Typen identisch sind.  
  
     `__is_base_of` funktioniert auch für Plattformtypen. Z. B. zurückgegeben True, wenn der erste ist ein [Schnittstellenklasse](../windows/interface-class-cpp-component-extensions.md) und der zweite Typ implementiert die Schnittstelle.  
  
    ```  
  
    // is_base_of.cpp  
    #include <stdio.h>  
    struct S {};  
    struct T : public S {};  
  
    int main() {  
    __is_base_of(S, T) == true ?  
    printf("true\n") : printf("false\n");  
  
    __is_base_of(S, S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_class(` `type` `)`  
  
     Gibt „true“ zurück, wenn der Typ eine systemeigene Klasse oder Struktur ist.  
  
    ```  
  
    #include <stdio.h>  
    struct S {};  
  
    int main() {  
    __is_class(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_convertible_to(` `from` `,`  `to` `)`  
  
     Gibt „true“ zurück, wenn der erste Typ in den zweiten Typ konvertiert werden kann.  
  
    ```  
  
    #include <stdio.h>  
    struct S {};  
    struct T : public S {};  
  
    int main() {  
    S * s = new S;  
    T * t = new T;  
    s = t;  
    __is_convertible_to(T, S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_delegate(` `type` `)`  
  
     Gibt „true“ zurück, wenn `type` ein Delegat ist. Weitere Informationen finden Sie unter [Delegaten (C++-Komponentenerweiterungen)](../windows/delegate-cpp-component-extensions.md).  
  
    ```  
  
    delegate void MyDel();  
    int main() {  
    System::Console::WriteLine(__is_delegate(MyDel));  
    }  
  
    ```  
  
-   `__is_empty(` `type` `)`  
  
     Gibt „true“ zurück, wenn der Typ keine Instanzdatenmember aufweist.  
  
    ```  
  
    #include <stdio.h>  
    struct S {  
    int Test() {}  
    static int i;  
    };  
    int main() {  
    __is_empty(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_enum(` `type` `)`  
  
     Gibt „true“ zurück, wenn der Typ eine systemeigene Enumeration ist.  
  
    ```  
  
    // is_enum.cpp  
    #include <stdio.h>  
    enum E { a, b };  
  
    struct S {  
    enum E2 { c, d };  
    };  
  
    int main() {  
    __is_enum(E) == true ?  
    printf("true\n") : printf("false\n");  
  
    __is_enum(S::E2) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_interface_class(` `type` `)`  
  
     Gibt „true“ zurück, wenn eine Plattformschnittstelle übergeben wurde. Weitere Informationen finden Sie unter [Schnittstellenklasse](../windows/interface-class-cpp-component-extensions.md).  
  
    ```  
  
    // is_interface_class.cpp  
  
    using namespace System;  
    interface class I {};  
    int main() {  
    Console::WriteLine(__is_interface_class(I));  
    }  
  
    ```  
  
-   `__is_pod(` `type` `)`  
  
     Gibt „true“ zurück, wenn der Typ eine Klasse oder Union ohne Konstruktor oder private oder geschützte nicht-statische Member, ohne Basisklassen und ohne virtuelle Funktionen ist. Weitere Informationen zu PODs finden Sie im C++-Standard in den Abschnitten 8.5.1/1, 9/4 und 3.9/10.  
  
     `__is_pod` gibt „false“ für grundlegende Typen zurück.  
  
    ```  
  
    #include <stdio.h>  
    struct S {};  
  
    int main() {  
    __is_pod(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_polymorphic(` `type` `)`  
  
     Gibt „true“ zurück, wenn ein systemeigener Typ über virtuelle Funktionen verfügt.  
  
    ```  
  
    #include <stdio.h>  
    struct S {  
    virtual void Test(){}  
    };  
  
    int main() {  
    __is_polymorphic(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_ref_array(` `type` `)`  
  
     Gibt „true“ zurück, wenn ein Plattformarray übergeben wurde. Weitere Informationen finden Sie unter [Arrays](../windows/arrays-cpp-component-extensions.md).  
  
    ```  
  
    using namespace System;  
    int main() {  
    array<int>^ x = gcnew array<int>(10);  
    Console::WriteLine(__is_ref_array(array<int>));  
    }  
  
    ```  
  
-   `__is_ref_class(` `type` `)`  
  
     Gibt „true“ zurück, wenn eine Verweisklasse übergeben wurde. Weitere Informationen zu benutzerdefinierten Verweistypen, finden Sie unter [Klassen und Strukturen](../windows/classes-and-structs-cpp-component-extensions.md).  
  
    ```  
  
    using namespace System;  
    ref class R {};  
    int main() {  
    Console::WriteLine(__is_ref_class(Buffer));  
    Console::WriteLine(__is_ref_class(R));  
    }  
  
    ```  
  
-   `__is_sealed(` `type` `)`  
  
     Gibt „true“ zurück, wenn eine Plattform oder ein systemeigener, als „versiegelt“ gekennzeichneter Typ übergeben wurde. Weitere Informationen finden Sie unter [versiegelte](../windows/sealed-cpp-component-extensions.md).  
  
    ```  
  
    ref class R sealed{};  
    int main() {  
    System::Console::WriteLine(__is_sealed(R));  
    }  
  
    ```  
  
-   `__is_simple_value_class(` `type` `)`  
  
     Gibt „true“ zurück, wenn ein Werttyp übergeben wurde, der keine Verweise auf den Garbage Collection Heap enthält. Weitere Informationen zu benutzerdefinierten Typen, finden Sie unter [Klassen und Strukturen](../windows/classes-and-structs-cpp-component-extensions.md).  
  
    ```  
  
    using namespace System;  
    ref class R {};  
    value struct V {};  
    value struct V2 {  
    R ^ r;   // not a simnple value type  
    };  
  
    int main() {  
    Console::WriteLine(__is_simple_value_class(V));  
    Console::WriteLine(__is_simple_value_class(V2));  
    }  
  
    ```  
  
-   `__is_union(` `type` `)`  
  
     Gibt „true“ zurück, wenn ein Typ eine Union ist.  
  
    ```  
  
    #include <stdio.h>  
    union A {  
    int i;  
    float f;  
    };  
  
    int main() {  
    __is_union(A) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_value_class(` `type` `)`  
  
     Gibt „true“ zurück, wenn ein Werttyp übergeben wurde. Weitere Informationen zu benutzerdefinierten Typen, finden Sie unter [Klassen und Strukturen](../windows/classes-and-structs-cpp-component-extensions.md).  
  
    ```  
  
    value struct V {};  
  
    int main() {  
    System::Console::WriteLine(__is_value_class(V));  
    }  
  
    ```  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 **Hinweise**  
  
 Die `__has_finalizer(`*Typ*`)` Typmerkmal wird nicht unterstützt, weil diese Plattform Finalizer nicht unterstützt.  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: **/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **Hinweise**  
  
 (Es gibt keine plattformspezifischen Hinweise für diese Funktion.)  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: **/clr**  
  
### <a name="examples"></a>Beispiele  
 **Beispiel**  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie mit einer Klassenvorlage ein Compiler Typmerkmal für eine **/CLR** Kompilierung. Weitere Informationen finden Sie unter [Windows-Runtime und verwaltete Vorlagen](../windows/windows-runtime-and-managed-templates-cpp-component-extensions.md).  
  
```  
// compiler_type_traits.cpp  
// compile with: /clr  
using namespace System;  
  
template <class T>  
ref struct is_class {  
   literal bool value = __is_ref_class(T);  
};  
  
ref class R {};  
  
int main () {  
   if (is_class<R>::value)  
      Console::WriteLine("R is a ref class");  
   else  
      Console::WriteLine("R is not a ref class");  
}  
```  
  
 **Ausgabe**  
  
```Output  
R is a ref class  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md)