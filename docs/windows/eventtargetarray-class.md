---
title: EventTargetArray-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/21/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::EventTargetArray
- event/Microsoft::WRL::Details::EventTargetArray::AddTail
- event/Microsoft::WRL::Details::EventTargetArray::Begin
- event/Microsoft::WRL::Details::EventTargetArray::End
- event/Microsoft::WRL::Details::EventTargetArray::EventTargetArray
- event/Microsoft::WRL::Details::EventTargetArray::Length
- event/Microsoft::WRL::Details::EventTargetArray::~EventTargetArray
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::EventTargetArray class
- Microsoft::WRL::Details::EventTargetArray::AddTail method
- Microsoft::WRL::Details::EventTargetArray::Begin method
- Microsoft::WRL::Details::EventTargetArray::End method
- Microsoft::WRL::Details::EventTargetArray::EventTargetArray, constructor
- Microsoft::WRL::Details::EventTargetArray::Length method
- Microsoft::WRL::Details::EventTargetArray::~EventTargetArray, destructor
ms.assetid: e3cadb7c-2160-4cbb-a2f8-c28733d1e96d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a02c571f33378ed65fc4b0c4efc7d1a82144279f
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2018
ms.locfileid: "48234699"
---
# <a name="eventtargetarray-class"></a>EventTargetArray-Klasse

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
class EventTargetArray : public Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<ClassicCom>, IUnknown>;
```

## <a name="remarks"></a>Hinweise

Stellt ein Array von Ereignishandlern.

Ereignishandler, die zugeordnet sind ein [EventSource](../windows/eventsource-class.md) Objekt befinden sich in einem geschützten `EventTargetArray` -Datenmember.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

Name                                                           | Beschreibung
-------------------------------------------------------------- | -----------------------------------------------------------
[Eventtargetarray:: Eventtargetarray](#eventtargetarray)        | Initialisiert eine neue Instanz der `EventTargetArray`-Klasse.
[EventTargetArray:: ~ EventTargetArray](#tilde-eventtargetarray) | Hebt die Initialisierung der aktuellen `EventTargetArray` Klasse.

### <a name="public-methods"></a>Öffentliche Methoden

Name                                  | Beschreibung
------------------------------------- | ---------------------------------------------------------------------------------------
[Eventtargetarray:: Addtail](#addtail) | Fügt den angegebenen Ereignishandler an das Ende des internen Arrays von Ereignishandlern an.
[Eventtargetarray:: begin](#begin)     | Ruft die Adresse des ersten Elements in das interne Array der Ereignishandler ab.
[Eventtargetarray:: End](#end)         | Ruft die Adresse des letzten Elements in das interne Array der Ereignishandler ab.
[Eventtargetarray:: Length](#length)   | Ruft die aktuelle Anzahl der Elemente in das interne Array der Ereignishandler ab.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`EventTargetArray`

## <a name="requirements"></a>Anforderungen

**Header:** event.h

**Namespace:** Microsoft::WRL::Details

## <a name="tilde-eventtargetarray"></a>EventTargetArray:: ~ EventTargetArray

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
~EventTargetArray();
```

### <a name="remarks"></a>Hinweise

Hebt die Initialisierung der aktuellen `EventTargetArray` Klasse.

## <a name="addtail"></a>Eventtargetarray:: Addtail

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
void AddTail(
   _In_ IUnknown* element
);
```

### <a name="parameters"></a>Parameter

*Element*<br/>
Zeiger auf den Ereignishandler, angefügt werden soll.

### <a name="remarks"></a>Hinweise

Fügt den angegebenen Ereignishandler an das Ende des internen Arrays von Ereignishandlern an.

`AddTail()` soll nur intern von verwendet werden. die `EventSource` Klasse.

## <a name="begin"></a>Eventtargetarray:: begin

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
ComPtr<IUnknown>* Begin();
```

### <a name="return-value"></a>Rückgabewert

Die Adresse des ersten Elements im internen Array von Ereignishandlern.

### <a name="remarks"></a>Hinweise

Ruft die Adresse des ersten Elements in das interne Array der Ereignishandler ab.

## <a name="end"></a>Eventtargetarray:: End

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
ComPtr<IUnknown>* End();
```

### <a name="return-value"></a>Rückgabewert

Die Adresse des letzten Elements im internen Array von Ereignishandlern.

### <a name="remarks"></a>Hinweise

Ruft die Adresse des letzten Elements in das interne Array der Ereignishandler ab.

## <a name="eventtargetarray"></a>Eventtargetarray:: Eventtargetarray

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
EventTargetArray(
   _Out_ HRESULT* hr,
   size_t items
);
```

### <a name="parameters"></a>Parameter

*HR*<br/>
Nach diesem Konstruktor-Vorgänge Parameter *hr* gibt an, ob das Array Zuordnung erfolgreich war oder nicht. Die folgende Liste enthält die möglichen Werte für *hr*.

+   S_OK<br/>
    Der Vorgang wurde erfolgreich ausgeführt.

+   E_OUTOFMEMORY<br/>
    Arbeitsspeicher konnte nicht für das Array zugeordnet werden.

+   S_FALSE<br/>
    Parameter *Elemente* ist kleiner als oder gleich 0 (null).

*Elemente*<br/>
Die Anzahl der Elemente des Arrays zugewiesen werden.

### <a name="remarks"></a>Hinweise

Initialisiert eine neue Instanz der `EventTargetArray`-Klasse.

`EventTargetArray` wird verwendet, um ein Array von Ereignishandlern in behalten eine `EventSource` Objekt.

## <a name="length"></a>Eventtargetarray:: Length

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
size_t Length();
```

### <a name="return-value"></a>Rückgabewert

Die aktuelle Anzahl der Elemente in das interne Array von Ereignishandlern.

### <a name="remarks"></a>Hinweise

Ruft die aktuelle Anzahl der Elemente in das interne Array der Ereignishandler ab.
