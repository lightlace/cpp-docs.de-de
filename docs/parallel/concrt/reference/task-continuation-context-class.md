---
title: task_continuation_context-Klasse
ms.date: 11/04/2016
f1_keywords:
- task_continuation_context
- PPLTASKS/concurrency::task_continuation_context
- PPLTASKS/concurrency::task_continuation_context::get_current_winrt_context
- PPLTASKS/concurrency::task_continuation_context::use_arbitrary
- PPLTASKS/concurrency::task_continuation_context::use_current
- PPLTASKS/concurrency::task_continuation_context::use_default
- PPLTASKS/concurrency::task_continuation_context::use_synchronous_execution
helpviewer_keywords:
- task_continuation_context class
ms.assetid: 1fb5a76a-3682-45c2-a615-8b6b527741f0
ms.openlocfilehash: ae8ac425f035839cdddc0b19f4f40d3b6369202a
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142574"
---
# <a name="task_continuation_context-class"></a>task_continuation_context-Klasse

Mit der `task_continuation_context`-Klasse können Sie angeben, an welcher Stelle eine Fortsetzung ausgeführt werden soll. Es ist nur nützlich, diese Klasse aus einer Windows-Runtime-APP zu verwenden. Bei nicht-Windows-Runtime-apps wird der Ausführungs Kontext der Aufgaben Fortsetzung von der Laufzeit bestimmt und kann nicht konfiguriert werden.

## <a name="syntax"></a>Syntax

```cpp
class task_continuation_context : public details::_ContextCallback;
```

## <a name="members"></a>Members

### <a name="public-methods"></a>Öffentliche Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|[get_current_winrt_context](#get_current_winrt_context)|Gibt ein Aufgaben Fortsetzungs Kontext Objekt zurück, das den aktuellen WinRT-Thread Kontext darstellt.|
|[use_arbitrary](#use_arbitrary)|Erstellt einen Aufgabenfortsetzungskontext, der er es der Laufzeit ermöglicht, den Ausführungskontext für eine Fortsetzung auszuwählen.|
|[use_current](#use_current)|Gibt ein Kontextobjekt für die Aufgabenfortsetzung zurück, das den aktuellen Ausführungskontext darstellt.|
|[use_default](#use_default)|Erstellt den standardmäßigen Aufgabenfortsetzungskontext.|
|[use_synchronous_execution](#use_synchronous_execution)|Gibt ein Aufgaben Fortsetzungs Kontext Objekt zurück, das den synchronen Ausführungs Kontext darstellt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`_ContextCallback`

`task_continuation_context`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** ppltasks. h

**Namespace:** Parallelität

## <a name="get_current_winrt_context"></a>get_current_winrt_context

Gibt ein Aufgaben Fortsetzungs Kontext Objekt zurück, das den aktuellen WinRT-Thread Kontext darstellt.

### <a name="syntax"></a>Syntax

```cpp
static task_continuation_context get_current_winrt_context();
```

### <a name="return-value"></a>Rückgabewert

Der aktuelle Windows-Runtime Thread Kontext. Gibt einen leeren task_continuation_context zurück, wenn er von einem nicht Windows-Runtime Kontext aufgerufen wird.

### <a name="remarks"></a>Bemerkungen

Die `get_current_winrt_context`-Methode erfasst den Windows-Runtime Thread Kontext des Aufrufers. Er gibt einen leeren Kontext an nicht-Windows-Runtime Aufrufer zurück.

Der von `get_current_winrt_context` zurückgegebene Wert kann verwendet werden, um der Laufzeit mitzuteilen, dass die Fortsetzung im Apartment Modell des erfassten Kontexts (STA vs MTA) ausgeführt werden soll, unabhängig davon, ob die Vorgänger Aufgabe Apartment fähig ist. Eine apartmentfähige Aufgabe ist eine Aufgabe, die eine `IAsyncInfo`-Windows-Runtime-Schnittstelle entpackt, oder eine Aufgabe, die von einer solchen Aufgabe abgeleitet wird.

Diese Methode ähnelt der `use_current`-Methode, ist aber auch für nativen C++ Code ohne C++/CX-Erweiterungs Unterstützung verfügbar. Es ist für die Verwendung durch erweiterte Benutzer vorgesehen C++, die/CX-Agnostic-Bibliotheks Code für systemeigene und Windows-Runtime Aufrufer schreiben. Wenn Sie diese Funktionalität nicht benötigen, empfehlen wir die `use_current`-Methode, die nur für C++/CX-Clients verfügbar ist.

## <a name="use_arbitrary"></a>use_arbitrary

Erstellt einen Aufgabenfortsetzungskontext, der er es der Laufzeit ermöglicht, den Ausführungskontext für eine Fortsetzung auszuwählen.

### <a name="syntax"></a>Syntax

```cpp
static task_continuation_context use_arbitrary();
```

### <a name="return-value"></a>Rückgabewert

Ein Aufgabenfortsetzungskontext, der einen beliebigen Ort darstellt.

### <a name="remarks"></a>Bemerkungen

Wenn dieser Fortsetzungskontext verwendet wird, wird die Fortsetzung in einem Kontext ausgeführt, den die Laufzeit selbst auswählt, auch wenn die Vorgängeraufgabe apartmentfähig ist.

`use_arbitrary` kann verwendet werden, um das Standardverhalten für eine Fortsetzung einer apartmentfähigen Aufgabe zu deaktivieren, die in einem STA erstellt wurde.

Diese Methode ist nur für Windows-Runtime-apps verfügbar.

## <a name="use_current"></a>use_current

Gibt ein Kontextobjekt für die Aufgabenfortsetzung zurück, das den aktuellen Ausführungskontext darstellt.

```cpp
static task_continuation_context use_current();
```

### <a name="return-value"></a>Rückgabewert

Der aktuelle Ausführungskontext.

### <a name="remarks"></a>Bemerkungen

Diese Methode erfasst den Windows-Runtime-Kontext des Aufrufers, sodass Fortsetzungen im richtigen Apartment ausgeführt werden können.

Der Wert, der von `use_current` zurückgegeben wird, teilt der Runtime mit, dass die Fortsetzung im erfassten Kontext (STA oder MTA) ausgeführt werden soll, unabhängig davon, ob die Vorgängeraufgabe apartmentfähig ist. Eine apartmentfähige Aufgabe ist eine Aufgabe, die eine `IAsyncInfo`-Windows-Runtime-Schnittstelle entpackt, oder eine Aufgabe, die von einer solchen Aufgabe abgeleitet wird.

Diese Methode ist nur für Windows-Runtime-apps verfügbar.

## <a name="use_default"></a>use_default

Erstellt den standardmäßigen Aufgabenfortsetzungskontext.

```cpp
static task_continuation_context use_default();
```

### <a name="return-value"></a>Rückgabewert

Der standardmäßige Fortsetzungskontext.

### <a name="remarks"></a>Bemerkungen

Der Standardkontext wird verwendet, wenn Sie einen Fortsetzungs Kontext nicht angeben, wenn Sie die `then`-Methode aufzurufen. In Windows-Anwendungen für Windows 7 und älter sowie in Desktopanwendungen für Windows 8 und höher bestimmt die Laufzeit, wo Aufgabenfortsetzungen ausgeführt werden. In einer Windows-Runtime-APP ist der Standard Fortsetzungs Kontext für eine Fortsetzung einer Apartment fähigen Aufgabe jedoch das Apartment, in dem `then` aufgerufen wird.

Eine apartmentfähige Aufgabe ist eine Aufgabe, die eine `IAsyncInfo`-Windows-Runtime-Schnittstelle entpackt, oder eine Aufgabe, die von einer solchen Aufgabe abgeleitet wird. Wenn Sie eine Fortsetzung einer apartmentfähigen Aufgabe in einem Windows-Runtime-STA planen, wird die Fortsetzung daher in diesem STA ausgeführt.

Eine Fortsetzung einer nicht apartmentfähigen Aufgabe wird in einem Kontext ausgeführt, den die Laufzeit auswählt.

## <a name="use_synchronous_execution"></a>task_continuation_context:: use_synchronous_execution

Gibt ein Aufgaben Fortsetzungs Kontext Objekt zurück, das den synchronen Ausführungs Kontext darstellt.

### <a name="syntax"></a>Syntax

```cpp
static task_continuation_context use_synchronous_execution();
```

### <a name="return-value"></a>Rückgabewert

Der synchrone Ausführungs Kontext.

### <a name="remarks"></a>Bemerkungen

Die `use_synchronous_execution`-Methode erzwingt, dass die Fortsetzungs Aufgabe synchron für den Kontext ausgeführt wird, was die Beendigung der Vorgänger Aufgabe bewirkt.

Wenn die vorangehende Aufgabe bereits abgeschlossen ist, wenn die Fortsetzung angefügt ist, wird die Fortsetzung synchron in dem Kontext ausgeführt, der die Fortsetzung anfügt.

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)
