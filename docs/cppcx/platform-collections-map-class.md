---
title: Platform::Collections::Map Klasse | Microsoft Docs
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- COLLECTION/Platform::Collections::Map::Map
- COLLECTION/Platform::Collections::Map::Clear
- COLLECTION/Platform::Collections::Map::First
- COLLECTION/Platform::Collections::Map::GetView
- COLLECTION/Platform::Collections::Map::HasKey
- COLLECTION/Platform::Collections::Map::Insert
- COLLECTION/Platform::Collections::Map::Lookup
- COLLECTION/Platform::Collections::Map::Remove
- COLLECTION/Platform::Collections::Map::Size
dev_langs: C++
helpviewer_keywords: Map Class (C++/Cx)
ms.assetid: 2b8cf968-1167-4898-a149-1195b32c1785
caps.latest.revision: "19"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 3cf7cec405170a1bb1ee02cfd076c78c43524c74
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="platformcollectionsmap-class"></a>Platform::Collections::Map-Klasse
Stellt eine *Zuordnung*dar, die eine Auflistung von Schlüssel-Wert-Paaren ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <  
   typename K,  
   typename V,  
   typename C = std::less<K>>  
ref class Map sealed;  
```  
#### <a name="parameters"></a>Parameter  
 `K`  
 Der Typ des Schlüssels im Schlüssel-Wert-Paar.  
  
 `V`  
 Der Typ des Werts im Schlüssel-Wert-Paar.  
  
 `C`  
 Ein Typ, der ein Funktionsobjekt bereitstellt, das zwei Elementwerte als Sortierschlüssel vergleichen kann, um deren relative Reihenfolge in der Map zu bestimmen. Standardmäßig [Std:: less\<K >](../standard-library/less-struct.md).  
  
 __is_valid_winrt_type()  
 Eine vom Compiler generierte Funktion, die den Typ von K und V überprüft und eine benutzerfreundliche Fehlermeldung ausgibt, wenn der Typ nicht in der Zuordnung gespeichert werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Zulässige Typen sind:  
  
-   Ganze Zahlen  
  
-   Schnittstellenklasse ^  
  
-   Öffentliche Referenzklasse^  
  
-   value struct  
  
-   Öffentliche Enumerationsklasse  
  
 Die Zuordnung ist im Grunde genommen ein Wrapper für [std::map](../standard-library/map-class.md). Es ist eine konkrete C++-Implementierung, der die [Windows::Foundation::Collections::IMap < Windows::Foundation::Collections::IKeyValuePair\<K, V >>](http://go.microsoft.com/fwlink/p/?LinkId=262408) und [IObservableMap](http://msdn.microsoft.com/library/windows/apps/br226050.aspx) Windows-Runtime-Schnittstellen auf Typen, die über öffentliche übergeben werden. Wenn Sie versuchen, einen `Platform::Collections::Map` -Typ in einem öffentlichen Rückgabewert oder Parameter zu verwenden, wird der Compilerfehler C3986 ausgelöst. Sie können das Problem beheben, durch den Typ des Parameters oder des Rückgabewerts Werts zu ändern [Windows::Foundation::Collections::IMap\<K, V >](http://go.microsoft.com/fwlink/p/?LinkId=262408).  
  
 Weitere Informationen finden Sie unter [Sammlungen](../cppcx/collections-c-cx.md).  
  
### <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Map:: Map](#ctor)|Initialisiert eine neue Instanz der Map-Klasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Map:: Clear](#clear)|Entfernt alle Schlüssel-Wert-Paare aus dem derzeitigen Map-Objekt.|  
|[Map:: First](#first)|Gibt einen Iterator zurück, der das erste Element in der Zuordnung angibt.|  
|[Map:: GetView](#getview)|Gibt eine schreibgeschützte Ansicht der aktuellen Zuordnung zurück; das heißt, eine [Platform::Collections::MapView Class](../cppcx/platform-collections-mapview-class.md).|  
|[Map:: haskey](#haskey)|Ermittelt, ob die aktuelle Map den angegebenen Schlüssel enthält.|  
|[Map:: Insert](#insert)|Fügt das angegebene Schlüssel-Wert-Paar dem aktuellen Map-Objekt hinzu.|  
|[Map:: Lookup](#lookup)|Ruft das Element am angegebenen Schlüssel im aktuellen Map-Objekt ab.|  
|[Map:: Remove](#remove)|Löscht das angegebene Schlüssel-Wert-Paar vom aktuellen Map-Objekt.|  
|[Map:: Size](#size)|Gibt die Anzahl von Elementen im aktuellen Map-Objekt zurück.|  
  
### <a name="events"></a>Ereignisse  
  
|||  
|-|-|  
|Name|Beschreibung|  
|[Map:: mapchanged](#mapchanged-event.md)`event`|Tritt auf, wenn sich die Map ändert.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `Map`  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  

## <a name="clear"></a>Map:: Clear-Methode
Entfernt alle Schlüssel-Wert-Paare aus dem derzeitigen Map-Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```    
virtual void Clear();   
```  
  


## <a name="first"></a>Map:: First-Methode
Gibt einen Iterator zurück, der das erste Element in der Zuordnung angibt, oder `nullptr`, wenn die Zuordnung leer ist.  
  
### <a name="syntax"></a>Syntax  
  
```    
virtual Windows::Foundation::Collections::IIterator<  
Windows::Foundation::Collections::IKeyValuePair<K, V>^>^ First();  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator, der das erste Element in der Zuordnung angibt.  
  
### <a name="remarks"></a>Hinweise  
 Eine einfache Möglichkeit, den von First() zurückgegeben Iterator zu halten, den Rückgabewert einer Variablen zuzuweisen, die mit deklariert wird ist das **Auto** typableitungsschlüsselwort. Beispielsweise `auto x = myMap->First();`.  
  


## <a name="getview"></a>Map:: GetView-Methode
Gibt eine schreibgeschützte Ansicht der aktuellen Zuordnung zurück; d. h. eine [Platform::Collections::MapView Klasse](../cppcx/platform-collections-mapview-class.md), implementiert die [Windows::Foundation::Collections::IMapView\<K, V >](http://msdn.microsoft.com/library/windows/apps/br226037.aspx) Schnittstelle.  
  
### <a name="syntax"></a>Syntax  
  
```    
Windows::Foundation::Collections::IMapView<K, V>^ GetView();  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `MapView`-Objekt.  
  


## <a name="haskey"></a>Map:: haskey-Methode
Ermittelt, ob die aktuelle Map den angegebenen Schlüssel enthält.  
  
### <a name="syntax"></a>Syntax  
  
```    
bool HasKey(K key);  
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Der zum Suchen des Map-Elements verwendete Schlüssel. Der Typ des `key` ist der Typname *K*.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn der Schlüssel gefunden wurde, andernfalls `false`.  
  


## <a name="insert"></a>Map:: Insert-Methode
Fügt das angegebene Schlüssel-Wert-Paar dem aktuellen Map-Objekt hinzu.  
  
### <a name="syntax"></a>Syntax  
  
```  
  
virtual bool Insert(K key, V value);  
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Der Schlüsselteil des Schlüssel-Wert-Paars. Der Typ des `key` ist der Typname *K*.  
  
 `value`  
 Der Wertteil des Schlüssel-Wert-Paars. Der Typ des `value` ist der Typname *V*.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn der Schlüssel eines vorhandenen Elements in der aktuellen Map `key` entspricht und der Wertteil dieses Elements auf `value` festgelegt ist. `false`, wenn kein vorhandenes Element in der aktuellen Map `key` entspricht und die `key`- und `value`-Parameter zu einem Schlüssel-Wert-Paar gemacht und anschließend zur aktuellen Map hinzugefügt werden.  
  


## <a name="lookup"></a>Map:: Lookup-Methode
Ruft den Wert des Typs V ab, der mit dem angegebenen Schlüssel des Typs K verknüpft ist, sofern der Schlüssel vorhanden ist.  
  
### <a name="syntax"></a>Syntax  
  
```  
V Lookup(K key);  
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Der zum Suchen eines in der Zuordnung vorhandenen Elements verwendete Schlüssel. Der Typ des `key` ist der Typname *K*.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert, der dem `key` zugeordnet ist. Der Typ des Rückgabewerts ist der Typname *V*.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Schlüssel nicht vorhanden ist, wird eine [Platform:: outofboundsexception](../cppcx/platform-outofboundsexception-class.md) ausgelöst wird.  
  


## <a name="ctor"></a>Map:: Map-Konstruktor
Initialisiert eine neue Instanz der Map-Klasse.  
  
### <a name="syntax"></a>Syntax  
  
```  
explicit Map(const C& comp = C());  
explicit Map(const StdMap& m);  
explicit Map(StdMap&& m ;  
template <typename InIt>  
Map(  
   InItfirst,  
   InItlast,  
   const C& comp = C());  
```  
  
### <a name="parameters"></a>Parameter  
 `InIt`  
 Der Typname der aktuellen Map.  
  
 `comp`  
 Ein Typ, der ein Funktionsobjekt bereitstellt, das zwei Elementwerte als Sortierschlüssel vergleichen kann, um deren relative Reihenfolge in der Map zu bestimmen.  
  
 `m`  
 Ein Verweis oder [Lvalues und Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md) zu einem `map Class` wird verwendet, um die aktuelle Map zu initialisieren.  
  
 `first`  
 Der Eingabeiterator des ersten Elements in einem Bereich von Elementen, die verwendet werden, um die aktuelle Map zu initialisieren.  
  
 `last`  
 Der Eingabeiterator des ersten Elements nach einem Bereich von Elementen, die verwendet werden, um die aktuelle Map zu initialisieren.  
  


## <a name="mapchanged"></a>Map:: mapchanged-Ereignis
Wird ausgelöst, wenn ein Element in eine Zuordnung eingefügt bzw. aus der Zuordnung entfernt wird.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
event Windows::Foundation::Collections::MapChangedEventHandler<K,V>^ MapChanged;  
```  
  
### <a name="property-valuereturn-value"></a>Eigenschaftswert/Rückgabewert  
 Ein [MapChangedEventHandler\<K, V >](http://msdn.microsoft.com/library/windows/apps/br206644.aspx) , enthält Informationen über das Objekt, das das Ereignis und die Art der entstandenen Änderung ausgelöst. Siehe auch [IMapChangedEventArgs\<K >](http://msdn.microsoft.com/library/windows/apps/br226034.aspx) und [CollectionChange-Enumeration](http://msdn.microsoft.com/library/windows/apps/windows.foundation.collections.collectionchange.aspx).  
  
## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework  
 Windows Store-apps, die mithilfe von c# oder Visual Basic-Projekt IMap\<K, V > als IDictionary\<K, V >.  
  


## <a name="remove"></a>Map:: Remove-Methode
Löscht das angegebene Schlüssel-Wert-Paar vom aktuellen Map-Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```    
virtual void Remove(K key);  
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Der Schlüsselteil des Schlüssel-Wert-Paars. Der Typ des `key` ist der Typname *K*.  
  


## <a name="size"></a>Map:: size-Methode
Gibt die Anzahl der [Windows::Foundation::Collections::IKeyValuePair\<K, V >](http://msdn.microsoft.com/library/windows/apps/br226031.aspx) Elementen in der Zuordnung.  
  
### <a name="syntax"></a>Syntax  
  
```    
virtual property unsigned int Size;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl von Elementen in der Zuordnung.  
  

  
## <a name="see-also"></a>Siehe auch  
 [Platform-Namespace](platform-namespace-c-cx.md)   
 [Erstellen von Windows-Runtime-Komponenten in C++](/MicrosoftDocs/windows-uwp/blob/docs/windows-apps-src/winrt-components/creating-windows-runtime-components-in-cpp.md)