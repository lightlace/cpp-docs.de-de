---
title: "range_adapter (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::range_adapter"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "range_adapter-Klasse [STL/CLR]"
ms.assetid: 3fbe2a65-1216-46a0-a182-422816b80cfb
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# range_adapter (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Klasse, die ein Paar Iteratoren umschließt, die verwendet werden, um einige Basisklassenbibliothek \(BCL\) zu implementieren, wird angezeigt.  Sie verwenden das range\_adapter, um einen CLR\-Bereich STL\/bearbeiten, als ob eine BCL\-Auflistung war.  
  
## Syntax  
  
```  
template<typename Iter>  
    ref class range_adapter  
        :   public  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<Value>,  
        System::Collections::Generic::ICollection<Value>  
    { ..... };  
```  
  
#### Parameter  
 ITER  
 Der Typ zugeordnete den umschlossenen Iteratoren.  
  
## Member  
  
|Memberfunktion|**Beschreibung**|  
|--------------------|----------------------|  
|[range\_adapter::range\_adapter](../dotnet/range-adapter-range-adapter-stl-clr.md)|Erstellt ein Adapterobjekt.|  
  
|Operator|**Beschreibung**|  
|--------------|----------------------|  
|[range\_adapter::operator\=](../dotnet/range-adapter-operator-assign-stl-clr.md)|Ersetzt die gespeicherten Iteratorpaare.|  
  
## Schnittstellen  
  
|Schnittstelle|**Beschreibung**|  
|-------------------|----------------------|  
|<xref:System.Collections.IEnumerable>|Durchlaufen von Elementen in der Auflistung durch.|  
|<xref:System.Collections.ICollection>|Verwendet eine Elementgruppe bei.|  
|<xref:System.Collections.Generic.IEnumerable`1>|Läuft von typisierten Elemente in der Auflistung. durch.|  
|<xref:System.Collections.Generic.ICollection`1>|Verwendet eine Gruppe typisierten Elemente bei.|  
  
## Hinweise  
 Das range\_adapter speichert ein Paar Iteratoren, die wiederum eine Sequenz von Elementen begrenzen.  Das Objekt implementiert vier BCL\-Schnittstellen, die durch die Elemente durchlaufen haben, in der Reihenfolge.  Sie verwenden diese Vorlagenklasse, dass STL\/CLR\-Bereiche ähnlich wie BCL\-Container zu bearbeiten.  
  
## Anforderungen  
 **Header:** \<cliext\/Adapter\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [collection\_adapter](../dotnet/collection-adapter-stl-clr.md)   
 [make\_collection](../dotnet/make-collection-stl-clr.md)