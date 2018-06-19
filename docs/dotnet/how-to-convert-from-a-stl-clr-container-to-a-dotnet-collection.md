---
title: 'Vorgehensweise: Konvertieren vom einem STL/CLR-Container für eine Sammlung von .NET | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- STL/CLR Containers [STL/CLR]
- STL/CLR, converting to .NET collections
ms.assetid: 70b2dfd9-869c-4e0f-9a29-b1ee0cb0d107
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7fb4938121d1d2beed3133bee6013e17d37f1402
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33132007"
---
# <a name="how-to-convert-from-a-stlclr-container-to-a-net-collection"></a>Gewusst wie: Umwandeln eines STL/CLR-Containers in eine .NET-Auflistung
In diesem Thema wird gezeigt, wie STL/CLR-Container in ihre entsprechenden Auflistungen von .NET konvertiert werden. Beispielsweise können wir zeigen, wie eine STL/CLR konvertieren [Vektor](../dotnet/vector-stl-clr.md) auf eine .NET <xref:System.Collections.Generic.ICollection%601> und zum Konvertieren einer STL/CLR [Zuordnung](../dotnet/map-stl-clr.md) in ein .NET <xref:System.Collections.Generic.IDictionary%602>, aber die Prozedur ist für alle Auflistungen ähnlich und Container.  
  
### <a name="to-create-a-collection-from-a-container"></a>So erstellen Sie eine Sammlung aus einem container  
  
1.  Verwenden Sie eine der folgenden Methoden:  
  
    -   Um Teil eines Containers zu konvertieren, rufen die [Make_collection](../dotnet/make-collection-stl-clr.md) -Funktion, und übergibt den Iterator Begin und End-Iterator, der die STL/CLR-Container, in die .NET Auflistung kopiert werden. Diese Vorlagenfunktion akzeptiert einen STL/CLR-Iterator als Vorlagenargument an. Das erste Beispiel veranschaulicht diese Methode.  
  
    -   Zum Konvertieren eines gesamten Containers wandeln Sie den Container an einem entsprechenden .NET sammlungsschnittstelle oder einer Schnittstelle-Auflistung. Im zweite Beispiel wird diese Methode veranschaulicht.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel erstellen wir eine STL/CLR `vector` und 5 Elemente hinzuzufügen. Anschließend erstellen wir eine Auflistung von .NET durch Aufrufen der `make_collection` Funktion. Schließlich wird der Inhalt der neu erstellte Auflistung angezeigt.  
  
```  
// cliext_convert_vector_to_icollection.cpp  
// compile with: /clr  
  
#include <cliext/adapter>  
#include <cliext/vector>  
  
using namespace cliext;  
using namespace System;  
using namespace System::Collections::Generic;  
  
int main(array<System::String ^> ^args)  
{  
    cliext::vector<int> primeNumbersCont;  
    primeNumbersCont.push_back(2);  
    primeNumbersCont.push_back(3);  
    primeNumbersCont.push_back(5);  
    primeNumbersCont.push_back(7);  
    primeNumbersCont.push_back(11);  
  
    System::Collections::Generic::ICollection<int> ^iColl =  
        make_collection<cliext::vector<int>::iterator>(  
            primeNumbersCont.begin() + 1,  
            primeNumbersCont.end() - 1);  
  
    Console::WriteLine("The contents of the System::Collections::Generic::ICollection are:");  
    for each (int i in iColl)  
    {  
        Console::WriteLine(i);  
    }  
}  
```  
  
```Output  
The contents of the System::Collections::Generic::ICollection are:  
3  
5  
7  
```  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel erstellen wir eine STL/CLR `map` und 5 Elemente hinzuzufügen. Anschließend erstellen wir eine .NET-Klasse <xref:System.Collections.Generic.IDictionary%602> , und weisen Sie die `map` direkt an. Schließlich wird der Inhalt der neu erstellte Auflistung angezeigt.  
  
```  
// cliext_convert_map_to_idictionary.cpp  
// compile with: /clr  
  
#include <cliext/adapter>  
#include <cliext/map>  
  
using namespace cliext;  
using namespace System;  
using namespace System::Collections::Generic;  
  
int main(array<System::String ^> ^args)  
{  
    cliext::map<float, int> ^aMap = gcnew cliext::map<float, int>;  
    aMap->insert(cliext::make_pair<float, int>(42.0, 42));  
    aMap->insert(cliext::make_pair<float, int>(13.0, 13));  
    aMap->insert(cliext::make_pair<float, int>(74.0, 74));  
    aMap->insert(cliext::make_pair<float, int>(22.0, 22));  
    aMap->insert(cliext::make_pair<float, int>(0.0, 0));  
  
    System::Collections::Generic::IDictionary<float, int> ^iDict = aMap;  
  
    Console::WriteLine("The contents of the IDictionary are:");  
    for each (KeyValuePair<float, int> ^kvp in iDict)  
    {  
        Console::WriteLine("Key: {0:F} Value: {1}", kvp->Key, kvp->Value);  
    }  
}  
```  
  
```Output  
The contents of the IDictionary are:  
Key: 0.00 Value: 0  
Key: 13.00 Value: 13  
Key: 22.00 Value: 22  
Key: 42.00 Value: 42  
Key: 74.00 Value: 74  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Referenz zur STL/CLR-Bibliothek](../dotnet/stl-clr-library-reference.md)   
 [Vorgehensweise: Konvertieren aus einer Auflistung .NET in einen STL/CLR-Container](../dotnet/how-to-convert-from-a-dotnet-collection-to-a-stl-clr-container.md)   
 [range_adapter (STL/CLR)](../dotnet/range-adapter-stl-clr.md)