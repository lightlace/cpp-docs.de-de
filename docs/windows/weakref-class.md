---
title: WeakRef-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/07/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef
- client/Microsoft::WRL::WeakRef::~WeakRef
- client/Microsoft::WRL::WeakRef::As
- client/Microsoft::WRL::WeakRef::AsIID
- client/Microsoft::WRL::WeakRef::CopyTo
- client/Microsoft::WRL::WeakRef::operator&
- client/Microsoft::WRL::WeakRef::WeakRef
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::WeakRef class
- Microsoft::WRL::WeakRef::~WeakRef, destructor
- Microsoft::WRL::WeakRef::As method
- Microsoft::WRL::WeakRef::AsIID method
- Microsoft::WRL::WeakRef::CopyTo method
- Microsoft::WRL::WeakRef::operator& operator
- Microsoft::WRL::WeakRef::WeakRef, constructor
ms.assetid: 572be703-c641-496c-8af5-ad6164670ba1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6f9b121b75e31fdd79313e36b9e1e19c1cf3200e
ms.sourcegitcommit: fb9448eb96c6351a77df04af16ec5c0fb9457d9e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2018
ms.locfileid: "44691535"
---
# <a name="weakref-class"></a>WeakRef-Klasse

Stellt einen *schwachen Verweis* dar, der nur durch die Windows-Runtime und nicht durch die klassische COM verwendet werden kann. Ein schwacher Verweis repräsentiert ein Objekt, auf das möglicherweise zugegriffen werden kann.

## <a name="syntax"></a>Syntax

```cpp
class WeakRef : public ComPtr<IWeakReference>
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[WeakRef::WeakRef-Konstruktor](#weakref)|Initialisiert eine neue Instanz der `WeakRef`-Klasse.|
|[WeakRef::~WeakRef-Destruktor](#tilde-weakref)|Hebt die Initialisierung der aktuellen Instanz von der `WeakRef` Klasse.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[WeakRef::As-Methode](#as)|Setzt den angegebenen `ComPtr` Parameter für den Zeiger auf die angegebene Schnittstelle darstellt.|
|[WeakRef::AsIID-Methode](#asiid)|Setzt den angegebenen `ComPtr` Parameter für den Zeiger auf die angegebene Schnittstellen-ID darstellt.|
|[WeakRef::CopyTo-Methode](#copyto)|Weist einer Schnittstelle einen Zeiger zu, falls verfügbar zur angegebenen Zeigervariablen.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[WeakRef::operator&-Operator](#operator-ampersand-operator)|Gibt eine `ComPtrRef` -Objekt, das der aktuelle darstellt `WeakRef` Objekt.|

## <a name="remarks"></a>Hinweise

Ein `WeakRef` -Objekt verwaltet einen *starken Verweis*, der mit einem Objekt zugeordnet ist und gültig oder ungültig sein kann. Rufen Sie die `As()` oder `AsIID()` Methode, um einen starken Verweis abzurufen. Wenn der starke Verweis gültig ist, kann er auf das zugeordnete Objekt zugreifen. Wenn der starke Verweis ungültig ist (`nullptr`), ist der Zugriff auf das zugeordnete Objekt nicht möglich.

Ein `WeakRef` Objekt wird normalerweise verwendet, um ein Objekt darstellt, dessen Vorhandensein durch einen externen Thread oder Anwendung gesteuert wird. Erstellen Sie z. B. eine `WeakRef` Objekt aus einem Verweis auf ein Dateiobjekt. Solange die Datei geöffnet ist, ist der starke Verweis gültig. Wenn die Datei aber geschlossen wird, wird der starke Verweis ungültig.

Beachten Sie, dass es eine verhaltensänderung bei den [als](#as), [AsIID](#asiid) und [CopyTo](#copyto) Methoden in das Windows 10 SDK. Zuvor, nach dem Aufrufen einer dieser Methoden, Sie können überprüfen, die `WeakRef` für `nullptr` zu bestimmen, ob ein starker Verweis erfolgreich, wie im folgenden Code abgerufen wurde:

```cpp
WeakRef wr;
strongComptrRef.AsWeak(&wr);

// Now suppose that the object strongComPtrRef points to no longer exists
// and the following code tries to get a strong ref from the weak ref:
ComPtr<ISomeInterface> strongRef;
HRESULT hr = wr.As(&strongRef);

// This check won't work with the Windows 10 SDK version of the library.
// Check the input pointer instead.
if(wr == nullptr)  
{
    wprintf(L"Couldn’t get strong ref!");
}
```

Dieser Code funktioniert bei Verwendung des Windows 10 SDKs (oder höher) nicht. Überprüfen Sie stattdessen den Zeiger, der übergeben wurde für `nullptr`.

```cpp
if (strongRef == nullptr)  
{
    wprintf(L"Couldn't get strong ref!");
}
```

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`ComPtr`

`WeakRef`

## <a name="requirements"></a>Anforderungen

**Header:** client.h

**Namespace:** Microsoft::WRL

## <a name="tilde-weakref"></a>WeakRef:: ~ WeakRef-Destruktor

Hebt die Initialisierung der aktuellen Instanz von der `WeakRef` Klasse.

```cpp
~WeakRef();
```

## <a name="as"></a>Weakref:: As-Methode

Setzt den angegebenen `ComPtr` Parameter für den Zeiger auf die angegebene Schnittstelle darstellt.

```cpp
template<typename U>
HRESULT As(
   _Out_ ComPtr<U>* ptr
);

template<typename U>
HRESULT As(
   _Out_ Details::ComPtrRef<ComPtr<U>> ptr
);
```

### <a name="parameters"></a>Parameter

*U*  
Eine Schnittstellen-ID.

*ptr*  
Wenn dieser Vorgang abgeschlossen ist, ein Objekt, das Parameter repräsentiert *U*.

### <a name="return-value"></a>Rückgabewert

- S_OK, wenn dieser Vorgang erfolgreich ist; andernfalls ein HRESULT, der den Grund angibt. der Vorgang fehlgeschlagen ist, und *Ptr* nastaven NA hodnotu `nullptr`.

- S_OK, wenn dieser Vorgang ist, aber das aktuelle erfolgreich `WeakRef` Objekt bereits freigegeben wurde. Parameter *Ptr* nastaven NA hodnotu `nullptr`.

- S_OK, wenn dieser Vorgang ist, aber das aktuelle erfolgreich `WeakRef` abgeleitetes Objekt ist nicht vom Parameter *U*. Parameter *Ptr* nastaven NA hodnotu `nullptr`.

### <a name="remarks"></a>Hinweise

Ein Fehler wird ausgegeben, wenn Parameter *U* ist `IWeakReference`, oder Sie stammt nicht aus `IInspectable`.

Die erste Vorlage ist die Form, die Sie in Ihrem Code verwenden sollten. Die zweite Vorlage ist eine interne Hilfsspezialisierung, die C++-Sprachfeatures unterstützt, wie etwa das Schlüsselwort [auto](../cpp/auto-cpp.md) zur Typableitung.

Ab Windows 10-SDKS können dieser Methode ist nicht festgelegt die `WeakRef` -Instanz `nullptr` Wenn der schwache Verweis nicht abgerufen werden kann, so vermeiden Sie Code zur fehlerüberprüfung, die überprüft die `WeakRef` für `nullptr`. Überprüfen Sie stattdessen *Ptr* für `nullptr`.

## <a name="asiid"></a>Weakref:: Asiid-Methode

Setzt den angegebenen `ComPtr` Parameter für den Zeiger auf die angegebene Schnittstellen-ID darstellt.

```cpp
HRESULT AsIID(
   REFIID riid,
   _Out_ ComPtr<IInspectable>* ptr
);
```

### <a name="parameters"></a>Parameter

*riid*  
Eine Schnittstellen-ID.

*ptr*  
Wenn dieser Vorgang abgeschlossen ist, ein Objekt, das Parameter repräsentiert *Riid*.

### <a name="return-value"></a>Rückgabewert

- S_OK, wenn dieser Vorgang erfolgreich ist; andernfalls ein HRESULT, der den Grund angibt. der Vorgang fehlgeschlagen ist, und *Ptr* nastaven NA hodnotu `nullptr`.

- S_OK, wenn dieser Vorgang ist, aber das aktuelle erfolgreich `WeakRef` Objekt bereits freigegeben wurde. Parameter *Ptr* nastaven NA hodnotu `nullptr`.

- S_OK, wenn dieser Vorgang ist, aber das aktuelle erfolgreich `WeakRef` abgeleitetes Objekt ist nicht vom Parameter *Riid*. Parameter *Ptr* nastaven NA hodnotu `nullptr`. (Weitere Informationen finden Sie in den Hinweisen.)

### <a name="remarks"></a>Hinweise

Ein Fehler wird ausgegeben, wenn Parameter *Riid* stammt nicht aus `IInspectable`. Dieser Fehler hat Vorrang vor den Rückgabewert.

Die erste Vorlage ist die Form, die Sie in Ihrem Code verwenden sollten. Die zweite Vorlage (die hier nicht dargestellt, aber in der Headerdatei deklariert ist) ist eine interne Hilfsspezialisierung, die C++-Sprachfeatures unterstützt, wie etwa das Schlüsselwort [auto](../cpp/auto-cpp.md) zur Typableitung.

Ab Windows 10-SDKS können dieser Methode ist nicht festgelegt die `WeakRef` -Instanz `nullptr` Wenn der schwache Verweis nicht abgerufen werden kann, so vermeiden Sie Code zur fehlerüberprüfung, die überprüft die `WeakRef` für `nullptr`. Überprüfen Sie stattdessen *Ptr* für `nullptr`.

## <a name="copyto"></a>Weakref:: CopyTo-Methode

Weist einer Schnittstelle einen Zeiger zu, falls verfügbar zur angegebenen Zeigervariablen.

```cpp
HRESULT CopyTo(
   REFIID riid,
   _Deref_out_ IInspectable** ptr
);

template<typename U>
HRESULT CopyTo(
   _Deref_out_ U** ptr
);

HRESULT CopyTo(
   _Deref_out_ IWeakReference** ptr
);
```

### <a name="parameters"></a>Parameter

*U*  
Zeiger ein `IInspectable` Schnittstelle. Ein Fehler wird ausgegeben, wenn *U* stammt nicht aus `IInspectable`.

*riid*  
Eine Schnittstellen-ID. Ein Fehler wird ausgegeben, wenn *Riid* stammt nicht aus `IWeakReference`.

*ptr*  
Ein doppelt indirekter Zeiger auf `IInspectable` oder `IWeakReference`.

### <a name="return-value"></a>Rückgabewert

„S_OK“ im Erfolgsfall, andernfalls ein HRESULT, das den Fehler beschreibt. Weitere Informationen finden Sie in den **Hinweisen**.

### <a name="remarks"></a>Hinweise

Der Rückgabewert „S_OK“ bedeutet, dass dieser Vorgang erfolgreich war, gibt aber nicht an, ob der schwache Verweis zu einem starken Verweis aufgelöst wurde. Wenn S_OK zurückgegeben wird, testen Sie diesen Parameter *p* ein starker Verweis, d. h. Parameter *p* ist kein `nullptr`.

Ab Windows 10-SDKS können dieser Methode ist nicht festgelegt die `WeakRef` -Instanz `nullptr` Wenn der schwache Verweis nicht abgerufen werden kann, so vermeiden Sie Fehler beim Überprüfen von Code, der überprüft die `WeakRef` für `nullptr`. Überprüfen Sie stattdessen *Ptr* für `nullptr`.

## <a name="operator-ampersand-operator"></a>Weakref::&amp; Operator

Gibt eine `ComPtrRef` -Objekt, das der aktuelle darstellt `WeakRef` Objekt.

```cpp
Details::ComPtrRef<WeakRef> operator&() throw()  
```

### <a name="return-value"></a>Rückgabewert

Ein `ComPtrRef` -Objekt, das der aktuelle darstellt `WeakRef` Objekt.

### <a name="remarks"></a>Hinweise

Dies ist eine interne Hilfsmethode-Operator, der nicht in Ihrem Code verwendet werden soll.

## <a name="weakref"></a>Weakref:: Weakref-Konstruktor

Initialisiert eine neue Instanz der `WeakRef`-Klasse.

```cpp
WeakRef();
WeakRef(
   decltype(__nullptr)  
);

WeakRef(
   _In_opt_ IWeakReference* ptr
);

WeakRef(
   const ComPtr<IWeakReference>& ptr
);

WeakRef(
   const WeakRef& ptr
);

WeakRef(
   _Inout_ WeakRef&& ptr
);
```

### <a name="parameters"></a>Parameter

*ptr*  
Ein Zeiger, Verweis oder Rvalue-Verweis auf ein vorhandenes Objekt, das das aktuelle initialisiert `WeakRef` Objekt.

### <a name="remarks"></a>Hinweise

Der erste Konstruktor initialisiert ein leeres `WeakRef` Objekt. Der zweite Konstruktor initialisiert ein `WeakRef` Objekt von einem Zeiger auf die `IWeakReference` Schnittstelle. Der dritte Konstruktor initialisiert ein `WeakRef` Objekt aus einem Verweis auf eine `ComPtr<IWeakReference>` Objekt. Der vierte und fünfte Konstruktor initialisiert ein `WeakRef` Objekt von einem anderen `WeakRef` Objekt.
