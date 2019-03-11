---
title: 'Vorgehensweise: Umwandeln einer .NET-Auflistung in einen STL/CLR-Container'
ms.date: 11/04/2016
helpviewer_keywords:
- STL/CLR, converting from .NET collections
- STL/CLR Containers [STL/CLR]
ms.assetid: bb927c48-78e8-4150-bd0b-787c651f4a87
ms.openlocfilehash: 836623f6d539b7b28765763a3dc36d477f8c1499
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57741684"
---
# <a name="how-to-convert-from-a-net-collection-to-a-stlclr-container"></a>Vorgehensweise: Umwandeln einer .NET-Auflistung in einen STL/CLR-Container

In diesem Thema wird gezeigt, wie Auflistungen von .NET in ihre entsprechenden STL/CLR-Container konvertiert. Als Beispiel erfahren, wie Sie eine .NET konvertieren <xref:System.Collections.Generic.List%601> auf einen STL/CLR [Vektor](../dotnet/vector-stl-clr.md) und konvertieren Sie eine .NET <xref:System.Collections.Generic.Dictionary%602> auf einen STL/CLR [Zuordnung](../dotnet/map-stl-clr.md), aber das Verfahren ist für alle Auflistungen und Container ähnlich .

### <a name="to-create-a-container-from-a-collection"></a>Zum Erstellen eines Containers aus einer Auflistung

1. Um eine ganze Sammlung zu konvertieren, erstellen Sie einen STL/CLR-Container, und übergeben Sie die Auflistung an den Konstruktor.

   Das erste Beispiel veranschaulicht dieses Verfahren.

-ODER-

1. Erstellen Sie einen generischen STL/CLR-Container, indem Sie erstellen eine [Collection_adapter](../dotnet/collection-adapter-stl-clr.md) Objekt. Diese Vorlagenklasse verwendet eine sammlungsschnittstelle .NET als Argument an. Um zu überprüfen, welche Schnittstellen unterstützt werden, finden Sie unter [Collection_adapter (STL/CLR)](../dotnet/collection-adapter-stl-clr.md).

1. Kopieren Sie den Inhalt der Auflistung .NET auf den Container ein. Dies kann erfolgen mithilfe einer STL/CLR [Algorithmus](../dotnet/algorithm-stl-clr.md), oder durch Durchlaufen der Auflistung von .NET und eine Kopie jedes Element in der STL/CLR-Container eingefügt.

   Das zweite Beispiel veranschaulicht dieses Verfahren.

## <a name="example"></a>Beispiel

In diesem Beispiel erstellen wir eine generische <xref:System.Collections.Generic.List%601> , und fügen Sie 5 Elemente hinzu. Anschließend erstellen wir eine `vector` mithilfe des Konstruktors, die akzeptiert eine <xref:System.Collections.Generic.IEnumerable%601> als Argument.

```
// cliext_convert_list_to_vector.cpp
// compile with: /clr

#include <cliext/adapter>
#include <cliext/algorithm>
#include <cliext/vector>

using namespace System;
using namespace System::Collections;
using namespace System::Collections::Generic;

int main(array<System::String ^> ^args)
{
    List<int> ^primeNumbersColl = gcnew List<int>();
    primeNumbersColl->Add(2);
    primeNumbersColl->Add(3);
    primeNumbersColl->Add(5);
    primeNumbersColl->Add(7);
    primeNumbersColl->Add(11);

    cliext::vector<int> ^primeNumbersCont =
        gcnew cliext::vector<int>(primeNumbersColl);

    Console::WriteLine("The contents of the cliext::vector are:");
    cliext::vector<int>::const_iterator it;
    for (it = primeNumbersCont->begin(); it != primeNumbersCont->end(); it++)
    {
        Console::WriteLine(*it);
    }
}
```

```Output
The contents of the cliext::vector are:
2
3
5
7
11
```

## <a name="example"></a>Beispiel

In diesem Beispiel erstellen wir eine generische <xref:System.Collections.Generic.Dictionary%602> , und fügen Sie 5 Elemente hinzu. Anschließend erstellen wir eine `collection_adapter` umschließen der <xref:System.Collections.Generic.Dictionary%602> als einfache STL/CLR-Container. Schließlich erstellen wir eine `map` , und kopieren Sie den Inhalt des der <xref:System.Collections.Generic.Dictionary%602> auf die `map` durch Iteration über die `collection_adapter`. Während dieses Vorgangs erstellen wir ein neues Paar mithilfe der `make_pair` funktionieren, und fügen Sie das neue Paar direkt in die `map`.

```
// cliext_convert_dictionary_to_map.cpp
// compile with: /clr

#include <cliext/adapter>
#include <cliext/algorithm>
#include <cliext/map>

using namespace System;
using namespace System::Collections;
using namespace System::Collections::Generic;

int main(array<System::String ^> ^args)
{
    System::Collections::Generic::Dictionary<float, int> ^dict =
        gcnew System::Collections::Generic::Dictionary<float, int>();
    dict->Add(42.0, 42);
    dict->Add(13.0, 13);
    dict->Add(74.0, 74);
    dict->Add(22.0, 22);
    dict->Add(0.0, 0);

    cliext::collection_adapter<System::Collections::Generic::IDictionary<float, int>> dictAdapter(dict);
    cliext::map<float, int> aMap;
    for each (KeyValuePair<float, int> ^kvp in dictAdapter)
    {
        cliext::pair<float, int> aPair = cliext::make_pair(kvp->Key, kvp->Value);
        aMap.insert(aPair);
    }

    Console::WriteLine("The contents of the cliext::map are:");
    cliext::map<float, int>::const_iterator it;
    for (it = aMap.begin(); it != aMap.end(); it++)
    {
        Console::WriteLine("Key: {0:F} Value: {1}", it->first, it->second);
    }
}
```

```Output
The contents of the cliext::map are:
Key: 0.00 Value: 0
Key: 13.00 Value: 13
Key: 22.00 Value: 22
Key: 42.00 Value: 42
Key: 74.00 Value: 74
```

## <a name="see-also"></a>Siehe auch

[Referenz zur STL/CLR-Bibliothek](../dotnet/stl-clr-library-reference.md)<br/>
[adapter (STL/CLR)](../dotnet/adapter-stl-clr.md)<br/>
[Vorgehensweise: Umwandeln eines STL/CLR-Containers in eine .NET-Auflistung](../dotnet/how-to-convert-from-a-stl-clr-container-to-a-dotnet-collection.md)
