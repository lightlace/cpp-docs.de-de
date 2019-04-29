---
title: EventTargetArray-Klasse
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::EventTargetArray
- event/Microsoft::WRL::Details::EventTargetArray::AddTail
- event/Microsoft::WRL::Details::EventTargetArray::Begin
- event/Microsoft::WRL::Details::EventTargetArray::End
- event/Microsoft::WRL::Details::EventTargetArray::EventTargetArray
- event/Microsoft::WRL::Details::EventTargetArray::Length
- event/Microsoft::WRL::Details::EventTargetArray::~EventTargetArray
helpviewer_keywords:
- Microsoft::WRL::Details::EventTargetArray class
- Microsoft::WRL::Details::EventTargetArray::AddTail method
- Microsoft::WRL::Details::EventTargetArray::Begin method
- Microsoft::WRL::Details::EventTargetArray::End method
- Microsoft::WRL::Details::EventTargetArray::EventTargetArray, constructor
- Microsoft::WRL::Details::EventTargetArray::Length method
- Microsoft::WRL::Details::EventTargetArray::~EventTargetArray, destructor
ms.assetid: e3cadb7c-2160-4cbb-a2f8-c28733d1e96d
ms.openlocfilehash: 1f3f8e299dba1f4b6ae5a5767f11989dc2fe8370
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398484"
---
# <a name="eventtargetarray-class"></a>EventTargetArray-Klasse

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
class EventTargetArray :
    public Microsoft::WRL::RuntimeClass<
        Microsoft::WRL::RuntimeClassFlags<ClassicCom>,
        IUnknown
    >;
```

## <a name="remarks"></a>Hinweise

Stellt ein Array von Ereignishandlern.

Ereignishandler, die zugeordnet sind ein [EventSource](eventsource-class.md) Objekt befinden sich in einem geschützten `EventTargetArray` -Datenmember.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

Name                                                           | Beschreibung
-------------------------------------------------------------- | -----------------------------------------------------------
[EventTargetArray::EventTargetArray](#eventtargetarray)        | Initialisiert eine neue Instanz der `EventTargetArray`-Klasse.
[EventTargetArray::~EventTargetArray](#tilde-eventtargetarray) | Hebt die Initialisierung der aktuellen `EventTargetArray` Klasse.

### <a name="public-methods"></a>Öffentliche Methoden

Name                                  | Beschreibung
------------------------------------- | ---------------------------------------------------------------------------------------
[EventTargetArray::AddTail](#addtail) | Fügt den angegebenen Ereignishandler an das Ende des internen Arrays von Ereignishandlern an.
[EventTargetArray::Begin](#begin)     | Ruft die Adresse des ersten Elements in das interne Array der Ereignishandler ab.
[EventTargetArray::End](#end)         | Ruft die Adresse des letzten Elements in das interne Array der Ereignishandler ab.
[EventTargetArray::Length](#length)   | Ruft die aktuelle Anzahl der Elemente in das interne Array der Ereignishandler ab.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`EventTargetArray`

## <a name="requirements"></a>Anforderungen

**Header:** event.h

**Namespace:** Microsoft::WRL::Details

## <a name="tilde-eventtargetarray"></a>EventTargetArray::~EventTargetArray

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
~EventTargetArray();
```

### <a name="remarks"></a>Hinweise

Hebt die Initialisierung der aktuellen `EventTargetArray` Klasse.

## <a name="addtail"></a>EventTargetArray::AddTail

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
void AddTail(
   _In_ IUnknown* element
);
```

### <a name="parameters"></a>Parameter

*element*<br/>
Zeiger auf den Ereignishandler, angefügt werden soll.

### <a name="remarks"></a>Hinweise

Fügt den angegebenen Ereignishandler an das Ende des internen Arrays von Ereignishandlern an.

`AddTail()` soll nur intern von verwendet werden. die `EventSource` Klasse.

## <a name="begin"></a>EventTargetArray::Begin

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
ComPtr<IUnknown>* Begin();
```

### <a name="return-value"></a>Rückgabewert

Die Adresse des ersten Elements im internen Array von Ereignishandlern.

### <a name="remarks"></a>Hinweise

Ruft die Adresse des ersten Elements in das interne Array der Ereignishandler ab.

## <a name="end"></a>EventTargetArray::End

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
ComPtr<IUnknown>* End();
```

### <a name="return-value"></a>Rückgabewert

Die Adresse des letzten Elements im internen Array von Ereignishandlern.

### <a name="remarks"></a>Hinweise

Ruft die Adresse des letzten Elements in das interne Array der Ereignishandler ab.

## <a name="eventtargetarray"></a>EventTargetArray::EventTargetArray

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
EventTargetArray(
   _Out_ HRESULT* hr,
   size_t items
);
```

### <a name="parameters"></a>Parameter

*hr*<br/>
Nach diesem Konstruktor-Vorgänge Parameter *hr* gibt an, ob das Array Zuordnung erfolgreich war oder nicht. Die folgende Liste enthält die möglichen Werte für *hr*.

+   S_OK<br/>
    Der Vorgang wurde erfolgreich ausgeführt.

+   E_OUTOFMEMORY<br/>
    Arbeitsspeicher konnte nicht für das Array zugeordnet werden.

+   S_FALSE<br/>
    Parameter *Elemente* ist kleiner als oder gleich 0 (null).

*items*<br/>
Die Anzahl der Elemente des Arrays zugewiesen werden.

### <a name="remarks"></a>Hinweise

Initialisiert eine neue Instanz der `EventTargetArray`-Klasse.

`EventTargetArray` wird verwendet, um ein Array von Ereignishandlern in behalten eine `EventSource` Objekt.

## <a name="length"></a>EventTargetArray::Length

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
size_t Length();
```

### <a name="return-value"></a>Rückgabewert

Die aktuelle Anzahl der Elemente in das interne Array von Ereignishandlern.

### <a name="remarks"></a>Hinweise

Ruft die aktuelle Anzahl der Elemente in das interne Array der Ereignishandler ab.
