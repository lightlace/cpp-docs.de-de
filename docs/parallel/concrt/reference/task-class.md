---
title: task-Klasse (Concurrency Runtime)
ms.date: 07/30/2019
f1_keywords:
- task
- PPLTASKS/concurrency::task
- PPLTASKS/concurrency::task::task
- PPLTASKS/concurrency::task::get
- PPLTASKS/concurrency::task::is_apartment_aware
- PPLTASKS/concurrency::task::is_done
- PPLTASKS/concurrency::task::scheduler
- PPLTASKS/concurrency::task::then
- PPLTASKS/concurrency::task::wait
helpviewer_keywords:
- task class
ms.assetid: cdc3a8c0-5cbe-45a0-b5d5-e9f81d94df1a
ms.openlocfilehash: 3657dc54584b120304ccda13ed93b5a0e37bb4af
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142614"
---
# <a name="task-class-concurrency-runtime"></a>task-Klasse (Concurrency Runtime)

Die Parallel Patterns Library (PPL) `task`-Klasse. Ein `task`-Objekt stellt Arbeit dar, die asynchron und gleichzeitig mit anderen Tasks und paralleler Arbeit, die von parallelen Algorithmen in der Concurrency Runtime erzeugt wird, ausgeführt werden kann. Es enthält bei erfolgreichem Abschluss ein Ergebnis vom Typ `_ResultType`. Tasks des Typs `task<void>` führen zu keinem Ergebnis. Eine Aufgabe kann erwartet und unabhängig von anderen Aufgaben abgebrochen werden. Sie kann auch mit anderen Aufgaben mithilfe von Fortsetzungen (`then`) und Join-(`when_all`) und Choice-Mustern (`when_any`) zusammengesetzt werden. Wenn ein Task-Objekt einer neuen Variablen zugewiesen wird, ist das Verhalten das `std::shared_ptr`; mit anderen Worten, beide Objekte stellen dieselbe zugrunde liegende Aufgabe dar.

## <a name="syntax"></a>Syntax

```cpp
template <>
class task<void>;

template<typename _ResultType>
class task;
```

### <a name="parameters"></a>Parameter

*_ResultType*<br/>
Der Typ des Ergebnisses, das von der Aufgabe erzeugt wird.

## <a name="members"></a>Members

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|BESCHREIBUNG|
|----------|-----------------|
|`result_type`|Der Typ des von einem Objekt dieser Klasse erstellten Ergebnisses.|

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[Task](#ctor)|Ist überladen. Erstellt ein `task`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|[get](#get)|Ist überladen. Gibt das von diesem Task erstellte Ergebnis zurück. Wenn sich die Aufgabe nicht in einem abschließenden Zustand befindet, wird mit dem `get`-Aufruf gewartet, bis die Aufgabe fertig gestellt wurde. Diese Methode gibt bei dem Aufruf einer Aufgabe mit einem `result_type` von `void` keinen Wert zurück.|
|[is_apartment_aware](#is_apartment_aware)|Bestimmt, ob der Task eine `IAsyncInfo`-Schnittstelle der Windows Runtime entpackt oder von einem solchen Task abgeleitet wurde.|
|[is_done](#is_done)|Bestimmt, ob die Aufgabe abgeschlossen wurde.|
|[Scheduler](#scheduler)|Gibt den Planer für diesen Task zurück.|
|[then](#then)|Ist überladen. Fügt diesem Task einen Fortsetzungstask hinzu.|
|[Warte](#wait)|Erwartet, dass dieser Task einen Terminalzustand erreicht. Es ist möglich, dass das `wait`-Element den Task inline ausführt, wenn alle Taskabhängigkeiten erfüllt sind und er nicht bereits zur Ausführung durch einen Hintergrundworker aufgehoben wurde.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[operator!=](#operator_neq)|Ist überladen. Bestimmt, ob zwei `task`-Objekte unterschiedliche interne Aufgaben darstellen.|
|[operator=](#operator_eq)|Ist überladen. Ersetzt den Inhalt eines `task`-Objekts durch einen anderen.|
|[operator==](#operator_eq_eq)|Ist überladen. Bestimmt, ob zwei `task`-Objekte die gleiche interne Aufgabe darstellen.|

## <a name="remarks"></a>Bemerkungen

Weitere Informationen finden Sie unter [Aufgaben Parallelität](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`task`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** ppltasks. h

**Namespace:** Parallelität

## <a name="get"></a>Erhalten

Gibt das von diesem Task erstellte Ergebnis zurück. Wenn sich die Aufgabe nicht in einem abschließenden Zustand befindet, wird mit dem `get`-Aufruf gewartet, bis die Aufgabe fertig gestellt wurde. Diese Methode gibt bei dem Aufruf einer Aufgabe mit einem `result_type` von `void` keinen Wert zurück.

```cpp
_ResultType get() const;

void get() const;
```

### <a name="return-value"></a>Rückgabewert

Das Ergebnis der Aufgabe.

### <a name="remarks"></a>Bemerkungen

Wenn die Aufgabe abgebrochen wird, löst ein `get` eine [task_canceled](task-canceled-class.md) -Ausnahme aus. Wenn die Aufgabe eine Ausnahme während der Ausführung feststellt oder an sie eine Ausnahme aus einer vorherigen Aufgabe weitergegeben wurde, löst ein Aufruf von `get` diese Ausnahme aus.

> [!IMPORTANT]
> Rufen Sie in einer universelle Windows-Plattform-app (UWP) nicht " [parallelcurrency:: Task:: Wait](#wait) " oder "`get` (`wait` Aufrufe `get`)" in Code auf, der auf dem Benutzeroberflächen Thread ausgeführt wird. Andernfalls löst die Laufzeit " [parallelcurrency:: Invalid_operation](invalid-operation-class.md) " aus, da diese Methoden den aktuellen Thread blockieren und bewirken können, dass die APP nicht mehr reagiert. Sie können jedoch die `get`-Methode aufrufen, um das Ergebnis der vorangegangenen Aufgabe in einer aufgabenbasierten Fortsetzung zu erhalten, da das Ergebnis sofort verfügbar ist.

## <a name="is_apartment_aware"></a>is_apartment_aware

Bestimmt, ob der Task eine `IAsyncInfo`-Schnittstelle der Windows Runtime entpackt oder von einem solchen Task abgeleitet wurde.

```cpp
bool is_apartment_aware() const;
```

### <a name="return-value"></a>Rückgabewert

**true** , wenn die Aufgabe eine `IAsyncInfo` Schnittstelle entpackt oder von einer solchen Aufgabe abgeleitet wird, andernfalls **false** .

## <a name="is_done"></a>Task:: is_done-Methode (Concurrency Runtime)

Bestimmt, ob die Aufgabe abgeschlossen wurde.

```cpp
bool is_done() const;
```

### <a name="return-value"></a>Rückgabewert

"True", wenn die Aufgabe abgeschlossen wurde, andernfalls "false".

### <a name="remarks"></a>Bemerkungen

Die Funktion gibt "true" zurück, wenn die Aufgabe abgeschlossen oder abgebrochen wurde (mit oder ohne Benutzerausnahme).

## <a name="operator_neq"></a>Operator! =

Bestimmt, ob zwei `task`-Objekte unterschiedliche interne Aufgaben darstellen.

```cpp
bool operator!= (const task<_ResultType>& _Rhs) const;

bool operator!= (const task<void>& _Rhs) const;
```

### <a name="parameters"></a>Parameter

*_Rhs*<br/>
Der zu vergleichende Task.

### <a name="return-value"></a>Rückgabewert

**true** , wenn die Objekte auf verschiedene zugrunde liegende Aufgaben verweisen, andernfalls **false** .

## <a name="operator_eq"></a>Operator =

Ersetzt den Inhalt eines `task`-Objekts durch einen anderen.

```cpp
task& operator= (const task& _Other);

task& operator= (task&& _Other);
```

### <a name="parameters"></a>Parameter

*_Other*<br/>
Das `task`-Quellobjekt.

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Bemerkungen

Da sich `task` wie ein intelligenter Zeiger verhält, stellt dieses `task`-Objekt nach einer Kopierzuweisung die gleiche Aufgabe dar wie `_Other`.

## <a name="operator_eq_eq"></a>Operator = =

Bestimmt, ob zwei `task`-Objekte die gleiche interne Aufgabe darstellen.

```cpp
bool operator== (const task<_ResultType>& _Rhs) const;

bool operator== (const task<void>& _Rhs) const;
```

### <a name="parameters"></a>Parameter

*_Rhs*<br/>
Der zu vergleichende Task.

### <a name="return-value"></a>Rückgabewert

**true** , wenn die Objekte auf dieselbe zugrunde liegende Aufgabe verweisen, andernfalls **false** .

## <a name="scheduler"></a>Task:: Scheduler-Methode (Concurrency Runtime)

Gibt den Planer für diesen Task zurück.

```cpp
scheduler_ptr scheduler() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den Planer.

## <a name="ctor"></a>Task

Erstellt ein `task`-Objekt.

```cpp
task();

template<typename T>
__declspec(
    noinline) explicit task(T _Param);

template<typename T>
__declspec(
    noinline) explicit task(T _Param, const task_options& _TaskOptions);

task(
    const task& _Other);

task(
    task&& _Other);
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der Typ des Parameters, von dem die Aufgabe erstellt werden soll.

*_Param*<br/>
Der Parameter, von dem der Task erstellt werden soll. Dies kann ein Lambda-, ein Funktions Objekt, ein `task_completion_event<result_type>` Objekt oder ein Windows:: Foundation:: iasyncinfo sein, wenn Sie Aufgaben in Ihrer Windows-Runtime-App verwenden. Beim Lambda-oder Funktions Objekt sollte es sich um einen Typ handeln, der `std::function<X(void)>`entspricht, wobei X eine Variable vom Typ "`result_type`", "`task<result_type>`" oder "Windows:: Foundation:: iasyncinfo" in Windows-Runtime-apps sein kann.

*_TaskOptions*<br/>
Die Aufgabenoptionen enthalten Abbruchtoken, Planer usw.

*_Other*<br/>
Das `task`-Quellobjekt.

### <a name="remarks"></a>Bemerkungen

Der Standardkonstruktor für `task` ist nur vorhanden, damit Aufgaben in Containern verwendet werden können. Eine erstellte Standardaufgabe kann nicht verwendet werden, bis Sie ihr eine gültige Aufgabe zuweisen. Methoden wie `get`, `wait` oder `then` lösen eine [Invalid_argument](../../../standard-library/invalid-argument-class.md) Ausnahme aus, wenn Sie für eine erstellte Standard Aufgabe aufgerufen werden.

Eine Aufgabe, die aus einem `task_completion_event` erstellt wird, wird abgeschlossen (und danach werden ihre Fortsetzungen geplant), wenn das Aufgabenabschlussereignis festgelegt ist.

Die Version des Konstruktors, die ein Abbruchtoken verwendet, erstellt eine Aufgabe, die mithilfe der `cancellation_token_source`, aus der das Token abgerufen wurde, abgebrochen werden kann. Die Aufgaben, die ohne ein Abbruchtoken erstellt werden, können nicht abgebrochen werden.

Die Aufgaben, die aus einer `Windows::Foundation::IAsyncInfo`-Schnittstelle oder einem Lambda-Ausdruck erstellt werden, der eine `IAsyncInfo`-Schnittstelle zurückgibt, erreichen den abgeschlossenen Zustand, wenn der enthaltene asynchrone Windows-Runtime-Vorgang oder die enthaltene Aktion abgeschlossen wurde. Ebenso werden Tasks, die von einem Lambda erstellt werden, der einen `task<result_type>` zurückgibt, den Endzustand erreichen, wenn die innere Aufgabe den Endzustand erreicht, nicht, wenn der Lambda-Wert zurückgibt.

`task` verhält sich wie ein intelligenter Zeiger und kann mehrmals als Wert übergeben werden. Ein Zugriff ist durch mehrere Threads ohne Sperren möglich.

Die Konstruktorüberladungen, die eine Windows:: Foundation:: iasyncinfo-Schnittstelle oder einen Lambda-Wert verwenden, der eine solche Schnittstelle zurückgibt, sind nur für Windows-Runtime-apps verfügbar.

Weitere Informationen finden Sie unter [Aufgaben Parallelität](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).

## <a name="then"></a>Seitdem

Fügt diesem Task einen Fortsetzungstask hinzu.

```cpp
template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func) const -> typename details::_ContinuationTypeTraits<_Function,
    _ResultType>::_TaskOfType;

template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func,
    const task_options& _TaskOptions) const -> typename details::_ContinuationTypeTraits<_Function,
    _ResultType>::_TaskOfType;

template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func,
    cancellation_token _CancellationToken,
    task_continuation_context _ContinuationContext) const -> typename details::_ContinuationTypeTraits<_Function,
    _ResultType>::_TaskOfType;

template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func,
    const task_options& _TaskOptions = task_options()) const -> typename details::_ContinuationTypeTraits<_Function,
    void>::_TaskOfType;

template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func,
    cancellation_token _CancellationToken,
    task_continuation_context _ContinuationContext) const -> typename details::_ContinuationTypeTraits<_Function,
    void>::_TaskOfType;
```

### <a name="parameters"></a>Parameter

*_Function*<br/>
Der Typ des Funktionsobjekts, das von dieser Aufgabe aufgerufen wird.

*_Func*<br/>
Die Fortsetzungsfunktion, die ausgeführt werden soll, wenn diese Aufgabe abgeschlossen ist. Diese Fortsetzungsfunktion muss als Eingabe die Variable `result_type` oder `task<result_type>` verwenden, wobei `result_type` der Ergebnistyp ist, den diese Aufgabe erzeugt.

*_TaskOptions*<br/>
Die Aufgabenoptionen umfassen das Abbruchtoken, den Planer und den Fortsetzungskontext. Standardmäßig werden die vorherigen drei Optionen von der Vorgängeraufgabe geerbt.

*_CancellationToken*<br/>
Das Abbruchtoken, das der Fortsetzungsaufgabe zugeordnet werden soll. Eine Fortsetzungsaufgabe, die ohne ein Abbruchtoken erstellt wird, erbt das Token von der Vorgängeraufgabe.

*_ContinuationContext*<br/>
Eine Variable, die angibt, wo die Fortsetzung ausgeführt werden soll. Diese Variable ist nur nützlich, wenn Sie in einer UWP-App verwendet wird. Weitere Informationen finden Sie unter [task_continuation_context](task-continuation-context-class.md)

### <a name="return-value"></a>Rückgabewert

Die neu erstellte Fortsetzungsaufgabe. Der Ergebnistyp der zurückgegebenen Aufgabe wird von dem bestimmt, was `_Func` zurückgibt.

### <a name="remarks"></a>Bemerkungen

Die über Ladungen von `then`, die einen Lambda-oder Funktions tüktor verwenden, der eine Windows:: Foundation:: iasyncinfo-Schnittstelle zurückgibt, sind nur für Windows-Runtime-apps verfügbar.

Weitere Informationen zum Verwenden von Aufgaben Fortsetzungen zum Verfassen von asynchronen Aufgaben finden Sie unter [Aufgaben Parallelität](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).

## <a name="wait"></a>Warte

Erwartet, dass dieser Task einen Terminalzustand erreicht. Es ist möglich, dass das `wait`-Element den Task inline ausführt, wenn alle Taskabhängigkeiten erfüllt sind und er nicht bereits zur Ausführung durch einen Hintergrundworker aufgehoben wurde.

```cpp
task_status wait() const;
```

### <a name="return-value"></a>Rückgabewert

Ein `task_status`-Wert, der entweder `completed` oder `canceled` ist. Wenn die Aufgabe eine Ausnahme während der Ausführung feststellt oder an sie eine Ausnahme aus einer vorherigen Aufgabe weitergegeben wurde, löst `wait` diese Ausnahme aus.

### <a name="remarks"></a>Bemerkungen

> [!IMPORTANT]
> In einer universelle Windows-Plattform-app (UWP) müssen Sie `wait` nicht in Code aufzurufen, der auf dem Benutzeroberflächen Thread ausgeführt wird. Andernfalls löst die Laufzeit [concurrency::invalid_operation](invalid-operation-class.md) aus, da diese Methode den aktuellen Thread blockiert und die App dadurch möglicherweise nicht mehr reagiert. Sie können jedoch die [concurrency::task::get](#get) -Methode aufrufen, um das Ergebnis der Vorgängeraufgabe in einer aufgabenbasierten Fortsetzung zu erhalten.

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)
