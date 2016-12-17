---
title: "Gewusst wie: Umwandeln einer .Net-Auflistung in einen STL/CLR-Container"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "STL/CLR-Container [STL/CLR]"
  - "STL/CLR, Konvertieren aus .NET-Auflistungen"
ms.assetid: bb927c48-78e8-4150-bd0b-787c651f4a87
caps.latest.revision: 9
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Umwandeln einer .Net-Auflistung in einen STL/CLR-Container
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieses Thema zeigt, wie .NET\-Auflistungen ihren Containern der Entsprechung STL\/CLR konvertiert.  Als Beispiel zeigen wir uns, wie .NET <xref:System.Collections.Generic.List`1> zu einem STL\/CLR [Vektor](../dotnet/vector-stl-clr.md) konvertiert und wie .NET <xref:System.Collections.Generic.Dictionary`2> zu einem STL\/CLR [Zuordnung](../dotnet/map-stl-clr.md) konvertiert, die Verfahren für alle Sammlungen und Container ähnlich.  
  
### Erstellen eines Containers aus einer Auflistung erstellen  
  
1.  Um eine vollständige Auflistung konvertiert, erstellen Sie einen CLR\-Container STL\/erstellt und übergeben Sie die Auflistung an den Konstruktor.  
  
     Im ersten Beispiel wird diese Prozedur.  
  
 – ODER –  
  
1.  Erstellen eines generischen STL\/CLR\-Container erstellt, indem Sie ein Objekt erstellen. [collection\_adapter](../dotnet/collection-adapter-stl-clr.md) Diese Vorlagenklasse verwendet eine .NET\-Auflistungsschnittstelle als Argument.  Um sicherzustellen welche Schnittstellen unterstützt werden, finden Sie unter [collection\_adapter](../dotnet/collection-adapter-stl-clr.md).  
  
2.  Kopieren Sie den Inhalt der .NET\-Auflistung bin.  Dies kann durchgeführt werden, indem ein STL\/CLR mithilfe von [Algorithmus](../dotnet/algorithm-stl-clr.md) oder über die .NET\-Auflistung durchläuft und eine Kopie jedes Elements in STL\/CLR\-Container einfügt.  
  
     Im zweiten Beispiel wird diese Prozedur.  
  
## Beispiel  
 In diesem Beispiel erstellen wir generisches <xref:System.Collections.Generic.List`1> und fügen 5 Elemente hinzu.  Anschließend erstellen Sie `vector` mit dem Konstruktor, der <xref:System.Collections.Generic.IEnumerable`1> als Argument verwendet.  
  
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
  
  **Der Inhalt des cliext::vector ist:**  
**2**  
**3**  
**5**  
**7**  
**11**   
## Beispiel  
 In diesem Beispiel erstellen wir generisches <xref:System.Collections.Generic.Dictionary`2> und fügen 5 Elemente hinzu.  Anschließend erstellen Sie `collection_adapter`, um <xref:System.Collections.Generic.Dictionary`2> als einfacher STL\/CLR\-Container zu umschließen.  Zuletzt erstellen wir `map` und kopiert den Inhalt von <xref:System.Collections.Generic.Dictionary`2> in `map`, indem der zum `collection_adapter` durchlaufen.  Während dieses Prozesses erstellen Sie ein neues Paar, indem wir die Funktion `make_pair` verwenden, und fügen die neuen Paare direkt in `map` ein.  
  
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
  
  **Der Inhalt des cliext::map ist:**  
**Key: 0.00 Value: 0**  
**Key: 13.00 Value: 13**  
**Key: 22.00 Value: 22**  
**Key: 42.00 Value: 42**  
**Key: 74.00 Value: 74**   
## Siehe auch  
 [STL\/CLR\-Bibliothek](../dotnet/stl-clr-library-reference.md)   
 [adapter](../dotnet/adapter-stl-clr.md)   
 [Gewusst wie: Umwandeln eines STL\/CLR\-Containers in eine .NET\-Auflistung](../dotnet/how-to-convert-from-a-stl-clr-container-to-a-dotnet-collection.md)