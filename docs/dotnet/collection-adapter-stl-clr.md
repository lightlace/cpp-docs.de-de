---
title: "collection_adapter (STL/CLR)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "cliext::collection_adapter"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "collection_adapter-Klasse [STL/CLR]"
ms.assetid: 31964058-1f50-48bf-82c2-b0b3cc8a7887
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# collection_adapter (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Umschließt eine .NET\-Auflistung zur Verwendung als STL\/CLR\-Container ein.  `collection_adapter` ist eine Vorlagenklasse, die ein einfaches STL\/CLR\-Containerobjekt beschreibt.  Sie wird eine Basisklassen\-Bibliotheks \(bcl\)\- Schnittstelle ein und gibt ein Iteratorpaar zurück, den Sie verwenden, um die gesteuerte Sequenz zu bearbeiten.  
  
## Syntax  
  
```  
template<typename Coll>  
    ref class collection_adapter;  
  
template<>  
    ref class collection_adapter<  
        System::Collections::ICollection>;  
template<>  
    ref class collection_adapter<  
        System::Collections::IEnumerable>;  
template<>  
    ref class collection_adapter<  
        System::Collections::IList>;  
template<>  
    ref class collection_adapter<  
        System::Collections::IDictionary>;  
template<typename Value>  
    ref class collection_adapter<  
        System::Collections::Generic::ICollection<Value>>;  
template<typename Value>  
    ref class collection_adapter<  
        System::Collections::Generic::IEnumerable<Value>>;  
template<typename Value>  
    ref class collection_adapter<  
        System::Collections::Generic::IList<Value>>;  
template<typename Key,  
    typename Value>  
    ref class collection_adapter<  
        System::Collections::Generic::IDictionary<Key, Value>>;  
```  
  
#### Parameter  
 Coll  
 Der Typ der Auflistung umschlossenen.  
  
## Spezialisierungen  
  
|Spezialisierung|**Beschreibung**|  
|---------------------|----------------------|  
|IEnumerable|Sequenzen von Elementen.|  
|ICollection|Verwendet eine Elementgruppe bei.|  
|IList|Verwendet eine geordnete Elementgruppe bei.|  
|IDictionary|Unbegrenztes Beibehalten eines Schlüssel Menge {,} Paare Wert bei.|  
|IEnumerableValue \<\>|Sequenzen von typisierten Elemente.|  
|ICollectionValue \<\>|Verwendet eine Gruppe typisierten Elemente bei.|  
|IListValue \<\>|Verwendet eine geordnete Gruppe typisierten Elemente bei.|  
|IDictionaryValue \<\>|Behält einen Satz typisierte {,} Paare Schlüssel Wert bei.|  
  
## Member  
  
|Typdefinition|**Beschreibung**|  
|-------------------|----------------------|  
|[collection\_adapter::difference\_type](../dotnet/collection-adapter-difference-type-stl-clr.md)|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|  
|[collection\_adapter::iterator](../dotnet/collection-adapter-iterator-stl-clr.md)|Der Typ eines Iterators für die gesteuerte Sequenz.|  
|[collection\_adapter::key\_type](../dotnet/collection-adapter-key-type-stl-clr.md)|Der Typ einer Wörterbuch\-Schlüssel.|  
|[collection\_adapter::mapped\_type](../dotnet/collection-adapter-mapped-type-stl-clr.md)|Der Typ eines Wörterbuchwerts.|  
|[collection\_adapter::reference](../dotnet/collection-adapter-reference-stl-clr.md)|Der Typ eines Verweises auf ein Element.|  
|[collection\_adapter::size\_type](../dotnet/collection-adapter-size-type-stl-clr.md)|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|  
|[collection\_adapter::value\_type](../dotnet/collection-adapter-value-type-stl-clr.md)|Der Typ eines Elements.|  
  
|Memberfunktion|**Beschreibung**|  
|--------------------|----------------------|  
|[collection\_adapter::base](../dotnet/collection-adapter-base-stl-clr.md)|Legt die umschlossene BCL\-Schnittstelle fest.|  
|[collection\_adapter::begin](../dotnet/collection-adapter-begin-stl-clr.md)|Legt den Anfang der kontrollierten Sequenz fest.|  
|[collection\_adapter::collection\_adapter](../dotnet/collection-adapter-collection-adapter-stl-clr.md)|Erstellt ein Adapterobjekt.|  
|[collection\_adapter::end](../dotnet/collection-adapter-end-stl-clr.md)|Legt das Ende der kontrollierten Sequenz fest.|  
|[collection\_adapter::size](../dotnet/collection-adapter-size-stl-clr.md)|Ermittelt die Anzahl der Elemente.|  
|[collection\_adapter::swap](../dotnet/collection-adapter-swap-stl-clr.md)|Vertauscht den Inhalt von zwei Containern.|  
  
|Operator|**Beschreibung**|  
|--------------|----------------------|  
|[collection\_adapter::operator\=](../dotnet/collection-adapter-operator-assign-stl-clr.md)|Ersetzt das gespeicherte BCL\-Handle.|  
  
## Hinweise  
 Sie verwenden diese Vorlagenklasse, um einen als BCL\-Container STL\/CLR\-Container zu bearbeiten.  `collection_adapter` speichert ein Handle für eine BCL\-Schnittstelle, die wiederum eine Sequenz von Elementen steuert.  Ein `collection_adapter`\-Objekt `X` gibt ein Paar Eingabeiteratoren `X.begin()` und `X.end()`, die Sie verwenden, um die Elemente zu finden, in der Reihenfolge zurück.  Einige der Spezialisierungen können Sie auch `X.size()` schreiben, um die Länge der Sequenz gesteuerten zu bestimmen.  
  
## Anforderungen  
 **Header:** \<cliext\/Adapter\>  
  
 **Namespace:** cliext  
  
## Siehe auch  
 [range\_adapter](../dotnet/range-adapter-stl-clr.md)   
 [make\_collection](../dotnet/make-collection-stl-clr.md)