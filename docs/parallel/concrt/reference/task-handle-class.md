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
ms.openlocfilehash: a61e72f14448d5033d5be9069ffeec7d3bb08061
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142558"
---
# <a name="task_handle-class"></a>task_handle-Klasse

Die `task_handle`-Klasse stellt ein einzelnes paralleles Arbeitselement dar. Sie kapselt die Anweisungen und die zum Ausführen eines Teils der Arbeit erforderlichen Daten.

## <a name="syntax"></a>Syntax

```cpp
template<
    typename _Function
>
class task_handle : public ::Concurrency::details::_UnrealizedChore;
```

### <a name="parameters"></a>Parameter

*_Function*<br/>
Der Typ des Funktions Objekts, das aufgerufen wird, um die durch das `task_handle` Objekt dargestellte Arbeit auszuführen.

## <a name="members"></a>Members

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[task_handle](#task_handle)|Erstellt ein neues `task_handle`-Objekt. Die Aufgabe der Aufgabe wird durch Aufrufen der Funktion ausgeführt, die als Parameter für den Konstruktor angegeben ist.|
|[~ task_handle-Dekonstruktor](#dtor)|Zerstört das `task_handle`-Objekt.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[Operator()](#task_handle__operator_call)|Der Funktionsaufruf Operator, den die Common Language Runtime aufruft, um die Arbeit des Task Handles auszuführen.|

## <a name="remarks"></a>Bemerkungen

`task_handle` Objekte können in Verbindung mit einem `structured_task_group` oder einem allgemeineren `task_group` Objekt verwendet werden, um die Arbeit in Parallele Aufgaben zu zerlegen. Weitere Informationen finden Sie unter [Aufgaben Parallelität](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).

Beachten Sie, dass der Ersteller eines `task_handle` Objekts für die Beibehaltung der Lebensdauer des erstellten `task_handle` Objekts verantwortlich ist, bis es vom Concurrency Runtime nicht mehr benötigt wird. In der Regel bedeutet dies, dass das `task_handle` Objekt nicht destrukturiert werden darf, bis entweder die `wait` oder `run_and_wait` Methode der `task_group` oder `structured_task_group`, in der es sich in der Warteschlange befindet, aufgerufen wurde.

`task_handle` Objekte werden in der Regel in Verbindung C++ mit Lambdas verwendet. Da Sie den wahren Typ des Lambda-Objekts nicht kennen, wird die [Make_task](concurrency-namespace-functions.md#make_task) -Funktion normalerweise verwendet, um ein `task_handle`-Objekt zu erstellen.

Die Laufzeit erstellt eine Kopie der Arbeitsfunktion, die Sie an ein `task_handle`-Objekt übergeben. Daher werden alle Zustandsänderungen, die in einem Funktions Objekt auftreten, das Sie an ein `task_handle` Objekt übergeben, nicht in Ihrer Kopie des Funktions Objekts angezeigt.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`task_handle`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** ppl. h

**Namespace:** Parallelität

## <a name="task_handle__operator_call"></a>Operator ()

Der Funktionsaufruf Operator, den die Common Language Runtime aufruft, um die Arbeit des Task Handles auszuführen.

```cpp
void operator()() const;
```

## <a name="task_handle"></a>task_handle

Erstellt ein neues `task_handle`-Objekt. Die Aufgabe der Aufgabe wird durch Aufrufen der Funktion ausgeführt, die als Parameter für den Konstruktor angegeben ist.

```cpp
task_handle(const _Function& _Func);
```

### <a name="parameters"></a>Parameter

*_Func*<br/>
Die Funktion, die aufgerufen wird, um die durch das `task_handle` Objekt dargestellte Arbeit auszuführen. Hierbei kann es sich um einen Lambda-Funktor, einen Zeiger auf eine Funktion oder ein beliebiges Objekt handeln, das eine Version des Funktions aufrufoperators mit der Signatur `void operator()()`unterstützt.

### <a name="remarks"></a>Bemerkungen

Die Laufzeit erstellt eine Kopie der Arbeitsfunktion, die Sie an den-Konstruktor übergeben. Daher werden alle Zustandsänderungen, die in einem Funktions Objekt auftreten, das Sie an ein `task_handle` Objekt übergeben, nicht in Ihrer Kopie des Funktions Objekts angezeigt.

## <a name="dtor"></a>~ task_handle

Zerstört das `task_handle`-Objekt.

```cpp
~task_handle();
```

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[task_group-Klasse](task-group-class.md)<br/>
[structured_task_group-Klasse](structured-task-group-class.md)
