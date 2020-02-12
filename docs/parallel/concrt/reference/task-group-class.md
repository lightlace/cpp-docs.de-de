---
title: task_group-Klasse
ms.date: 07/20/2018
f1_keywords:
- task_group
- PPL/concurrency::task_group
- PPL/concurrency::task_group::task_group
helpviewer_keywords:
- task_group class
ms.openlocfilehash: 60c147f38ddc3936f47aea0cfd1ab1548b382441
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142563"
---
# <a name="task_group-class"></a>task_group-Klasse

Die `task_group`-Klasse stellt eine Auflistung der parallelen Arbeit dar, auf die gewartet oder die abgebrochen werden kann.

## <a name="syntax"></a>Syntax

```cpp
class task_group;
```

## <a name="members"></a>Members

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[task_group](#ctor)|Ist überladen. Erstellt ein neues `task_group`-Objekt.|
|[~ Task_group-Dekonstruktor](#dtor)|Zerstört ein `task_group` -Objekt. Es wird erwartet, dass Sie die `wait`-oder `run_and_wait`-Methode für das-Objekt vor dem Ausführen des Dekonstruktors aufruft, es sei denn, der Dekonstruktor wird aufgrund einer Ausnahme als Ergebnis der Stapel Auflösung ausgeführt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|[cancel](#cancel)|Versucht, die Unterstruktur der Arbeit abzubrechen, die an dieser Aufgaben Gruppe verankert ist. Alle Aufgaben, die für die Aufgaben Gruppe geplant werden, werden, wenn möglich, vorübergehend abgebrochen.|
|[is_canceling](#is_canceling)|Informiert den Aufrufer darüber, ob die Aufgaben Gruppe derzeit in der Mitte eines Abbruchs liegt. Dies weist nicht unbedingt darauf hin, dass die `cancel`-Methode für das `task_group` Objekt aufgerufen wurde (obwohl diese Methode sicherlich für die Rückgabe von `true`qualifiziert ist). Dies kann der Fall sein, wenn das `task_group` Objekt Inline ausgeführt wird und eine Aufgaben Gruppe weiter oben in der Arbeitsstruktur abgebrochen wurde. In Fällen, in denen die Common Language Runtime feststellen kann, dass der Abbruch durch dieses `task_group` Objekt fließt, werden `true` ebenfalls zurückgegeben.|
|[run](#run)|Ist überladen. Plant eine Aufgabe für das `task_group` Objekt. Wenn ein `task_handle` Objekt als Parameter an `run`übergeben wird, ist der Aufrufer für die Verwaltung der Lebensdauer des `task_handle` Objekts verantwortlich. Die Version der-Methode, die einen Verweis auf ein Funktions Objekt als Parameter annimmt, umfasst die Heap Zuordnung innerhalb der Laufzeit, die weniger gut ausgeführt werden kann als die Verwendung der-Version, die einen Verweis auf ein `task_handle`-Objekt annimmt. Die Version, die den-Parameter annimmt, `_Placement` bewirkt, dass die Aufgabe an der durch den-Parameter angegebenen Position vorangeht.|
|[run_and_wait](#run_and_wait)|Ist überladen. Plant, dass eine Aufgabe Inline im aufrufenden Kontext ausgeführt wird, wobei die Unterstützung des `task_group` Objekts für vollständige Abbruch Unterstützung unterstützt wird. Die Funktion wartet dann, bis alle Aufgaben am `task_group` Objekt entweder abgeschlossen oder abgebrochen wurden. Wenn ein `task_handle` Objekt als Parameter an `run_and_wait`übergeben wird, ist der Aufrufer für die Verwaltung der Lebensdauer des `task_handle` Objekts verantwortlich.|
|[Warte](#wait)|Wartet, bis alle Arbeiten am `task_group` Objekt entweder abgeschlossen oder abgebrochen wurden.|

## <a name="remarks"></a>Bemerkungen

Anders als bei der stark eingeschränkten `structured_task_group`-Klasse ist die `task_group`-Klasse weitaus allgemeineres Konstrukt. Sie verfügt nicht über die Einschränkungen, die durch [structured_task_group](structured-task-group-class.md)beschrieben werden. `task_group` Objekte können problemlos Thread übergreifend verwendet und in frei Form Weise verwendet werden. Der Nachteil des `task_group`-Konstrukts besteht darin, dass es möglicherweise nicht ebenso wie das `structured_task_group` Konstrukt für Aufgaben, die eine kleine Menge an Arbeit ausführen, nicht ausgeführt werden kann.

Weitere Informationen finden Sie unter [Aufgaben Parallelität](../task-parallelism-concurrency-runtime.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`task_group`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** ppl. h

**Namespace:** Parallelität

## <a name="cancel"></a>Abbrechen

Versucht, die Unterstruktur der Arbeit abzubrechen, die an dieser Aufgaben Gruppe verankert ist. Alle Aufgaben, die für die Aufgaben Gruppe geplant werden, werden, wenn möglich, vorübergehend abgebrochen.

```cpp
void cancel();
```

### <a name="remarks"></a>Bemerkungen

Weitere Informationen finden Sie unter [Abbruch](../cancellation-in-the-ppl.md).

## <a name="is_canceling"></a>is_canceling

Informiert den Aufrufer darüber, ob die Aufgaben Gruppe derzeit in der Mitte eines Abbruchs liegt. Dies weist nicht unbedingt darauf hin, dass die `cancel`-Methode für das `task_group` Objekt aufgerufen wurde (obwohl diese Methode sicherlich für die Rückgabe von `true`qualifiziert ist). Dies kann der Fall sein, wenn das `task_group` Objekt Inline ausgeführt wird und eine Aufgaben Gruppe weiter oben in der Arbeitsstruktur abgebrochen wurde. In Fällen, in denen die Common Language Runtime feststellen kann, dass der Abbruch durch dieses `task_group` Objekt fließt, werden `true` ebenfalls zurückgegeben.

```cpp
bool is_canceling();
```

### <a name="return-value"></a>Rückgabewert

Ein Hinweis darauf, ob sich das `task_group` Objekt mitten in einem Abbruch befindet (oder sicher ist, dass es in Kürze ist).

### <a name="remarks"></a>Bemerkungen

Weitere Informationen finden Sie unter [Abbruch](../cancellation-in-the-ppl.md).

## <a name="run"></a>Lauf

Plant eine Aufgabe für das `task_group` Objekt. Wenn ein `task_handle` Objekt als Parameter an `run`übergeben wird, ist der Aufrufer für die Verwaltung der Lebensdauer des `task_handle` Objekts verantwortlich. Die Version der-Methode, die einen Verweis auf ein Funktions Objekt als Parameter annimmt, umfasst die Heap Zuordnung innerhalb der Laufzeit, die weniger gut ausgeführt werden kann als die Verwendung der-Version, die einen Verweis auf ein `task_handle`-Objekt annimmt. Die Version, die den-Parameter annimmt, `_Placement` bewirkt, dass die Aufgabe an der durch den-Parameter angegebenen Position vorangeht.

```cpp
template<
   typename _Function
>
void run(
   const _Function& _Func
);

template<
   typename _Function
>
void run(
   const _Function& _Func,
   location& _Placement
);

template<
   typename _Function
>
void run(
   task_handle<_Function>& _Task_handle
);

template<
   typename _Function
>
void run(
   task_handle<_Function>& _Task_handle,
   location& _Placement
);
```

### <a name="parameters"></a>Parameter

*_Function*<br/>
Der Typ des Funktions Objekts, das aufgerufen wird, um den Text des Task Handles auszuführen.

*_Func*<br/>
Eine Funktion, die aufgerufen wird, um den Textkörper der Aufgabe aufzurufen. Hierbei kann es sich um einen Lambda-Ausdruck oder ein anderes Objekt handeln, das eine Version des Funktions aufrufoperators mit der Signatur `void operator()()`unterstützt.

*_Placement*<br/>
Ein Verweis auf den Speicherort, an dem die durch den `_Func`-Parameter dargestellte Aufgabe ausgeführt werden soll.

*_Task_handle*<br/>
Ein Handle für die geplante Arbeit. Beachten Sie, dass der Aufrufer für die Lebensdauer dieses Objekts zuständig ist. Die Laufzeit erwartet, dass Sie aktiv bleibt, bis entweder die `wait` oder `run_and_wait` Methode für dieses `task_group` Objekt aufgerufen wurde.

### <a name="remarks"></a>Bemerkungen

Die Laufzeit plant, dass die bereitgestellte Arbeitsfunktion zu einem späteren Zeitpunkt ausgeführt wird. Dies kann nach der Rückgabe der aufrufenden Funktion erfolgen. Diese Methode verwendet ein [task_handle](task-handle-class.md) Objekt, um eine Kopie der bereitgestellten Arbeitsfunktion zu speichern. Daher werden alle Zustandsänderungen, die in einem Funktions Objekt auftreten, das Sie an diese Methode übergeben, nicht in Ihrer Kopie des Funktions Objekts angezeigt. Stellen Sie außerdem sicher, dass die Lebensdauer von Objekten, die Sie als Zeiger oder als Verweis an die Arbeitsfunktion übergeben, gültig bleibt, bis die Arbeitsfunktion zurückgibt.

Wenn die `task_group` als Ergebnis der Stapel Auflösung von einer Ausnahme zerstört wird, müssen Sie nicht garantieren, dass ein-oder `run_and_wait`-Methode `wait` aufgerufen wurde. In diesem Fall wird der Dekonstruktor entsprechend abbrechen und darauf warten, dass die durch den `_Task_handle`-Parameter dargestellte Aufgabe beendet wird.

Die-Methode löst eine [Invalid_multiple_scheduling](invalid-multiple-scheduling-class.md) Ausnahme aus, wenn das vom `_Task_handle`-Parameter angegebene Aufgaben handle bereits über die `run`-Methode für ein Aufgaben Gruppen Objekt geplant wurde und es keinen zwischenzeitlichen Aufrufen der `wait`-oder `run_and_wait`-Methode für diese Aufgaben Gruppe gab.

## <a name="run_and_wait"></a>run_and_wait

Plant, dass eine Aufgabe Inline im aufrufenden Kontext ausgeführt wird, wobei die Unterstützung des `task_group` Objekts für vollständige Abbruch Unterstützung unterstützt wird. Die Funktion wartet dann, bis alle Aufgaben am `task_group` Objekt entweder abgeschlossen oder abgebrochen wurden. Wenn ein `task_handle` Objekt als Parameter an `run_and_wait`übergeben wird, ist der Aufrufer für die Verwaltung der Lebensdauer des `task_handle` Objekts verantwortlich.

```cpp
template<
   class _Function
>
task_group_status run_and_wait(
   task_handle<_Function>& _Task_handle
);

template<
   class _Function
>
task_group_status run_and_wait(
   const _Function& _Func
);
```

### <a name="parameters"></a>Parameter

*_Function*<br/>
Der Typ des Funktions Objekts, das aufgerufen wird, um den Hauptteil der Aufgabe auszuführen.

*_Task_handle*<br/>
Ein Handle für die Aufgabe, die Inline im aufrufenden Kontext ausgeführt wird. Beachten Sie, dass der Aufrufer für die Lebensdauer dieses Objekts zuständig ist. Die Laufzeit wird fortgesetzt, bis die Ausführung der `run_and_wait`-Methode abgeschlossen ist.

*_Func*<br/>
Eine Funktion, die aufgerufen wird, um den Hauptteil der Arbeit aufzurufen. Hierbei kann es sich um einen Lambda-Ausdruck oder ein anderes Objekt handeln, das eine Version des Funktions aufrufoperators mit der Signatur `void operator()()`unterstützt.

### <a name="return-value"></a>Rückgabewert

Gibt an, ob der Warte Vorgang durch einen expliziten Abbruch Vorgang oder durch Auslösen einer Ausnahme von einer seiner Aufgaben abgebrochen wurde oder ob die Aufgaben Gruppe abgebrochen wurde. Weitere Informationen finden Sie unter [Task_group_status](concurrency-namespace-enums.md#task_group_status).

### <a name="remarks"></a>Bemerkungen

Beachten Sie, dass mindestens eine der Aufgaben, die für dieses `task_group` Objekt geplant sind, im aufrufenden Kontext Inline ausgeführt werden kann.

Wenn mindestens eine der Aufgaben, die für dieses `task_group` Objekt geplant sind, eine Ausnahme auslöst, wählt die Common Language Runtime eine Ausnahme von Ihrer Wahl aus und gibt Sie aus dem Aufrufen der `run_and_wait`-Methode weiter.

Bei der Rückgabe von der `run_and_wait`-Methode für ein `task_group`-Objekt setzt die Laufzeit das Objekt auf einen fehlerfreien Zustand zurück, in dem es wieder verwendet werden kann. Dies gilt auch für den Fall, dass das `task_group` Objekt abgebrochen wurde.

Im nicht außergewöhnlichen Ausführungs Pfad haben Sie die Möglichkeit, entweder diese Methode oder die `wait` Methode aufzurufen, bevor der Dekonstruktor des `task_group` ausgeführt wird.

## <a name="ctor"></a>task_group

Erstellt ein neues `task_group`-Objekt.

```cpp
task_group();

task_group(
   cancellation_token _CancellationToken
);
```

### <a name="parameters"></a>Parameter

*_CancellationToken*<br/>
Ein Abbruch Token, das dieser Aufgaben Gruppe zugeordnet werden soll. Die Aufgaben Gruppe wird abgebrochen, wenn das Token abgebrochen wird.

### <a name="remarks"></a>Bemerkungen

Der Konstruktor, der ein Abbruch Token annimmt, erstellt eine `task_group`, die abgebrochen wird, wenn die dem Token zugeordnete Quelle abgebrochen wird. Das Bereitstellen eines expliziten Abbruch Tokens isoliert diese Aufgaben Gruppe auch von der Teilnahme an einem impliziten Abbruch von einer übergeordneten Gruppe mit einem anderen Token oder ohne Token.

## <a name="dtor"></a>~ Task_group

Zerstört ein `task_group` -Objekt. Es wird erwartet, dass Sie die `wait`-oder `run_and_wait`-Methode für das-Objekt vor dem Ausführen des Dekonstruktors aufruft, es sei denn, der Dekonstruktor wird aufgrund einer Ausnahme als Ergebnis der Stapel Auflösung ausgeführt.

```cpp
~task_group();
```

### <a name="remarks"></a>Bemerkungen

Wenn der Dekonstruktor als Ergebnis der normalen Ausführung ausgeführt wird (z. b. aufgrund einer Ausnahme keine Stapel entruppe) und weder die `wait` noch `run_and_wait` Methoden aufgerufen wurden, kann der Dekonstruktor eine [Missing_wait](missing-wait-class.md) Ausnahme auslösen.

## <a name="wait"></a>Warte

Wartet, bis alle Arbeiten am `task_group` Objekt entweder abgeschlossen oder abgebrochen wurden.

```cpp
task_group_status wait();
```

### <a name="return-value"></a>Rückgabewert

Gibt an, ob der Warte Vorgang durch einen expliziten Abbruch Vorgang oder durch Auslösen einer Ausnahme von einer seiner Aufgaben abgebrochen wurde oder ob die Aufgaben Gruppe abgebrochen wurde. Weitere Informationen finden Sie unter [Task_group_status](concurrency-namespace-enums.md#task_group_status).

### <a name="remarks"></a>Bemerkungen

Beachten Sie, dass mindestens eine der Aufgaben, die für dieses `task_group` Objekt geplant sind, im aufrufenden Kontext Inline ausgeführt werden kann.

Wenn mindestens eine der Aufgaben, die für dieses `task_group` Objekt geplant sind, eine Ausnahme auslöst, wählt die Common Language Runtime eine Ausnahme von Ihrer Wahl aus und gibt Sie aus dem Aufrufen der `wait`-Methode weiter.

Wenn Sie `wait` für ein `task_group`-Objekt aufrufen, wird es auf einen sauberen Zustand zurückgesetzt, in dem es wieder verwendet werden kann. Dies gilt auch für den Fall, dass das `task_group` Objekt abgebrochen wurde.

Im nicht außergewöhnlichen Ausführungs Pfad haben Sie die Möglichkeit, entweder diese Methode oder die `run_and_wait` Methode aufzurufen, bevor der Dekonstruktor des `task_group` ausgeführt wird.

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[structured_task_group-Klasse](structured-task-group-class.md)<br/>
[task_handle-Klasse](task-handle-class.md)
