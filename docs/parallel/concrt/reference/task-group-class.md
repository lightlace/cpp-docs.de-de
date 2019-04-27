---
title: task_group-Klasse
ms.date: 07/20/2018
f1_keywords:
- task_group
- PPL/concurrency::task_group
- PPL/concurrency::task_group::task_group
helpviewer_keywords:
- task_group class
ms.openlocfilehash: 545b368b3042da74a42db5a6ea30e97054d5fd03
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62180179"
---
# <a name="taskgroup-class"></a>task_group-Klasse

Die `task_group`-Klasse stellt eine Auflistung der parallelen Arbeit dar, auf die gewartet oder die abgebrochen werden kann.

## <a name="syntax"></a>Syntax

```
class task_group;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[task_group](#ctor)|Überladen. Erstellt ein neues `task_group`-Objekt.|
|[~ Task_group-Destruktor](#dtor)|Zerstört ein `task_group`-Objekt. Es wird erwartet, rufen Sie entweder die `wait` oder `run_and_wait` Methode für das Objekt vor der Destruktor ausgeführt, es sei denn, der Destruktor als Ergebnis der stapelentladung aufgrund einer Ausnahme ausgeführt wird.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[cancel](#cancel)|Macht die Teilstruktur des Arbeit Rooting manipuliert wurde, klicken Sie auf diese Aufgabengruppe abbrechen versucht. Jede Aufgabe, die für die Aufgabengruppe geplant werden transitiv abgebrochen, wenn möglich.|
|[is_canceling](#is_canceling)|Informiert den Aufrufer, und zwar unabhängig davon, ob die Aufgabengruppe derzeit sich mitten in der ein Abbruch ist. Dies bedeutet nicht unbedingt, die die `cancel` Methode wurde aufgerufen, auf die `task_group` Objekt (auch wenn diese Methode zurückgibt, das z. B. sicherlich qualifiziert ist `true`). Es kann der Fall sein, die die `task_group` Objekt Inline ausführt und eine Aufgabengruppe weiter oben in der Arbeitsstruktur wurde abgebrochen. In Fällen, z. B. diesen, in denen die Laufzeit voraus, die dies Abbruch durchlaufen wird bestimmen kann `task_group` Objekt `true` wird ebenfalls zurückgegeben werden.|
|[run](#run)|Überladen. Plant eine Aufgabe für die `task_group` Objekt. Wenn eine `task_handle` Objekt wird als Parameter übergeben `run`, der Aufrufer ist verantwortlich für die Verwaltung der Lebensdauer der `task_handle` Objekt. Führen Sie die Version der Methode, die einen Verweis auf ein Funktionsobjekt akzeptiert, wie ein Parameter Heapzuordnung in der Laufzeit enthält, der möglicherweise nicht so gut wie mit der Version, die akzeptiert einen Verweis auf eine `task_handle` Objekt. Die Version, die den Parameter akzeptiert `_Placement` bewirkt, dass der Task Blockcontainer ausführen an der Position, die durch diesen Parameter angegeben werden.|
|[run_and_wait](#run_and_wait)|Überladen. Plant eine Aufgabe Inline im aufrufenden Kontext ausgeführt werden, mit der Hilfe von der `task_group` -Objekt für die vollständige Abbruch-Unterstützung. Die Funktion dann wartet, bis die gesamte Arbeit der `task_group` Objekt wurde entweder abgeschlossen oder abgebrochen wurde. Wenn eine `task_handle` Objekt wird als Parameter übergeben `run_and_wait`, der Aufrufer ist verantwortlich für die Verwaltung der Lebensdauer der `task_handle` Objekt.|
|[wait](#wait)|Wartet, bis die gesamte Arbeit der `task_group` Objekt wurde entweder abgeschlossen oder abgebrochen wurde.|

## <a name="remarks"></a>Hinweise

Im Gegensatz zu den stark eingeschränkten `structured_task_group` -Klasse, die `task_group` Klasse ist wesentlich allgemeineren Konstrukt. Es verfügt über keine der beschriebenen Einschränkungen [Structured_task_group](structured-task-group-class.md). `task_group` Objekte können sicher threadübergreifend verwendet und in Freiform-Methoden verwendet werden. Den Nachteil, dass die `task_group` Konstrukt ist, die nicht ausgeführt werden kann, sowie die `structured_task_group` für Aufgaben, die wenig Arbeit führen zu erstellen.

Weitere Informationen finden Sie unter [Aufgabenparallelität](../task-parallelism-concurrency-runtime.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`task_group`

## <a name="requirements"></a>Anforderungen

**Header:** ppl.h

**Namespace:** Parallelität

##  <a name="cancel"></a> Abbrechen

Macht die Teilstruktur des Arbeit Rooting manipuliert wurde, klicken Sie auf diese Aufgabengruppe abbrechen versucht. Jede Aufgabe, die für die Aufgabengruppe geplant werden transitiv abgebrochen, wenn möglich.

```
void cancel();
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [Abbruch](../cancellation-in-the-ppl.md).

##  <a name="is_canceling"></a> is_canceling

Informiert den Aufrufer, und zwar unabhängig davon, ob die Aufgabengruppe derzeit sich mitten in der ein Abbruch ist. Dies bedeutet nicht unbedingt, die die `cancel` Methode wurde aufgerufen, auf die `task_group` Objekt (auch wenn diese Methode zurückgibt, das z. B. sicherlich qualifiziert ist `true`). Es kann der Fall sein, die die `task_group` Objekt Inline ausführt und eine Aufgabengruppe weiter oben in der Arbeitsstruktur wurde abgebrochen. In Fällen, z. B. diesen, in denen die Laufzeit voraus, die dies Abbruch durchlaufen wird bestimmen kann `task_group` Objekt `true` wird ebenfalls zurückgegeben werden.

```
bool is_canceling();
```

### <a name="return-value"></a>Rückgabewert

Angabe, ob die `task_group` Objekt in ein Abbruch ist (oder gewährleistet ist in Kürze).

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [Abbruch](../cancellation-in-the-ppl.md).

##  <a name="run"></a> Führen Sie

Plant eine Aufgabe für die `task_group` Objekt. Wenn eine `task_handle` Objekt wird als Parameter übergeben `run`, der Aufrufer ist verantwortlich für die Verwaltung der Lebensdauer der `task_handle` Objekt. Führen Sie die Version der Methode, die einen Verweis auf ein Funktionsobjekt akzeptiert, wie ein Parameter Heapzuordnung in der Laufzeit enthält, der möglicherweise nicht so gut wie mit der Version, die akzeptiert einen Verweis auf eine `task_handle` Objekt. Die Version, die den Parameter akzeptiert `_Placement` bewirkt, dass der Task Blockcontainer ausführen an der Position, die durch diesen Parameter angegeben werden.

```
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
Der Typ des Funktionsobjekts, das aufgerufen wird, um den Text der Aufgabenhandle auszuführen.

*_Func*<br/>
Eine Funktion, die aufgerufen wird, um den Text der Aufgabe aufzurufen. Dies ist möglicherweise ein Lambda-Ausdruck oder ein anderes Objekt, das eine Version von den Funktionsaufrufoperator mit der Signatur unterstützt `void operator()()`.

*_Placement*<br/>
Ein Verweis auf den Speicherort, in denen die Aufgabe, durch dargestellt, die `_Func` Parameter sollte ausgeführt werden.

*_Task_handle*<br/>
Ein Handle für die Arbeit geplant. Beachten Sie, dass der Aufrufer die Verantwortung für die Lebensdauer dieses Objekts verfügt. Die Laufzeit ist so lange Sie erwartet, bis entweder die Gültigkeitsdauer der `wait` oder `run_and_wait` für diese Methode aufgerufen wurde `task_group` Objekt.

### <a name="remarks"></a>Hinweise

Die Runtime plant, die bereitgestellte Arbeitsfunktion zu einem späteren Zeitpunkt ausgeführt werden kann, nachdem die aufrufende Funktion zurückgegeben wird. Diese Methode verwendet eine [Task_handle](task-handle-class.md) Objekt, das eine Kopie der bereitgestellte Arbeitsfunktion enthalten. Aus diesem Grund werden alle Zustandsänderungen, die in ein Funktionsobjekt auftreten, die Sie für diese Methode übergeben, in Ihrer Kopie des Funktionsobjekts nicht angezeigt. Darüber hinaus stellen Sie sicher, dass die Lebensdauer von Objekten, die Sie, Zeiger oder Verweis auf die Arbeitsfunktion übergeben gültig bleiben, bis die Arbeitsfunktion zurückgegeben.

Wenn die `task_group` Destructs als Ergebnis der stapelentladung von einer Ausnahme, Sie müssen nicht garantieren, dass ein Aufruf entweder wurde die `wait` oder `run_and_wait` Methode. In diesem Fall der Destruktor wird entsprechend abgebrochen und warten, bis die Aufgabe, dargestellt durch die `_Task_handle` Parameter ausführen.

Löst die Methode eine [Invalid_multiple_scheduling](invalid-multiple-scheduling-class.md) -Ausnahme aus, wenn der Task behandeln Angabe durch die `_Task_handle` Parameter wurde bereits einem Aufgabengruppenobjekt über geplant wurde die `run` Methode und es wurde keine dazwischen liegenden rufen Sie entweder die `wait` oder `run_and_wait` Methode für diese Aufgabengruppe.

##  <a name="run_and_wait"></a> run_and_wait

Plant eine Aufgabe Inline im aufrufenden Kontext ausgeführt werden, mit der Hilfe von der `task_group` -Objekt für die vollständige Abbruch-Unterstützung. Die Funktion dann wartet, bis die gesamte Arbeit der `task_group` Objekt wurde entweder abgeschlossen oder abgebrochen wurde. Wenn eine `task_handle` Objekt wird als Parameter übergeben `run_and_wait`, der Aufrufer ist verantwortlich für die Verwaltung der Lebensdauer der `task_handle` Objekt.

```
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
Der Typ des Funktionsobjekts, das aufgerufen wird, um den Text der Aufgabe auszuführen.

*_Task_handle*<br/>
Ein Handle für die Aufgabe, die Inline im aufrufenden Kontext ausgeführt wird. Beachten Sie, dass der Aufrufer die Verantwortung für die Lebensdauer dieses Objekts verfügt. Die Laufzeit ist so lange Sie erwartet, bis die Gültigkeitsdauer der `run_and_wait` -Methode die Ausführung beendet.

*_Func*<br/>
Eine Funktion, die aufgerufen wird, um den Text der Arbeit aufzurufen. Dies ist möglicherweise ein Lambda-Ausdruck oder ein anderes Objekt, das eine Version von den Funktionsaufrufoperator mit der Signatur unterstützt `void operator()()`.

### <a name="return-value"></a>Rückgabewert

Ein Anzeichen dafür, ob der Wartevorgang erfüllt wurde oder die Aufgabengruppe wurde, entweder eine explizite Abbruchvorgang oder eine Ausnahme ausgelöst wird, von einer der Tasks abgebrochen. Weitere Informationen finden Sie unter [Task_group_status](concurrency-namespace-enums.md#task_group_status).

### <a name="remarks"></a>Hinweise

Beachten Sie, dass eine oder mehrere dieser geplante Aufgaben `task_group` Objekt kann Inline im aufrufenden Kontext ausgeführt.

Wenn eine oder mehrere dieser geplante Aufgaben `task_group` Objekt löst eine Ausnahme aus. die Laufzeit wird, wählen Sie eine solche Ausnahme seiner Wahl und aus dem Aufruf zum Weitergeben der `run_and_wait` Methode.

Bei der Rückgabe aus der `run_and_wait` Methode für eine `task_group` Objekt ist, wird die Laufzeit setzt das Objekt zurück, um einen fehlerfreien Zustand, in denen es wiederverwendet werden kann. Dies schließt die Groß-/Kleinschreibung, in denen die `task_group` Objekt wurde abgebrochen.

In den Pfad ohne Ausnahmen der Ausführung haben Sie eine zwingende Vorgabe entweder diese Methode aufrufen oder die `wait` -Methode auf, bevor der Destruktor von der `task_group` ausgeführt wird.

##  <a name="ctor"></a> task_group

Erstellt ein neues `task_group`-Objekt.

```
task_group();

task_group(
   cancellation_token _CancellationToken
);
```

### <a name="parameters"></a>Parameter

*_CancellationToken*<br/>
Ein Abbruchtoken, das diese Aufgabengruppe zugeordnet werden soll. Wenn das Token abgebrochen wird, wird die Aufgabengruppe abgebrochen werden.

### <a name="remarks"></a>Hinweise

Der Konstruktor, die ein Abbruchtoken akzeptiert erstellt eine `task_group` wird, die abgebrochen werden, wenn die Quelle mit dem Token verknüpften abgebrochen wird. Als explizites Abbruchtoken bereitstellen, werden auch diese Aufgabengruppe aus der Einbeziehung in einen impliziten Abbruch von einer übergeordneten Gruppe mit einem anderen Token "oder" kein Token isoliert.

##  <a name="dtor"></a> ~task_group

Zerstört ein `task_group`-Objekt. Es wird erwartet, rufen Sie entweder die `wait` oder `run_and_wait` Methode für das Objekt vor der Destruktor ausgeführt, es sei denn, der Destruktor als Ergebnis der stapelentladung aufgrund einer Ausnahme ausgeführt wird.

```
~task_group();
```

### <a name="remarks"></a>Hinweise

Wenn der Destruktor ausgeführt wird, als Ergebnis der normalen programmausführung (z. B. keine stapelentladung aufgrund einer Ausnahme) und weder der `wait` noch `run_and_wait` Methoden aufgerufen wurden, der Destruktor Auslösen einer [Missing_wait](missing-wait-class.md) Diese Ausnahme.

##  <a name="wait"></a> Warte

Wartet, bis die gesamte Arbeit der `task_group` Objekt wurde entweder abgeschlossen oder abgebrochen wurde.

```
task_group_status wait();
```

### <a name="return-value"></a>Rückgabewert

Ein Anzeichen dafür, ob der Wartevorgang erfüllt wurde oder die Aufgabengruppe wurde, entweder eine explizite Abbruchvorgang oder eine Ausnahme ausgelöst wird, von einer der Tasks abgebrochen. Weitere Informationen finden Sie unter [Task_group_status](concurrency-namespace-enums.md#task_group_status).

### <a name="remarks"></a>Hinweise

Beachten Sie, dass eine oder mehrere dieser geplante Aufgaben `task_group` Objekt kann Inline im aufrufenden Kontext ausgeführt.

Wenn eine oder mehrere dieser geplante Aufgaben `task_group` Objekt löst eine Ausnahme aus. die Laufzeit wird, wählen Sie eine solche Ausnahme seiner Wahl und aus dem Aufruf zum Weitergeben der `wait` Methode.

Aufrufen von `wait` auf eine `task_group` Objekt setzt es zurück, in einen fehlerfreien Zustand, in denen es wiederverwendet werden kann. Dies schließt die Groß-/Kleinschreibung, in denen die `task_group` Objekt wurde abgebrochen.

In den Pfad ohne Ausnahmen der Ausführung haben Sie eine zwingende Vorgabe entweder diese Methode aufrufen oder die `run_and_wait` -Methode auf, bevor der Destruktor von der `task_group` ausgeführt wird.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[structured_task_group-Klasse](structured-task-group-class.md)<br/>
[task_handle-Klasse](task-handle-class.md)
