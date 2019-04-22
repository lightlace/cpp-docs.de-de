---
title: ComPtr-Klasse
ms.date: 10/01/2018
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
ms.openlocfilehash: 9e5b2419f070ead17e72b1642f510f74bad8260e
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58784385"
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
[ComPtr::ComPtr](#comptr)        | Initialisiert eine neue Instanz der `ComPtr`-Klasse. Überladungen stellen Standard-, Kopier-, Verschiebe- und Konvertierungskonstruktoren bereit.
[ComPtr::~ComPtr](#tilde-comptr) | Hebt die Initialisierung einer Instanz von `ComPtr`.

### <a name="public-methods"></a>Öffentliche Methoden

Name                                                      | Beschreibung
--------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[ComPtr::As](#as)                                         | Gibt eine `ComPtr` -Objekt, das die Schnittstelle, die durch den angegebenen Vorlagenparameter gekennzeichnet darstellt.
[ComPtr::AsIID](#asiid)                                   | Gibt eine `ComPtr` Objekt, das die Schnittstelle, die die angegebene Schnittstellen-ID identifizierte darstellt.
[ComPtr::AsWeak](#asweak)                                 | Ruft einen schwachen Verweis (WeakReference) auf das aktuelle Objekt ab.
[ComPtr::Attach](#attach)                                 | Dies ordnet `ComPtr` mit dem Schnittstellentyp, der von der aktuellen Vorlagentyp-Parameter angegeben.
[ComPtr::CopyTo](#copyto)                                 | Kopiert die aktuelle oder angegebene-Schnittstelle, die zugeordneten `ComPtr` auf den angegebenen Ausgabezeiger.
[ComPtr::Detach](#detach)                                 | Hebt die Zuordnung dieser `ComPtr` von der Schnittstelle, die es darstellt.
[ComPtr::Get](#get)                                       | Ruft einen Zeiger auf die Schnittstelle, die mit dieser verknüpft ist `ComPtr`.
[ComPtr::GetAddressOf](#getaddressof)                     | Ruft die Adresse der [Ptr_](#ptr) Datenmember, der einen Zeiger auf die von dieser Schnittstelle enthält `ComPtr`.
[ComPtr::ReleaseAndGetAddressOf](#releaseandgetaddressof) | Gibt die Schnittstelle frei zugeordneten `ComPtr` und ruft dann die Adresse der [Ptr_](#ptr) Datenmember, der einen Zeiger auf die Schnittstelle enthält, die veröffentlicht wurde.
[ComPtr::Reset](#reset)                                   | Gibt alle Verweise für den Zeiger auf die Schnittstelle, die mit dieser verknüpft ist `ComPtr`.
[ComPtr::Swap](#swap)                                     | Tauscht die Schnittstelle, die von der aktuellen verwalteten `ComPtr` mit der Schnittstelle, die durch das angegebene verwaltete `ComPtr`.

### <a name="protected-methods"></a>Geschützte Methoden

Name                                        | Beschreibung
------------------------------------------- | --------------------------------------------------------------------------------
[ComPtr::InternalAddRef](#internaladdref)   | Inkrementiert den Verweiszähler der Schnittstelle zugeordneten `ComPtr`.
[ComPtr::InternalRelease](#internalrelease) | Führt einen COM-Freigabe-Vorgang für die Schnittstelle zugeordneten `ComPtr`.

### <a name="public-operators"></a>Öffentliche Operatoren

Name                                                                                           | Beschreibung
---------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------
[ComPtr::operator&](#operator-ampersand)                                                       | Ruft die Adresse des aktuellen `ComPtr`.
[ComPtr::operator->](#operator-arrow)                                                          | Ruft einen Zeiger auf den Typ ab, der durch den aktuellen Vorlagenparameter angegeben ist.
[ComPtr::operator=](#operator-assign)                                                          | Weist einen Wert mit dem aktuellen `ComPtr`.
[ComPtr::operator==](#operator-equality)                                                       | Gibt an, ob zwei `ComPtr`-Objekte gleich sind.
[ComPtr::operator!=](#operator-inequality)                                                     | Gibt an, ob zwei `ComPtr`-Objekte ungleich sind.
[ComPtr::operator Microsoft::WRL::Details::BoolType](#operator-microsoft-wrl-details-booltype) | Gibt an, ob eine `ComPtr` die Objektlebensdauer einer Schnittstelle verwaltet.

### <a name="protected-data-members"></a>Geschützte Datenmember

Name                 | Beschreibung
-------------------- | ------------------------------------------------------------------------------------------
[ComPtr::ptr_](#ptr) | Enthält einen Zeiger auf die Schnittstelle, die zugeordnet wird, und das von diesem verwaltet `ComPtr`.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`ComPtr`

## <a name="requirements"></a>Anforderungen

**Header:** client.h

**Namespace:** Microsoft::WRL

## <a name="tilde-comptr"></a>ComPtr::~ComPtr

Hebt die Initialisierung einer Instanz von `ComPtr`.

```cpp
WRL_NOTHROW ~ComPtr();
```

## <a name="as"></a>ComPtr::As

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

Die erste Vorlage ist die Form, die Sie in Ihrem Code verwenden sollten. Die zweite Vorlage ist eine interne Hilfsspezialisierung, die C++-Sprachfeatures unterstützt, wie etwa das Schlüsselwort [auto](../../cpp/auto-cpp.md) zur Typableitung.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.

## <a name="asiid"></a>ComPtr::AsIID

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

## <a name="asweak"></a>ComPtr::AsWeak

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

## <a name="attach"></a>ComPtr::Attach

Dies ordnet `ComPtr` mit dem Schnittstellentyp, der von der aktuellen Vorlagentyp-Parameter angegeben.

```cpp
void Attach(
   _In_opt_ InterfaceType* other
);
```

### <a name="parameters"></a>Parameter

*other*<br/>
Ein Schnittstellentyp ist.

## <a name="comptr"></a>ComPtr::ComPtr

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

Der erste Konstruktor ist der Standardkonstruktor, der implizit ein leeres Objekt erstellt. Gibt an, der zweite Konstruktor [__nullptr](../../extensions/nullptr-cpp-component-extensions.md), die explizit erstellt ein leeres Objekt.

Der dritte Konstruktor erstellt ein Objekt aus dem Objekt, das durch einen Zeiger angegeben.

Die vierten und fünften Konstruktoren sind Kopierkonstruktoren Der fünfte Konstruktor kopiert ein Objekt aus, wenn es auf den aktuellen Typ konvertiert werden kann.

Die sechsten und siebten Konstruktoren sind Move-Konstruktoren. Der siebte Konstruktor verschiebt ein Objekt aus, wenn es auf den aktuellen Typ konvertiert werden kann.

## <a name="copyto"></a>ComPtr::CopyTo

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

## <a name="detach"></a>ComPtr::Detach

Hebt die Zuordnung dieser `ComPtr` Objekt von der Schnittstelle, die es darstellt.

```cpp
T* Detach();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die Schnittstelle, die von diesem dargestellt wurde `ComPtr` Objekt.

## <a name="get"></a>ComPtr::Get

Ruft einen Zeiger auf die Schnittstelle, die mit dieser verknüpft ist `ComPtr`.

```cpp
T* Get() const;
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf die Schnittstelle, die mit dieser verknüpft ist `ComPtr`.

## <a name="getaddressof"></a>ComPtr::GetAddressOf

Ruft die Adresse der [Ptr_](#ptr) Datenmember, der einen Zeiger auf die von dieser Schnittstelle enthält `ComPtr`.

```cpp
T* const* GetAddressOf() const;
T** GetAddressOf();
```

### <a name="return-value"></a>Rückgabewert

Die Adresse einer Variablen.

## <a name="internaladdref"></a>ComPtr::InternalAddRef

Inkrementiert den Verweiszähler der Schnittstelle zugeordneten `ComPtr`.

```cpp
void InternalAddRef() const;
```

### <a name="remarks"></a>Hinweise

Diese Methode ist geschützt.

## <a name="internalrelease"></a>ComPtr::InternalRelease

Führt einen COM-Freigabe-Vorgang für die Schnittstelle zugeordneten `ComPtr`.

```cpp
void InternalRelease();
```

### <a name="remarks"></a>Hinweise

Diese Methode ist geschützt.

## <a name="operator-ampersand"></a>ComPtr::operator&amp;

Gibt die Schnittstelle frei zugeordneten `ComPtr` -Objekt und ruft dann die Adresse der `ComPtr` Objekt.

```cpp
Details::ComPtrRef<WeakRef> operator&()

const Details::ComPtrRef<const WeakRef> operator&() const
```

### <a name="return-value"></a>Rückgabewert

Einen schwachen Verweis auf das aktuelle `ComPtr`.

### <a name="remarks"></a>Hinweise

Diese Methode unterscheidet sich von [comptr:: Getaddressof](#getaddressof) , gibt diese Methode einen Verweis auf den Schnittstellenzeiger auf. Verwendung `ComPtr::GetAddressOf` Wenn muss die Adresse des Schnittstellenzeigers, jedoch nicht diese Schnittstelle freigeben möchten.

## <a name="operator-arrow"></a>ComPtr::operator-&gt;

Ruft einen Zeiger auf den Typ ab, der durch den aktuellen Vorlagenparameter angegeben ist.

```cpp
WRL_NOTHROW Microsoft::WRL::Details::RemoveIUnknown<InterfaceType>* operator->() const;
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf den Typ, von der aktuellen vorlagentypname angegeben.

### <a name="remarks"></a>Hinweise

Diese Hilfsfunktion entfernt unnötigen Mehraufwand verursacht werden, die STDMETHOD-Makro. Diese Funktion macht `IUnknown` Typen `private` anstelle von `virtual`.

## <a name="operator-assign"></a>ComPtr::operator=

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

## <a name="operator-equality"></a>ComPtr::operator==

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

Der erste Operator ergibt `true` Wenn Objekt *eine* Objekt entspricht *b*ist, andernfalls `false`.

Führen Sie die zweite und dritte Operator `true` Wenn Objekt *eine* gleich `nullptr`ist, andernfalls `false`.

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

Der erste Operator ergibt `true` Wenn Objekt *eine* ist nicht gleich Objekt *b*ist, andernfalls `false`.

Führen Sie die zweite und dritte Operator `true` Wenn Objekt *eine* ist nicht gleich `nullptr`ist, andernfalls `false`.

## <a name="operator-microsoft-wrl-details-booltype"></a>ComPtr::operator Microsoft::WRL::Details::BoolType

Gibt an, ob eine `ComPtr` die Objektlebensdauer einer Schnittstelle verwaltet.

```cpp
WRL_NOTHROW operator Microsoft::WRL::Details::BoolType() const;
```

### <a name="return-value"></a>Rückgabewert

Wenn eine Schnittstelle zugeordnet ist `ComPtr`, die Adresse der [boolstruct::](boolstruct-structure.md#member) -Datenmember ist, andernfalls `nullptr`.

## <a name="ptr"></a>ComPtr::ptr_

Enthält einen Zeiger auf die Schnittstelle, die zugeordnet wird, und das von diesem verwaltet `ComPtr`.

```cpp
InterfaceType *ptr_;
```

### <a name="remarks"></a>Hinweise

`ptr_` eine interne, geschützte Daten gehört.

## <a name="releaseandgetaddressof"></a>ComPtr::ReleaseAndGetAddressOf

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

## <a name="swap"></a>ComPtr::Swap

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

