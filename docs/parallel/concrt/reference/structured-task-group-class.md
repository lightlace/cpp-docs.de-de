---
title: structured_task_group-Klasse
ms.date: 11/04/2016
f1_keywords:
- structured_task_group
- PPL/concurrency::structured_task_group
- PPL/concurrency::structured_task_group::structured_task_group
- PPL/concurrency::structured_task_group::cancel
- PPL/concurrency::structured_task_group::is_canceling
- PPL/concurrency::structured_task_group::run
- PPL/concurrency::structured_task_group::run_and_wait
- PPL/concurrency::structured_task_group::wait
helpviewer_keywords:
- structured_task_group class
ms.assetid: 742afa8c-c7b6-482c-b0ba-04c809927b22
ms.openlocfilehash: 27610539ab500a113ea41021744c55425fe9cd9b
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57299292"
---
# <a name="structuredtaskgroup-class"></a>structured_task_group-Klasse

Die `structured_task_group`-Klasse stellt eine stark strukturierte Auflistung paralleler Arbeit dar. Sie können einzelne parallele Aufgaben mithilfe von `structured_task_group`-Objekten in eine `task_handle` stellen und warten, bis sie abgeschlossen werden, oder Sie können die Aufgabengruppe abbrechen, bevor deren Ausführung beendet wird, wodurch auch alle Aufgaben abgebrochen werden, deren Ausführung nicht gestartet wurde.

## <a name="syntax"></a>Syntax

```
class structured_task_group;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[structured_task_group](#ctor)|Überladen. Erstellt ein neues `structured_task_group`-Objekt.|
|[~ Structured_task_group-Destruktor](#dtor)|Zerstört ein `structured_task_group`-Objekt. Es wird erwartet, rufen Sie entweder die `wait` oder `run_and_wait` Methode für das Objekt vor der Destruktor ausgeführt, es sei denn, der Destruktor ausgeführt wird als Ergebnis des stapelentladung aufgrund einer Ausnahme.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[cancel](#cancel)|Macht die Teilstruktur des Arbeit Rooting manipuliert wurde, klicken Sie auf diese Aufgabengruppe abbrechen versucht. Jede Aufgabe, die für die Aufgabengruppe geplant werden transitiv abgebrochen, wenn möglich.|
|[is_canceling](#is_canceling)|Informiert den Aufrufer, und zwar unabhängig davon, ob die Aufgabengruppe derzeit sich mitten in der ein Abbruch ist. Dies bedeutet nicht unbedingt, die die `cancel` Methode wurde aufgerufen, auf die `structured_task_group` Objekt (auch wenn diese Methode zurückgibt, das z. B. sicherlich qualifiziert ist **"true"**). Es kann der Fall sein, die die `structured_task_group` Objekt Inline ausführt und eine Aufgabengruppe weiter oben in der Arbeitsstruktur wurde abgebrochen. In Fällen, z. B. diesen, in denen die Laufzeit voraus, die dies Abbruch durchlaufen wird bestimmen kann `structured_task_group` Objekt **"true"** wird ebenfalls zurückgegeben werden.|
|[run](#run)|Überladen. Plant eine Aufgabe für die `structured_task_group` Objekt. Der Aufrufer verwaltet die Lebensdauer der `task_handle` Objekt übergeben wurde die `_Task_handle` Parameter. Die Version, die den Parameter akzeptiert `_Placement` bewirkt, dass der Task Blockcontainer ausführen an der Position, die durch diesen Parameter angegeben werden.|
|[run_and_wait](#run_and_wait)|Überladen. Plant eine Aufgabe Inline im aufrufenden Kontext ausgeführt werden, mit der Hilfe von der `structured_task_group` -Objekt für die vollständige Abbruch-Unterstützung. Wenn eine `task_handle` Objekt wird als Parameter übergeben `run_and_wait`, der Aufrufer ist verantwortlich für die Verwaltung der Lebensdauer der `task_handle` Objekt. Die Funktion dann wartet, bis die gesamte Arbeit der `structured_task_group` Objekt wurde entweder abgeschlossen oder abgebrochen wurde.|
|[wait](#wait)|Wartet, bis die gesamte Arbeit der `structured_task_group` abgeschlossen oder abgebrochen wird.|

## <a name="remarks"></a>Hinweise

Es gibt eine Reihe von schweren Einschränkungen zur Verwendung der einen `structured_task_group` Objekt, um die Leistung zu erzielen:

- Ein einzelnes `structured_task_group` Objekt kann nicht von mehreren Threads verwendet werden. Alle Vorgänge für eine `structured_task_group` Objekt durch den Thread, der Erstellung des Objekts durchgeführt werden muss. Die zwei Ausnahmen von dieser Regel werden die Memberfunktionen `cancel` und `is_canceling`. Das Objekt möglicherweise nicht in der Erfassungsliste eines Lambda-Ausdrucks und innerhalb einer Aufgabe verwendet werden, es sei denn, der Task eine der Abbruchoperationen verwendet werden.

- Alle geplanten Aufgaben eine `structured_task_group` -Objekt geplant sind, mithilfe des `task_handle` Objekte, die Sie explizit die Lebensdauer des verwalten müssen.

- Mehrere Gruppen können nur in absolut geschachtelter Reihenfolge verwendet werden. Wenn zwei `structured_task_group` -Objekte deklariert werden, das zweite Argument (den inneren Knoten) deklariert wird zerstört werden muss, bevor eine Methode, mit Ausnahme von `cancel` oder `is_canceling` für das erste Abonnement aufgerufen wird (äußeren Ausdrucks). Diese Bedingung gilt für beide die Groß-/Kleinschreibung einfach Deklarieren mehrerer `structured_task_group` Objekte innerhalb der gleichen oder funktional geschachtelte Bereiche als auch eine Aufgabe, die in die Warteschlange eingereiht wurde die Groß-/Kleinschreibung der `structured_task_group` über die `run` oder `run_and_wait` Methoden.

- Im Gegensatz zu den allgemeinen `task_group` Klasse, alle Zustände in der `structured_task_group` Klasse sind endgültig. Nachdem Sie die Aufgaben der Gruppe in der Warteschlange und gewartet, bis sie abgeschlossen haben, können Sie nicht die gleiche Gruppe wieder verwenden.

Weitere Informationen finden Sie unter [Aufgabenparallelität](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`structured_task_group`

## <a name="requirements"></a>Anforderungen

**Header:** ppl.h

**Namespace:** Parallelität

##  <a name="cancel"></a> Abbrechen

Macht die Teilstruktur des Arbeit Rooting manipuliert wurde, klicken Sie auf diese Aufgabengruppe abbrechen versucht. Jede Aufgabe, die für die Aufgabengruppe geplant werden transitiv abgebrochen, wenn möglich.

```
void cancel();
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [Abbruch](../../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation).

##  <a name="is_canceling"></a> is_canceling

Informiert den Aufrufer, und zwar unabhängig davon, ob die Aufgabengruppe derzeit sich mitten in der ein Abbruch ist. Dies bedeutet nicht unbedingt, die die `cancel` Methode wurde aufgerufen, auf die `structured_task_group` Objekt (auch wenn diese Methode zurückgibt, das z. B. sicherlich qualifiziert ist **"true"**). Es kann der Fall sein, die die `structured_task_group` Objekt Inline ausführt und eine Aufgabengruppe weiter oben in der Arbeitsstruktur wurde abgebrochen. In Fällen, z. B. diesen, in denen die Laufzeit voraus, die dies Abbruch durchlaufen wird bestimmen kann `structured_task_group` Objekt **"true"** wird ebenfalls zurückgegeben werden.

```
bool is_canceling();
```

### <a name="return-value"></a>Rückgabewert

Angabe, ob die `structured_task_group` Objekt in ein Abbruch ist (oder gewährleistet ist in Kürze).

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [Abbruch](../../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation).

##  <a name="run"></a> Führen Sie

Plant eine Aufgabe für die `structured_task_group` Objekt. Der Aufrufer verwaltet die Lebensdauer der `task_handle` Objekt übergeben wurde die `_Task_handle` Parameter. Die Version, die den Parameter akzeptiert `_Placement` bewirkt, dass der Task Blockcontainer ausführen an der Position, die durch diesen Parameter angegeben werden.

```
template<class _Function>
void run(
    task_handle<_Function>& _Task_handle);

template<class _Function>
void run(
    task_handle<_Function>& _Task_handle,
    location& _Placement);
```

### <a name="parameters"></a>Parameter

*_Function*<br/>
Der Typ des Funktionsobjekts, das aufgerufen wird, um den Text der Aufgabenhandle auszuführen.

*_Task_handle*<br/>
Ein Handle für die Arbeit geplant. Beachten Sie, dass der Aufrufer die Verantwortung für die Lebensdauer dieses Objekts verfügt. Die Laufzeit ist so lange Sie erwartet, bis entweder die Gültigkeitsdauer der `wait` oder `run_and_wait` für diese Methode aufgerufen wurde `structured_task_group` Objekt.

*_Placement*<br/>
Ein Verweis auf den Speicherort, in denen die Aufgabe, durch dargestellt, die `_Task_handle` Parameter sollte ausgeführt werden.

### <a name="remarks"></a>Hinweise

Die Laufzeit erstellt eine Kopie der Arbeitsfunktion, die Sie für diese Methode übergeben. Alle Zustandsänderungen, die in ein Funktionsobjekt auftreten, die Sie für diese Methode übergeben, werden nicht in der Kopie des Funktionsobjekts angezeigt.

Wenn die `structured_task_group` Destructs als Ergebnis der stapelentladung von einer Ausnahme, Sie müssen nicht garantieren, dass ein Aufruf entweder wurde die `wait` oder `run_and_wait` Methode. In diesem Fall der Destruktor wird entsprechend abgebrochen und warten, bis die Aufgabe, dargestellt durch die `_Task_handle` Parameter ausführen.

Löst ein [Invalid_multiple_scheduling](invalid-multiple-scheduling-class.md) -Ausnahme aus, wenn der Task behandeln Angabe durch die `_Task_handle` Parameter wurde bereits einem Aufgabengruppenobjekt über geplant wurde die `run` Methode und es wurde keine zwischenzeitlich ein Aufruf von entweder die `wait` oder `run_and_wait` Methode für diese Aufgabengruppe.

##  <a name="run_and_wait"></a> run_and_wait

Plant eine Aufgabe Inline im aufrufenden Kontext ausgeführt werden, mit der Hilfe von der `structured_task_group` -Objekt für die vollständige Abbruch-Unterstützung. Wenn eine `task_handle` Objekt wird als Parameter übergeben `run_and_wait`, der Aufrufer ist verantwortlich für die Verwaltung der Lebensdauer der `task_handle` Objekt. Die Funktion dann wartet, bis die gesamte Arbeit der `structured_task_group` Objekt wurde entweder abgeschlossen oder abgebrochen wurde.

```
template<class _Function>
task_group_status run_and_wait(task_handle<_Function>& _Task_handle);

template<class _Function>
task_group_status run_and_wait(const _Function& _Func);
```

### <a name="parameters"></a>Parameter

*_Function*<br/>
Der Typ des Funktionsobjekts, das aufgerufen wird, um die Aufgabe auszuführen.

*_Task_handle*<br/>
Ein Handle für die Aufgabe, die Inline im aufrufenden Kontext ausgeführt wird. Beachten Sie, dass der Aufrufer die Verantwortung für die Lebensdauer dieses Objekts verfügt. Die Laufzeit ist so lange Sie erwartet, bis die Gültigkeitsdauer der `run_and_wait` -Methode die Ausführung beendet.

*_Func*<br/>
Eine Funktion, die aufgerufen wird, um den Text der Arbeit aufzurufen. Dies ist möglicherweise ein Lambda-Ausdruck oder ein anderes Objekt, das eine Version von den Funktionsaufrufoperator mit der Signatur unterstützt `void operator()()`.

### <a name="return-value"></a>Rückgabewert

Ein Anzeichen dafür, ob der Wartevorgang erfüllt wurde oder die Aufgabengruppe wurde, entweder eine explizite Abbruchvorgang oder eine Ausnahme ausgelöst wird, von einer der Tasks abgebrochen. Weitere Informationen finden Sie unter [Task_group_status](concurrency-namespace-enums.md)

### <a name="remarks"></a>Hinweise

Beachten Sie, dass eine oder mehrere dieser geplante Aufgaben `structured_task_group` Objekt kann Inline im aufrufenden Kontext ausgeführt.

Wenn eine oder mehrere dieser geplante Aufgaben `structured_task_group` Objekt löst eine Ausnahme aus. die Laufzeit wird, wählen Sie eine solche Ausnahme seiner Wahl und aus dem Aufruf zum Weitergeben der `run_and_wait` Methode.

Nachdem Sie diese Funktion zurückgibt, die `structured_task_group` Objekt wird in einem abschließenden Zustand betrachtet und sollte nicht verwendet werden. Beachten Sie, dass eine nach der Verwendung der `run_and_wait` Methodenrückgabe führt zu nicht definiertem Verhalten.

In den Pfad ohne Ausnahmen der Ausführung haben Sie eine zwingende Vorgabe entweder diese Methode aufrufen oder die `wait` -Methode auf, bevor der Destruktor von der `structured_task_group` ausgeführt wird.

##  <a name="ctor"></a> structured_task_group

Erstellt ein neues `structured_task_group`-Objekt.

```
structured_task_group();

structured_task_group(cancellation_token _CancellationToken);
```

### <a name="parameters"></a>Parameter

*_CancellationToken*<br/>
Ein Abbruchtoken, das diese strukturierten Taskgruppe zugeordnet werden soll. Der strukturierten Taskgruppe werden abgebrochen, wenn das Token abgebrochen wird.

### <a name="remarks"></a>Hinweise

Der Konstruktor, die ein Abbruchtoken akzeptiert erstellt eine `structured_task_group` wird, die abgebrochen werden, wenn die Quelle mit dem Token verknüpften abgebrochen wird. Als explizites Abbruchtoken bereitstellen, werden auch diese strukturierten Taskgruppe aus der Einbeziehung in einen impliziten Abbruch von einer übergeordneten Gruppe mit einem anderen Token "oder" kein Token isoliert.

##  <a name="dtor"></a> ~structured_task_group

Zerstört ein `structured_task_group`-Objekt. Es wird erwartet, rufen Sie entweder die `wait` oder `run_and_wait` Methode für das Objekt vor der Destruktor ausgeführt, es sei denn, der Destruktor ausgeführt wird als Ergebnis des stapelentladung aufgrund einer Ausnahme.

```
~structured_task_group();
```

### <a name="remarks"></a>Hinweise

Wenn der Destruktor ausgeführt wird, als Ergebnis der normalen programmausführung (z. B. keine stapelentladung aufgrund einer Ausnahme) und weder der `wait` noch `run_and_wait` Methoden aufgerufen wurden, der Destruktor Auslösen einer [Missing_wait](missing-wait-class.md) Diese Ausnahme.

##  <a name="wait"></a> Warte

Wartet, bis die gesamte Arbeit der `structured_task_group` abgeschlossen oder abgebrochen wird.

```
task_group_status wait();
```

### <a name="return-value"></a>Rückgabewert

Ein Anzeichen dafür, ob der Wartevorgang erfüllt wurde oder die Aufgabengruppe wurde, entweder eine explizite Abbruchvorgang oder eine Ausnahme ausgelöst wird, von einer der Tasks abgebrochen. Weitere Informationen finden Sie unter [Task_group_status](concurrency-namespace-enums.md)

### <a name="remarks"></a>Hinweise

Beachten Sie, dass eine oder mehrere dieser geplante Aufgaben `structured_task_group` Objekt kann Inline im aufrufenden Kontext ausgeführt.

Wenn eine oder mehrere dieser geplante Aufgaben `structured_task_group` Objekt löst eine Ausnahme aus. die Laufzeit wird, wählen Sie eine solche Ausnahme seiner Wahl und aus dem Aufruf zum Weitergeben der `wait` Methode.

Nachdem Sie diese Funktion zurückgibt, die `structured_task_group` Objekt wird in einem abschließenden Zustand betrachtet und sollte nicht verwendet werden. Beachten Sie, dass eine nach der Verwendung der `wait` Methodenrückgabe führt zu nicht definiertem Verhalten.

In den Pfad ohne Ausnahmen der Ausführung haben Sie eine zwingende Vorgabe entweder diese Methode aufrufen oder die `run_and_wait` -Methode auf, bevor der Destruktor von der `structured_task_group` ausgeführt wird.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[task_group-Klasse](task-group-class.md)<br/>
[task_handle-Klasse](task-handle-class.md)
