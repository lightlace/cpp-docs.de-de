---
title: ComPtr-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/01/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr
- client/Microsoft::WRL::ComPtr::As
- client/Microsoft::WRL::ComPtr::AsIID
- client/Microsoft::WRL::ComPtr::AsWeak
- client/Microsoft::WRL::ComPtr::Attach
- client/Microsoft::WRL::ComPtr::ComPtr
- client/Microsoft::WRL::ComPtr::CopyTo
- client/Microsoft::WRL::ComPtr::Detach
- client/Microsoft::WRL::ComPtr::Get
- client/Microsoft::WRL::ComPtr::GetAddressOf
- client/Microsoft::WRL::ComPtr::InternalAddRef
- client/Microsoft::WRL::ComPtr::InternalRelease
- client/Microsoft::WRL::ComPtr::operator&
- client/Microsoft::WRL::ComPtr::operator->
- client/Microsoft::WRL::ComPtr::operator=
- client/Microsoft::WRL::ComPtr::operator==
- client/Microsoft::WRL::ComPtr::operator!=
- client/Microsoft::WRL::ComPtr::operator Microsoft::WRL::Details::BoolType
- client/Microsoft::WRL::ComPtr::ptr_
- client/Microsoft::WRL::ComPtr::ReleaseAndGetAddressOf
- client/Microsoft::WRL::ComPtr::Reset
- client/Microsoft::WRL::ComPtr::Swap
- client/Microsoft::WRL::ComPtr::~ComPtr
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::ComPtr class
- Microsoft::WRL::ComPtr::As method
- Microsoft::WRL::ComPtr::AsIID method
- Microsoft::WRL::ComPtr::AsWeak method
- Microsoft::WRL::ComPtr::Attach method
- Microsoft::WRL::ComPtr::ComPtr, constructor
- Microsoft::WRL::ComPtr::CopyTo method
- Microsoft::WRL::ComPtr::Detach method
- Microsoft::WRL::ComPtr::Get method
- Microsoft::WRL::ComPtr::GetAddressOf method
- Microsoft::WRL::ComPtr::InternalAddRef method
- Microsoft::WRL::ComPtr::InternalRelease method
- Microsoft::WRL::ComPtr::operator& operator
- Microsoft::WRL::ComPtr::operator-> operator
- Microsoft::WRL::ComPtr::operator= operator
- Microsoft::WRL::ComPtr::operator== operator
- Microsoft::WRL::ComPtr::operator!= operator
- Microsoft::WRL::ComPtr::operator Microsoft::WRL::Details::BoolType operator
- Microsoft::WRL::ComPtr::ptr_ data member
- Microsoft::WRL::ComPtr::ReleaseAndGetAddressOf method
- Microsoft::WRL::ComPtr::Reset method
- Microsoft::WRL::ComPtr::Swap method
- Microsoft::WRL::ComPtr::~ComPtr, destructor
ms.assetid: a6551902-6819-478a-8df7-b6f312ab1fb0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 12afcfe09335082f873d88e1aa825b4eee3a1ae2
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2018
ms.locfileid: "49163230"
---
# <a name="comptr-class"></a>ComPtr-Klasse

Erstellt einen *intelligenten Zeigertyp* , der die Schnittstelle darstellt, die vom Vorlagenparameter angegeben wird. `ComPtr` verwaltet automatisch einen Verweiszähler für den zugrunde liegenden Schnittstellenzeiger und gibt die Schnittstelle frei, wenn der Verweiszähler auf null geht.

## <a name="syntax"></a>Syntax

```cpp
template <typename T>
class ComPtr;

template<class T>
friend class ComPtr;
```

### <a name="parameters"></a>Parameter

*T*<br/>
Die Schnittstelle, die die `ComPtr` darstellt.

*U*<br/>
Eine Klasse, die aktuelle `ComPtr` ist ein Friend. (Die Vorlage, die diesen Parameter verwendet, ist geschützt.)

## <a name="remarks"></a>Hinweise

`ComPtr<>` deklariert einen Typ, der den zugrunde liegenden Schnittstellenzeiger darstellt. Verwenden Sie `ComPtr<>` auf eine Variable deklarieren und verwenden Sie dann auf den Pfeil-Memberzugriffsoperator (`->`) auf eine Schnittstellenmemberfunktion zuzugreifen.

Weitere Informationen zu intelligenten Zeigern finden Sie unter der Unterabschnitt "Intelligente Zeiger für COM" den [COM Coding Practices](/windows/desktop/LearnWin32/com-coding-practices) in der MSDN Library.

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

Name            | Beschreibung
--------------- | ---------------------------------------------------------------
`InterfaceType` | Ein Synonym für den vom angegebenen Typ der *T* Template-Parameter.

### <a name="public-constructors"></a>Öffentliche Konstruktoren

Name                             | Beschreibung
-------------------------------- | --------------------------------------------------------------------------------------------------------------------
[Comptr:: Comptr](#comptr)        | Initialisiert eine neue Instanz der `ComPtr`-Klasse. Überladungen stellen Standard-, Kopier-, Verschiebe- und Konvertierungskonstruktoren bereit.
[ComPtr:: ~ comptr-Objekt](#tilde-comptr) | Hebt die Initialisierung einer Instanz von `ComPtr`.

### <a name="public-methods"></a>Öffentliche Methoden

Name                                                      | Beschreibung
--------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[Comptr:: As](#as)                                         | Gibt eine `ComPtr` -Objekt, das die Schnittstelle, die durch den angegebenen Vorlagenparameter gekennzeichnet darstellt.
[Comptr:: Asiid](#asiid)                                   | Gibt eine `ComPtr` Objekt, das die Schnittstelle, die die angegebene Schnittstellen-ID identifizierte darstellt.
[Comptr:: Asweak](#asweak)                                 | Ruft einen schwachen Verweis (WeakReference) auf das aktuelle Objekt ab.
[Comptr:: Attach](#attach)                                 | Dies ordnet `ComPtr` mit dem Schnittstellentyp, der von der aktuellen Vorlagentyp-Parameter angegeben.
[Comptr:: CopyTo](#copyto)                                 | Kopiert die aktuelle oder angegebene-Schnittstelle, die zugeordneten `ComPtr` auf den angegebenen Ausgabezeiger.
[Comptr:: Detach](#detach)                                 | Hebt die Zuordnung dieser `ComPtr` von der Schnittstelle, die es darstellt.
[Comptr:: Get](#get)                                       | Ruft einen Zeiger auf die Schnittstelle, die mit dieser verknüpft ist `ComPtr`.
[Comptr:: Getaddressof](#getaddressof)                     | Ruft die Adresse der [Ptr_](#ptr) Datenmember, der einen Zeiger auf die von dieser Schnittstelle enthält `ComPtr`.
[Comptr:: Releaseandgetaddressof](#releaseandgetaddressof) | Gibt die Schnittstelle frei zugeordneten `ComPtr` und ruft dann die Adresse der [Ptr_](#ptr) Datenmember, der einen Zeiger auf die Schnittstelle enthält, die veröffentlicht wurde.
[ComPtr::Reset](#reset)                                   | Gibt alle Verweise für den Zeiger auf die Schnittstelle, die mit dieser verknüpft ist `ComPtr`.
[Comptr:: Swap](#swap)                                     | Tauscht die Schnittstelle, die von der aktuellen verwalteten `ComPtr` mit der Schnittstelle, die durch das angegebene verwaltete `ComPtr`.

### <a name="protected-methods"></a>Geschützte Methoden

Name                                        | Beschreibung
------------------------------------------- | --------------------------------------------------------------------------------
[Comptr:: Internaladdref](#internaladdref)   | Inkrementiert den Verweiszähler der Schnittstelle zugeordneten `ComPtr`.
[Comptr:: Internalrelease](#internalrelease) | Führt einen COM-Freigabe-Vorgang für die Schnittstelle zugeordneten `ComPtr`.

### <a name="public-operators"></a>Öffentliche Operatoren

Name                                                                                           | Beschreibung
---------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------
[Comptr:: &](#operator-ampersand)                                                       | Ruft die Adresse des aktuellen `ComPtr`.
[Comptr:: ->](#operator-arrow)                                                          | Ruft einen Zeiger auf den Typ ab, der durch den aktuellen Vorlagenparameter angegeben ist.
[Comptr:: =](#operator-assign)                                                          | Weist einen Wert mit dem aktuellen `ComPtr`.
[Comptr:: ==](#operator-equality)                                                       | Gibt an, ob zwei `ComPtr`-Objekte gleich sind.
[Comptr::! =](#operator-inequality)                                                     | Gibt an, ob zwei `ComPtr`-Objekte ungleich sind.
[Comptr:: booltype](#operator-microsoft-wrl-details-booltype) | Gibt an, ob eine `ComPtr` die Objektlebensdauer einer Schnittstelle verwaltet.

### <a name="protected-data-members"></a>Geschützte Datenmember

name                 | Beschreibung
-------------------- | ------------------------------------------------------------------------------------------
[Comptr:: Ptr_](#ptr) | Enthält einen Zeiger auf die Schnittstelle, die zugeordnet wird, und das von diesem verwaltet `ComPtr`.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`ComPtr`

## <a name="requirements"></a>Anforderungen

**Header:** client.h

**Namespace:** Microsoft::WRL

## <a name="tilde-comptr"></a>ComPtr:: ~ comptr-Objekt

Hebt die Initialisierung einer Instanz von `ComPtr`.

```cpp
WRL_NOTHROW ~ComPtr();
```

## <a name="as"></a>Comptr:: As

Gibt eine `ComPtr` -Objekt, das die Schnittstelle, die durch den angegebenen Vorlagenparameter gekennzeichnet darstellt.

```cpp
template<typename U>
HRESULT As(
   _Out_ ComPtr<U>* p
) const;

template<typename U>
HRESULT As(
   _Out_ Details::ComPtrRef<ComPtr<U>> p
) const;
```

### <a name="parameters"></a>Parameter

*U*<br/>
Die Schnittstelle, die vom Parameter dargestellt werden *p*.

*p*<br/>
Ein `ComPtr` Objekt, das vom Parameter angegebene Schnittstelle darstellt *U*. Parameter *p* muss nicht mit dem aktuellen verweisen `ComPtr` Objekt.

### <a name="remarks"></a>Hinweise

Die erste Vorlage ist die Form, die Sie in Ihrem Code verwenden sollten. Die zweite Vorlage ist eine interne Hilfsspezialisierung, die C++-Sprachfeatures unterstützt, wie etwa das Schlüsselwort [auto](../cpp/auto-cpp.md) zur Typableitung.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.

## <a name="asiid"></a>Comptr:: Asiid

Gibt eine `ComPtr` Objekt, das die Schnittstelle, die die angegebene Schnittstellen-ID identifizierte darstellt.

```cpp
WRL_NOTHROW HRESULT AsIID(
   REFIID riid,
   _Out_ ComPtr<IUnknown>* p
) const;
```

### <a name="parameters"></a>Parameter

*riid*<br/>
Eine Schnittstellen-ID.

*p*<br/>
Wenn das Objekt eine Schnittstelle verfügt, deren ID gleich *Riid*, ein doppelt indirekter Zeiger auf die angegebene Schnittstelle die *Riid* Parameter ist, andernfalls ein Zeiger auf `IUnknown`.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.

## <a name="asweak"></a>Comptr:: Asweak

Ruft einen schwachen Verweis (WeakReference) auf das aktuelle Objekt ab.

```cpp
HRESULT AsWeak(
   _Out_ WeakRef* pWeakRef
);
```

### <a name="parameters"></a>Parameter

*pWeakRef*<br/>
Wenn dieser Vorgang abgeschlossen ist, einen Zeiger auf einen schwachen Verweis-Objekt.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.

## <a name="attach"></a>Comptr:: Attach

Dies ordnet `ComPtr` mit dem Schnittstellentyp, der von der aktuellen Vorlagentyp-Parameter angegeben.

```cpp
void Attach(
   _In_opt_ InterfaceType* other
);
```

### <a name="parameters"></a>Parameter

*other*<br/>
Ein Schnittstellentyp ist.

## <a name="comptr"></a>Comptr:: Comptr

Initialisiert eine neue Instanz der `ComPtr`-Klasse. Überladungen stellen Standard-, Kopier-, Verschiebe- und Konvertierungskonstruktoren bereit.

```cpp
WRL_NOTHROW ComPtr();
WRL_NOTHROW ComPtr(
   decltype(__nullptr)  
);
template<class U>
WRL_NOTHROW ComPtr(
   _In_opt_ U *other
);
WRL_NOTHROW ComPtr(
   const ComPtr& other
);
template<class U>
WRL_NOTHROW ComPtr(
   const ComPtr<U> &other,
   typename ENABLE_IF<__is_convertible_to(U*,
   T*),
   void *>;
WRL_NOTHROW ComPtr(
   _Inout_ ComPtr &&other
);
template<class U>
WRL_NOTHROW ComPtr(
   _Inout_ ComPtr<U>&& other,
   typename ENABLE_IF<__is_convertible_to(U*,
   T*),
   void *>;
```

### <a name="parameters"></a>Parameter

*U*<br/>
Der Typ des der *andere* Parameter.

*other*<br/>
Ein Objekt des Typs *U*.

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

Der erste Konstruktor ist der Standardkonstruktor, der implizit ein leeres Objekt erstellt. Gibt an, der zweite Konstruktor [__nullptr](../windows/nullptr-cpp-component-extensions.md), die explizit erstellt ein leeres Objekt.

Der dritte Konstruktor erstellt ein Objekt aus dem Objekt, das durch einen Zeiger angegeben.

Die vierten und fünften Konstruktoren sind Kopierkonstruktoren Der fünfte Konstruktor kopiert ein Objekt aus, wenn es auf den aktuellen Typ konvertiert werden kann.

Die sechsten und siebten Konstruktoren sind Move-Konstruktoren. Der siebte Konstruktor verschiebt ein Objekt aus, wenn es auf den aktuellen Typ konvertiert werden kann.

## <a name="copyto"></a>Comptr:: CopyTo

Kopiert die aktuelle oder angegebene-Schnittstelle, die zugeordneten `ComPtr` an den angegebenen Zeiger.

```cpp
HRESULT CopyTo(
   _Deref_out_ InterfaceType** ptr
);

HRESULT CopyTo(
   REFIID riid,
   _Deref_out_ void** ptr
) const;

template<typename U>
HRESULT CopyTo(
   _Deref_out_ U** ptr
) const;
```

### <a name="parameters"></a>Parameter

*U*<br/>
Ein Typname.

*ptr*<br/>
Wenn dieser Vorgang abgeschlossen ist, einen Zeiger auf die angeforderte Schnittstelle.

*riid*<br/>
Eine Schnittstellen-ID.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das gibt an, warum das implizite `QueryInterface` Fehler beim Vorgang.

### <a name="remarks"></a>Hinweise

Die erste Funktion gibt eine Kopie eines Zeigers auf die Schnittstelle zugeordneten `ComPtr`. Diese Funktion gibt stets S_OK zurück.

Die zweite Funktion führt eine `QueryInterface` Vorgang für die Schnittstelle zugeordneten `ComPtr` für die angegebene Schnittstelle die *Riid* Parameter.

Die dritte Funktion führt eine `QueryInterface` Vorgang für die Schnittstelle zugeordneten `ComPtr` für die zugrunde liegenden Schnittstelle die *U* Parameter.

## <a name="detach"></a>Comptr:: Detach

Hebt die Zuordnung dieser `ComPtr` Objekt von der Schnittstelle, die es darstellt.

```cpp
T* Detach();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die Schnittstelle, die von diesem dargestellt wurde `ComPtr` Objekt.

## <a name="get"></a>Comptr:: Get

Ruft einen Zeiger auf die Schnittstelle, die mit dieser verknüpft ist `ComPtr`.

```cpp
T* Get() const;
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf die Schnittstelle, die mit dieser verknüpft ist `ComPtr`.

## <a name="getaddressof"></a>Comptr:: Getaddressof

Ruft die Adresse der [Ptr_](#ptr) Datenmember, der einen Zeiger auf die von dieser Schnittstelle enthält `ComPtr`.

```cpp
T* const* GetAddressOf() const;
T** GetAddressOf();
```

### <a name="return-value"></a>Rückgabewert

Die Adresse einer Variablen.

## <a name="internaladdref"></a>Comptr:: Internaladdref

Inkrementiert den Verweiszähler der Schnittstelle zugeordneten `ComPtr`.

```cpp
void InternalAddRef() const;
```

### <a name="remarks"></a>Hinweise

Diese Methode ist geschützt.

## <a name="internalrelease"></a>Comptr:: Internalrelease

Führt einen COM-Freigabe-Vorgang für die Schnittstelle zugeordneten `ComPtr`.

```cpp
void InternalRelease();
```

### <a name="remarks"></a>Hinweise

Diese Methode ist geschützt.

## <a name="operator-ampersand"></a>Comptr::&amp;

Gibt die Schnittstelle frei zugeordneten `ComPtr` -Objekt und ruft dann die Adresse der `ComPtr` Objekt.

```cpp
Details::ComPtrRef<WeakRef> operator&()

const Details::ComPtrRef<const WeakRef> operator&() const
```

### <a name="return-value"></a>Rückgabewert

Einen schwachen Verweis auf das aktuelle `ComPtr`.

### <a name="remarks"></a>Hinweise

Diese Methode unterscheidet sich von [comptr:: Getaddressof](#getaddressof) , gibt diese Methode einen Verweis auf den Schnittstellenzeiger auf. Verwendung `ComPtr::GetAddressOf` Wenn muss die Adresse des Schnittstellenzeigers, jedoch nicht diese Schnittstelle freigeben möchten.

## <a name="operator-arrow"></a>Comptr::-&gt;

Ruft einen Zeiger auf den Typ ab, der durch den aktuellen Vorlagenparameter angegeben ist.

```cpp
WRL_NOTHROW Microsoft::WRL::Details::RemoveIUnknown<InterfaceType>* operator->() const;
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf den Typ, von der aktuellen vorlagentypname angegeben.

### <a name="remarks"></a>Hinweise

Diese Hilfsfunktion entfernt unnötigen Mehraufwand verursacht werden, die STDMETHOD-Makro. Diese Funktion macht `IUnknown` Typen `private` anstelle von `virtual`.

## <a name="operator-assign"></a>Comptr:: =

Weist einen Wert mit dem aktuellen `ComPtr`.

```cpp
WRL_NOTHROW ComPtr& operator=(
   decltype(__nullptr)  
);
WRL_NOTHROW ComPtr& operator=(
   _In_opt_ T *other
);
template <typename U>
WRL_NOTHROW ComPtr& operator=(
   _In_opt_ U *other
);
WRL_NOTHROW ComPtr& operator=(
   const ComPtr &other
);
template<class U>
WRL_NOTHROW ComPtr& operator=(
   const ComPtr<U>& other
);
WRL_NOTHROW ComPtr& operator=(
   _Inout_ ComPtr &&other
);
template<class U>
WRL_NOTHROW ComPtr& operator=(
   _Inout_ ComPtr<U>&& other
);
```

### <a name="parameters"></a>Parameter

*U*<br/>
Eine Klasse.

*other*<br/>
Ein Zeiger, Verweis oder Rvalue-Verweis auf einen Typ oder eine andere `ComPtr`.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das aktuelle `ComPtr`.

### <a name="remarks"></a>Hinweise

Die erste Version dieses Operators weist einen leeren Wert der aktuellen `ComPtr`.

In der zweiten Version, ist der Zuweisen von Schnittstellenzeiger nicht identisch mit dem aktuellen `ComPtr` -Schnittstellenzeiger, der zweite Schnittstellenzeiger wird zugewiesen, mit dem aktuellen `ComPtr`.

In der dritten Version erhält der zuweisen Schnittstellenzeiger mit dem aktuellen `ComPtr`.

In der vierten Version ist der Schnittstellenzeiger des zuweisen Werts nicht identisch mit dem aktuellen `ComPtr` -Schnittstellenzeiger, der zweite Schnittstellenzeiger wird zugewiesen, mit dem aktuellen `ComPtr`.

Die fünfte Version ist ein Operator kopieren. Ein Verweis auf eine `ComPtr` zugewiesen ist, mit dem aktuellen `ComPtr`.

Die sechste Version ist ein Copy-Operator, der verwendet die move-Semantik; Ein Rvalue-Verweis auf eine `ComPtr` wenn keinerlei statisch ist, umgewandelt, und klicken Sie dann auf den aktuellen zugewiesen `ComPtr`.

Die siebte Version ist ein Copy-Operator, der verwendet die move-Semantik; Ein Rvalue-Verweis auf eine `ComPtr` des Typs *U* ist statische dann umgewandelt und mit dem aktuellen zugewiesen `ComPtr`.

## <a name="operator-equality"></a>Comptr:: ==

Gibt an, ob zwei `ComPtr`-Objekte gleich sind.

```cpp
bool operator==(
   const ComPtr<T>& a,
   const ComPtr<U>& b
);

bool operator==(
   const ComPtr<T>& a,
   decltype(__nullptr)  
);

bool operator==(
   decltype(__nullptr),
   const ComPtr<T>& a
);
```

### <a name="parameters"></a>Parameter

*a*<br/>
Ein Verweis auf ein `ComPtr`-Objekt.

*b*<br/>
Ein Verweis auf einen anderen `ComPtr` Objekt.

### <a name="return-value"></a>Rückgabewert

Der erste Operator ergibt **"true"** Wenn Objekt *eine* Objekt entspricht *b*ist, andernfalls **"false"**.

Führen Sie die zweite und dritte Operator **"true"** Wenn Objekt *eine* gleich **"nullptr"** ist, andernfalls **"false"**.

## <a name="operator-inequality"></a>Comptr::! =

Gibt an, ob zwei `ComPtr`-Objekte ungleich sind.

```cpp
bool operator!=(
   const ComPtr<T>& a,
   const ComPtr<U>& b
);

bool operator!=(
   const ComPtr<T>& a,
   decltype(__nullptr)  
);

bool operator!=(
   decltype(__nullptr),
   const ComPtr<T>& a
);
```

### <a name="parameters"></a>Parameter

*a*<br/>
Ein Verweis auf ein `ComPtr`-Objekt.

*b*<br/>
Ein Verweis auf einen anderen `ComPtr` Objekt.

### <a name="return-value"></a>Rückgabewert

Der erste Operator ergibt **"true"** Wenn Objekt *eine* ist nicht gleich Objekt *b*ist, andernfalls **"false"**.

Führen Sie die zweite und dritte Operator **"true"** Wenn Objekt *eine* ist nicht gleich **"nullptr"** ist, andernfalls **"false"**.

## <a name="operator-microsoft-wrl-details-booltype"></a>Comptr:: booltype

Gibt an, ob eine `ComPtr` die Objektlebensdauer einer Schnittstelle verwaltet.

```cpp
WRL_NOTHROW operator Microsoft::WRL::Details::BoolType() const;
```

### <a name="return-value"></a>Rückgabewert

Wenn eine Schnittstelle zugeordnet ist `ComPtr`, die Adresse der [boolstruct::](../windows/boolstruct-member-data-member.md) -Datenmember ist, andernfalls **"nullptr"**.

## <a name="ptr"></a>Comptr:: Ptr_

Enthält einen Zeiger auf die Schnittstelle, die zugeordnet wird, und das von diesem verwaltet `ComPtr`.

```cpp
InterfaceType *ptr_;
```

### <a name="remarks"></a>Hinweise

`ptr_` eine interne, geschützte Daten gehört.

## <a name="releaseandgetaddressof"></a>Comptr:: Releaseandgetaddressof

Gibt die Schnittstelle frei zugeordneten `ComPtr` und ruft dann die Adresse der [Ptr_](#ptr) Datenmember, der einen Zeiger auf die Schnittstelle enthält, die veröffentlicht wurde.

```cpp
T** ReleaseAndGetAddressOf();
```

### <a name="return-value"></a>Rückgabewert

Die Adresse der [Ptr_](#ptr) Datenmember dieses `ComPtr`.

## <a name="reset"></a>ComPtr::Reset

Gibt alle Verweise für den Zeiger auf die Schnittstelle, die mit dieser verknüpft ist `ComPtr`.

```cpp
unsigned long Reset();
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der freigegeben Verweise, sofern vorhanden.

## <a name="swap"></a>Comptr:: Swap

Tauscht die Schnittstelle, die von der aktuellen verwalteten `ComPtr` mit der Schnittstelle, die durch das angegebene verwaltete `ComPtr`.

```cpp
void Swap(
   _Inout_ ComPtr&& r
);

void Swap(
   _Inout_ ComPtr& r
);
```

### <a name="parameters"></a>Parameter

*r*<br/>
Ein `ComPtr`.

