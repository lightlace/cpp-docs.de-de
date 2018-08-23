---
title: Platform::Collections::VectorView-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::VectorView::VectorView
- COLLECTION/Platform::Collections::VectorView::First
- COLLECTION/Platform::Collections::VectorView::GetAt
- COLLECTION/Platform::Collections::VectorView::GetMany
- COLLECTION/Platform::Collections::VectorView::IndexOf
- COLLECTION/Platform::Collections::VectorView::Size
dev_langs:
- C++
helpviewer_keywords:
- VectorView Class
ms.assetid: 05cd461d-dce7-49d3-b0e7-2e5c78ed8192
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b0020937bae5f6392c7d9e5e8daf22f3cc4e6a31
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42584105"
---
# <a name="platformcollectionsvectorview-class"></a>Platform::Collections::VectorView-Klasse
Stellt eine schreibgeschützte Ansicht einer sequenziellen Auflistung von Objekten dar, auf die einzeln nach Index zugegriffen werden kann. Der Typ der einzelnen Objekte in der Auflistung wird durch den Vorlagenparameter spezifiziert.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <typename T, typename E>  
   ref class VectorView sealed;  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Typ der im `VectorView` -Objekt enthaltenen Elemente.  
  
 `E`  
 Gibt ein binäres Prädikat zum Testen der Übereinstimmung mit Werten des Typs `T`an. Der Standardwert ist `std::equal_to<T>`.  
  
### <a name="remarks"></a>Hinweise  
 Die `VectorView` -Klasse implementiert die [Windows::Foundation::Collections::IVectorView\<T >](http://go.microsoft.com/fwlink/p/?LinkId=262411) -Schnittstelle und die Unterstützung für standardvorlagenbibliotheksiteratoren.  
  
### <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[VectorView::VectorView](#ctor)|Initialisiert eine neue Instanz der VectorView-Klasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[VectorView::First](#first)|Gibt einen Iterator zurück, der das erste Element in der VectorView angibt.|  
|[VectorView::GetAt](#getat)|Ruft das Element der aktuellen VectorView ab, das durch den angegebenen Index bezeichnet wird.|  
|[VectorView::GetMany](#getmany)|Ruft eine Sequenz von Elementen von der aktuellen VectorView ab, die am angegebenen Index beginnt.|  
|[VectorView::IndexOf](#indexof)|Sucht das angegebene Element in der aktuellen VectorView und gibt, wenn es gefunden wurde, den Index des Elements zurück.|  
|[VectorView::Size](#size)|Gibt die Anzahl von Elementen im aktuellen VectorView-Objekt zurück.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `VectorView`  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  

## <a name="first"></a>  Vectorview:: First-Methode
Gibt einen Iterator zurück, der das erste Element in der VectorView angibt.  
  
### <a name="syntax"></a>Syntax  
  
```  
  
virtual Windows::Foundation::Collections::IIterator<T>^   
   First();  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator, der das erste Element in der VectorView angibt.  
  
### <a name="remarks"></a>Hinweise  
 Den Rückgabewert einer Variablen zuweisen, die mit deklariert ist eine bequeme Möglichkeit, den von First() zurückgegeben Iterator zu halten ist die **automatisch** typableitungs-Schlüsselwort. Beispielsweise `auto x = myVectorView->First();`.  
  


## <a name="getat"></a>  Vectorview:: GetAt-Methode
Ruft das Element der aktuellen VectorView ab, das durch den angegebenen Index bezeichnet wird.  
  
### <a name="syntax"></a>Syntax  
  
```  
  
T GetAt(  
   UInt32 index  
);  
```  
  
### <a name="parameters"></a>Parameter  
 `index`  
 Eine nullbasierte ganze Zahl, die ein bestimmtes Element im VectorView-Objekt angibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Element, das durch den `index`-Parameter spezifiziert wird. Der Elementtyp wird durch den VectorView-Vorlagenparameter angegeben *T*.  
  


## <a name="getmany"></a>  Vectorview:: Getmany-Methode
Ruft eine Sequenz von Elementen von der aktuellen VectorView ab, die am angegebenen Index beginnt.  
  
### <a name="syntax"></a>Syntax  
  
```  
  
virtual unsigned int GetMany(  
   unsigned int startIndex,   
   ::Platform::WriteOnlyArray<T>^ dest  
);  
```  
  
### <a name="parameters"></a>Parameter  
 `startIndex`  
 Der nullbasierte Index des Anfangs der Elemente, die abgerufen werden sollen.  
  
 `dest`  
 Wenn dieser Vorgang abgeschlossen ist, ein Array von Elementen, die bei das angegebene Element beginnen `startIndex` und beim letzten Element in der VectorView.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der abgerufenen Elemente.  
  


## <a name="indexof"></a>  Vectorview:: IndexOf-Methode
Sucht das angegebene Element in der aktuellen VectorView und gibt, wenn es gefunden wurde, den Index des Elements zurück.  
  
### <a name="syntax"></a>Syntax  
  
```  
  
virtual bool IndexOf(  
   T value,  
   unsigned int* index  
);  
```  
  
### <a name="parameters"></a>Parameter  
 `value`  
 Das Element, das gesucht werden soll.  
  
 `index`  
 Der nullbasierte Index des Elements, wenn der Parameter `value` gefunden wurde, andernfalls 0.  
  
 Der `index`-Parameter ist 0, wenn das Element entweder das erste Element der VectorView ist oder wenn das Element nicht gefunden wurde. Wenn der Rückgabewert `true` ist, wurde das Element gefunden und es ist das erste Element; andernfalls wurde das Element nicht gefunden.  
  
### <a name="return-value"></a>Rückgabewert  
 `true` wenn das angegebene Element gefunden wurde, andernfalls `false`.  
  


## <a name="size"></a>  Vectorview:: size-Methode
Gibt die Anzahl von Elementen im aktuellen VectorView-Objekt zurück.  
  
### <a name="syntax"></a>Syntax  
  
```  
  
virtual property unsigned int Size;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente in der aktuellen VectorView.  
  


## <a name="ctor"></a>  Vectorview:: Vectorview-Konstruktor
Initialisiert eine neue Instanz der VectorView-Klasse.  
  
### <a name="syntax"></a>Syntax  
  
```  
VectorView();  
explicit VectorView(  
   UInt32 size  
);  
VectorView(  
   UInt32 size,  
   T value  
);  
explicit VectorView(  
   const ::std::vector<T>& v  
);  
explicit VectorView(  
   ::std::vector<T>&& v  
);  
VectorView(  
   const T * ptr,  
   UInt32 size  
);  
  
template <  
   size_t N  
>  
explicit VectorView(  
   const T (&arr)[N]  
);  
  
template <  
   size_t N  
>  
explicit VectorView(  
   const ::std::array<T,  
   N>& a  
);  
  
explicit VectorView(  
   const ::Platform::Array<T>^ arr  
);  
  
template <  
   typename InIt  
>  
VectorView(  
   InItfirst,  
   InItlast  
);  
  
VectorView(  
   std::initializer_list<T> il  
);  
```  
  
### <a name="parameters"></a>Parameter  
 `InIt`  
 Der Typ einer Auflistung von Objekten, die verwendet wird, um die aktuelle VectorView zu initialisieren.  
  
 il  
 Ein [Std:: initializer_list](../standard-library/initializer-list-class.md) , dessen Elemente werden verwendet, um die vectorview zu initialisieren.  
  
 `N`  
 Die Anzahl von Elementen in einer Auflistung von Objekten, die verwendet wird, um die aktuelle VectorView zu initialisieren.  
  
 `size`  
 Die Anzahl von Elementen in der VectorView.  
  
 `value`  
 Ein Wert, der verwendet wird, um die einzelnen Elemente in der aktuellen VectorView zu initialisieren.  
  
 `v`  
 Ein [Lvalues und Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md) zu einem [Std:: vector](../standard-library/vector-class.md) , wird verwendet, um die aktuelle vectorview zu initialisieren.  
  
 `ptr`  
 Zeiger zu `std::vector`, der verwendet wird, um die aktuelle VectorView zu initialisieren.  
  
 `arr`  
 Ein [Platform:: Array](../cppcx/platform-array-class.md) -Objekt, das verwendet wird, um die aktuelle vectorview zu initialisieren.  
  
 `a`  
 Ein [Std:: Array](../standard-library/array-class-stl.md) -Objekt, das verwendet wird, um die aktuelle vectorview zu initialisieren.  
  
 `first`  
 Das erste Element in einer Sequenz von Objekten, die verwendet werden, um die aktuelle VectorView zu initialisieren. Der Typ des `first` übergeben wird, mithilfe von *eine perfekte Weiterleitung*. Weitere Informationen finden Sie unter [RValue-Verweisdeklarator: &&](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
 `last`  
 Das letzte Element in einer Sequenz von Objekten, die verwendet werden, um die aktuelle VectorView zu initialisieren. Der Typ des `last` übergeben wird, mithilfe von *eine perfekte Weiterleitung*. Weitere Informationen finden Sie unter [RValue-Verweisdeklarator: &&](../cpp/rvalue-reference-declarator-amp-amp.md).  
  


  
## <a name="see-also"></a>Siehe auch  
 [Plattform-Namespace](platform-namespace-c-cx.md)   
 [Erstellen von Windows-Runtime-Komponenten in C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)