---
title: Compilerunterstützung für Typmerkmale (C++ / CLI und C++ / CX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/12/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- __is_simple_value_class
- __has_trivial_destructor
- __has_assign
- __is_union
- __is_class
- __is_abstract
- __has_trivial_assign
- __has_virtual_destructor
- __is_ref_array
- __is_base_of
- __has_copy
- __is_polymorphic
- __has_nothrow_constructor
- __is_ref_class
- __is_delegate
- __is_convertible_to
- __is_value_class
- __is_interface_class
- __has_nothrow_copy
- __is_sealed
- __has_trivial_constructor
- __has_trivial_copy
- __is_enum
- __has_nothrow_assign
- __has_finalizer
- __is_empty
- __is_pod
- __has_user_destructor
dev_langs:
- C++
helpviewer_keywords:
- __is_class keyword [C++]
- __is_pod keyword [C++]
- __is_delegate keyword [C++]
- __is_value_class keyword [C++]
- __has_copy keyword [C++]
- __has_nothrow_copy keyword [C++]
- __is_interface_class keyword [C++]
- __is_sealed keyword [C++]
- __is_convertible_to keyword [C++]
- __is_ref_class keyword [C++]
- __has_trivial_copy keyword [C++]
- __has_user_destructor keyword [C++]
- __is_abstract keyword [C++]
- __is_empty keyword [C++]
- __has_trivial_assign keyword [C++]
- __has_nothrow_constructor keyword [C++]
- __is_ref_array keyword [C++]
- __is_base_of keyword [C++]
- __has_nothrow_assign keyword [C++]
- __has_virtual_destructor keyword [C++]
- __has_finalizer keyword [C++]
- __is_union keyword [C++]
- __has_assign keyword [C++]
- __has_trivial_destructor keyword [C++]
- __is_polymorphic keyword [C++]
- __is_enum keyword [C++]
- __is_simple_value_class keyword [C++]
- __has_trivial_constructor keyword [C++]
ms.assetid: cd440630-0394-48c0-a16b-1580b6ef5844
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bef92e7315418e13b660f655a54f20e8696c7590
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50066590"
---
# <a name="compiler-support-for-type-traits-ccli-and-ccx"></a>Compilerunterstützung für Typmerkmale (C++ / CLI und C++ / CX)

Der Microsoft C++-Compiler unterstützt *typmerkmale* für C++ / CLI und C++ / CX-Erweiterungen, die verschiedene Merkmale eines Typs zum Zeitpunkt der Kompilierung angeben.

## <a name="all-runtimes"></a>Alle Laufzeiten

### <a name="remarks"></a>Hinweise

Typeigenschaften sind besonders nützlich für Programmierer, die Bibliotheken schreiben.

Die folgende Liste enthält die Typeigenschaften, die vom Compiler unterstützt werden. Geben Sie alle Merkmale von Rückgabe **"false"** Wenn die durch den Namen der Typeigenschaft angegebene Bedingung nicht erfüllt wird.

(In der folgenden Liste sind Codebeispiele nur in C++ geschrieben c++ / CLI. Jedoch unterstützt die entsprechende Typeigenschaft auch in C++ / CX, sofern nichts anderes angegeben ist. Der Begriff bezieht sich "Plattformtyp" entweder Windows-Runtime-Typen oder common Language Runtime verwendet.)

- `__has_assign(` *Typ* `)`

   Gibt **"true"** , wenn die Plattform oder der systemeigene Typ einen Kopierzuweisungsoperator aufweist.

    ```cpp
    ref struct R {
    void operator=(R% r) {}
    };

    int main() {
    System::Console::WriteLine(__has_assign(R));
    }
    ```

- `__has_copy(` *Typ* `)`

   Gibt **"true"** , wenn die Plattform oder der systemeigene Typ einen Kopierkonstruktor aufweist.

    ```cpp
    ref struct R {
    R(R% r) {}
    };

    int main() {
    System::Console::WriteLine(__has_copy(R));
    }
    ```

- `__has_finalizer(` *Typ* `)`

   (Nicht unterstützt, die in C++ / CX.) Gibt **"true"** , wenn die CLR-Typ einen Finalizer aufweist. Finden Sie unter [Destruktoren und Finalizer in der Vorgehensweise: definieren und Verarbeiten von Klassen und Strukturen (C++ / CLI)](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers) für Weitere Informationen.

    ```cpp
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

- `__has_nothrow_assign(` *Typ* `)`

   Gibt **"true"** , wenn ein Kopierzuweisungsoperator eine leere Ausnahmespezifikation aufweist.

    ```cpp
    #include <stdio.h>
    struct S {
    void operator=(S& r) throw() {}
    };

    int main() {
    __has_nothrow_assign(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_nothrow_constructor(` *Typ* `)`

   Gibt **"true"** , wenn der Standardkonstruktor eine leere Ausnahmespezifikation aufweist.

    ```cpp
    #include <stdio.h>
    struct S {
    S() throw() {}
    };

    int main() {
    __has_nothrow_constructor(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_nothrow_copy(` *Typ* `)`

   Gibt **"true"** , wenn der Kopierkonstruktor eine leere Ausnahmespezifikation aufweist.

    ```cpp
    #include <stdio.h>
    struct S {
    S(S& r) throw() {}
    };

    int main() {
    __has_nothrow_copy(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_trivial_assign(` *Typ* `)`

   Gibt **"true"** Wenn der Typ einen trivialen, vom Compiler generierten Zuweisungsoperator aufweist.

    ```cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __has_trivial_assign(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_trivial_constructor(` *Typ* `)`

   Gibt **"true"** Wenn der Typ einen trivialen, vom Compiler generierten Konstruktor aufweist.

    ```cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __has_trivial_constructor(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_trivial_copy(` *Typ* `)`

   Gibt **"true"** Wenn der Typ einen trivialen, vom Compiler generierten Kopierkonstruktor aufweist.

    ```cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __has_trivial_copy(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_trivial_destructor(` *Typ* `)`

   Gibt **"true"** , wenn der Typ einen trivialen, vom Compiler generierten Destruktor aufweist.

    ``` cpp
    // has_trivial_destructor.cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __has_trivial_destructor(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_user_destructor(` *Typ* `)`

   Gibt **"true"** , wenn die Plattform oder der systemeigene Typ einen benutzerdeklarierten Destruktor aufweist.

    ```cpp
    // has_user_destructor.cpp

    using namespace System;
    ref class R {
    ~R() {}
    };

    int main() {
    Console::WriteLine(__has_user_destructor(R));
    }
    ```

- `__has_virtual_destructor(` *Typ* `)`

   Gibt **"true"** , wenn der Typ einen virtuellen Destruktor aufweist.

   `__has_virtual_destructor` funktioniert auch für Plattformtypen, und jeder benutzerdefinierte Destruktor in einem Plattformtyp ist ein virtueller Destruktor.

    ```cpp
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

- `__is_abstract(` *Typ* `)`

   Gibt **"true"** Wenn der Typ ein abstrakter Typ ist. Weitere Informationen zu systemeigenen abstrakten Typen finden Sie unter [abstrakte Klassen](../cpp/abstract-classes-cpp.md).

   `__is_abstract` funktioniert auch für die Plattformtypen. Eine Schnittstelle mit mindestens einem Member ist ein abstrakter Typ, genauso wie ein Verweistyp mit mindestens einem abstrakten Member. Weitere Informationen zu abstrakten Plattformtypen finden Sie unter [abstrakte](../windows/abstract-cpp-component-extensions.md).

    ```cpp
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

- `__is_base_of(` `base` `,` `derived` `)`

   Gibt **"true"** Wenn der erste Typ eine Basisklasse des zweiten Typs ist, zurück, wenn beide Typen sind identisch.

   `__is_base_of` funktioniert auch für Plattformtypen. Beispielsweise gibt es zurück **"true"** , wenn der erste Typ ist ein [Schnittstellenklasse](../windows/interface-class-cpp-component-extensions.md) und der zweite Typ implementiert die Schnittstelle.

    ```cpp
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

- `__is_class(` *Typ* `)`

   Gibt **"true"** Wenn der Typ eine systemeigene Klasse oder Struktur ist.

    ```cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __is_class(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__is_convertible_to(` `from` `,`  `to` `)`

   Gibt **"true"** , wenn der erste Typ in den zweiten Typ konvertiert werden kann.

    ```cpp
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

- `__is_delegate(` *Typ* `)`

   Gibt **"true"** Wenn `type` ist ein Delegat. Weitere Informationen finden Sie unter [delegieren (C++ / CLI und C++ / CX)](../windows/delegate-cpp-component-extensions.md).

    ```cpp
    delegate void MyDel();
    int main() {
    System::Console::WriteLine(__is_delegate(MyDel));
    }
    ```

- `__is_empty(` *Typ* `)`

   Gibt **"true"** Wenn der Typ keine instanzdatenmember aufweist.

    ```cpp
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

- `__is_enum(` *Typ* `)`

   Gibt **"true"** Wenn der Typ eine systemeigene Enumeration ist.

    ```cpp
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

- `__is_interface_class(` *Typ* `)`

   Gibt **"true"** , wenn eine plattformschnittstelle übergeben wurde. Weitere Informationen finden Sie unter [Schnittstellenklasse](../windows/interface-class-cpp-component-extensions.md).

    ```cpp
    // is_interface_class.cpp

    using namespace System;
    interface class I {};
    int main() {
    Console::WriteLine(__is_interface_class(I));
    }
    ```

- `__is_pod(` *Typ* `)`

   Gibt **"true"** ist der Typ eine Klasse oder Union ohne Konstruktor oder privaten oder geschützten nicht statischen Member, ohne Basisklassen und ohne virtuellen Funktionen. Weitere Informationen zu PODs finden Sie im C++-Standard in den Abschnitten 8.5.1/1, 9/4 und 3.9/10.

   `__is_pod` gibt „false“ für grundlegende Typen zurück.

    ```cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __is_pod(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__is_polymorphic(` *Typ* `)`

   Gibt **"true"** , wenn ein systemeigener Typ über virtuelle Funktionen verfügt.

    ```cpp
    #include <stdio.h>
    struct S {
    virtual void Test(){}
    };

    int main() {
    __is_polymorphic(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__is_ref_array(` *Typ* `)`

   Gibt **"true"** , wenn ein plattformarray übergeben wurde. Weitere Informationen finden Sie unter [Arrays](../windows/arrays-cpp-component-extensions.md).

    ```cpp
    using namespace System;
    int main() {
    array<int>^ x = gcnew array<int>(10);
    Console::WriteLine(__is_ref_array(array<int>));
    }
    ```

- `__is_ref_class(` *Typ* `)`

   Gibt **"true"** , wenn eine Verweisklasse übergeben wurde. Weitere Informationen zu benutzerdefinierten Verweistypen finden Sie unter [Klassen und Strukturen](../windows/classes-and-structs-cpp-component-extensions.md).

    ```cpp
    using namespace System;
    ref class R {};
    int main() {
    Console::WriteLine(__is_ref_class(Buffer));
    Console::WriteLine(__is_ref_class(R));
    }
    ```

- `__is_sealed(` *Typ* `)`

   Gibt **"true"** übergeben Sie eine Plattform oder einen systemeigenen Typ versiegelt gekennzeichnet. Weitere Informationen finden Sie unter [versiegelten](../windows/sealed-cpp-component-extensions.md).

    ```cpp
    ref class R sealed{};
    int main() {
    System::Console::WriteLine(__is_sealed(R));
    }
    ```

- `__is_simple_value_class(` *Typ* `)`

   Gibt **"true"** , wenn ein Werttyp übergeben, die keine Verweise auf dem Heap der Garbage collection enthält. Weitere Informationen zu benutzerdefinierten Werttypen finden Sie unter [Klassen und Strukturen](../windows/classes-and-structs-cpp-component-extensions.md).

    ```cpp
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

- `__is_union(` *Typ* `)`

   Gibt **"true"** Wenn ein Typ eine Union ist.

    ```cpp
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

- `__is_value_class(` *Typ* `)`

   Gibt **"true"** , wenn ein Werttyp übergeben. Weitere Informationen zu benutzerdefinierten Werttypen finden Sie unter [Klassen und Strukturen](../windows/classes-and-structs-cpp-component-extensions.md).

    ```cpp
    value struct V {};

    int main() {
    System::Console::WriteLine(__is_value_class(V));
    }
    ```

## <a name="windows-runtime"></a>Windows-Runtime

### <a name="remarks"></a>Hinweise

Die `__has_finalizer(` *Typ* `)` Typeigenschaft wird nicht unterstützt, da diese Plattform keine Finalizer unterstützt.

### <a name="requirements"></a>Anforderungen

Compileroption: `/ZW`

## <a name="common-language-runtime"></a>Common Language Runtime

### <a name="remarks"></a>Hinweise

(Es gibt keine plattformspezifischen Hinweise für diese Funktion.)

### <a name="requirements"></a>Anforderungen

Compileroption: `/clr`

### <a name="examples"></a>Beispiele

**Beispiel**

Im folgenden Codebeispiel wird veranschaulicht, wie Sie mit einer Klassenvorlage eine Compiler-Typeigenschaft für eine `/clr`-Kompilierung verfügbar machen. Weitere Informationen finden Sie unter [Windows-Laufzeit und verwaltete Vorlagen](../windows/windows-runtime-and-managed-templates-cpp-component-extensions.md).

```cpp
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

```Output
R is a ref class
```

## <a name="see-also"></a>Siehe auch

[Komponentenerweiterungen für .NET und UWP](../windows/component-extensions-for-runtime-platforms.md)