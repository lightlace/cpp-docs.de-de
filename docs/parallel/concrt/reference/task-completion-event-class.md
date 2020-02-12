---
title: task_completion_event-Klasse
ms.date: 11/04/2016
f1_keywords:
- task_completion_event
- PPLTASKS/concurrency::task_completion_event
- PPLTASKS/concurrency::task_completion_event::task_completion_event
- PPLTASKS/concurrency::task_completion_event::set
- PPLTASKS/concurrency::task_completion_event::set_exception
helpviewer_keywords:
- task_completion_event class
ms.assetid: fb19ed98-f245-48dc-9ba5-487ba879b28a
ms.openlocfilehash: b3e3093cb76df507f8c707e497c9aec75a065057
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142595"
---
# <a name="task_completion_event-class"></a>task_completion_event-Klasse

Mit der `task_completion_event`-Klasse können Sie die Ausführung einer Aufgabe verzögern, bis eine Bedingung erfüllt ist, oder eine Aufgabe als Reaktion auf ein externes Ereignis starten.

## <a name="syntax"></a>Syntax

```cpp
template<typename _ResultType>
class task_completion_event;

template<>
class task_completion_event<void>;
```

### <a name="parameters"></a>Parameter

*_ResultType*<br/>
Der Ergebnistyp dieser `task_completion_event`-Klasse.

## <a name="members"></a>Members

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[task_completion_event](#ctor)|Erstellt ein `task_completion_event`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|[set](#set)|Ist überladen. Legt das Aufgabenabschlussereignis fest.|
|[set_exception](#set_exception)|Ist überladen. Gibt eine Ausnahme an alle Aufgaben weiter, die dem Ereignis zugeordnet sind.|

## <a name="remarks"></a>Bemerkungen

Verwenden Sie eine Aufgabe, die aus einem Aufgabenabschlussereignis erstellt wird, wenn Ihr Szenario die Erstellung einer Aufgabe erfordert, die abgeschlossen wird, und planen Sie die Ausführung ihrer Fortsetzungen für einen späteren Zeitpunkt. `task_completion_event` muss den gleichen Typ haben, wie die Aufgabe, die Sie erstellen, und das Aufrufen der set-Methode für das Aufgabenabschlussereignis mit einem Wert dieses Typs führt zu einem Abschluss der zugeordneten Aufgabe und liefert diesen Wert als Ergebnis ihrer Fortsetzungen.

Wenn das Aufgabenabschlussereignis kein Signal erhält, werden alle Aufgaben, die daraus erstellt wurden, abgebrochen, wenn es zerstört wird.

`task_completion_event` verhält sich wie ein intelligenter Zeiger und sollte von einem Wert übergeben werden.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`task_completion_event`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** ppltasks. h

**Namespace:** Parallelität

## <a name="set"></a>Set

Legt das Aufgabenabschlussereignis fest.

```cpp
bool set(_ResultType _Result) const ;

bool set() const ;
```

### <a name="parameters"></a>Parameter

*_Result*<br/>
Das Ergebnis, das für dieses Ereignis festgelegt werden soll.

### <a name="return-value"></a>Rückgabewert

Die Methode gibt " **true** " zurück, wenn das Ereignis erfolgreich festgelegt wurde. Gibt **false** zurück, wenn das Ereignis bereits festgelegt ist.

### <a name="remarks"></a>Bemerkungen

Bei mehrfachen oder gleichzeitigen Aufrufen von `set` ist nur der erste Aufruf erfolgreich, und sein Ergebnis (falls vorhanden) wird im Aufgabenabschlussereignis gespeichert. Die verbleibenden Sätze werden ignoriert, und die Methode gibt "false" zurück. Wenn Sie ein Aufgabenabschlussereignis festlegen, werden alle Aufgaben, die aus diesem Ereignis erstellt wurden, abgeschlossen, und ihre Fortsetzungen, falls vorhanden, werden geplant. Aufgaben Vervollständigungs Objekte, die eine andere `_ResultType` als **void** aufweisen, übergeben den Wert an Ihre Fortsetzungen.

## <a name="set_exception"></a>set_exception

Gibt eine Ausnahme an alle Aufgaben weiter, die dem Ereignis zugeordnet sind.

```cpp
template<typename _E>
__declspec(noinline) bool set_exception(_E _Except) const;

__declspec(noinline) bool set_exception(std::exception_ptr _ExceptionPtr) const ;
```

### <a name="parameters"></a>Parameter

*_E*<br/>
Der Ausnahmetyp.

*_Except*<br/>
Die festzulegende Ausnahme.

*_ExceptionPtr*<br/>
Der festzulegende Ausnahme Zeiger.

### <a name="return-value"></a>Rückgabewert

## <a name="ctor"></a>task_completion_event

Erstellt ein `task_completion_event`-Objekt.

```cpp
task_completion_event();
```

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)
