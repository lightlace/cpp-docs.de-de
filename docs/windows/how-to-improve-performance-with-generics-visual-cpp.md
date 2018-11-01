---
title: 'Vorgehensweise: Verbessern der Leistung mit Generika (C++ / CLI)'
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- performance, C++
- C++, performance
- C++, generics
- generics [C++], performance
ms.assetid: f14a175b-301f-46cc-86e4-c82d35f9aa3e
ms.openlocfilehash: 61d858542505b0e37b03e13cca803df10ffbdddc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50527958"
---
# <a name="how-to-improve-performance-with-generics-ccli"></a>Vorgehensweise: Verbessern der Leistung mit Generika (C++ / CLI)

Mit Generika können Sie wiederverwendbaren Code, die auf einem Typparameter basierenden erstellen. Der tatsächliche Typ des Typparameters wird verzögert, bis von Clientcode aufgerufen wird. Weitere Informationen zu Generika finden Sie unter [Generics](../windows/generics-cpp-component-extensions.md).

In diesem Artikel wird erläutert, wie Generika können die Leistung einer Anwendung zu erhöhen, die Auflistungen verwendet.

## <a name="example"></a>Beispiel

Viele Auflistungsklassen im Lieferumfang von .NET Framework die <xref:System.Collections?displayProperty=fullName> Namespace. Die meisten dieser Sammlungen ausgeführt werden, für Objekte vom Typ <xref:System.Object?displayProperty=fullName>. Dadurch können Sammlungen, um einen beliebigen Typ zu speichern, da alle Typen in .NET Framework auch Werttypen abgeleitet <xref:System.Object?displayProperty=fullName>. Es gibt jedoch zwei Nachteile dieses Ansatzes.

Zuerst, wenn die Auflistung Werttypen wie z. B. ganze Zahlen gespeichert werden, der Wert muss mittels Boxing konvertiert, bevor Sie der Auflistung hinzugefügt werden und mittels Unboxing zurückkonvertiert, wenn der Wert aus der Auflistung abgerufen wird. Hierbei handelt es sich um kostenintensive Vorgänge.

Zweitens besteht keine Möglichkeit, die steuern, welche Typen für eine Sammlung hinzugefügt werden können. Es ist durchaus legal, eine ganze Zahl oder eine Zeichenfolge der gleichen Auflistung hinzufügen, obwohl dies ist wahrscheinlich nicht beabsichtigt war. In der Reihenfolge für Ihren Code typsicher gelten kann, müssen Sie daher überprüfen, dass der Typ, der aus der Auflistung abgerufen wirklich Was erwartet wurde.

Im folgenden Codebeispiel wird veranschaulicht, die zwei größere Nachteile von der .NET Framework-Auflistungen vor Generika.

```cpp
// perf_pre_generics.cpp
// compile with: /clr

using namespace System;
using namespace System::Collections;

int main()
{
    // This Stack can contain any type.
    Stack ^s = gcnew Stack();

    // Push an integer to the Stack.
    // A boxing operation is performed here.
    s->Push(7);

    // Push a String to the same Stack.
    // The Stack now contains two different data types.
    s->Push("Seven");

    // Pop the items off the Stack.
    // The item is returned as an Object, so a cast is
    // necessary to convert it to its proper type.
    while (s->Count> 0)
    {
        Object ^o = s->Pop();
        if (o->GetType() == Type::GetType("System.String"))
        {
            Console::WriteLine("Popped a String: {0}", (String ^)o);
        }
        else if (o->GetType() == Type::GetType("System.Int32"))
        {
            Console::WriteLine("Popped an int: {0}", (int)o);
        }
        else
        {
            Console::WriteLine("Popped an unknown type!");
        }
    }
}
```

```Output
Popped a String: Seven
Popped an int: 7
```

## <a name="example"></a>Beispiel

Die neue <xref:System.Collections.Generic?displayProperty=fullName> -Namespace enthält viele der gleichen Sammlungen finden Sie in der <xref:System.Collections?displayProperty=fullName> -Namespace, aber sie generische Typparameter akzeptieren geändert wurden. Dadurch, dass zwei Nachteile von nicht generischen Auflistungen: das Boxing und unboxing eines Werttypen und die Unfähigkeit, die Typen angeben, in den Auflistungen gespeichert werden. Vorgänge für die beiden Auflistungen sind identisch. Sie unterscheiden sich nur in der Weise, wie sie instanziiert werden.

Vergleichen Sie das Beispiel oben in diesem Beispiel, das einen generischen verwendet geschrieben <xref:System.Collections.Generic.Stack%601> Auflistung. Für große Auflistungen, die häufig zugegriffen werden, werden in diesem Beispiel wird die Leistung deutlich höher als im vorherigen Beispiel.

```cpp
// perf_post_generics.cpp
// compile with: /clr

#using <System.dll>

using namespace System;
using namespace System::Collections::Generic;

int main()
{
    // This Stack can only contain integers.
    Stack<int> ^s = gcnew Stack<int>();

    // Push an integer to the Stack.
    // A boxing operation is performed here.
    s->Push(7);
    s->Push(14);

    // You can no longer push a String to the same Stack.
    // This will result in compile time error C2664.
    //s->Push("Seven");

    // Pop an item off the Stack.
    // The item is returned as the type of the collection, so no
    // casting is necessary and no unboxing is performed for
    // value types.
    int i = s->Pop();
    Console::WriteLine(i);

    // You can no longer retrieve a String from the Stack.
    // This will result in compile time error C2440.
    //String ^str = s->Pop();
}
```

```Output
14
```

## <a name="see-also"></a>Siehe auch

[Generika](../windows/generics-cpp-component-extensions.md)