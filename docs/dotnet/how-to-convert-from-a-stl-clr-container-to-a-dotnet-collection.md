---
title: "Gewusst wie: Umwandeln eines STL/CLR-Containers in eine .NET-Auflistung"
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
  - "STL/CLR, Konvertieren in .NET-Auflistungen"
ms.assetid: 70b2dfd9-869c-4e0f-9a29-b1ee0cb0d107
caps.latest.revision: 8
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Umwandeln eines STL/CLR-Containers in eine .NET-Auflistung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieses Thema zeigt, wie STL\/CLR\-Container ihren entsprechenden .NET\-Auflistungen konvertiert.  Als Beispiel zeigen Sie an, wie ein STL\/CLR [Vektor](../dotnet/vector-stl-clr.md) zu .NET <xref:System.Collections.Generic.ICollection`1> konvertiert und wie ein STL\/CLR [Zuordnung](../dotnet/map-stl-clr.md) zu .NET <xref:System.Collections.Generic.IDictionary`2> konvertiert, die Verfahren für alle Sammlungen und Container ähnlich.  
  
### Um eine Auflistung von einem Container erstellen  
  
1.  Verwenden Sie eine der folgenden Methoden:  
  
    -   Um einen Teil eines Containers konvertieren, die [make\_collection](../dotnet/make-collection-stl-clr.md)\-Funktion aufrufen, und den beginnensiterator übergeben und Iterator des in die .NET\-Auflistung kopiert werden CLR\-Containers, STL\/beenden.  Diese Vorlagenfunktion akzeptiert einen STL\/CLR\-Iterator als Vorlagenargument.  Das erste Beispiel veranschaulicht diese Methode.  
  
    -   Um einen gesamten Container zu konvertieren, wandeln Sie den Container mit einer übereinstimmenden .NET\-Auflistungsschnittstelle oder einer Schnittstellenauflistung um.  Das zweite Beispiel veranschaulicht diese Methode.  
  
## Beispiel  
 In diesem Beispiel erstellen wir ein STL\/CLR `vector` und fügen 5 Elemente hinzu.  Anschließend erstellen wir eine .NET\-Auflistung, indem wir die Funktion `make_collection` aufrufen.  Schließlich zeigen Sie den Inhalt der neu erstellten Auflistung an.  
  
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
  
  **Der Inhalt des System::Collections::Generic::ICollection ist:**  
**3**  
**5**  
**7**   
## Beispiel  
 In diesem Beispiel erstellen wir ein STL\/CLR `map` und fügen 5 Elemente hinzu.  Dann erstellen wir .NET <xref:System.Collections.Generic.IDictionary`2> nehmen `map` direkt zu.  Schließlich zeigen Sie den Inhalt der neu erstellten Auflistung an.  
  
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
  
  **Der Inhalt des IDictionary ist:**  
**Key: 0.00 Value: 0**  
**Key: 13.00 Value: 13**  
**Key: 22.00 Value: 22**  
**Key: 42.00 Value: 42**  
**Key: 74.00 Value: 74**   
## Siehe auch  
 [STL\/CLR\-Bibliothek](../dotnet/stl-clr-library-reference.md)   
 [Gewusst wie: Umwandeln einer .Net\-Auflistung in einen STL\/CLR\-Container](../dotnet/how-to-convert-from-a-dotnet-collection-to-a-stl-clr-container.md)   
 [range\_adapter](../dotnet/range-adapter-stl-clr.md)