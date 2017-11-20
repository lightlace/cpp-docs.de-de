---
title: ':: Collections:: Vector-Klasse | Microsoft Docs'
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- COLLECTION/Platform::Collections::Vector::Vector
- COLLECTION/Platform::Collections::Vector::Append
- COLLECTION/Platform::Collections::Vector::Clear
- COLLECTION/Platform::Collections::Vector::First
- COLLECTION/Platform::Collections::Vector::GetAt
- COLLECTION/Platform::Collections::Vector::GetMany
- COLLECTION/Platform::Collections::Vector::GetView
- COLLECTION/Platform::Collections::Vector::IndexOf
- COLLECTION/Platform::Collections::Vector::InsertAt
- COLLECTION/Platform::Collections::Vector::ReplaceAll
- COLLECTION/Platform::Collections::Vector::RemoveAt
- COLLECTION/Platform::Collections::Vector::RemoveAtEnd
- COLLECTION/Platform::Collections::Vector::SetAt
- COLLECTION/Platform::Collections::Vector::Size
- COLLECTION/Platform::Collections::Vector::VectorChanged
dev_langs: C++
helpviewer_keywords: Vector Class (C++/Cx)
ms.assetid: aee8c076-9700-47c3-99b6-799fd3edb0ca
caps.latest.revision: "17"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 35299f80b85432286859ed76afdd7a599809f67f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="platformcollectionsvector-class"></a>Platform::Collections::Vector-Klasse
Stellt eine sequenzielle Auflistung von Objekten dar, auf die einzeln über einen Index zugegriffen werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <typename T, typename E>  
   ref class Vector sealed;  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Typ der im Vektorobjekt enthaltenen Elemente.  
  
 `E`  
 Gibt ein binäres Prädikat zum Testen der Übereinstimmung mit Werten des Typs `T`an. Der Standardwert ist `std::equal_to<T>`.  
  
### <a name="remarks"></a>Hinweise  
 Zulässige Typen sind:  
  
1.  Ganze Zahlen  
  
2.  Schnittstellenklasse ^  
  
3.  Öffentliche Referenzklasse^  
  
4.  value struct  
  
5.  Öffentliche Enumerationsklasse  
  
 Die Vektorklasse ist die konkrete C++ Implementierung der [Windows::Foundation::Collections::IVector](http://go.microsoft.com/fwlink/p/?LinkId=262410) -Schnittstelle.  
  
 Wenn Sie versuchen, einen Vector-Typ in einem öffentlichen Rückgabewert oder Parameter zu verwenden, wir der Compilerfehler C3986 ausgelöst. Sie können den Fehler beheben, indem Sie den Typ des Parameters oder des Rückgabewerts in [Windows::Foundation::Collections::IVector](http://go.microsoft.com/fwlink/p/?LinkId=262410)ändern. Weitere Informationen finden Sie unter [Auflistungen (C++/CX)](../cppcx/collections-c-cx.md).  
  
### <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Vector:: Vector](#ctor)|Initialisiert eine neue Instanz der Vector-Klasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Vector:: Append](#append)|Fügt das angegebene Element nach dem letzten Element im aktuellen Vektor ein.|  
|[Vector:: Clear](#clear)|Löscht alle Elemente im aktuellen Vector.|  
|[Vector:: First](#first)|Gibt einen Iterator zurück, der das erste Element im Vektor angibt.|  
|[Vector:: GetAt](#getat)|Ruft das Element des aktuellen Vector ab, das durch den angegebenen Index bezeichnet wird.|  
|[Vector:: getmany](#getmany)|Ruft eine Sequenz von Elementen vom aktuellen Vektor ab, die am angegebenen Index beginnt.|  
|[Vector:: GetView](#getview)|Gibt eine schreibgeschützte Ansicht eines Vektors zurück; also [Platform::Collections::VectorView](../cppcx/platform-collections-vectorview-class.md).|  
|[Vector:: IndexOf](#indexof)|Sucht das angegebene Element im aktuellen Vector und gibt, wenn es gefunden wurde, den Index des Elements zurück.|  
|[Vector:: InsertAt](#insertat)|Fügt das angegebene Element in den aktuellen Vector nach dem Element ein, das durch den angegebenen Index identifiziert wird.|  
|[Vector:: ReplaceAll](#replaceall)|Löscht die Elemente im aktuellen Vektor und fügt dann die Elemente aus dem angegebenen Array ein.|  
|[Vector:: RemoveAt](#removeat)|Löscht das Element, das durch den angegebenen Index von dem aktuellen Vektor identifiziert wird.|  
|[Vector:: removeatend](#removeatend)|Löscht das Element am Ende des aktuellen Vektors.|  
|[Vector:: SetAt](#setat)|Weist den angegebenen Wert dem Element im aktuellen Vektor zu, der vom angegebenen Index identifiziert wird.|  
|[Vector:: Size](#size)|Gibt die Anzahl von Elementen im aktuellen Vector-Objekt zurück.|  
  
### <a name="events"></a>Ereignisse  
  
|||  
|-|-|  
|Name|Beschreibung|  
|Ereignis [Windows::Foundation::Collection::VectorChangedEventHandler\<T > ^ VectorChanged](http://go.microsoft.com/fwlink/p/?LinkId=262644)|Tritt auf, wenn sich der Vektor ändert.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `Vector`  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** collection.h  
  
 **Namespace:** Platform::Collections  

## <a name="append"></a>Vector:: Append-Methode
Fügt das angegebene Element nach dem letzten Element im aktuellen Vektor ein.  
  
### <a name="syntax"></a>Syntax  
  
```    
virtual void Append(T item);  
```  
  
### <a name="parameters"></a>Parameter  
 `index`  
 Das Element, das in den Vektor eingefügt werden soll. Der Typ des `item` wird definiert, indem die *T* Typname.  
  


## <a name="clear"></a>Vector:: Clear-Methode
Löscht alle Elemente im aktuellen Vector.  
  
### <a name="syntax"></a>Syntax  
  
```    
virtual void Clear();  
```   


## <a name="first"></a>Vector:: First-Methode
Gibt einen Iterator zurück, der auf das erste Element im Vektor verweist.  
  
### <a name="syntax"></a>Syntax  
  
```  
  
virtual Windows::Foundation::Collections::IIterator <T>^ First();  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator, der auf das erste Element im Vektor verweist.  
  
### <a name="remarks"></a>Hinweise  
 Eine einfache Möglichkeit, den von First() zurückgegeben Iterator zu halten, den Rückgabewert einer Variablen zuzuweisen, die mit deklariert wird ist das **Auto** typableitungsschlüsselwort. Beispielsweise `auto x = myVector->First();`. Dieser Iterator kennt die Länge der Auflistung.  
  
 Wenn Sie ein Paar von Iteratoren zur Übergabe an eine STL-Funktion benötigen, verwenden Sie die freien-Funktionen [Collections:: begin](../cppcx/begin-function.md) und [Windows](../cppcx/end-function.md)  
  


## <a name="getat"></a>Vector:: GetAt-Methode
Ruft das Element des aktuellen Vector ab, das durch den angegebenen Index bezeichnet wird.  
  
### <a name="syntax"></a>Syntax  
  
```    
virtual T GetAt(unsigned int index);  
```  
  
### <a name="parameters"></a>Parameter  
 `index`  
 Eine nullbasierte, ganze Zahl ohne Vorzeichen, die ein bestimmtes Element im Vector-Objekt spezifiziert.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Element, das durch den `index`-Parameter spezifiziert wird. Der Elementtyp wird durch definiert die *T* Typname.  
  


## <a name="getmany"></a>Vector:: getmany-Methode
Ruft eine Sequenz von Elementen vom aktuellen Vektor ab, die am angegebenen Index beginnt, und kopiert sie in das vom Aufrufer reservierten Array.  
  
### <a name="syntax"></a>Syntax  
  
```    
virtual unsigned int GetMany(
    unsigned int startIndex, 
    Platform::WriteOnlyArray<T>^ dest);  
```  
  
### <a name="parameters"></a>Parameter  
 `startIndex`  
 Der nullbasierte Index des Anfangs der Elemente, die abgerufen werden sollen.  
  
 `dest`  
 Ein vom Aufrufer reserviertes Array von Elementen, die bei dem Element beginnen, das durch `startIndex` angegeben ist, und beim letzten Element im Vektor enden.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der abgerufenen Elemente.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist nicht für die direkte Verwendung durch Clientcode vorgesehen. Sie wird intern in verwendet das [To_vector-Funktion](../cppcx/to-vector-function.md) auf effiziente Konvertierung von Platform:: Std:: Vector-Instanzen zu ermöglichen.  
  


## <a name="getview"></a>Vector:: GetView-Methode
Gibt eine schreibgeschützte Ansicht eines Vektors zurück, das heißt, eine IVectorView.  
  
### <a name="syntax"></a>Syntax  
  
```    
Windows::Foundation::Collections::IVectorView<T>^ GetView();  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein IVectorView-Objekt.  
  


## <a name="indexof"></a>Vector:: IndexOf-Methode
Sucht das angegebene Element im aktuellen Vector und gibt, wenn es gefunden wurde, den Index des Elements zurück.  
  
### <a name="syntax"></a>Syntax  
  
```  
  
virtual bool IndexOf(T value, unsigned int* index);  
```  
  
### <a name="parameters"></a>Parameter  
 `value`  
 Das Element, das gesucht werden soll.  
  
 `index`  
 Der nullbasierte Index des Elements, wenn der Parameter `value` gefunden wurde, andernfalls 0.  
  
 Der `index`-Parameter ist 0, wenn das Element entweder das erste Element des Vektors ist oder wenn das Element nicht gefunden wurde. Wenn der Rückgabewert `true` ist, wurde das Element gefunden und es ist das erste Element; andernfalls wurde das Element nicht gefunden.  
  
### <a name="return-value"></a>Rückgabewert  
 `true` wenn das angegebene Element gefunden wurde, andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 IndexOf verwendet std::find_if, um das Element zu suchen. Benutzerdefinierte Elementtypen sollten deshalb den Operator == und != überladen, um die Übereinstimmungsvergleiche zu ermöglichen, die für "find_if" erforderlich sind.  
  


##  <a name="insertat"></a>Vector:: InsertAt-Methode
Fügt das angegebene Element in den aktuellen Vector nach dem Element ein, das durch den angegebenen Index identifiziert wird.  
  
### <a name="syntax"></a>Syntax  
  
```    
virtual void InsertAt(unsigned int index, T item)  
```  
  
### <a name="parameters"></a>Parameter  
 `index`  
 Eine nullbasierte, ganze Zahl ohne Vorzeichen, die ein bestimmtes Element im Vector-Objekt spezifiziert.  
  
 `item`  
 Ein Element, das nach dem durch `index` spezifizierten Elements in den Vector einzufügen ist. Der Typ des `item` wird definiert, indem die *T* Typname.  
  


## <a name="removeat"></a>Vector:: RemoveAt-Methode
Löscht das Element, das durch den angegebenen Index von dem aktuellen Vektor identifiziert wird.  
  
### <a name="syntax"></a>Syntax  
  
```    
virtual void RemoveAt(unsigned int index);  
```  
  
### <a name="parameters"></a>Parameter  
 `index`  
 Eine nullbasierte, ganze Zahl ohne Vorzeichen, die ein bestimmtes Element im Vector-Objekt spezifiziert.  
  


## <a name="removeatend"></a>Vector:: removeatend-Methode
Löscht das Element am Ende des aktuellen Vektors.  
  
### <a name="syntax"></a>Syntax  
  
```    
virtual void RemoveAtEnd();  
```  
  


## <a name="replaceall"></a>Vector:: ReplaceAll-Methode
Löscht die Elemente im aktuellen Vektor und fügt dann die Elemente aus dem angegebenen Array ein.  
  
### <a name="syntax"></a>Syntax  
  
```    
virtual void ReplaceAll(const ::Platform::Array<T>^ arr);  
```  
  
### <a name="parameters"></a>Parameter  
 `arr`  
 Ein Array von Objekten, deren Typ, indem definiert, die *T* Typname.  
  


## <a name="setat"></a>Vector:: SetAt-Methode
Weist den angegebenen Wert dem Element im aktuellen Vektor zu, der vom angegebenen Index identifiziert wird.  
  
### <a name="syntax"></a>Syntax  
  
```    
virtual void SetAt(unsigned int index, T item);  
```  
  
### <a name="parameters"></a>Parameter  
 `index`  
 Eine nullbasierte, ganze Zahl ohne Vorzeichen, die ein bestimmtes Element im Vector-Objekt spezifiziert.  
  
 `item`  
 Der dem angegebenen Element zuzuweisende Wert. Der Typ des `item` wird definiert, indem die *T* Typname.  
  


## <a name="size"></a>Vector:: size-Methode
Gibt die Anzahl von Elementen im aktuellen Vector-Objekt zurück.  
  
### <a name="syntax"></a>Syntax  
  
```    
virtual property unsigned int Size;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente im aktuellen Vector.  
  


## <a name="ctor"></a>Vector:: Vector-Konstruktor
Initialisiert eine neue Instanz der Vector-Klasse.  
  
### <a name="syntax"></a>Syntax  
  
```  
Vector();  
  
explicit Vector(unsigned int size);  
Vector( unsigned int size, T value);    
template <typename U> explicit Vector( const ::std::vector<U>& v);    
template <typename U> explicit Vector( std::vector<U>&& v);    

Vector( const T * ptr, unsigned int size);    
template <size_t N> explicit Vector(const T(&arr)[N]);    
template <size_t N> explicit Vector(const std::array<T, N>& a);   
explicit Vector(const Array<T>^ arr);  
  
template <typename InIt> Vector(InIt first, InIt last);   
Vector(std::initializer_list<T> il);  
```  
  
### <a name="parameters"></a>Parameter  
 eine  
 Ein [Std:: Array](../standard-library/array-class-stl.md) , die verwendet werden wird, um den Vector zu initialisieren.  
  
 eine  
 Ein [Platform:: Array](../cppcx/platform-array-class.md) , die verwendet werden wird, um den Vector zu initialisieren.  
  
 `InIt`  
 Der Typ einer Auflistung von Objekten, die verwendet werden, um den aktuelle Vector zu initialisieren.  
  
 il  
 Ein [Std:: initializer_list](../standard-library/initializer-list-class.md) von Objekten des Typs `T` , die verwendet werden wird, um den Vector zu initialisieren.  
  
 `N`  
 Die Anzahl von Elementen in einer Auflistung von Objekten, die verwendet wird, um den aktuellen Vector zu initialisieren.  
  
 `size`  
 Die Anzahl von Elementen im Vector.  
  
 `value`  
 Ein Wert, der verwendet wird, um die einzelnen Elemente im aktuellen Vector zu initialisieren.  
  
 `v`  
 Ein [Lvalues und Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md) zu einem [Std:: vector](../standard-library/vector-class.md) , wird verwendet, um den aktuellen Vector zu initialisieren.  
  
 `ptr`  
 Zeiger zu `std::vector`, der verwendet wird, um den aktuellen Vector zu initialisieren.  
  
 `arr`  
 Ein [Platform:: Array](../cppcx/platform-array-class.md) -Objekt, das verwendet wird, um den aktuellen Vector zu initialisieren.  
  
 `a`  
 Ein [Std:: Array](../standard-library/array-class-stl.md) -Objekt, das verwendet wird, um den aktuellen Vector zu initialisieren.  
  
 `first`  
 Das erste Element in einer Sequenz von Objekten, die verwendet werden, um den aktuellen Vector zu initialisieren. Der Typ des `first` übergeben wird, anhand der *eine perfekte Weiterleitung*. Weitere Informationen finden Sie unter [RValue-Verweisdeklarator: &&](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
 `last`  
 Das letzte Element in einer Sequenz von Objekten, die verwendet werden, um den aktuellen Vector zu initialisieren. Der Typ des `last` übergeben wird, anhand der *eine perfekte Weiterleitung*. Weitere Informationen finden Sie unter [RValue-Verweisdeklarator: &&](../cpp/rvalue-reference-declarator-amp-amp.md).  
  


  
## <a name="see-also"></a>Siehe auch  
 [Platform-Namespace](platform-namespace-c-cx.md)   
 [Erstellen von Windows-Runtime-Komponenten in C++](/MicrosoftDocs/windows-uwp/blob/docs/windows-apps-src/winrt-components/creating-windows-runtime-components-in-cpp.md)