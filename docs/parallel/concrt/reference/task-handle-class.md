---
title: task_handle-Klasse
ms.date: 03/27/2019
f1_keywords:
- task_handle
- PPL/concurrency::task_handle
- PPL/concurrency::task_handle::task_handle
helpviewer_keywords:
- task_handle class
ms.assetid: 74a34b15-708b-4231-a509-947874292b13
ms.openlocfilehash: 8528bc212603484be9325ed967e9475e4faa1348
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2019
ms.locfileid: "58565099"
---
# <a name="taskhandle-class"></a>task_handle-Klasse

Die `task_handle`-Klasse stellt ein einzelnes paralleles Arbeitselement dar. Sie kapselt die Anweisungen und die zum Ausführen eines Teils der Arbeit erforderlichen Daten.

## <a name="syntax"></a>Syntax

```
template<
    typename _Function
>
class task_handle : public ::Concurrency::details::_UnrealizedChore;
```

#### <a name="parameters"></a>Parameter

*_Function*<br/>
Der Typ des Funktionsobjekts, die aufgerufen werden, um die Arbeit, dargestellt durch Ausführen der `task_handle` Objekt.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[task_handle](#task_handle)|Erstellt ein neues `task_handle`-Objekt. Die Aktionen der Aufgabe wird ausgeführt, durch den Aufruf der Funktion, die als Parameter an den Konstruktor angegeben.|
|[~ Task_handle-Destruktor](#dtor)|Zerstört das `task_handle`-Objekt.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[Operator()](#task_handle__operator_call)|Der Funktionsaufrufoperator, den von der Laufzeit aufgerufen, um die Arbeit des Aufgabenhandles auszuführen.|

## <a name="remarks"></a>Hinweise

`task_handle` Objekte können verwendet werden, in Verbindung mit einem `structured_task_group` oder eine allgemeinere `task_group` Objekt, das Arbeit in Parallele Aufgaben aufzuteilen. Weitere Informationen finden Sie unter [Aufgabenparallelität](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).

Beachten Sie, dass der Ersteller einer `task_handle` Objekt ist verantwortlich für die Verwaltung der Lebensdauer des erstellten `task_handle` Objekt, bis sie von der Concurrency Runtime nicht mehr benötigt wird. In der Regel bedeutet dies, dass die `task_handle` -Objekt nicht zerstört werden darf, bis entweder der `wait` oder `run_and_wait` Methode der `task_group` oder `structured_task_group` , die sie in der Warteschlange befindet aufgerufen wurde.

`task_handle` Objekte werden in der Regel in Verbindung mit C++-Lambda-Ausdrücken verwendet. Da Sie nicht, dass den tatsächliche Typ des Lambda-Ausdrucks wissen, der [Make_task](concurrency-namespace-functions.md#make_task) Funktion wird in der Regel zum Erstellen einer `task_handle` Objekt.

Die Common Language Runtime erstellt eine Kopie der Arbeitsfunktion, die Sie zum Übergeben einer `task_handle` Objekt. Aus diesem Grund Objekt von Zustandsänderungen, die in einer Funktion auftreten, dass Sie zum Übergeben einer `task_handle` Objekt wird nicht angezeigt, in der Kopie des Funktionsobjekts.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`task_handle`

## <a name="requirements"></a>Anforderungen

**Header:** ppl.h

**Namespace:** Parallelität

##  <a name="task_handle__operator_call"></a> operator()

Der Funktionsaufrufoperator, den von der Laufzeit aufgerufen, um die Arbeit des Aufgabenhandles auszuführen.

```
void operator()() const;
```

## <a name="taskhandle"></a>task_handle

Erstellt ein neues `task_handle`-Objekt. Die Aktionen der Aufgabe wird ausgeführt, durch den Aufruf der Funktion, die als Parameter an den Konstruktor angegeben.

```
task_handle(const _Function& _Func);
```

### <a name="parameters"></a>Parameter

*_Func*<br/>
Die Funktion, die aufgerufen werden, um die Arbeit, dargestellt durch Ausführen der `task_handle` Objekt. Dies ist möglicherweise eine Lambda-Funktion, ein Zeiger auf eine Funktion oder ein anderes Objekt, das eine Version von den Funktionsaufrufoperator mit der Signatur unterstützt `void operator()()`.

### <a name="remarks"></a>Hinweise

Die Laufzeit erstellt eine Kopie der Arbeitsfunktion, die Sie an den Konstruktor übergeben. Aus diesem Grund Objekt von Zustandsänderungen, die in einer Funktion auftreten, dass Sie zum Übergeben einer `task_handle` Objekt wird nicht angezeigt, in der Kopie des Funktionsobjekts.

##  <a name="dtor"></a> ~task_handle

Zerstört das `task_handle`-Objekt.

```
~task_handle();
```

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[task_group-Klasse](task-group-class.md)<br/>
[structured_task_group-Klasse](structured-task-group-class.md)
