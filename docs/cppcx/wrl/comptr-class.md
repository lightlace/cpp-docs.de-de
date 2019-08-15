---
title: ComPtr-Klasse
ms.date: 07/26/2019
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
ms.openlocfilehash: 1e20a991c8f32027aeea6a17df0534aa6e1c2c43
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498412"
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
Die-Schnittstelle `ComPtr` , die der darstellt.

*U*<br/>
Eine Klasse, zu der der `ComPtr` aktuelle ein Freund ist. (Die Vorlage, die diesen Parameter verwendet, ist geschützt.)

## <a name="remarks"></a>Hinweise

`ComPtr<>`deklariert einen Typ, der den zugrunde liegenden Schnittstellen Zeiger darstellt. Verwenden `ComPtr<>` Sie, um eine Variable zu deklarieren, und verwenden Sie dann den`->`Pfeil Element Zugriffs Operator (), um auf eine Schnittstellenmember-Funktion zuzugreifen.

Weitere Informationen zu intelligenten Zeigern finden Sie im Abschnitt "com Intelligent Pointer" des Themas [com-Codierungspraktiken](/windows/win32/LearnWin32/com-coding-practices) in der MSDN Library.

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

Name            | Beschreibung
--------------- | ---------------------------------------------------------------
`InterfaceType` | Ein Synonym für den Typ, der vom *T* -Vorlagen Parameter angegeben wird.

### <a name="public-constructors"></a>Öffentliche Konstruktoren

Name                             | Beschreibung
-------------------------------- | --------------------------------------------------------------------------------------------------------------------
[ComPtr::ComPtr](#comptr)        | Initialisiert eine neue Instanz der `ComPtr`-Klasse. Überladungen stellen Standard-, Kopier-, Verschiebe- und Konvertierungskonstruktoren bereit.
[ComPtr::~ComPtr](#tilde-comptr) | Deinitialisiert eine Instanz von `ComPtr`.

### <a name="public-methods"></a>Öffentliche Methoden

Name                                                      | Beschreibung
--------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[Comptr:: As](#as)                                         | Gibt ein `ComPtr` -Objekt zurück, das die durch den angegebenen Vorlagen Parameter identifizierte Schnittstelle darstellt.
[Comptr:: asiid](#asiid)                                   | Gibt ein `ComPtr` -Objekt zurück, das die durch die angegebene Schnittstellen-ID identifizierte Schnittstelle darstellt.
[ComPtr::AsWeak](#asweak)                                 | Ruft einen schwachen Verweis (WeakReference) auf das aktuelle Objekt ab.
[Comptr:: Attach](#attach)                                 | Ordnet diesen `ComPtr` dem Schnittstellentyp zu, der durch den aktuellen Template Type-Parameter angegeben wird.
[ComPtr::CopyTo](#copyto)                                 | Kopiert die aktuelle oder angegebene-Schnittstelle, `ComPtr` die diesem zugeordnet ist, in den angegebenen Ausgabe Zeiger.
[ComPtr::Detach](#detach)                                 | Trennt dieses `ComPtr` von der-Schnittstelle, die es darstellt.
[ComPtr::Get](#get)                                       | Ruft einen Zeiger auf die-Schnittstelle ab, die diesem `ComPtr`zugeordnet ist.
[ComPtr::GetAddressOf](#getaddressof)                     | Ruft die Adresse des [ptr_](#ptr) -Datenmembers ab, der einen Zeiger auf die-Schnittstelle enthält, `ComPtr`die von diesem dargestellt wird.
[ComPtr::ReleaseAndGetAddressOf](#releaseandgetaddressof) | Gibt die-Schnittstelle frei `ComPtr` , die diesem zugeordnet ist, und ruft dann die Adresse des [ptr_](#ptr) -Datenmembers ab, der einen Zeiger auf die-Schnittstelle enthält, die freigegeben wurde.
[ComPtr::Reset](#reset)                                   | Gibt alle Verweise für den Zeiger auf die-Schnittstelle frei, die `ComPtr`diesem zugeordnet ist.
[Comptr:: Swap](#swap)                                     | Tauscht die Schnittstelle, die vom `ComPtr` aktuellen verwaltet wird, mit der vom `ComPtr`angegebenen verwalteten Schnittstelle aus.

### <a name="protected-methods"></a>Geschützte Methoden

Name                                        | Beschreibung
------------------------------------------- | --------------------------------------------------------------------------------
[Comptr:: internaladressf](#internaladdref)   | Inkremente den Verweis Zähler der Schnittstelle, die `ComPtr`diesem zugeordnet ist.
[Comptr:: internalrelease](#internalrelease) | Führt einen com-Releasevorgang für die Schnittstelle `ComPtr`aus, die diesem zugeordnet ist.

### <a name="public-operators"></a>Öffentliche Operatoren

Name                                                                                           | Beschreibung
---------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------
[Comptr:: Operator-&](#operator-ampersand)                                                       | Ruft die Adresse des aktuellen `ComPtr`ab.
[Comptr:: Operator->](#operator-arrow)                                                          | Ruft einen Zeiger auf den Typ ab, der durch den aktuellen Vorlagenparameter angegeben ist.
[ComPtr::operator=](#operator-assign)                                                          | Weist dem aktuellen `ComPtr`einen Wert zu.
[Comptr:: Operator = =](#operator-equality)                                                       | Gibt an, ob zwei `ComPtr`-Objekte gleich sind.
[Comptr:: Operator! =](#operator-inequality)                                                     | Gibt an, ob zwei `ComPtr`-Objekte ungleich sind.
[Comptr:: Operator Microsoft:: WRL::D etails:: booltype](#operator-microsoft-wrl-details-booltype) | Gibt an, ob eine `ComPtr` die Objekt Lebensdauer einer Schnittstelle verwaltet.

### <a name="protected-data-members"></a>Geschützte Datenmember

Name                 | Beschreibung
-------------------- | ------------------------------------------------------------------------------------------
[ComPtr::ptr_](#ptr) | Enthält einen Zeiger auf die-Schnittstelle, die dieser zugeordnet ist und von `ComPtr`diesem verwaltet wird.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`ComPtr`

## <a name="requirements"></a>Anforderungen

**Header:** client.h

**Namespace:** Microsoft::WRL

## <a name="tilde-comptr"></a>ComPtr::~ComPtr

Deinitialisiert eine Instanz von `ComPtr`.

```cpp
WRL_NOTHROW ~ComPtr();
```

## <a name="as"></a>Comptr:: As

Gibt ein `ComPtr` -Objekt zurück, das die durch den angegebenen Vorlagen Parameter identifizierte Schnittstelle darstellt.

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
Die Schnittstelle, die durch den Parameter *p*dargestellt werden soll.

*p*<br/>
Ein `ComPtr` -Objekt, das die durch den Parameter *U*angegebene Schnittstelle darstellt. Der Parameter " *p* " darf nicht auf `ComPtr` das aktuelle Objekt verweisen.

### <a name="remarks"></a>Hinweise

Die erste Vorlage ist die Form, die Sie in Ihrem Code verwenden sollten. Die zweite Vorlage ist eine interne Hilfsspezialisierung, die C++-Sprachfeatures unterstützt, wie etwa das Schlüsselwort [auto](../../cpp/auto-cpp.md) zur Typableitung.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.

## <a name="asiid"></a>Comptr:: asiid

Gibt ein `ComPtr` -Objekt zurück, das die durch die angegebene Schnittstellen-ID identifizierte Schnittstelle darstellt.

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
Wenn das Objekt über eine Schnittstelle verfügt, deren ID gleich *riid*ist, ein doppelt indirekter Zeiger auf die Schnittstelle, die durch den *riid* -Parameter angegeben wird. andernfalls ein Zeiger auf `IUnknown`.

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
Wenn dieser Vorgang abgeschlossen ist, ein Zeiger auf ein schwaches Verweis Objekt.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.

## <a name="attach"></a>Comptr:: Attach

Ordnet diesen `ComPtr` dem Schnittstellentyp zu, der durch den aktuellen Template Type-Parameter angegeben wird.

```cpp
void Attach(
   _In_opt_ InterfaceType* other
);
```

### <a name="parameters"></a>Parameter

*other*<br/>
Ein Schnittstellentyp.

## <a name="comptr"></a>Comptr:: comptr

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
   typename ENABLE_IF<__is_convertible_to(U*, T*), void *>
);

WRL_NOTHROW ComPtr(
   _Inout_ ComPtr &&other
);

template<class U>
WRL_NOTHROW ComPtr(
   _Inout_ ComPtr<U>&& other, typename ENABLE_IF<__is_convertible_to(U*, T*), void *>
);
```

### <a name="parameters"></a>Parameter

*U*<br/>
Der Typ des *anderen* Parameters.

*other*<br/>
Ein Objekt vom Typ " *U*".

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

Der erste Konstruktor ist der Standardkonstruktor, der implizit ein leeres-Objekt erstellt. Der zweite Konstruktor gibt [__nullptr](../../extensions/nullptr-cpp-component-extensions.md)an, der explizit ein leeres-Objekt erstellt.

Der dritte Konstruktor erstellt ein-Objekt aus dem-Objekt, das durch einen-Zeiger angegeben wird. Der comptr besitzt jetzt den referenzierten Speicher und verwaltet einen Verweis Zähler.

Der vierte und fünfte Konstruktor sind Kopierkonstruktoren. Der fünfte Konstruktor kopiert ein Objekt, wenn es in den aktuellen Typ konvertiert werden kann.

Die sechsten und siebten Konstruktoren sind bewegungskonstruktoren. Der siebte Konstruktor verschiebt ein Objekt, wenn es in den aktuellen Typ konvertiert werden kann.

## <a name="copyto"></a>ComPtr::CopyTo

Kopiert die aktuelle oder angegebene-Schnittstelle, `ComPtr` die diesem zugeordnet ist, in den angegebenen Zeiger.

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
Wenn dieser Vorgang abgeschlossen ist, ein Zeiger auf die angeforderte Schnittstelle.

*riid*<br/>
Eine Schnittstellen-ID.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das angibt, warum der `QueryInterface` implizite Vorgang fehlgeschlagen ist.

### <a name="remarks"></a>Hinweise

Die erste Funktion gibt eine Kopie eines Zeigers auf die-Schnittstelle zurück `ComPtr`, die diesem zugeordnet ist. Diese Funktion gibt immer S_OK zurück.

Die zweite Funktion führt einen `QueryInterface` -Vorgang für die-Schnittstelle `ComPtr` aus, die diesem für die durch den *riid* -Parameter angegebene Schnittstelle zugeordnet ist.

Die dritte Funktion führt einen `QueryInterface` -Vorgang für die Schnittstelle aus `ComPtr` , die diesem für die zugrunde liegende Schnittstelle des *U* -Parameters zugeordnet ist.

## <a name="detach"></a>ComPtr::Detach

Trennt dieses `ComPtr` -Objekt von der-Schnittstelle, die es darstellt.

```cpp
T* Detach();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die-Schnittstelle, die von `ComPtr` diesem-Objekt dargestellt wurde.

## <a name="get"></a>Comptr:: Get

Ruft einen Zeiger auf die-Schnittstelle ab, die diesem `ComPtr`zugeordnet ist.

```cpp
T* Get() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die-Schnittstelle, die `ComPtr`diesem zugeordnet ist.

## <a name="getaddressof"></a>ComPtr::GetAddressOf

Ruft die Adresse des [ptr_](#ptr) -Datenmembers ab, der einen Zeiger auf die-Schnittstelle enthält, `ComPtr`die von diesem dargestellt wird.

```cpp
T* const* GetAddressOf() const;
T** GetAddressOf();
```

### <a name="return-value"></a>Rückgabewert

Die Adresse einer Variablen.

## <a name="internaladdref"></a>Comptr:: internaladressf

Inkremente den Verweis Zähler der Schnittstelle, die `ComPtr`diesem zugeordnet ist.

```cpp
void InternalAddRef() const;
```

### <a name="remarks"></a>Hinweise

Diese Methode ist geschützt.

## <a name="internalrelease"></a>Comptr:: internalrelease

Führt einen com-Releasevorgang für die Schnittstelle `ComPtr`aus, die diesem zugeordnet ist.

```cpp
void InternalRelease();
```

### <a name="remarks"></a>Hinweise

Diese Methode ist geschützt.

## <a name="operator-ampersand"></a>Comptr::-Operator&amp;

Gibt die diesem `ComPtr` -Objekt zugeordnete-Schnittstelle frei und ruft dann die `ComPtr` Adresse des-Objekts ab.

```cpp
Details::ComPtrRef<WeakRef> operator&()

const Details::ComPtrRef<const WeakRef> operator&() const
```

### <a name="return-value"></a>Rückgabewert

Ein schwacher Verweis auf den aktuellen `ComPtr`.

### <a name="remarks"></a>Hinweise

Diese Methode unterscheidet sich von [comptr:: getaddressof](#getaddressof) insofern, als diese Methode einen Verweis auf den Schnittstellen Zeiger freigibt. Verwenden `ComPtr::GetAddressOf` Sie, wenn Sie die Adresse des Schnittstellen Zeigers benötigen, diese Schnittstelle aber nicht freigeben möchten.

## <a name="operator-arrow"></a>Comptr:: Operator-&gt;

Ruft einen Zeiger auf den Typ ab, der durch den aktuellen Vorlagenparameter angegeben ist.

```cpp
WRL_NOTHROW Microsoft::WRL::Details::RemoveIUnknown<InterfaceType>* operator->() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den Typ, der durch den Namen des aktuellen Vorlagen Typs angegeben wird.

### <a name="remarks"></a>Hinweise

Diese Hilfsfunktion entfernt unnötigen mehr Aufwand, der durch die Verwendung des STDMETHOD-Makros verursacht wird. Diese Funktion macht `IUnknown` - `private` Typen anstelle `virtual`von.

## <a name="operator-assign"></a>Comptr:: Operator =

Weist dem aktuellen `ComPtr`einen Wert zu.

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
Eine-Klasse.

*other*<br/>
Ein Zeiger, ein Verweis oder ein rvalue-Verweis auf einen Typ `ComPtr`oder einen anderen.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf den aktuellen `ComPtr`.

### <a name="remarks"></a>Hinweise

Die erste Version dieses Operators weist dem aktuellen `ComPtr`einen leeren Wert zu.

In der zweiten Version ist der zweite Schnittstellen Zeiger dem aktuellen `ComPtr` `ComPtr`zugewiesen, wenn der Zuweisungs Schnittstellen Zeiger nicht mit dem aktuellen Schnittstellen Zeiger identisch ist.

In der dritten Version wird der dem aktuellen `ComPtr`zugeordnete Schnittstellen Zeiger zugewiesen.

Wenn in der vierten Version der Schnittstellen Zeiger des Zuweisungs Werts nicht mit dem aktuellen `ComPtr` Schnittstellen Zeiger identisch ist, wird der zweite Schnittstellen Zeiger dem aktuellen `ComPtr`zugewiesen.

Die fünfte Version ist ein Kopier Operator. dem aktuellen `ComPtr` `ComPtr`wird ein Verweis auf ein zugewiesen.

Die sechste Version ist ein Kopier Operator, der Verschiebungs Semantik verwendet. ein rvalue-Verweis auf `ComPtr` einen, wenn ein beliebiger Typ eine statische Umwandlung ist und `ComPtr`dann dem aktuellen zugewiesen ist.

Die siebte Version ist ein Kopier Operator, der Verschiebungs Semantik verwendet. ein rvalue-Verweis auf `ComPtr` einen vom Typ *U* ist eine statische Umwandlung und wird dann dem `ComPtr`aktuellen zugewiesen.

## <a name="operator-equality"></a>Comptr:: Operator = =

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
Ein Verweis auf ein `ComPtr` anderes Objekt.

### <a name="return-value"></a>Rückgabewert

Der erste Operator ergibt `true` , `false`Wenn Objekt *a* und Objekt *b*gleich sind, andernfalls.

Der zweite und der dritte Operator `true` ergeben sich, wenn Objekt *a* gleich `nullptr`ist, `false`andernfalls.

## <a name="operator-inequality"></a>Comptr:: Operator! =

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
Ein Verweis auf ein `ComPtr` anderes Objekt.

### <a name="return-value"></a>Rückgabewert

Der erste Operator ergibt `true` , `false`Wenn Objekt *a* nicht gleich Objekt *b*ist; andernfalls.

Der zweite und der dritte Operator `true` ergeben sich, `false`Wenn Objekt *a* nicht `nullptr`gleich ist, andernfalls.

## <a name="operator-microsoft-wrl-details-booltype"></a>Comptr:: Operator Microsoft:: WRL::D etails:: booltype

Gibt an, ob eine `ComPtr` die Objekt Lebensdauer einer Schnittstelle verwaltet.

```cpp
WRL_NOTHROW operator Microsoft::WRL::Details::BoolType() const;
```

### <a name="return-value"></a>Rückgabewert

Wenn eine Schnittstelle diesem `ComPtr`zugeordnet ist, die Adresse des [boolstruct:: Member](boolstruct-structure.md#member) -Datenmembers, andernfalls. `nullptr`

## <a name="ptr"></a>ComPtr::ptr_

Enthält einen Zeiger auf die-Schnittstelle, die dieser zugeordnet ist und von `ComPtr`diesem verwaltet wird.

```cpp
InterfaceType *ptr_;
```

### <a name="remarks"></a>Hinweise

`ptr_`ist ein interner, geschützter Datenmember.

## <a name="releaseandgetaddressof"></a>Comptr:: releaseandgetaddressof

Gibt die-Schnittstelle frei `ComPtr` , die diesem zugeordnet ist, und ruft dann die Adresse des [ptr_](#ptr) -Datenmembers ab, der einen Zeiger auf die-Schnittstelle enthält, die freigegeben wurde.

```cpp
T** ReleaseAndGetAddressOf();
```

### <a name="return-value"></a>Rückgabewert

Die Adresse des [ptr_](#ptr) -Datenmembers dieses `ComPtr`.

## <a name="reset"></a>Comptr:: Reset

Gibt alle Verweise für den Zeiger auf die-Schnittstelle frei, die `ComPtr`diesem zugeordnet ist.

```cpp
unsigned long Reset();
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der freigegeben Verweise, sofern vorhanden.

## <a name="swap"></a>Comptr:: Swap

Tauscht die Schnittstelle, die vom `ComPtr` aktuellen verwaltet wird, mit der vom `ComPtr`angegebenen verwalteten Schnittstelle aus.

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

