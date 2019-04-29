---
title: 'Vorgehensweise: Machen Sie einen STL/CLR-Container aus einer Assembly verfügbar'
ms.date: 11/04/2016
helpviewer_keywords:
- STL/CLR Containers [STL/CLR]
- STL/CLR, cross-assembly issues
ms.assetid: 87efb41b-3db3-4498-a2e7-f3ef8a99f04d
ms.openlocfilehash: 206a95cbaa808f54d7ae0e500b5a2bea272d974b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387330"
---
# <a name="how-to-expose-an-stlclr-container-from-an-assembly"></a>Vorgehensweise: Machen Sie einen STL/CLR-Container aus einer Assembly verfügbar

STL/CLR-Container, z. B. `list` und `map` werden als vorlagenverweisklassen implementiert. Da C++-Vorlagen zum Zeitpunkt der Kompilierung instanziiert werden, sind zwei Vorlagenklassen, die genau die gleiche Signatur haben, aber in verschiedenen Assemblys sind tatsächlich verschiedene Typen. Dies bedeutet, dass Vorlagenklassen können nicht über assemblygrenzen hinweg verwendet werden.

Um assemblyübergreifende Freigabe zu ermöglichen, STL/CLR-Container implementieren die generische Schnittstelle <xref:System.Collections.Generic.ICollection%601>. Mithilfe der generischen Schnittstelle können alle Sprachen, die generische Typen, einschließlich C++, c# und Visual Basic unterstützen STL/CLR-Container zugreifen.

In diesem Thema erfahren Sie, wie die Elemente von mehreren STL/CLR-Container, die aus einer C++-Assembly, die mit dem Namen angezeigt werden sollen `StlClrClassLibrary`. Wir zeigen zwei Assemblys den Zugriff auf `StlClrClassLibrary`. Die erste Assembly wird in C++ und der zweite in c# geschrieben.

Wenn beide Assemblys in C++ geschrieben sind, können Sie die generische Schnittstelle eines Containers zugreifen, mithilfe dessen `generic_container` Typedef. Wenn Sie einen Container des Typs haben z. B. `cliext::vector<int>`, dann ist die generische Schnittstelle: `cliext::vector<int>::generic_container`. Sie können auf ähnliche Weise einen Iterator über die generische Schnittstelle abrufen, mithilfe der `generic_iterator` Typedef verwendet werden, wie in: `cliext::vector<int>::generic_iterator`.

Da dieser Typdefinitionen im C++-Headerdateien deklariert werden, können keine Assemblys, die in anderen Sprachen geschrieben werden. Aus diesem Grund die generische Schnittstelle für den Zugriff auf `cliext::vector<int>` in c# oder jeder anderen verwenden `System.Collections.Generic.ICollection<int>`. Um diese Auflistung durchlaufen, verwenden Sie eine `foreach` Schleife.

Die folgende Tabelle enthält die generische Schnittstelle, die jeder STL/CLR-Container implementiert:

|STL/CLR container|Generische Schnittstelle|
|------------------------|-----------------------|
|`deque<T>`|`ICollection<T>`|
|`hash_map<K, V>`|`IDictionary<K, V>`|
|`hash_multimap<K, V>`|`IDictionary<K, V>`|
|`hash_multiset<T>`|`ICollection<T>`|
|`hash_set<T>`|`ICollection<T>`|
|`list<T>`|`ICollection<T>`|
|`map<K, V>`|`IDictionary<K, V>`|
|`multimap<K, V>`|`IDictionary<K, V>`|
|`multiset<T>`|`ICollection<T>`|
|`set<T>`|`ICollection<T>`|
|`vector<T>`|`ICollection<T>`|

> [!NOTE]
> Da die `queue`, `priority_queue`, und `stack` Container unterstützen keine Iteratoren, die sie implementieren nicht generische Schnittstellen und können nicht assemblyübergreifende zugegriffen werden.

## <a name="example-1"></a>Beispiel 1

### <a name="description"></a>Beschreibung

In diesem Beispiel deklarieren wir eine C++-Klasse, die private STL/CLR-Elementdaten enthält. Klicken Sie dann deklarieren wir die öffentliche Methoden gewähren Zugriff auf die private Auflistungen von der Klasse. Wir führen es zwei Möglichkeiten, eine für C++-Clients und eine für andere Clients .NET.

### <a name="code"></a>Code

```cpp
// StlClrClassLibrary.h
#pragma once

#include <cliext/deque>
#include <cliext/list>
#include <cliext/map>
#include <cliext/set>
#include <cliext/stack>
#include <cliext/vector>

using namespace System;
using namespace System::Collections::Generic;
using namespace cliext;

namespace StlClrClassLibrary {

    public ref class StlClrClass
    {
    public:
        StlClrClass();

        // These methods can be called by a C++ class
        // in another assembly to get access to the
        // private STL/CLR types defined below.
        deque<wchar_t>::generic_container ^GetDequeCpp();
        list<float>::generic_container ^GetListCpp();
        map<int, String ^>::generic_container ^GetMapCpp();
        set<double>::generic_container ^GetSetCpp();
        vector<int>::generic_container ^GetVectorCpp();

        // These methods can be called by a non-C++ class
        // in another assembly to get access to the
        // private STL/CLR types defined below.
        ICollection<wchar_t> ^GetDequeCs();
        ICollection<float> ^GetListCs();
        IDictionary<int, String ^> ^GetMapCs();
        ICollection<double> ^GetSetCs();
        ICollection<int> ^GetVectorCs();

    private:
        deque<wchar_t> ^aDeque;
        list<float> ^aList;
        map<int, String ^> ^aMap;
        set<double> ^aSet;
        vector<int> ^aVector;
    };
}
```

## <a name="example-2"></a>Beispiel 2

### <a name="description"></a>Beschreibung

In diesem Beispiel implementieren wir die Klasse deklariert, die in Beispiel 1. Damit Clients diese Klassenbibliothek verwenden, verwenden wir das Manifesttool **mt.exe** die Manifestdatei in die DLL einbetten. Weitere Informationen finden Sie in den Codekommentaren.

Weitere Informationen zu den Manifesttool und die Seite-an-Seite-Assemblys finden Sie unter [Erstellen von C/C++-isolierte Anwendungen und Seite-an-Seite-Assemblys](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md).

### <a name="code"></a>Code

```cpp
// StlClrClassLibrary.cpp
// compile with: /clr /LD /link /manifest
// post-build command: (attrib -r StlClrClassLibrary.dll & mt /manifest StlClrClassLibrary.dll.manifest /outputresource:StlClrClassLibrary.dll;#2 & attrib +r StlClrClassLibrary.dll)

#include "StlClrClassLibrary.h"

namespace StlClrClassLibrary
{
    StlClrClass::StlClrClass()
    {
        aDeque = gcnew deque<wchar_t>();
        aDeque->push_back(L'a');
        aDeque->push_back(L'b');

        aList = gcnew list<float>();
        aList->push_back(3.14159f);
        aList->push_back(2.71828f);

        aMap = gcnew map<int, String ^>();
        aMap[0] = "Hello";
        aMap[1] = "World";

        aSet = gcnew set<double>();
        aSet->insert(3.14159);
        aSet->insert(2.71828);

        aVector = gcnew vector<int>();
        aVector->push_back(10);
        aVector->push_back(20);
    }

    deque<wchar_t>::generic_container ^StlClrClass::GetDequeCpp()
    {
        return aDeque;
    }

    list<float>::generic_container ^StlClrClass::GetListCpp()
    {
        return aList;
    }

    map<int, String ^>::generic_container ^StlClrClass::GetMapCpp()
    {
        return aMap;
    }

    set<double>::generic_container ^StlClrClass::GetSetCpp()
    {
        return aSet;
    }

    vector<int>::generic_container ^StlClrClass::GetVectorCpp()
    {
        return aVector;
    }

    ICollection<wchar_t> ^StlClrClass::GetDequeCs()
    {
        return aDeque;
    }

    ICollection<float> ^StlClrClass::GetListCs()
    {
        return aList;
    }

    IDictionary<int, String ^> ^StlClrClass::GetMapCs()
    {
        return aMap;
    }

    ICollection<double> ^StlClrClass::GetSetCs()
    {
        return aSet;
    }

    ICollection<int> ^StlClrClass::GetVectorCs()
    {
        return aVector;
    }
}
```

## <a name="example-3"></a>Beispiel 3

### <a name="description"></a>Beschreibung

In diesem Beispiel erstellen wir einen C++-Client, der die Klassenbibliothek erstellt, die in den Beispielen 1 und 2 verwendet. Dieser Client verwendet die `generic_container` Typdefinitionen von STL/CLR-Container, um die Container durchlaufen und ihren Inhalt anzuzeigen.

### <a name="code"></a>Code

```cpp
// CppConsoleApp.cpp
// compile with: /clr /FUStlClrClassLibrary.dll

#include <cliext/deque>
#include <cliext/list>
#include <cliext/map>
#include <cliext/set>
#include <cliext/vector>

using namespace System;
using namespace StlClrClassLibrary;
using namespace cliext;

int main(array<System::String ^> ^args)
{
    StlClrClass theClass;

    Console::WriteLine("cliext::deque contents:");
    deque<wchar_t>::generic_container ^aDeque = theClass.GetDequeCpp();
    for each (wchar_t wc in aDeque)
    {
        Console::WriteLine(wc);
    }
    Console::WriteLine();

    Console::WriteLine("cliext::list contents:");
    list<float>::generic_container ^aList = theClass.GetListCpp();
    for each (float f in aList)
    {
        Console::WriteLine(f);
    }
    Console::WriteLine();

    Console::WriteLine("cliext::map contents:");
    map<int, String ^>::generic_container ^aMap = theClass.GetMapCpp();
    for each (map<int, String ^>::value_type rp in aMap)
    {
        Console::WriteLine("{0} {1}", rp->first, rp->second);
    }
    Console::WriteLine();

    Console::WriteLine("cliext::set contents:");
    set<double>::generic_container ^aSet = theClass.GetSetCpp();
    for each (double d in aSet)
    {
        Console::WriteLine(d);
    }
    Console::WriteLine();

    Console::WriteLine("cliext::vector contents:");
    vector<int>::generic_container ^aVector = theClass.GetVectorCpp();
    for each (int i in aVector)
    {
        Console::WriteLine(i);
    }
    Console::WriteLine();

    return 0;
}
```

### <a name="output"></a>Output

```Output
cliext::deque contents:
a
b

cliext::list contents:
3.14159
2.71828

cliext::map contents:
0 Hello
1 World

cliext::set contents:
2.71828
3.14159

cliext::vector contents:
10
20
```

## <a name="example-4"></a>Beispiel 4

### <a name="description"></a>Beschreibung

In diesem Beispiel erstellen wir einen c#-Client, der die Klassenbibliothek erstellt, die in den Beispielen 1 und 2 verwendet. Dieser Client verwendet die <xref:System.Collections.Generic.ICollection%601> Methoden die STL/CLR-Container, um die Container durchlaufen und ihren Inhalt anzuzeigen.

### <a name="code"></a>Code

```csharp
// CsConsoleApp.cs
// compile with: /r:Microsoft.VisualC.STLCLR.dll /r:StlClrClassLibrary.dll /r:System.dll

using System;
using System.Collections.Generic;
using StlClrClassLibrary;
using cliext;

namespace CsConsoleApp
{
    class Program
    {
        static int Main(string[] args)
        {
            StlClrClass theClass = new StlClrClass();

            Console.WriteLine("cliext::deque contents:");
            ICollection<char> iCollChar = theClass.GetDequeCs();
            foreach (char c in iCollChar)
            {
                Console.WriteLine(c);
            }
            Console.WriteLine();

            Console.WriteLine("cliext::list contents:");
            ICollection<float> iCollFloat = theClass.GetListCs();
            foreach (float f in iCollFloat)
            {
                Console.WriteLine(f);
            }
            Console.WriteLine();

            Console.WriteLine("cliext::map contents:");
            IDictionary<int, string> iDict = theClass.GetMapCs();
            foreach (KeyValuePair<int, string> kvp in iDict)
            {
                Console.WriteLine("{0} {1}", kvp.Key, kvp.Value);
            }
            Console.WriteLine();

            Console.WriteLine("cliext::set contents:");
            ICollection<double> iCollDouble = theClass.GetSetCs();
            foreach (double d in iCollDouble)
            {
                Console.WriteLine(d);
            }
            Console.WriteLine();

            Console.WriteLine("cliext::vector contents:");
            ICollection<int> iCollInt = theClass.GetVectorCs();
            foreach (int i in iCollInt)
            {
                Console.WriteLine(i);
            }
            Console.WriteLine();

            return 0;
        }
    }
}
```

### <a name="output"></a>Output

```Output
cliext::deque contents:
a
b

cliext::list contents:
3.14159
2.71828

cliext::map contents:
0 Hello
1 World

cliext::set contents:
2.71828
3.14159

cliext::vector contents:
10
20
```

## <a name="see-also"></a>Siehe auch

[Referenz zur STL/CLR-Bibliothek](../dotnet/stl-clr-library-reference.md)
