---
title: Platform::Collections::UnorderedMapView Klasse | Microsoft Docs
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: collection/Platform::Collections::UnorderedMapView
ms.assetid: 545a3725-2efd-4cc1-b590-4a7cd2351f61
caps.latest.revision: "5"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c172246bc0e8fd7acb1661a9547fee3bf6c24421
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="platformcollectionsunorderedmapview-class"></a>Platform::Collections::UnorderedMapView-Klasse
Stellt eine schreibgeschützte Ansicht einer *Zuordnung*dar, die eine Auflistung von Schlüssel-Wert-Paaren ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
template <  
   typename K,  
   typename V,  
   typename C = ::std::equal_to<K>>  
ref class UnorderedMapView sealed;  
```  
  
#### <a name="parameters"></a>Parameter  
 `K`  
 Der Typ des Schlüssels im Schlüssel-Wert-Paar.  
  
 `V`  
 Der Typ des Werts im Schlüssel-Wert-Paar.  
  
 `C`  
 Ein Typ, der ein Funktionsobjekt bereitstellt, das zwei Schlüsselwerte vergleichen kann, um deren Gleichzeit zu bestimmen. Standardmäßig [Std:: equal_to\<K >](../standard-library/equal-to-struct.md)  
  
### <a name="remarks"></a>Hinweise  
 UnorderedMapView ist eine konkrete C++ Implementierung der [Windows::Foundation::Collections::IMapView\<K, V >](http://go.microsoft.com/fwlink/p/?LinkId=262409) Schnittstelle, die über die anwendungsbinärdateischnittstelle (ABI) übergeben wird. Weitere Informationen finden Sie unter [Auflistungen (C++/CX)](../cppcx/collections-c-cx.md).  
  
### <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Unorderedmapview:: Unorderedmapview](#ctor)|Initialisiert eine neue Instanz der UnorderedMapView-Klasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Unorderedmapview:: First](#first)|Gibt einen Iterator zurück, der mit dem ersten Element der Zuordnungsansicht initialisiert wird.|  
|[Unorderedmapview:: Haskey](#haskey)|Ermittelt, ob die aktuelle UnorderedMapView den angegebenen Schlüssel enthält.|  
|[Unorderedmapview:: Lookup](#lookup)|Ruft das Element am angegebenen Schlüssel im aktuellen UnorderedMapView-Objekt ab.|  
|[Unorderedmapview:: Size](#size)|Gibt die Anzahl von Elementen im aktuellen UnorderedMapView-Objekt zurück.|  
|[Unorderedmapview:: Split](#split)|Teilt ein originales UnorderedMapView-Objekt in zwei UnorderedMapView-Objekte.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `UnorderedMapView`  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  

## <a name="first"></a>  UnorderedMapView::First-Methode
Gibt einen Iterator, der angibt, das erste [Windows::Foundation::Collections::IKeyValuePair\<K, V >](http://msdn.microsoft.com/library/windows/apps/br226031.aspx) Element in der ungeordneten Zuordnung.  
  
### <a name="syntax"></a>Syntax  
  
```cpp   
virtual Windows::Foundation::Collections::IIterator<  
    Windows::Foundation::Collections::IKeyValuePair<K, V>^>^   
    First();  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator, der das erste Element in der Kartenansicht angibt.  
  
### <a name="remarks"></a>Hinweise  
 Eine einfache Möglichkeit, den von First() zurückgegeben Iterator zu halten, den Rückgabewert einer Variablen zuzuweisen, die mit deklariert wird ist das **Auto** typableitungsschlüsselwort. Beispielsweise `auto x = myMapView->First();`.  
  


## <a name="haskey"></a>  UnorderedMapView::HasKey-Methode
Ermittelt, ob die aktuelle ungeordnete Zuordnung den angegebenen Schlüssel enthält.  
  
### <a name="syntax"></a>Syntax  
  
```cpp    
bool HasKey(K key);  
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Der zum Suchen des Elements verwendete Schlüssel. Der Typ des `key` ist der Typname *K*.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn der Schlüssel gefunden wurde, andernfalls `false`.  
  


## <a name="lookup"></a>  UnorderedMapView::Lookup-Methode
Ruft den Wert des Typs V ab, der dem angegebenen Schlüssel des Typs K zugeordnet ist.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
V Lookup(K key);  
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Der zum Suchen eines in der UnorderedMapView vorhandenen Elements verwendete Schlüssel. Der Typ des `key` ist der Typname *K*.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert, der dem `key` zugeordnet ist. Der Typ des Rückgabewerts ist der Typname *V*.  
  


## <a name="size"></a>  UnorderedMapView::Size-Methode
Gibt die Anzahl der [Windows::Foundation::Collections::IKeyValuePair\<K, V >](http://msdn.microsoft.com/library/windows/apps/br226031.aspx) Elemente in der unorderedmapview zurück.  
  
### <a name="syntax"></a>Syntax  
  
```cpp    
virtual property unsigned int Size;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl von Elementen in der UnorderedMapView.  
  


## <a name="split"></a>  UnorderedMapView::Split-Methode
Teilt das aktuelle UnorderedMapView-Objekt in zwei UnorderedMapView-Objekte. Diese Methode führt keine Operationen aus.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
void Split(  
   Windows::Foundation::Collections::IMapView<  
                         K,V>^ * firstPartition,  
   Windows::Foundation::Collections::IMapView<  
                         K,V>^ * secondPartition);  
```  
  
### <a name="parameters"></a>Parameter  
 `firstPartition`  
 Der erste Teil des ursprünglichen UnorderedMapView-Objekts.  
  
 `secondPartition`  
 Der zweite Teil des ursprünglichen UnorderedMapView-Objekts.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode führt keine Operationen aus und hat keine Auswirkungen.  
  


## <a name="ctor"></a>  UnorderedMapView::UnorderedMapView-Konstruktor
Initialisiert eine neue Instanz der UnorderedMapView-Klasse.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
  
UnorderedMapView();    
explicit UnorderedMapView(size_t n);   
UnorderedMapView(size_t n, const H& h);   
UnorderedMapView(size_t n, const H& h, const P& p);  
  
explicit UnorderedMapView(  
    const std::unordered_map<K, V, H, P>& m);  
explicit UnorderedMapView(  
    std::unordered_map<K, V, H, P>&& m);  
  
template <typename InIt> UnorderedMapView(InIt first, InIt last );  
template <typename InIt> UnorderedMapView(InIt first, InIt last, size_t n );  
  
template <typename InIt> UnorderedMapView(  
    InIt first,  
    InIt last,  
    size_t n,  
    const H& h );  
  
template <typename InIt> UnorderedMapView(  
    InIt first,  
    InIt last,  
    size_t n,  
    const H& h,  
    const P& p );  
  
UnorderedMapView(std::initializer_list<std::pair<const K, V>);  
  
UnorderedMapView(std::initializer_list< std::pair<const K, V>> il, size_t n   
  
UnorderedMapView(  
    std::initializer_list< std::pair<const K, V>> il,  
    size_t n,  
    const H& h);  
  
UnorderedMapView(  
    std::initializer_list< std::pair<const K, V>> il,  
    size_t n,  
    const H& h,  
    const P& p );  
```  
  
### <a name="parameters"></a>Parameter  
 n  
 Die Anzahl der Elemente, für die Speicherplatz vorab zugewiesen werden soll.  
  
 `InIt`  
 Der Typname der UnorderedMapView.  
  
 `H`  
 Ein Funktionsobjekt, das einen Hashwert für einen Schlüssel haben kann. Standardmäßig [Std:: Hash\<K >](http://msdn.microsoft.com/en-us/54f67435-af9d-4217-a29d-fa4d2491a104) für die Typen, die `std::hash` unterstützt.  
  
 `P`  
 Ein Typ, der ein Funktionsobjekt bereitstellt, das zwei Schlüssel vergleichen kann, um deren Gleichheit zu bestimmen. Standardmäßig [Std:: equal_to\<K >](../standard-library/equal-to-struct.md).  
  
 `m`  
 Ein Verweis oder [Lvalues und Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md) zu einem [Std:: unordered_map](../standard-library/unordered-map-class.md) , wird verwendet, um die UnorderedMapView zu initialisieren.  
  
 `first`  
 Der Eingabeiterator des ersten Elements in einem Bereich von Elementen, die verwendet werden, um die UnorderedMapView zu initialisieren.  
  
 `last`  
 Der Eingabeiterator des ersten Elements nach einem Bereich von Elementen, die verwendet werden, um die UnorderedMapView zu initialisieren.  
   
## <a name="see-also"></a>Siehe auch  
 [Platform:: Collections-Namespace](../cppcx/platform-collections-namespace.md)   
 [Windows::Foundation::IMapView](http://go.microsoft.com/fwlink/p/?LinkId=262409)