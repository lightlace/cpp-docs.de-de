---
title: Platform::Collections::VectorIterator Klasse | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::VectorIterator::VectorIterator
dev_langs:
- C++
helpviewer_keywords:
- VectorIterator Class
ms.assetid: d531cb42-27e0-48a6-bf5e-c265891a18ff
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: deaab183a092a073c6681004654312485959e924
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33092531"
---
# <a name="platformcollectionsvectoriterator-class"></a>Platform::Collections::VectorIterator-Klasse
Stellt einen standardvorlagenbibliotheksiterator für Objekte, die von der Windows-Runtime-IVector-Schnittstelle abgeleitet.  
  
 VectorIterator ist ein proxyiterator, der Elemente des Typs VectorProxy speichert\<T >. Allerdings ist das Proxyobjekt fast nie für Benutzercode sichtbar. Weitere Informationen finden Sie unter [Auflistungen (C++/CX)](../cppcx/collections-c-cx.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
template <typename T>  
class VectorIterator;  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Typname der VectorIterator-Vorlagenklasse.  
  
### <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`difference_type`|Ein Zeigerunterschied (ptrdiff_t).|  
|`iterator_category`|Die Kategorie eines direkten Iterators (::std::random_access_iterator_tag).|  
|`pointer`|Ein Zeiger auf einen internen Typ, Platform::Collections::Details::VectorProxy\<T >, d. h. für die Implementierung von VectorIterator erforderlich sind.|  
|`reference`|Ein Verweis auf einen internen Typ, Platform::Collections::Details::VectorProxy\<T >, d. h. für die Implementierung von VectorIterator erforderlich sind.|  
|`value_type`|Der `T` -Typname.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[VectorIterator::VectorIterator](#ctor)|Initialisiert eine neue Instanz der VectorIterator-Klasse.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[VectorIterator::operator-Operator](#operator-minus)|Subtrahiert entweder eine angegebene Anzahl von Elementen vom aktuellen Iterator und bildet einen neuen Iterator, oder subtrahiert einen angegebenen Iterator vom aktuellen Iterator, und gibt die Anzahl von Elementen zwischen den Iteratoren zurück.|  
|[VectorIterator::operator--Operator](#operator-decrement)|Dekrementiert den aktuellen VectorIterator.|  
|[VectorIterator::operator!=-Operator](#operator-inequality)|Gibt an, ob der aktuelle VectorIterator ungleich einem angegebenen VectorIterator ist.|  
|[VectorIterator::operator*-Operator](#operator-dereference)|Ruft einen Verweis auf das Element ab, das vom aktuellen VectorIterator angegeben wird.|  
|[VectorIterator::operator\[\]](#operator-at)|Ruft einen Verweis auf das Element ab, das eine angegebene Verschiebung vom aktuellen VectorIterator ist.|  
|[VectorIterator::operator+-Operator](#operator-plus)|Gibt einen VectorIterator zurück, der auf das Element an der angegebenen Verschiebung von dem angegebenen VectorIterator verweist.|  
|[VectorIterator::operator++-Operator](#operator-increment)|Inkrementiert den aktuellen VectorIterator.|  
|[VectorIterator::operator+=-Operator](#operator-plus-assign)|Inkrementiert den aktuellen VectorIterator um die angegebene Verschiebung.|  
|[VectorIterator::operator<-Operator](#operator-less-than)|Gibt an, ob der aktuelle VectorIterator kleiner einem angegebenen VectorIterator ist.|  
|[Vectoriterator::\<=-Operator](#operator-less-than-or-equals)|Gibt an, ob der aktuelle VectorIterator kleiner oder gleich einem angegebenen VectorIterator ist.|  
|[VectorIterator::operator-=-Operator](#operator-subtract-assign)|Dekrementiert den aktuellen VectorIterator um die angegebene Verschiebung.|  
|[VectorIterator::operator==-Operator](#operator-equality)|Gibt an, ob der aktuelle VectorIterator gleich einem angegebenen VectorIterator ist.|  
|[VectorIterator::operator>-Operator](#operator-greater-than)|Gibt an, ob der aktuelle VectorIterator größer als ein angegebener VectorIterator ist.|  
|[VectorIterator::operator->-Operator](#operator-arrow)|Ruft die Adresse des Elements ab, auf das vom aktuellen VectorIterator verwiesen wird.|  
|[VectorIterator::operator>=-Operator](#operator-greater-than-or-equal)|Gibt an, ob der aktuelle VectorIterator größer oder gleich einem angegebenen VectorIterator ist.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `VectorIterator`  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  

## <a name="operator-arrow"></a>  Vectoriterator:: -&gt; Operator
Ruft die Adresse des Elements ab, auf das vom aktuellen VectorIterator verwiesen wird.  
  
### <a name="syntax"></a>Syntax  
  
```  
Detail::ArrowProxy<T> operator->() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert des Elements, auf das vom aktuellen VectorIterator verwiesen wird.  
  
 Der Typ des Rückgabewerts ist ein nicht angegebener interner Typ, der für die Implementierung dieses Operators erforderlich ist.  
  


## <a name="operator-decrement"></a>  Vectoriterator:: – Operator
Dekrementiert den aktuellen VectorIterator.  
  
### <a name="syntax"></a>Syntax  
  
```  
  
VectorIterator& operator--();  
VectorIterator operator--(int);  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die erste Syntax dekrementiert und gibt dann den aktuellen VectorIterator zurück. Die zweite Syntax gibt eine Kopie des aktuellen VectorIterator zurück und dekrementiert dann den aktuellen VectorIterator.  
  
### <a name="remarks"></a>Hinweise  
 Die erste VectorIterator-Syntax prädekrementiert den aktuellen VectorIterator.  
  
 Die zweite Syntax postdekrementiert den aktuellen VectorIterator. Die `int` Typ in der zweiten Syntax gibt eine nach-dekrementierungsoperation an, keinen tatsächlichen ganzzahligen Operanden.  
  


## <a name="operator-dereference"></a>  Vectoriterator:: *-Operator
Ruft die Adresse des Elements ab, das vom aktuellen VectorIterator angegeben wird.  
  
### <a name="syntax"></a>Syntax  
  
```  
reference operator*() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das vom aktuellen VectorIterator angegebene Element.  
  


## <a name="operator-equality"></a>  Vectoriterator:: Operator ==-Operator
Gibt an, ob der aktuelle VectorIterator gleich einem angegebenen VectorIterator ist.  
  
### <a name="syntax"></a>Syntax  
  
```  
bool operator==(const VectorIterator& other) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `other`  
 Ein weiterer VectorIterator.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn der aktuelle VectorIterator gleich dem `other` ist, andernfalls `false`.  
  


## <a name="operator-greater-than"></a>  Vectoriterator::&gt; Operator
Gibt an, ob der aktuelle VectorIterator größer als ein angegebener VectorIterator ist.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
  
bool operator>(const VectorIterator& other) const   
```  
  
### <a name="parameters"></a>Parameter  
 `other`  
 Ein weiterer VectorIterator.  
  
### <a name="return-value"></a>Rückgabewert  
 `true` Wenn der aktuelle VectorIterator größer als `other`ist, andernfalls `false`.  
  


## <a name="operator-greater-than-or-equals"></a>  Vectoriterator::&gt;=-Operator
Gibt an, ob der aktuelle VectorIterator größer oder gleich dem angegebenen VectorIterator ist.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
  
bool operator>=(const VectorIterator& other) const   
```  
  
### <a name="parameters"></a>Parameter  
 `other`  
 Ein weiterer VectorIterator.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn der aktuelle VectorIterator größer oder gleich `other` ist, andernfalls `false`.    


## <a name="operator-increment"></a>  Vectoriterator:: Operator++-Operator
Inkrementiert den aktuellen VectorIterator.  
  
### <a name="syntax"></a>Syntax  
  
```    
VectorIterator& operator++();  
VectorIterator operator++(int);  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die erste Syntax inkrementiert und gibt dann den aktuellen VectorIterator zurück. Die zweite Syntax gibt eine Kopie des aktuellen VectorIterator zurück und inkrementiert dann den aktuellen VectorIterator.  
  
### <a name="remarks"></a>Hinweise  
 Die erste VectorIterator-Syntax präinkrementiert den aktuellen VectorIterator.  
  
 Die zweite Syntax postinkrementiert den aktuellen VectorIterator. Der Typ `int` in der zweiten Syntax gibt eine Nach-Inkrementierungsoperation an, keinen tatsächlichen ganzzahligen Operanden.  
  


## <a name="operator-inequality"></a>  Vectoriterator::! =-Operator
Gibt an, ob der aktuelle VectorIterator ungleich einem angegebenen VectorIterator ist.  
  
### <a name="syntax"></a>Syntax  
  
```  
bool operator!=(const VectorIterator& other) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `other`  
 Ein weiterer VectorIterator.  
  
### <a name="return-value"></a>Rückgabewert  
 `true` Wenn der aktuelle VectorIterator ungleich ist `other`ist, andernfalls `false`.  
  


## <a name="operator-less-than"></a>  Vectoriterator::&lt; Operator
Gibt an, ob der aktuelle VectorIterator kleiner einem angegebenen VectorIterator ist.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
  
bool operator<(const VectorIterator& other) const   
```  
  
### <a name="parameters"></a>Parameter  
 `other`  
 Ein weiterer VectorIterator.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn der aktuelle VectorIterator kleiner als `other` ist, andernfalls `false`.  
  


## <a name="operator-less-than-or-equals"></a>  Vectoriterator::&lt;=-Operator
Gibt an, ob der aktuelle VectorIterator kleiner oder gleich einem angegebenen VectorIterator ist.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
  
bool operator<=(const VectorIterator& other) const   
```  
  
### <a name="parameters"></a>Parameter  
 `other`  
 Ein weiterer VectorIterator.  
  
### <a name="return-value"></a>Rückgabewert  
 `true` Wenn der aktuelle VectorIterator kleiner als oder gleich `other`ist, andernfalls `false`.  
  


## <a name="operator-minus"></a>  Vectoriterator:: Operator--Operator
Subtrahiert entweder eine angegebene Anzahl von Elementen vom aktuellen Iterator und bildet einen neuen Iterator, oder subtrahiert einen angegebenen Iterator vom aktuellen Iterator, und gibt die Anzahl von Elementen zwischen den Iteratoren zurück.  
  
### <a name="syntax"></a>Syntax  
  
```  
  
VectorIterator operator-(difference_type n) const;  
  
difference_type operator-(const VectorIterator& other) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `n`  
 Eine Anzahl von Elementen.  
  
 `other`  
 Ein weiterer VectorIterator.  
  
### <a name="return-value"></a>Rückgabewert  
 Die erste Operatorsyntax gibt ein VectorIterator-Objekt, das `n` Elemente kleiner ist als der aktuelle VectorIterator. Die zweite Operatorsyntax gibt die Anzahl von Elementen zwischen dem aktuellen und dem `other` VectorIterator.  
  


## <a name="operator-plus-assign"></a>  Vectoriterator:: Operator +=-Operator
Inkrementiert den aktuellen VectorIterator um die angegebene Verschiebung.  
  
### <a name="syntax"></a>Syntax  
  
```  
VectorIterator& operator+=(difference_type n);  
```  
  
### <a name="parameters"></a>Parameter  
 `n`  
 Eine ganzzahlige Verschiebung.  
  
### <a name="return-value"></a>Rückgabewert  
 Der aktualisierte VectorIterator.  
  


## <a name="operator-plus"></a>  ectorIterator::operator +-Operator
Gibt einen VectorIterator zurück, der auf das Element an der angegebenen Verschiebung von dem angegebenen VectorIterator verweist.  
  
### <a name="syntax"></a>Syntax  
  
```  
  
VectorIterator operator+(difference_type n);  
  
template <typename T>  
inline VectorIterator<T> operator+(
  ptrdiff_t n, 
  const VectorIterator<T>& i);  
  
```  
  
### <a name="parameters"></a>Parameter  
 `T`  
 In der zweiten Syntax der Typname vom VectorIterator.  
  
 `n`  
 Eine ganzzahlige Verschiebung.  
  
 `i`  
 In der zweiten Syntax ein VectorIterator.  
  
### <a name="return-value"></a>Rückgabewert  
 In der ersten Syntax ein VectorIterator, der auf das Element an der angegebenen Verschiebung vom aktuellen VectorIterator verweist.  
  
 In der zweiten Syntax ein VectorIterator, der auf das Element an der angegebenen Verschiebung vom Anfang des Parameters `i` verweist.  
  
### <a name="remarks"></a>Hinweise  
 Das erste Syntaxbeispiel  
  


## <a name="operator-minus-equals"></a>  Vectoriterator:: Operator-=-Operator
Dekrementiert den aktuellen VectorIterator um die angegebene Verschiebung.  
  
### <a name="syntax"></a>Syntax  
  
```  
VectorIterator& operator-=(difference_type n);  
```  
  
### <a name="parameters"></a>Parameter  
 `n`  
 Eine ganzzahlige Verschiebung.  
  
### <a name="return-value"></a>Rückgabewert  
 Der aktualisierte VectorIterator.  
  


## <a name="operator-at"></a>  Vectoriterator::\[\]
Ruft einen Verweis auf das Element ab, das eine angegebene Verschiebung vom aktuellen VectorIterator ist.  
  
### <a name="syntax"></a>Syntax  
  
```    
reference operator[](difference_type n) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `n`  
 Eine ganzzahlige Verschiebung.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Element, das vom aktuellen VectorIterator durch die `n`-Elemente ersetzt wird.  
  


## <a name="ctor"></a>  Vectoriterator:: Vectoriterator-Konstruktor
Initialisiert eine neue Instanz der VectorIterator-Klasse.  
  
### <a name="syntax"></a>Syntax  
  
```    
VectorIterator();  
  
explicit VectorIterator(  
   Windows::Foundation::Collections::IVector<T>^ v);  
```  
  
### <a name="parameters"></a>Parameter  
 `v`  
 Ein IVector\<T >-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Das erste Syntaxbeispiel ist der Standardkonstruktor. Das zweite Syntaxbeispiel ist ein expliziter Konstruktor, der verwendet wird, um einen VectorIterator aus einem IVector erstellen\<T >-Objekt.  
  


  
## <a name="see-also"></a>Siehe auch  
 [Platform-Namespace](platform-namespace-c-cx.md)