---
title: EventSource-Klasse
ms.date: 09/12/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::EventSource
- event/Microsoft::WRL::EventSource::Add
- event/Microsoft::WRL::EventSource::addRemoveLock_
- event/Microsoft::WRL::EventSource::EventSource
- event/Microsoft::WRL::EventSource::GetSize
- event/Microsoft::WRL::EventSource::InvokeAll
- event/Microsoft::WRL::EventSource::Remove
- event/Microsoft::WRL::EventSource::targets_
- event/Microsoft::WRL::EventSource::targetsPointerLock_
helpviewer_keywords:
- Microsoft::WRL::EventSource class
- Microsoft::WRL::EventSource::Add method
- Microsoft::WRL::EventSource::addRemoveLock_ data member
- Microsoft::WRL::EventSource::EventSource, constructor
- Microsoft::WRL::EventSource::GetSize method
- Microsoft::WRL::EventSource::InvokeAll method
- Microsoft::WRL::EventSource::Remove method
- Microsoft::WRL::EventSource::targets_ data member
- Microsoft::WRL::EventSource::targetsPointerLock_ data member
ms.assetid: 91f1c072-6af4-44e6-b6d8-ac6d0c688dde
ms.openlocfilehash: e9070fe756410e3e1bb1e5840eb3f06e29c2f46b
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58785431"
---
# <a name="eventsource-class"></a>EventSource-Klasse

Stellt ein nicht-agile-Ereignis. `EventSource`-Memberfunktionen fügen Ereignishandler hinzu, entfernen sie und rufen sie auf. Verwenden Sie für agile-Ereignisse [AgileEventSource](agileeventsource-class.md).

## <a name="syntax"></a>Syntax

```cpp
template<typename TDelegateInterface>
class EventSource;
```

### <a name="parameters"></a>Parameter

*TDelegateInterface*<br/>
Die Schnittstelle, ein Delegat, der einen Ereignishandler darstellt.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

| Name                                     | Beschreibung                                            |
| ---------------------------------------- | ------------------------------------------------------ |
| [EventSource::EventSource](#eventsource) | Initialisiert eine neue Instanz der `EventSource`-Klasse. |

### <a name="public-methods"></a>Öffentliche Methoden

| Name                                 | Beschreibung                                                                                                                                                      |
| ------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [EventSource::Add](#add)             | Fügt den Ereignishandler, die durch die Schnittstelle für die angegebenen Delegaten dargestellt wird, auf den Satz von Ereignishandlern für die aktuelle `EventSource` Objekt.                     |
| [EventSource::GetSize](#getsize)     | Ruft die Anzahl der aktuellen zugeordneten Ereignishandler `EventSource` Objekt.                                                                         |
| [EventSource::InvokeAll](#invokeall) | Ruft jede Ereignishandler verknüpft ist, mit dem aktuellen `EventSource` -Objekt mit den angegebenen Argumenttypen und der Argumente.                                      |
| [EventSource::Remove](#remove)       | Löscht den Ereignishandler, die durch das angegebene Ereignis Registrierungstoken dargestellt wird, aus dem Satz von Ereignishandlern verknüpft ist, mit dem aktuellen `EventSource` Objekt. |

### <a name="protected-data-members"></a>Geschützte Datenmember

| Name                                                    | Beschreibung                                                                                                                       |
| ------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| [EventSource::addRemoveLock_](#addremovelock)           | Synchronisiert den Zugriff auf die [Targets_](#targets) Arrays beim Hinzufügen, entfernen oder Ereignishandler aufrufen.                          |
| [EventSource::targets_](#targets)                       | Ein Array von einem oder mehreren Ereignishandlern.                                                                                           |
| [EventSource::targetsPointerLock_](#targetspointerlock) | Synchronisiert den Zugriff auf interne Datenmember, die auch bei der Ereignishandler für diese Ereignisquelle hinzugefügt, entfernt oder aufgerufen. |

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`EventSource`

## <a name="requirements"></a>Anforderungen

**Header:** event.h

**Namespace:** Microsoft::WRL

## <a name="add"></a>EventSource::Add

Fügt den Ereignishandler, die durch die Schnittstelle für die angegebenen Delegaten dargestellt wird, auf den Satz von Ereignishandlern für die aktuelle `EventSource` Objekt.

```cpp
HRESULT Add(
   _In_ TDelegateInterface* delegateInterface,
   _Out_ EventRegistrationToken* token
);
```

### <a name="parameters"></a>Parameter

*delegateInterface*<br/>
Die Schnittstelle an ein Delegatobjekt, das einen Ereignishandler darstellt.

*token*<br/>
Wenn dieser Vorgang abgeschlossen ist, ein Handle, das das Ereignis darstellt. Verwenden Sie dieses Token als Parameter an die ["Remove()""](#remove) Methode, um den Ereignishandler zu verwerfen.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.

## <a name="addremovelock"></a>EventSource::addRemoveLock_

Synchronisiert den Zugriff auf die [Targets_](#targets) Arrays beim Hinzufügen, entfernen oder Ereignishandler aufrufen.

```cpp
Wrappers::SRWLock addRemoveLock_;
```

## <a name="eventsource"></a>EventSource::EventSource

Initialisiert eine neue Instanz der `EventSource`-Klasse.

```cpp
EventSource();
```

## <a name="getsize"></a>EventSource::GetSize

Ruft die Anzahl der aktuellen zugeordneten Ereignishandler `EventSource` Objekt.

```cpp
size_t GetSize() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl von Ereignishandlern in [Targets_](#targets).

## <a name="invokeall"></a>EventSource::InvokeAll

Ruft jede Ereignishandler verknüpft ist, mit dem aktuellen `EventSource` -Objekt mit den angegebenen Argumenttypen und der Argumente.

```cpp
void InvokeAll();
template <
   typename T0
>
void InvokeAll(
   T0arg0
);
template <
   typename T0,
   typename T1
>
void InvokeAll(
   T0arg0,
   T1arg1
);
template <
   typename T0,
   typename T1,
   typename T2
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4,
   typename T5
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4,
   T5arg5
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4,
   typename T5,
   typename T6
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4,
   T5arg5,
   T6arg6
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4,
   typename T5,
   typename T6,
   typename T7
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4,
   T5arg5,
   T6arg6,
   T7arg7
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4,
   typename T5,
   typename T6,
   typename T7,
   typename T8
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4,
   T5arg5,
   T6arg6,
   T7arg7,
   T8arg8
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4,
   typename T5,
   typename T6,
   typename T7,
   typename T8,
   typename T9
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4,
   T5arg5,
   T6arg6,
   T7arg7,
   T8arg8,
   T9arg9
);
```

### <a name="parameters"></a>Parameter

*T0*<br/>
Der Typ des Arguments nullten Event Handler.

*T1*<br/>
Der Typ, der das erste Argument der Ereignis-Handler.

*T2*<br/>
Der Typ des zweiten Arguments der Ereignis-Handler.

*T3*<br/>
Der Typ des dritten Arguments der Ereignis-Handler.

*T4*<br/>
Der Typ des vierten Arguments der Ereignis-Handler.

*T5*<br/>
Der Typ des fünften Arguments der Ereignis-Handler.

*T6*<br/>
Der Typ des sechsten Arguments der Ereignis-Handler.

*T7*<br/>
Der Typ des siebten Arguments der Ereignis-Handler.

*T8*<br/>
Der Typ des Arguments achte Event Handler.

*T9*<br/>
Der Typ des neunten Arguments der Ereignis-Handler.

*arg0*<br/>
Das Argument der nullten Ereignis-Handler.

*arg1*<br/>
Das erste Argument der Ereignis-Handler.

*arg2*<br/>
Das zweite Argument der Ereignis-Handler.

*arg3*<br/>
Das dritte Argument der Ereignis-Handler.

*arg4*<br/>
Das vierte Argument der Ereignis-Handler.

*arg5*<br/>
Das fünfte Argument der Ereignis-Handler.

*arg6*<br/>
Das sechste Handler Ereignisargument.

*arg7*<br/>
Das siebte Handler Ereignisargument.

*arg8*<br/>
Das achte Handler Ereignisargument.

*arg9*<br/>
Das neunte Handler Ereignisargument.

## <a name="remove"></a>EventSource::Remove

Löscht den Ereignishandler, die durch das angegebene Ereignis Registrierungstoken dargestellt wird, aus dem Satz von Ereignishandlern verknüpft ist, mit dem aktuellen `EventSource` Objekt.

```cpp
HRESULT Remove(
   EventRegistrationToken token
);
```

### <a name="parameters"></a>Parameter

*token*<br/>
Ein Handle, das einen Ereignishandler darstellt. Dieses Token zurückgegeben wurde, wenn der Ereignishandler, indem registriert wurde die [Add()](#add) Methode.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.

### <a name="remarks"></a>Hinweise

Weitere Informationen zu den `EventRegistrationToken` Struktur, siehe die **Windows::Foundation::EventRegistrationToken Struktur** Thema in der **Windows-Runtime** Referenzdokumentation.

## <a name="targets"></a>EventSource:: Targets_

Ein Array von einem oder mehreren Ereignishandlern.

```cpp
ComPtr<Details::EventTargetArray> targets_;
```

### <a name="remarks"></a>Hinweise

Wenn das Ereignis, das vom aktuellen entspricht `EventSource` Objekt wird der Ereignishandler werden aufgerufen.

## <a name="targetspointerlock"></a>EventSource::targetsPointerLock_

Synchronisiert den Zugriff auf interne Datenmember, auch wenn der Ereignishandler für dieses `EventSource` hinzugefügt wird, entfernt oder aufgerufen.

```cpp
Wrappers::SRWLock targetsPointerLock_;
```
