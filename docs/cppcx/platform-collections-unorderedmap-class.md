---
title: Platform::Collections::UnorderedMap Klasse | Microsoft Docs
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- collection/Platform::Collections::UnorderedMap
ms.assetid: dc84f261-b13c-4c0a-9b57-30dcb9e3065e
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 248b25e61af0ce766c81d480d7ebf39618a8dfec
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="platformcollectionsunorderedmap-class"></a>Platform::Collections::UnorderedMap-Klasse

Stellt eine ungeordnete *Zuordnung*dar, die eine Auflistung von Schlüssel-Wert-Paaren ist.

## <a name="syntax"></a>Syntax

```cpp
template <
   typename K,
   typename V,
   typename C = std::equal_to<K>
>
ref class Map sealed;
```

#### <a name="parameters"></a>Parameter

*K*  
Der Typ des Schlüssels im Schlüssel-Wert-Paar.

*V*  
Der Typ des Werts im Schlüssel-Wert-Paar.

*C*  
Ein Typ, der ein Funktionsobjekt bereitstellt, das zwei Elementwerte als Sortierschlüssel vergleichen kann, um deren relative Reihenfolge in der Map zu bestimmen. Standardmäßig [Std:: equal_to\<K >](../standard-library/equal-to-struct.md).

### <a name="remarks"></a>Hinweise

Zulässige Typen sind:

- Ganze Zahlen

- Schnittstellenklasse ^

- Öffentliche Referenzklasse^

- value struct

- Öffentliche Enumerationsklasse

**UnorderedMap** ist im Grunde genommen ein Wrapper für [Std:: unordered_map](../standard-library/unordered-map-class.md) , die das Speichern von Windows-Runtime-Typen unterstützt. Es ist der eine konkrete Implementierung der der [Windows::Foundation::Collections::IMap](/uwp/api/Windows.Foundation.Collections.IMap_K_V_) und [IObservableMap](/uwp/api/Windows.Foundation.Collections.IObservableMap_K_V_) Typen, die über öffentliche übergeben werden Windows-Runtime-Schnittstellen. Wenn Sie versuchen, einen `Platform::Collections::UnorderedMap`-Typ in einem öffentlichen Rückgabewert oder Parameter zu verwenden, wird der Compilerfehler C3986 ausgelöst. Sie können das Problem beheben, durch den Typ des Parameters oder des Rückgabewerts Werts zu ändern [Windows::Foundation::Collections::IMap](/uwp/api/Windows.Foundation.Collections.IMap_K_V_).

Weitere Informationen finden Sie unter [Sammlungen](../cppcx/collections-c-cx.md).

### <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[UnorderedMap::UnorderedMap](#ctor)|Initialisiert eine neue Instanz der Map-Klasse.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[UnorderedMap::Clear](#clear)|Entfernt alle Schlüssel-Wert-Paare aus dem derzeitigen Map-Objekt.|
|[UnorderedMap::First](#first)|Gibt einen Iterator zurück, der das erste Element in der Zuordnung angibt.|
|[UnorderedMap::GetView](#getview)|Gibt eine schreibgeschützte Ansicht der aktuellen Zuordnung zurück; das heißt, eine Platform::Collections::UnorderedMapView-Klasse.|
|[UnorderedMap::HasKey](#haskey)|Ermittelt, ob die aktuelle Map den angegebenen Schlüssel enthält.|
|[UnorderedMap::Insert](#insert)|Fügt das angegebene Schlüssel-Wert-Paar dem aktuellen Map-Objekt hinzu.|
|[UnorderedMap::Lookup](#lookup)|Ruft das Element am angegebenen Schlüssel im aktuellen Map-Objekt ab.|
|[UnorderedMap::Remove](#remove)|Löscht das angegebene Schlüssel-Wert-Paar vom aktuellen Map-Objekt.|
|[UnorderedMap::Size](#size)|Gibt die Anzahl von Elementen im aktuellen Map-Objekt zurück.|

### <a name="events"></a>Ereignisse

|||
|-|-|
|name|Beschreibung|
|[Map:: mapchanged](#mapchanged) Ereignis|Tritt auf, wenn sich die Map ändert.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`UnorderedMap`

### <a name="requirements"></a>Anforderungen

**Header:** collection.h

**Namespace:** Platform::Collections

## <a name="clear"></a>  Unorderedmap:: Clear-Methode

Entfernt alle Schlüssel-Wert-Paare aus dem aktuellen UnorderedMap-Objekt.

### <a name="syntax"></a>Syntax

```cpp
virtual void Clear();
```

## <a name="first"></a>  Unorderedmap:: First-Methode

Gibt einen Iterator, der angibt, das erste [Windows::Foundation::Collections::IKeyValuePair\<K, V >](http://msdn.microsoft.com/library/windows/apps/br226031.aspx) Element in der ungeordneten Zuordnung.

### <a name="syntax"></a>Syntax

```cpp
virtual Windows::Foundation::Collections::IIterator<
   Windows::Foundation::Collections::IKeyValuePair<K, V>^>^ 
   First();
```

### <a name="return-value"></a>Rückgabewert

Ein Iterator, der das erste Element in der Zuordnung angibt.

### <a name="remarks"></a>Hinweise

Eine einfache Möglichkeit, den von First() zurückgegeben Iterator zu halten, den Rückgabewert einer Variablen zuzuweisen, die mit deklariert wird ist das **Auto** typableitungsschlüsselwort. Beispielsweise `auto x = myUnorderedMap->First();`.

## <a name="getview"></a>  Unorderedmap:: GetView-Methode

Gibt eine schreibgeschützte Ansicht der aktuellen UnorderedMap zurück; d. h. eine [Platform::Collections::UnorderedMapView Klasse](../cppcx/platform-collections-unorderedmapview-class.md) , implementiert die [Windows::Foundation::Collections::IMapView::IMapView](http://msdn.microsoft.com/library/windows/apps/br226037.aspx) Schnittstelle.

### <a name="syntax"></a>Syntax

```cpp
Windows::Foundation::Collections::IMapView<K, V>^ GetView();
```

### <a name="return-value"></a>Rückgabewert

Ein `UnorderedMapView`-Objekt.

## <a name="haskey"></a>  Unorderedmap:: Haskey-Methode

Ermittelt, ob die aktuelle ungeordnete Zuordnung den angegebenen Schlüssel enthält.

### <a name="syntax"></a>Syntax

```cpp
bool HasKey(
   K key
);
```

### <a name="parameters"></a>Parameter

*key*  
Der zum Suchen des UnorderedMap-Elements verwendete Schlüssel. Der Typ des *Schlüssel* ist der Typname *K*.

### <a name="return-value"></a>Rückgabewert

`true`, wenn der Schlüssel gefunden wurde, andernfalls `false`.

## <a name="insert"></a>  UnorderedMap::Insert Method

Fügt das angegebene Schlüssel-Wert-Paar dem aktuellen UnorderedMap-Objekt hinzu.

### <a name="syntax"></a>Syntax

```cpp
virtual bool Insert(
   K key,
   V value
);
```

### <a name="parameters"></a>Parameter

*key*  
Der Schlüsselteil des Schlüssel-Wert-Paars. Der Typ des *Schlüssel* ist der Typname *K*.

*Wert*  
Der Wertteil des Schlüssel-Wert-Paars. Der Typ des *Wert* ist der Typname *V*.

### <a name="return-value"></a>Rückgabewert

`true` Wenn der Schlüssel eines vorhandenen Elements in der aktuellen Map entspricht *Schlüssel* und der Wertteil dieses Elements wird festgelegt, um *Wert*. `false` Wenn kein vorhandenes Element in der aktuellen Map entspricht *Schlüssel* und *Schlüssel* und *Wert* -Parameter zu einem Schlüssel-Wert-Paar gemacht und anschließend zur aktuellen ungeordneten Zuordnung hinzugefügt werden.

## <a name="lookup"></a>  Unorderedmap:: Lookup-Methode

Ruft den Wert des Typs V ab, der dem angegebenen Schlüssel des Typs K zugeordnet ist.

### <a name="syntax"></a>Syntax

```cpp
V Lookup(
   K key
);
```

### <a name="parameters"></a>Parameter

*key*  
Der zum Suchen eines in der UnorderedMap vorhandenen Elements verwendete Schlüssel. Der Typ des *Schlüssel* ist der Typname *K*.

### <a name="return-value"></a>Rückgabewert

Der Wert, der zugeordnet ist die *Schlüssel*. Der Typ des Rückgabewerts ist der Typname *V*.

## <a name="mapchanged"></a>  Unorderedmap:: Mapchanged

Wird ausgelöst, wenn ein Element in eine Zuordnung eingefügt bzw. aus der Zuordnung entfernt wird.

### <a name="syntax"></a>Syntax

```cpp
event Windows::Foundation::Collections::MapChangedEventHandler<K,V>^ MapChanged;
```

### <a name="property-valuereturn-value"></a>Eigenschaftswert/Rückgabewert

Ein [MapChangedEventHandler\<K, V >](http://msdn.microsoft.com/library/windows/apps/br206644.aspx) , enthält Informationen über das Objekt, das das Ereignis und die Art der entstandenen Änderung ausgelöst. Siehe auch [IMapChangedEventArgs\<K >](http://msdn.microsoft.com/library/windows/apps/br226034.aspx) und [CollectionChange-Enumeration](http://msdn.microsoft.com/library/windows/apps/windows.foundation.collections.collectionchange.aspx).

## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework

Windows-Runtime-apps, die für C#- oder Visual Basic-IMap Projekt\<K, V > als IDictionary\<K, V >.

## <a name="remove"></a>  Unorderedmap:: Remove-Methode

Löscht das angegebene Schlüssel-Wert-Paar vom UnorderedMap-Objekt.

### <a name="syntax"></a>Syntax

```cpp
virtual void Remove(
   K key);
```

### <a name="parameters"></a>Parameter

*key*  
Der Schlüsselteil des Schlüssel-Wert-Paars. Der Typ des *Schlüssel* ist der Typname *K*.

## <a name="size"></a>  Unorderedmap:: size-Methode

Gibt die Anzahl der [Windows::Foundation::Collections::IKeyValuePair\<K, V >](http://msdn.microsoft.com/library/windows/apps/br226031.aspx) Elemente in der unorderedmap zurück.

### <a name="syntax"></a>Syntax

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl von Elementen in der ungeordneten Zuordnung.

## <a name="ctor"></a>  UnorderedMap::UnorderedMap-Konstruktor

Initialisiert eine neue Instanz der UnorderedMap-Klasse.

### <a name="syntax"></a>Syntax

```cpp
UnorderedMap();

explicit UnorderedMap(
    size_t n
    );

UnorderedMap(
    size_t n,
    const H& h
    );

UnorderedMap(
    size_t n,
    const H& h,
    const P& p
    );

explicit UnorderedMap(
    const std::unordered_map<K, V, H, P>& m
    );

explicit UnorderedMap(
    std::unordered_map<K, V, H, P>&& m
    );

template <typename InIt>
UnorderedMap(
    InIt first,
    InIt last
    );

template <typename InIt>
UnorderedMap(
    InIt first,
    InIt last,
    size_t n
    );

template <typename InIt>
UnorderedMap(
    InIt first,
    InIt last,
    size_t n,
    const H& h
    );

template <typename InIt>
UnorderedMap(
    InIt first,
    InIt last,
    size_t n,
    const H& h,
    const P& p
    );

UnorderedMap(
    std::initializer_list< std::pair<const K, V>> il
    );

UnorderedMap(
    std::initializer_list< std::pair<const K, V>> il,
    size_t n
    );

UnorderedMap(
    std::initializer_list< std::pair<const K, V>> il,
    size_t n,
    const H& h
    );

UnorderedMap(
    std::initializer_list< std::pair<const K, V>> il,
    size_t n,
    const H& h,
    const P& p
    );
```

### <a name="parameters"></a>Parameter

*InIt*  
Der Typname der aktuellen UnorderedMap.

*P*  
Ein Funktionsobjekt, das zwei Schlüssel vergleichen kann, um zu bestimmen, ob sie gleich sind. Dieser Parameter ist standardmäßig [Std:: equal_to\<K >](../standard-library/equal-to-struct.md).

*H*  
Ein Funktionsobjekt, das einen Hashwert für Schlüssel erzeugt. Dieser Parameter ist standardmäßig [hash-Klasse 1](../standard-library/hash-class.md) für die Typen, die diese Klasse unterstützt.

*m*  
Ein Verweis oder [Lvalues und Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md) zu einem [Std:: unordered_map](../standard-library/unordered-map-class.md) , wird verwendet, um die aktuelle UnorderedMap zu initialisieren.

*IL* ein [Std:: initializer_list](../standard-library/initializer-list-class.md) von [Std:: Pair](../standard-library/pair-structure.md) Objekte, die verwendet wird, um die Zuordnung zu initialisieren.

*first*  
Der Eingabeiterator des ersten Elements in einem Bereich von Elementen, die verwendet werden, um die aktuelle UnorderedMap zu initialisieren.

*last*  
Der Eingabeiterator des ersten Elements nach einem Bereich von Elementen, die verwendet werden, um die aktuelle UnorderedMap zu initialisieren.

## <a name="see-also"></a>Siehe auch

[Platform-Namespace](platform-namespace-c-cx.md)  
[Platform::Collections-Namespace](../cppcx/platform-collections-namespace.md)  
[Platform::Collections::Map-Klasse](../cppcx/platform-collections-map-class.md)  
[Platform::Collections::UnorderedMapView-Klasse](../cppcx/platform-collections-unorderedmapview-class.md)  
[Sammlungen](../cppcx/collections-c-cx.md)  
[Erstellen von Windows-Runtime-Komponenten in C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)  
