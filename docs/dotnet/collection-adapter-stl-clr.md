---
title: Collection_adapter (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::collection_adapter
dev_langs:
- C++
helpviewer_keywords:
- collection_adapter class [STL/CLR]
ms.assetid: 31964058-1f50-48bf-82c2-b0b3cc8a7887
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 62fb5dc48175d755771960e9121c3371a0292595
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33114444"
---
# <a name="collectionadapter-stlclr"></a>collection_adapter (STL/CLR)
Dient als Wrapper für eine .NET Auflistung für die Verwendung als STL/CLR-Container. Ein `collection_adapter` ist eine Vorlagenklasse, die ein einfaches STL/CLR-Container-Objekt beschreibt. Es dient als Wrapper für eine Schnittstelle für die Basisklassenbibliothek (Base Class Library, BCL) und gibt ein Iterator-Paar, das Sie verwenden, um die gesteuerte Sequenz zu bearbeiten.  
  
## <a name="syntax"></a>Syntax  
  
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
  
#### <a name="parameters"></a>Parameter  
 Coll  
 Der Typ des umschlossenen Auflistung.  
  
## <a name="specializations"></a>Spezialisierungen  
  
|Spezialisierung|Beschreibung|  
|--------------------|-----------------|  
|IEnumerable|Sequenzen durch die Elemente.|  
|ICollection|Verwaltet eine Gruppe von Elementen an.|  
|IList|Verwaltet eine geordnete Gruppe von Elementen an.|  
|IDictionary|Verwalten Sie einen Satz von {Schlüssel, Wert} Paare.|  
|IEnumerable\<Wert >|Sequenzen durch typisierte Elemente.|  
|ICollection\<Wert >|Verwaltet eine Gruppe von typisierten Elementen an.|  
|IList\<Wert >|Verwaltet eine geordnete Gruppe von typisierten Elementen an.|  
|IDictionary\<Wert >|Verwaltet einen Satz von typisierten {Schlüssel, Wert} Paare.|  
  
## <a name="members"></a>Member  
  
|Typdefinition|Beschreibung|  
|---------------------|-----------------|  
|[collection_adapter::difference_type (STL/CLR)](../dotnet/collection-adapter-difference-type-stl-clr.md)|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|  
|[collection_adapter::iterator (STL/CLR)](../dotnet/collection-adapter-iterator-stl-clr.md)|Der Typ eines Iterators für die gesteuerte Sequenz.|  
|[collection_adapter::key_type (STL/CLR)](../dotnet/collection-adapter-key-type-stl-clr.md)|Der Typ eines Schlüssels Wörterbuch.|  
|[collection_adapter::mapped_type (STL/CLR)](../dotnet/collection-adapter-mapped-type-stl-clr.md)|Der Typ des ein Dictionary-Wert.|  
|[collection_adapter::reference (STL/CLR)](../dotnet/collection-adapter-reference-stl-clr.md)|Der Typ eines Verweises auf ein Element.|  
|[collection_adapter::size_type (STL/CLR)](../dotnet/collection-adapter-size-type-stl-clr.md)|Der Typ eines Abstands mit Vorzeichen zwischen zwei Elementen.|  
|[collection_adapter::value_type (STL/CLR)](../dotnet/collection-adapter-value-type-stl-clr.md)|Der Typ eines Elements.|  
  
|Memberfunktion|Beschreibung|  
|---------------------|-----------------|  
|[collection_adapter::base (STL/CLR)](../dotnet/collection-adapter-base-stl-clr.md)|Legt die umschlossene BCL-Schnittstelle.|  
|[collection_adapter::begin (STL/CLR)](../dotnet/collection-adapter-begin-stl-clr.md)|Legt den Anfang der kontrollierten Sequenz fest.|  
|[collection_adapter::collection_adapter (STL/CLR)](../dotnet/collection-adapter-collection-adapter-stl-clr.md)|Erstellt ein Adapterobjekt.|  
|[collection_adapter::end (STL/CLR)](../dotnet/collection-adapter-end-stl-clr.md)|Legt das Ende der kontrollierten Sequenz fest.|  
|[collection_adapter::size (STL/CLR)](../dotnet/collection-adapter-size-stl-clr.md)|Ermittelt die Anzahl von Elementen.|  
|[collection_adapter::swap (STL/CLR)](../dotnet/collection-adapter-swap-stl-clr.md)|Vertauscht den Inhalt von zwei Containern.|  
  
|Operator|Beschreibung|  
|--------------|-----------------|  
|[collection_adapter::operator= (STL/CLR)](../dotnet/collection-adapter-operator-assign-stl-clr.md)|Ersetzt den gespeicherten BCL-Handle an.|  
  
## <a name="remarks"></a>Hinweise  
 Sie verwenden diese Vorlagenklasse BCL Container als einen STL/CLR-Container zu bearbeiten. Die `collection_adapter` speichert ein Handle auf eine BCL-Schnittstelle, die wiederum eine Sequenz von Elementen steuert. Ein `collection_adapter` Objekt `X` gibt ein Paar von eingabeiteratoren `X.begin()` und `X.end()` , besuchen Sie die Elemente in der Reihenfolge zu verwenden. Einige der spezialisierungen können Sie schreiben, auch `X.size()` die Länge der kontrollierten Sequenz fest.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext-Adapter >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [Range_adapter (STL/CLR)](../dotnet/range-adapter-stl-clr.md)   
 [make_collection (STL/CLR)](../dotnet/make-collection-stl-clr.md)