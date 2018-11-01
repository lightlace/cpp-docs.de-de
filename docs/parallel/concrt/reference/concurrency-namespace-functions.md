---
title: Concurrency-Namespace-Funktionen
ms.date: 11/04/2016
f1_keywords:
- concrt/concurrency::Alloc
- concrt/concurrency::DisableTracing
- concrt/concurrency::EnableTracing
- concrtrm/concurrency::GetExecutionContextId
- concrtrm/concurrency::GetOSVersion
- concrtrm/concurrency::GetProcessorNodeCount
- concrtrm/concurrency::GetSchedulerId
- agents/concurrency::asend
- ppltasks/concurrency::cancel_current_task
- ppltasks/concurrency::create_async
- ppltasks/concurrency::create_task
- concurrent_vector/concurrency::internal_assign_iterators
- ppl/concurrency::interruption_point
- agents/concurrency::make_choice
- agents/concurrency::make_greedy_join
- ppl/concurrency::make_task
- ppl/concurrency::parallel_buffered_sort
- ppl/concurrency::parallel_for_each
- ppl/concurrency::parallel_invoke
- ppl/concurrency::parallel_reduce
- ppl/concurrency::parallel_sort
- agents/concurrency::receive
- ppl/concurrency::run_with_cancellation_token
- pplconcrt/concurrency::set_ambient_scheduler
- concrt/concurrency::set_task_execution_resources
- ppltasks/concurrency::task_from_exception
- ppltasks/concurrency::task_from_result
- concrt/concurrency::wait
- ppltasks/concurrency::when_all
- ppltasks/concurrency::when_any
ms.assetid: 520a6dff-9324-4df2-990d-302e3050af6a
ms.openlocfilehash: 7550e6f0ef44abd19b3fab89127ff898c72738f2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50436178"
---
# <a name="concurrency-namespace-functions"></a>Concurrency-Namespace-Funktionen

||||
|-|-|-|
|[Alloc](#alloc)|[CreateResourceManager](#createresourcemanager)|[DisableTracing](#disabletracing)|
|[EnableTracing](#enabletracing)|[kostenlos](#free)|[GetExecutionContextId](#getexecutioncontextid)|
|[GetOSVersion](#getosversion)|[GetProcessorCount](#getprocessorcount)|[GetProcessorNodeCount](#getprocessornodecount)|
|[GetSchedulerId](#getschedulerid)|[Trace_agents_register_name](#trace_agents_register_name)|[asend](#asend)|
|[cancel_current_task](#cancel_current_task)|[clear](#clear)|[create_async](#create_async)|
|[create_task](#create_task)|[get_ambient_scheduler](#get_ambient_scheduler)|[internal_assign_iterators](#internal_assign_iterators)|
|[interruption_point](#interruption_point)|[is_current_task_group_canceling](#is_current_task_group_canceling)|[make_choice](#make_choice)|
|[make_greedy_join](#make_greedy_join)|[make_join](#make_join)|[make_task](#make_task)|
|[parallel_buffered_sort](#parallel_buffered_sort)|[parallel_for](#parallel_for)|[parallel_for_each](#parallel_for_each)|
|[parallel_invoke](#parallel_invoke)|[parallel_radixsort](#parallel_radixsort)|[parallel_reduce](#parallel_reduce)|
|[parallel_sort](#parallel_sort)|[parallel_transform](#parallel_transform)|[receive](#receive)|
|[run_with_cancellation_token](#run_with_cancellation_token)|[Senden](#send)|[set_ambient_scheduler](#set_ambient_scheduler)|
|[set_task_execution_resources](#set_task_execution_resources)|[swap](#swap)|[task_from_exception](#task_from_exception)|
|[task_from_result](#task_from_result)|[try_receive](#try_receive)|[wait](#wait)|
|[when_all](#when_all)|[when_any](#when_any)|

##  <a name="alloc"></a>  Alloc

Reserviert einen Speicherblock mit der in der Unterbelegungsfunktion für die Zwischenspeicherung der Concurrency Runtime angegebenen Größe.

```
void* __cdecl Alloc(size_t _NumBytes);
```

### <a name="parameters"></a>Parameter

*_NumBytes*<br/>
Die Anzahl der Bytes an Arbeitsspeicher zugewiesen werden.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den neu reservierten Speicher.

### <a name="remarks"></a>Hinweise

Weitere Informationen darüber, welche Szenarien in Ihrer Anwendung aus der Verwendung der Unterbelegungsfunktion für die Zwischenspeicherung profitieren könnten, finden Sie unter [Taskplaner](../../../parallel/concrt/task-scheduler-concurrency-runtime.md).

##  <a name="asend"></a>  asend

Ein asynchroner Sendevorgang, der eine Aufgabe zum Weitergeben der Daten an den Zielblock plant.

```
template <class T>
bool asend(
    _Inout_ ITarget<T>* _Trg,
    const T& _Data);

template <class T>
bool asend(
    ITarget<T>& _Trg,
    const T& _Data);
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der Typ der Daten, die gesendet werden.

*_Trg*<br/>
Ein Zeiger oder Verweis auf das Ziel, an dem Daten gesendet werden.

*"_Data"*<br/>
Ein Verweis auf die Daten gesendet werden.

### <a name="return-value"></a>Rückgabewert

**"true"** , wenn die Meldung akzeptiert wurde, bevor die Methode zurückgegeben, **"false"** andernfalls.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [Message Passing Functions](../../../parallel/concrt/message-passing-functions.md).

##  <a name="cancel_current_task"></a>  cancel_current_task

Bricht die gerade ausgeführte Aufgabe ab. Diese Funktion kann aus dem Text einer Aufgabe aufgerufen werden, um die Ausführung der Aufgabe abzubrechen und ihn dabei in den `canceled` Zustand übergehen zu lassen.

Der Aufruf dieser Funktion, wenn Sie sich nicht innerhalb des Texts von einem `task` befinden, ist kein unterstütztes Szenario. Dies würde zu nicht definiertem Verhalten, wie einem Absturz oder einem Hänger in der Anwendung, führen.

```
inline __declspec(noreturn) void __cdecl cancel_current_task();
```

##  <a name="clear"></a>  Deaktivieren

Löscht die gleichzeitige Warteschlange, zerstört alle derzeit die Elemente in die Warteschlange eingereiht. Diese Methode ist nicht nebenläufigkeitssicher.

```
template<typename T, class _Ax>
void concurrent_queue<T, _Ax>::clear();
```

### <a name="parameters"></a>Parameter

*T*<br/>

*_Ax*<br/>

##  <a name="create_async"></a>  create_async-Methode

Erstellt ein asynchrones Konstrukt der Windows Runtime auf einem vom Benutzer angegebenes Lambda oder Funktionsobjekt. Der Rückgabetyp von `create_async` ist entweder `IAsyncAction^`, `IAsyncActionWithProgress<TProgress>^`, `IAsyncOperation<TResult>^` oder `IAsyncOperationWithProgress<TResult, TProgress>^` auf Grundlage der Signatur des Lambdaausdrucks, der an die Methode übergeben wurde.

```
template<typename _Function>
__declspec(noinline) auto create_async(const _Function& _Func)
    -> decltype(ref new details::_AsyncTaskGeneratorThunk<_Function>(_Func));
```

### <a name="parameters"></a>Parameter

*_Function*<br/>
Geben Sie ein.

*_Func*<br/>
Der Lambda-Ausdruck oder das Funktionsobjekt, aus dem ein asynchrones Windows-Runtime-Konstrukt erstellt werden soll.

### <a name="return-value"></a>Rückgabewert

Ein asynchrones Konstrukt, dargestellt durch IAsyncAction ^, IAsyncActionWithProgress\<TProgress > ^, IAsyncOperation\<TResult > ^, oder IAsyncOperationWithProgress\<TResult, TProgress > ^. Die Schnittstelle, die zurückgegeben wird, hängt von der Signatur des Lambda-Ausdrucks ab, der an die Funktion übergeben wird.

### <a name="remarks"></a>Hinweise

Der Rückgabetyp des Lambdaausdrucks bestimmt, ob das Konstrukt eine Aktion oder ein Vorgang ist.

Lambda-Ausdrücke, die "void" zurückgeben, führen zur Erstellung von Aktionen. Lambda-Ausdrücke, die ein Ergebnis vom Typ `TResult` zurückgeben, führen zur Erstellung von TResult-Vorgängen.

Der Lambda-Ausdruck kann auch `task<TResult>` zurückgeben, was die asynchronen Abläufe kapselt, oder die Fortsetzung einer Kette von Aufgaben ist, die die asynchronen Abläufe darstellen. In diesem Fall wird der Lambdaausdruck selbst inline ausgeführt, da die Aufgaben asynchron ausgeführt werden, und der Rückgabetyp des Lambdaausdrucks wird entpackt, um das von `create_async` zurückgegebene asynchrone Konstrukt zu erstellen. Dies bedeutet, dass ein Lambda-Ausdruck, der eine Aufgabe zurückgibt\<"void" > bewirkt, dass die Erstellung von Aktionen und einen Lambda-Ausdruck, der eine Aufgabe zurückgibt\<TResult > bewirkt, dass die Erstellung von TResult-Vorgängen.

Der Lambda-Ausdruck akzeptiert null, ein oder zwei Argumente. Die gültigen Argumente sind `progress_reporter<TProgress>` und `cancellation_token` in dieser Reihenfolge, wenn beide verwendet werden. Ein Lambda-Ausdruck ohne Argumente bewirkt die Erstellung eines asynchronen Konstrukts ohne die Möglichkeit der Statusberichterstellung. Ein Lambda-Ausdruck, der eine "progress_reporter" akzeptiert\<TProgress > bewirkt, dass `create_async` ein asynchrones Konstrukt zurückgibt, das den Status des Typs TProgress jedes Mal meldet die `report` -Methode des Objekts "progress_reporter" aufgerufen wird. Ein Lambda-Ausdruck, der ein „cancellation_token“ verwendet, kann dieses Token verwenden, um auf einen Abbruch zu prüfen, oder es an Aufgaben übergeben, die er erstellt, sodass ein Abbruch des asynchronen Konstrukts den Abbruch dieser Aufgaben verursacht.

Wenn der Text des Lambda-Ausdrucks oder der Funktion ein Ergebnis zurückgibt (und nicht auf einen Task\<TResult >), wird der Lambda-Ausdruck innerhalb des Prozesses MTA im Kontext einer Aufgabe die Laufzeit implizit für diese erstellt asynchron ausgeführt. Die `IAsyncInfo::Cancel`-Methode verursacht den Abbruch der impliziten Aufgabe.

Wenn der Text des Lambda-Ausdrucks eine Aufgabe zurückgibt, wird der Lambda-Ausdruck inline ausgeführt. Durch Deklarieren des Lambda-Ausdrucks zur Verwendung eines Arguments des Typs `cancellation_token` können Sie den Abbruch aller Aufgaben auslösen, die Sie innerhalb des Lambda-Ausdrucks erstellen, indem Sie dieses Token bei ihrer Erstellung übergeben. Sie können auch die `register_callback`-Methode im Token verwenden, um die Laufzeit zu veranlassen, einen Rückruf aufzurufen, wenn Sie `IAsyncInfo::Cancel` für den asynchronen Vorgang oder die verursachte Aktion aufrufen.

Diese Funktion ist nur für Windows-Runtime-apps verfügbar.

##  <a name="createresourcemanager"></a>  CreateResourceManager

Gibt eine Schnittstelle zurück, die die Singletoninstanz des Ressourcen-Managers der Concurrency Runtime darstellt. Der Ressourcen-Manager ist für das Zuweisen von Ressourcen für Planer, die miteinander kooperieren möchten, zuständig.

```
IResourceManager* __cdecl CreateResourceManager();
```

### <a name="return-value"></a>Rückgabewert

Eine `IResourceManager`-Schnittstelle.

### <a name="remarks"></a>Hinweise

Mehrere nachfolgende Aufrufe dieser Methode geben die gleiche Instanz des Ressourcen-Managers zurück. Jeder Aufruf der Methode inkrementiert einen Verweis auf die Ressourcen-Manager, und muss mit einem Aufruf von abgeglichen werden die [IResourceManager:: Release](iresourcemanager-structure.md) Methode, wenn der Planer erfolgt Kommunikation mit dem Resource Manager.

[Unsupported_os](unsupported-os-class.md) wird ausgelöst, wenn das Betriebssystem nicht von der Concurrency Runtime unterstützt wird.

##  <a name="create_task"></a>  create_task

Erstellt ein PPL- [Aufgabe](task-class.md) Objekt. Das Element `create_task` kann überall dort verwendet werden, wo Sie einen Aufgabenkonstruktor verwendet hätten. Es wird hauptsächlich der Einfachheit halber bereitgestellt, da es beim Erstellen einer Aufgabe die Verwendung des `auto`-Schlüsselwort ermöglicht.

```
template<typename T>
__declspec(noinline) auto create_task(T _Param, const task_options& _TaskOptions = task_options())
    -> task<typename details::_TaskTypeFromParam<T>::T>;

template<typename _ReturnType>
__declspec( noinline) task<_ReturnType> create_task(const task<_ReturnType>& _Task);
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der Typ des Parameters, von dem die Aufgabe erstellt werden soll.

*_ReturnType*<br/>
Geben Sie ein.

*_Param*<br/>
Der Parameter, von dem die Aufgabe erstellt werden soll. Dies ist möglicherweise ein Lambda- oder Funktionsobjekt-Objekt, ein `task_completion_event` Objekt, ein anderes `task` Objekt oder eine iasyncinfo-Schnittstelle, die bei Verwendung von Aufgaben in Ihrer UWP-app.

*_TaskOptions*<br/>
Die Aufgabenoptionen.

*_Task*<br/>
Die Aufgabe zu erstellen.

### <a name="return-value"></a>Rückgabewert

Eine neue Aufgabe des Typs `T`, der von `_Param` abgeleitet wird.

### <a name="remarks"></a>Hinweise

Die erste Überladung verhält sich wie ein Aufgabenkonstruktor, der einen einzelnen Parameter akzeptiert.

Die zweite Überladung weist das Abbruchtoken, das der neu erstellten Aufgabe bereitgestellt wird, zu. Wenn Sie diese Überladung verwenden, ist die Übergabe eines anderen `task`-Objekts als erster Parameter nicht zulässig.

Der Typ des zurückgegebenen Tasks wird vom ersten Parameter zur Funktion abgeleitet. Wenn `_Param` ein `task_completion_event<T>`, ein `task<T>` oder ein Funktionselement ist, das entweder den Typ `T` oder `task<T>` zurückgibt, ist der Typ der erstellten Aufgabe `task<T>`.

In einer UWP-app Wenn `_Param` ist vom Typ iasyncoperation\<T > ^ oder Windows::Foundation::IAsyncOperationWithProgress\<T, P > ^, oder ein Funktionselement ist, das einen dieser Typen zurückgibt, wird die erstellte Aufgabe von Typ `task<T>`. Wenn `_Param` ist vom Typ Windows::Foundation::IAsyncAction ^ oder Windows::Foundation::IAsyncActionWithProgress\<P > ^, oder ein Funktionselement ist, das einen dieser Typen zurückgibt, die erstellte Aufgabe von Typ `task<void>`.

##  <a name="disabletracing"></a>  DisableTracing

Deaktiviert die Ablaufverfolgung in der Concurrency Runtime. Diese Funktion ist veraltet, da die Registrierung der ETW-Ablaufverfolgung standardmäßig aufgehoben wird.

```
__declspec(deprecated("Concurrency::DisableTracing is a deprecated function.")) _CRTIMP HRESULT __cdecl DisableTracing();
```

### <a name="return-value"></a>Rückgabewert

Wenn die Ablaufverfolgung ordnungsgemäß deaktiviert wurde, `S_OK` zurückgegeben wird. Wenn die Ablaufverfolgung nicht zuvor initiiert, `E_NOT_STARTED` wird zurückgegeben

##  <a name="enabletracing"></a>  EnableTracing

Aktiviert die Ablaufverfolgung in der Concurrency Runtime. Diese Funktion ist veraltet, da die Registrierung der ETW-Ablaufverfolgung jetzt standardmäßig erfolgt.

```
__declspec(deprecated("Concurrency::EnableTracing is a deprecated function.")) _CRTIMP HRESULT __cdecl EnableTracing();
```

### <a name="return-value"></a>Rückgabewert

Wenn die Ablaufverfolgung richtig initiiert wurde, `S_OK` wird zurückgegeben, andernfalls `E_NOT_STARTED` zurückgegeben wird.

##  <a name="free"></a>  kostenlos

Gibt einen Speicherblock frei, der zuvor mit der `Alloc`-Methode der Unterbelegungsfunktion für die Zwischenspeicherung der Concurrency Runtime reserviert wurde.

```
void __cdecl Free(_Pre_maybenull_ _Post_invalid_ void* _PAllocation);
```

### <a name="parameters"></a>Parameter

*_PAllocation*<br/>
Ein Zeiger auf den Arbeitsspeicher, der zuvor mit der `Alloc`-Methode reserviert wurde und jetzt freigegeben werden soll. Wenn der `_PAllocation`-Parameter auf den Wert `NULL` festgelegt wurde, ignoriert diese Methode den Parameter und kehrt sofort zurück.

### <a name="remarks"></a>Hinweise

Weitere Informationen darüber, welche Szenarien in Ihrer Anwendung aus der Verwendung der Unterbelegungsfunktion für die Zwischenspeicherung profitieren könnten, finden Sie unter [Taskplaner](../../../parallel/concrt/task-scheduler-concurrency-runtime.md).

##  <a name="get_ambient_scheduler"></a>  get_ambient_scheduler

```
inline std::shared_ptr<::Concurrency::scheduler_interface> get_ambient_scheduler();
```

### <a name="return-value"></a>Rückgabewert

##  <a name="getexecutioncontextid"></a>  GetExecutionContextId

Gibt einen eindeutigen Bezeichner zurück, der einem Ausführungskontext zugewiesen werden kann, der die `IExecutionContext`-Schnittstelle implementiert.

```
unsigned int __cdecl GetExecutionContextId();
```

### <a name="return-value"></a>Rückgabewert

Ein eindeutiger Bezeichner für einen Ausführungskontext.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode, um einen Bezeichner für den Ausführungskontext zu erhalten, bevor Sie übergeben eine `IExecutionContext` Schnittstelle als Parameter an eine der Methoden, die vom Ressourcen-Manager angeboten.

##  <a name="getosversion"></a>  GetOSVersion

Gibt die Betriebssystemversion zurück.

```
IResourceManager::OSVersion __cdecl GetOSVersion();
```

### <a name="return-value"></a>Rückgabewert

Ein Enumerationswert, der das Betriebssystem darstellt.

### <a name="remarks"></a>Hinweise

[Unsupported_os](unsupported-os-class.md) wird ausgelöst, wenn das Betriebssystem nicht von der Concurrency Runtime unterstützt wird.

##  <a name="getprocessorcount"></a>  GetProcessorCount

Gibt die Anzahl von Hardwarethreads des zugrunde liegenden Systems zurück.

```
unsigned int __cdecl GetProcessorCount();
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Hardwarethreads.

### <a name="remarks"></a>Hinweise

[Unsupported_os](unsupported-os-class.md) wird ausgelöst, wenn das Betriebssystem nicht von der Concurrency Runtime unterstützt wird.

##  <a name="getprocessornodecount"></a>  GetProcessorNodeCount

Gibt die Anzahl von NUMA-Knoten oder Prozessorpaketen des zugrunde liegenden Systems zurück.

```
unsigned int __cdecl GetProcessorNodeCount();
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl von NUMA-Knoten oder Prozessorpaketen.

### <a name="remarks"></a>Hinweise

Wenn das System mehr NUMA-Knoten als Prozessorpakete enthält, wird die Anzahl der NUMA-Knoten zurückgegeben. Andernfalls wird die Anzahl der Prozessorpakete zurückgegeben.

[Unsupported_os](unsupported-os-class.md) wird ausgelöst, wenn das Betriebssystem nicht von der Concurrency Runtime unterstützt wird.

##  <a name="getschedulerid"></a>  GetSchedulerId

Gibt einen eindeutigen Bezeichner zurück, der einem Planer zugewiesen werden kann, der die `IScheduler`-Schnittstelle implementiert.

```
unsigned int __cdecl GetSchedulerId();
```

### <a name="return-value"></a>Rückgabewert

Ein eindeutiger Bezeichner für einen Planer.

### <a name="remarks"></a>Hinweise

Mit dieser Methode können Sie um einen Bezeichner für den Planer zu erhalten, bevor Sie übergeben eine `IScheduler` Schnittstelle als Parameter an eine der Methoden, die vom Ressourcen-Manager angeboten.

##  <a name="internal_assign_iterators"></a>  internal_assign_iterators

```
template<typename T, class _Ax>
template<class _I>
void concurrent_vector<T, _Ax>::internal_assign_iterators(
   _I first,
   _I last);
```

### <a name="parameters"></a>Parameter

*T*<br/>

*_Ax*<br/>

*_I*<br/>

*Erste*<br/>

*last*<br/>

##  <a name="interruption_point"></a>  interruption_point

Erstellt einen Unterbrechungspunkt für den Abbruch. Wenn ein Abbruch im Kontext, in dem diese Funktion aufgerufen wird, ausgeführt wird, löst diese eine interne Ausnahme aus, mit der die Ausführung der aktuell ausgeführten parallelen Verarbeitung abgebrochen wird. Wenn kein Abbruch ausgeführt wird, bleibt die Funktion untätig.

```
inline void interruption_point();
```

### <a name="remarks"></a>Hinweise

Sie sollten nicht interner Abbruch von ausgelöste Ausnahme abfangen der `interruption_point()` Funktion. Die Ausnahme abgefangen und behandelt, die von der Laufzeit sein wird, und abfangen kann dazu führen, dass das Programm nicht normal verhält.

##  <a name="is_current_task_group_canceling"></a>  is_current_task_group_canceling

Gibt zurück, ob die Aufgabengruppe, die gerade inline auf dem aktuellen Kontext ausgeführt wird, in diesem Moment (oder in Kürze) einen Abbruch durchführt. Beachten Sie, dass `false` zurückgegeben wird, wenn auf dem aktuellen Kontext zurzeit inline keine Aufgabengruppe ausgeführt wird.

```
bool __cdecl is_current_task_group_canceling();
```

### <a name="return-value"></a>Rückgabewert

**"true"** , wenn die Aufgabengruppe, die gerade ausgeführt wird, abgebrochen wird, **"false"** andernfalls.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [Abbruch](../../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation).

##  <a name="make_choice"></a>  make_choice

Erstellt einen `choice`-Meldungsblock aus einem optionalen `Scheduler` oder einer `ScheduleGroup` und mindestens zwei Eingabequellen.

```
template<typename T1, typename T2, typename... Ts>
choice<std::tuple<T1, T2, Ts...>> make_choice(
    Scheduler& _PScheduler,
    T1  _Item1,
    T2  _Item2,
    Ts... _Items);

template<typename T1, typename T2, typename... Ts>
choice<std::tuple<T1, T2, Ts...>> make_choice(
    ScheduleGroup& _PScheduleGroup,
    T1  _Item1,
    T2  _Item2,
    Ts... _Items);

template<typename T1, typename T2, typename... Ts>
choice<std::tuple<T1, T2, Ts...>> make_choice(
    T1  _Item1,
    T2  _Item2,
    Ts... _Items);
```

### <a name="parameters"></a>Parameter

*T1*<br/>
Der Meldungsblocktyp der ersten Quelle.

*T2*<br/>
Der Meldungsblocktyp der zweiten Quelle.

*_PScheduler*<br/>
Das `Scheduler` -Objekt, in dem die Weiterleitungsaufgabe für den `choice` -Meldungsblock geplant ist.

*_Item1*<br/>
Die erste Quelle.

*_Item2*<br/>
Die zweite Quelle.

*_Items*<br/>
Zusätzliche Quellen.

*_PScheduleGroup*<br/>
Das `ScheduleGroup` -Objekt, in dem die Weiterleitungsaufgabe für den `choice` -Meldungsblock geplant ist. Das verwendete `Scheduler` -Objekt wird von der Planungsgruppe impliziert.

### <a name="return-value"></a>Rückgabewert

Ein `choice`-Nachrichtenblock mit zwei oder mehr Eingabequellen.

##  <a name="make_greedy_join"></a>  make_greedy_join

Erstellt einen `greedy multitype_join`-Meldungsblock aus einem optionalen `Scheduler` oder einer `ScheduleGroup` und mindestens zwei Eingabequellen.

```
template<typename T1, typename T2, typename... Ts>
multitype_join<std::tuple<T1, T2, Ts...>,greedy> make_greedy_join(
    Scheduler& _PScheduler,
    T1 _Item1,
    T2 _Item2,
    Ts... _Items);

template<typename T1, typename T2, typename... Ts>
multitype_join<std::tuple<T1, T2, Ts...>, greedy> make_greedy_join(
    ScheduleGroup& _PScheduleGroup,
    T1 _Item1,
    T2 _Item2,
    Ts... _Items);

template<typename T1, typename T2, typename... Ts>
multitype_join<std::tuple<T1, T2, Ts...>, greedy> make_greedy_join(
    T1 _Item1,
    T2 _Items,
    Ts... _Items);
```

### <a name="parameters"></a>Parameter

*T1*<br/>
Der Meldungsblocktyp der ersten Quelle.

*T2*<br/>
Der Meldungsblocktyp der zweiten Quelle.

*_PScheduler*<br/>
Das `Scheduler` -Objekt, in dem die Weiterleitungsaufgabe für den `multitype_join` -Meldungsblock geplant ist.

*_Item1*<br/>
Die erste Quelle.

*_Item2*<br/>
Die zweite Quelle.

*_Items*<br/>
Zusätzliche Quellen.

*_PScheduleGroup*<br/>
Das `ScheduleGroup` -Objekt, in dem die Weiterleitungsaufgabe für den `multitype_join` -Meldungsblock geplant ist. Das verwendete `Scheduler` -Objekt wird von der Planungsgruppe impliziert.

### <a name="return-value"></a>Rückgabewert

Ein `greedy multitype_join`-Nachrichtenblock mit zwei oder mehr Eingabequellen.

##  <a name="make_join"></a>  make_join

Erstellt einen `non_greedy multitype_join`-Meldungsblock aus einem optionalen `Scheduler` oder einer `ScheduleGroup` und mindestens zwei Eingabequellen.

```
template<typename T1, typename T2, typename... Ts>
multitype_join<std::tuple<T1, T2, Ts...>>
    make_join(
Scheduler& _PScheduler,
    T1 _Item1,
    T2 _Item2,
    Ts... _Items);

template<typename T1, typename T2, typename... Ts>
multitype_join<std::tuple<T1, T2, Ts...>> make_join(
ScheduleGroup& _PScheduleGroup,
    T1 _Item1,
    T2 _Item2,
    Ts... _Items);

template<typename T1, typename T2, typename... Ts>
multitype_join<std::tuple<T1, T2, Ts...>> make_join(
    T1 _Item1,
    T2 _Item2,
    Ts... _Items);
```

### <a name="parameters"></a>Parameter

*T1*<br/>
Der Meldungsblocktyp der ersten Quelle.

*T2*<br/>
Der Meldungsblocktyp der zweiten Quelle.

*_PScheduler*<br/>
Das `Scheduler` -Objekt, in dem die Weiterleitungsaufgabe für den `multitype_join` -Meldungsblock geplant ist.

*_Item1*<br/>
Die erste Quelle.

*_Item2*<br/>
Die zweite Quelle.

*_Items*<br/>
Zusätzliche Quellen.

*_PScheduleGroup*<br/>
Das `ScheduleGroup` -Objekt, in dem die Weiterleitungsaufgabe für den `multitype_join` -Meldungsblock geplant ist. Das verwendete `Scheduler` -Objekt wird von der Planungsgruppe impliziert.

### <a name="return-value"></a>Rückgabewert

Ein `non_greedy multitype_join`-Nachrichtenblock mit zwei oder mehr Eingabequellen.

##  <a name="make_task"></a>  make_task

Eine Factorymethode zum Erstellen eines `task_handle`-Objekts.

```
template <class _Function>
task_handle<_Function> make_task(const _Function& _Func);
```

### <a name="parameters"></a>Parameter

*_Function*<br/>
Der Typ des Funktionsobjekts, die aufgerufen werden, um die Arbeit, dargestellt durch Ausführen der `task_handle` Objekt.

*_Func*<br/>
Die Funktion, die aufgerufen werden, um die Arbeit, dargestellt durch Ausführen der `task_handle` Objekt. Dies ist möglicherweise eine Lambda-Funktion, ein Zeiger auf eine Funktion oder ein anderes Objekt, das eine Version von den Funktionsaufrufoperator mit der Signatur unterstützt `void operator()()`.

### <a name="return-value"></a>Rückgabewert

Ein `task_handle`-Objekt.

### <a name="remarks"></a>Hinweise

Diese Funktion ist nützlich, wenn Sie erstellen müssen eine `task_handle` Objekt mit einem Lambdaausdruck, da es Ihnen ermöglicht, die das Objekt zu erstellen, ohne zu wissen, welche das Lambda-Funktionselement "true".

##  <a name="parallel_buffered_sort"></a>  parallel_buffered_sort

Ordnet die Elemente in einem angegebenen Bereich in einer aufsteigenden Reihenfolge oder gemäß eines Sortierkriteriums an, das von einem binären Prädikat parallel angegeben wird. Diese Funktion entspricht `std::sort` semantisch darin, dass sie eine vergleichsbasierte, instabile, direkte Sortierung ist, abgesehen von den zusätzlich erforderlichen `O(n)`-Leerzeichen und er notwendigen Standardinitialisierung für die sortierten Elemente.

```
template<typename _Random_iterator>
inline void parallel_buffered_sort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End);

template<typename _Allocator,
    typename _Random_iterator>
inline void parallel_buffered_sort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End);

template<typename _Allocator,
    typename _Random_iterator>
inline void parallel_buffered_sort(
    const _Allocator& _Alloc,
    const _Random_iterator& _Begin,
    const _Random_iterator& _End);

template<typename _Random_iterator,
    typename _Function>
inline void parallel_buffered_sort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End,
    const _Function& _Func,
    const size_t _Chunk_size = 2048);

template<typename _Allocator,
    typename _Random_iterator,
    typename _Function>
inline void parallel_buffered_sort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End,
    const _Function& _Func,
    const size_t _Chunk_size = 2048);

template<typename _Allocator,
    typename _Random_iterator,
    typename _Function>
inline void parallel_buffered_sort(
    const _Allocator& _Alloc,
    const _Random_iterator& _Begin,
    const _Random_iterator& _End,
    const _Function& _Func,
    const size_t _Chunk_size = 2048);
```

### <a name="parameters"></a>Parameter

*_Random_iterator*<br/>
Der iteratortyp, der den Eingabebereich geradzahlig werden soll.

*_Allocator*<br/>
Der Typ des einer C++-Standardbibliothek-kompatiblen Speicher-Zuweisung.

*_Function*<br/>
Der Typ des binären Vergleichsoperator.

*_Begin*<br/>
Ein zufälliger Eingabeiterator, der die Position des ersten Elements in dem Bereich adressiert, der sortiert werden soll.

*_Beenden*<br/>
Ein zufälliger Eingabeiterator, der die Position des ersten Elements direkt hinter dem letzten Element in dem Bereich adressiert, der sortiert werden soll.

*_Alloc*<br/>
Eine Instanz einer C++-Standardbibliothek-kompatiblen Speicher-Zuweisung.

*_Func*<br/>
Eine benutzerdefinierte prädikatfunktionsobjekt, das das Vergleichskriterium erfüllt werden muss, indem aufeinander folgende Elemente in der Reihenfolge definiert. Ein binäres Prädikat akzeptiert zwei Argumente und gibt bei Erfüllung **true** und bei Nichterfüllung **false** zurück. Diese Vergleichoperatorfunktion muss eine strikte schwache Sortierung auf Elementenpaare der Sequenz anwenden.

*_Chunk_size*<br/>
Die Mindestgröße des AutoBildlaufs ein Segment, das in zwei für die parallele Ausführung aufgeteilt werden soll.

### <a name="remarks"></a>Hinweise

Alle Überladungen erfordern `n * sizeof(T)` zusätzlichen Speicherplatz, in denen `n` ist die Anzahl der zu sortierenden Elemente und `T` ist der Typ des Elements. In den meisten Fällen Parallel_buffered_sort zeigt eine Verbesserung der Leistung über [Parallel_sort](concurrency-namespace-functions.md), und Sie sollten es über Parallel_sort verwenden, wenn Sie den verfügbaren Arbeitsspeicher verfügen.

Wenn Sie keinen binären Vergleichsoperator angeben `std::less` dient als die Standardeinstellung, die Typ des Elements, zu der Operator erfordert `operator<()`.

Wenn Sie kein Allocator-Typ oder die Instanz, die C++-Standardbibliothek-Speicherbelegungsfunktion angeben `std::allocator<T>` wird verwendet, um die Puffer zuzuweisen.

Der Algorithmus wird von den Eingabebereich geradzahlig in zwei Blöcke unterteilt und nacheinander wird jeder Block in zwei untergeordnete Blöcke unterteilt für die Ausführung parallel. Das optionale Argument `_Chunk_size` kann verwendet werden, für den Algorithmus an, wenn Blöcke Größe verarbeitet sollte < `_Chunk_size` Seriell.

##  <a name="parallel_for"></a>  "parallel_for"

`parallel_for` durchläuft einen Bereich von Indizes und führt bei jeder Iteration parallel eine vom Benutzer bereitgestellte Funktion aus.

```
template <typename _Index_type, typename _Function, typename _Partitioner>
void parallel_for(
    _Index_type first,
    _Index_type last,
    _Index_type _Step,
    const _Function& _Func,
    _Partitioner&& _Part);

template <typename _Index_type, typename _Function>
void parallel_for(
    _Index_type first,
    _Index_type last,
    _Index_type _Step,
    const _Function& _Func);

template <typename _Index_type, typename _Function>
void parallel_for(
    _Index_type first,
    _Index_type last,
    const _Function& _Func,
    const auto_partitioner& _Part = auto_partitioner());

template <typename _Index_type, typename _Function>
void parallel_for(
    _Index_type first,
    _Index_type last,
    const _Function& _Func,
    const static_partitioner& _Part);

template <typename _Index_type, typename _Function>
void parallel_for(
    _Index_type first,
    _Index_type last,
    const _Function& _Func,
    const simple_partitioner& _Part);

template <typename _Index_type, typename _Function>
void parallel_for(
    _Index_type first,
    _Index_type last,
    const _Function& _Func,
    affinity_partitioner& _Part);
```

### <a name="parameters"></a>Parameter

*_Index_type*<br/>
Der Typ des Indexes für die Iteration verwendet wird.

*_Function*<br/>
Der Typ der Funktion, die bei jeder Iteration ausgeführt wird.

*_Partitioner*<br/>
Der Typ des Partitionierers, der verwendet wird, um den angegebenen Bereich zu partitionieren.

*Erste*<br/>
Der erste Index in einer Iteration einbezogen werden.

*last*<br/>
Der Index nach der letzten Index in einer Iteration einbezogen werden.

*_Step*<br/>
Der Wert, um die Schritte beim Durchlaufen von `first` zu `last`. Der Schritt muss positiv sein. [Invalid_argument](../../../standard-library/invalid-argument-class.md) wird ausgelöst, wenn der Schritt kleiner als 1 ist.

*_Func*<br/>
Die Funktion, die bei jeder Iteration ausgeführt werden. Dies ist möglicherweise ein Lambda-Ausdruck einen Funktionszeiger oder ein anderes Objekt, das eine Version von den Funktionsaufrufoperator mit der Signatur unterstützt `void operator()(_Index_type)`.

*_Part*<br/>
Ein Verweis auf das Objekt kann. Das Argument kann eine der `const` [Auto_partitioner](auto-partitioner-class.md)`&`, `const` [Static_partitioner](static-partitioner-class.md)`&`, `const` [Simple_ Partitionierer](simple-partitioner-class.md) `&` oder [Affinity_partitioner](affinity-partitioner-class.md) `&` Wenn ein [Affinity_partitioner](affinity-partitioner-class.md) Objekt wird verwendet, das der Verweis muss ein l-Wert der nicht konstant sein Verweis, damit der Algorithmus Status für zukünftige Schleifen auf, um die Wiederverwendung speichern kann.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [parallele Algorithmen](../../../parallel/concrt/parallel-algorithms.md).

##  <a name="parallel_for_each"></a>  parallel_for_each

`parallel_for_each` wendet eine angegebene Funktion parallel auf jedes Element innerhalb eines Bereichs an. Sie entspricht semantisch der `for_each`-Funktion im `std`-Namespace, außer dass die Iteration über die Elemente parallel ausgeführt wird und die Reihenfolge der Iteration nicht angegeben ist. Das Argument `_Func` muss einen Funktionsaufrufoperator in der Form `operator()(T)` unterstützen, wobei der Parameter `T` der Elementtyp des durchlaufenen Containers ist.

```
template <typename _Iterator, typename _Function>
void parallel_for_each(
    _Iterator first,
    _Iterator last,
    const _Function& _Func);

template <typename _Iterator, typename _Function, typename _Partitioner>
void parallel_for_each(
    _Iterator first,
    _Iterator last,
    const _Function& _Func,
    _Partitioner&& _Part);
```

### <a name="parameters"></a>Parameter

*_Iterator*<br/>
Der Typ des Iterators, der zum Durchlaufen des Containers verwendet wird.

*_Function*<br/>
Der Typ der Funktion, die auf jedes Element innerhalb des Bereichs angewendet werden.

*_Partitioner*<br/>
*Erste*<br/>
Ein Iterator, der die Position des ersten Elements in parallele Iteration einbezogen werden.

*last*<br/>
Ein Iterator, der die Position hinter dem letzten Element in parallele Iteration einbezogen werden.

*_Func*<br/>
Eine User-defined Function,-Objekt, das jedem Element im Bereich angewendet wird.

*_Part*<br/>
Ein Verweis auf das Objekt kann. Das Argument kann eine der `const` [Auto_partitioner](auto-partitioner-class.md)`&`, `const` [Static_partitioner](static-partitioner-class.md)`&`, `const` [Simple_ Partitionierer](simple-partitioner-class.md) `&` oder [Affinity_partitioner](affinity-partitioner-class.md) `&` Wenn ein [Affinity_partitioner](affinity-partitioner-class.md) Objekt wird verwendet, das der Verweis muss ein l-Wert der nicht konstant sein Verweis, damit der Algorithmus Status für zukünftige Schleifen auf, um die Wiederverwendung speichern kann.

### <a name="remarks"></a>Hinweise

[Auto_partitioner](auto-partitioner-class.md) für die Überladung ohne einen expliziten kann verwendet werden.

Für Iteratoren, die keine zufälligen unterstützen, nur zugreifen [Auto_partitioner](auto-partitioner-class.md) wird unterstützt.

Weitere Informationen finden Sie unter [parallele Algorithmen](../../../parallel/concrt/parallel-algorithms.md).

##  <a name="parallel_invoke"></a>  parallel_invoke

Führt die als Parameter angegebenen Funktionsobjekte parallel aus, und blockiert, bis die Ausführung beendet ist. Jedes Funktionsobjekt kann ein Lambdaausdruck, ein Zeiger auf eine Funktion oder ein anderes Objekt sein, das den Funktionsaufrufoperator mit der Signatur `void operator()()` unterstützt.

```
template <typename _Function1, typename _Function2>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2);

template <typename _Function1, typename _Function2, typename _Function3>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3);

template <typename _Function1,
    typename _Function2,
    typename _Function3,
    typename _Function4>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3,
    const _Function4& _Func4);

template <typename _Function1,
    typename _Function2,
    typename _Function3,
    typename _Function4,
    typename _Function5>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3,
    const _Function4& _Func4,
    const _Function5& _Func5);

template <typename _Function1,
    typename _Function2,
    typename _Function3,
    typename _Function4,
    typename _Function5,
    typename _Function6>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3,
    const _Function4& _Func4,
    const _Function5& _Func5,
    const _Function6& _Func6);

template <typename _Function1,
    typename _Function2,
    typename _Function3,
    typename _Function4,
    typename _Function5,
    typename _Function6,
    typename _Function7>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3,
    const _Function4& _Func4,
    const _Function5& _Func5,
    const _Function6& _Func6,
    const _Function7& _Func7);

template <typename _Function1,
    typename _Function2,
    typename _Function3,
    typename _Function4,
    typename _Function5,
    typename _Function6,
    typename _Function7,
    typename _Function8>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3,
    const _Function4& _Func4,
    const _Function5& _Func5,
    const _Function6& _Func6,
    const _Function7& _Func7,
    const _Function8& _Func8);

template <typename _Function1,
    typename _Function2,
    typename _Function3,
    typename _Function4,
    typename _Function5,
    typename _Function6,
    typename _Function7,
    typename _Function8,
    typename _Function9>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3,
    const _Function4& _Func4,
    const _Function5& _Func5,
    const _Function6& _Func6,
    const _Function7& _Func7,
    const _Function8& _Func8,
    const _Function9& _Func9);

template <typename _Function1,
    typename _Function2,
    typename _Function3,
    typename _Function4,
    typename _Function5,
    typename _Function6,
    typename _Function7,
    typename _Function8,
    typename _Function9,
    typename _Function10>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3,
    const _Function4& _Func4,
    const _Function5& _Func5,
    const _Function6& _Func6,
    const _Function7& _Func7,
    const _Function8& _Func8,
    const _Function9& _Func9,
    const _Function10& _Func10);
```

### <a name="parameters"></a>Parameter

*_Function1*<br/>
Der Typ des ersten Funktionsobjekts parallel ausgeführt werden.

*_Function2*<br/>
Der Typ des zweiten Funktionsobjekts parallel ausgeführt werden.

*_Function3*<br/>
Der Typ des dritten Funktionsobjekts parallel ausgeführt werden.

*_Function4*<br/>
Der Typ des vierten Funktionsobjekts parallel ausgeführt werden.

*_Function5*<br/>
Der Typ des fünften Funktionsobjekts parallel ausgeführt werden.

*_Function6*<br/>
Der Typ des sechsten Funktionsobjekts parallel ausgeführt werden.

*_Function7*<br/>
Der Typ des siebten Funktionsobjekts parallel ausgeführt werden.

*_Function8*<br/>
Der Typ des achten Funktionsobjekts parallel ausgeführt werden.

*_Function9*<br/>
Der Typ des neunten Funktionsobjekts parallel ausgeführt werden.

*_Function10*<br/>
Der Typ des zehnten Funktionsobjekts parallel ausgeführt werden.

*_Func1*<br/>
Das erste Funktionsobjekt parallel ausgeführt werden.

*_Func2*<br/>
Das zweite Funktionsobjekt parallel ausgeführt werden.

*_Func3*<br/>
Das dritte Funktionsobjekt, das parallel ausgeführt werden.

*_Func4*<br/>
Das vierte Funktionsobjekt parallel ausgeführt werden.

*_Func5*<br/>
Das fünfte Funktionsobjekt parallel ausgeführt werden.

*_Func6*<br/>
Das sechste Funktionsobjekt parallel ausgeführt werden.

*_Func7*<br/>
Das siebte Funktionsobjekt parallel ausgeführt werden.

*_Func8*<br/>
Das achte Funktionsobjekt parallel ausgeführt werden.

*_Func9*<br/>
Das neunte Funktionsobjekt parallel ausgeführt werden.

*_Func10*<br/>
Das zehnte Funktionsobjekt parallel ausgeführt werden.

### <a name="remarks"></a>Hinweise

Beachten Sie, dass eine oder mehrere der Funktionsobjekte bereitgestellt werden, wie Parameter Inline im aufrufenden Kontext ausgeführt werden können.

Wenn eine oder mehrere der Funktionsobjekte als Parameter übergeben wird, um diese Funktion eine Ausnahme auslöst, die Runtime wählen Sie eine solche Ausnahme seiner Wahl und aus dem Aufruf zum übertragen wird `parallel_invoke`.

Weitere Informationen finden Sie unter [parallele Algorithmen](../../../parallel/concrt/parallel-algorithms.md).

##  <a name="parallel_radixsort"></a>  parallel_radixsort

Ordnet Elemente in einem angegebenen Bereich mithilfe eines Basis-Sortieralgorithmus in einer absteigenden Reihenfolge an. Dies ist eine stabile Sortierfunktion, die eine Projektionsfunktion erfordert, mit der Elemente zur Sortierung in Schlüssel, die ganzen Zahlen ohne Vorzeichen ähneln, projiziert werden können. Standardinitialisierung ist für die zu sortierenden Elemente erforderlich.

```
template<typename _Random_iterator>
inline void parallel_radixsort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End);

template<typename _Allocator, typename _Random_iterator>
inline void parallel_radixsort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End);

template<typename _Allocator, typename _Random_iterator>
inline void parallel_radixsort(
    const _Allocator& _Alloc,
    const _Random_iterator& _Begin,
    const _Random_iterator& _End);

template<typename _Random_iterator, typename _Function>
inline void parallel_radixsort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End,
    const _Function& _Proj_func,
    const size_t _Chunk_size = 256* 256);

template<typename _Allocator, typename _Random_iterator,
    typename _Function>
inline void parallel_radixsort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End,
    const _Function& _Proj_func,
    const size_t _Chunk_size = 256* 256);

template<typename _Allocator,
    typename _Random_iterator,
    typename _Function>
inline void parallel_radixsort(
    const _Allocator& _Alloc,
    const _Random_iterator& _Begin,
    const _Random_iterator& _End,
    const _Function& _Proj_func,
    const size_t _Chunk_size = 256* 256);
```

### <a name="parameters"></a>Parameter

*_Random_iterator*<br/>
Der iteratortyp, der den Eingabebereich geradzahlig werden soll.

*_Allocator*<br/>
Der Typ des einer C++-Standardbibliothek-kompatiblen Speicher-Zuweisung.

*_Function*<br/>
Der Typ der Projektionsfunktion.

*_Begin*<br/>
Ein zufälliger Eingabeiterator, der die Position des ersten Elements in dem Bereich adressiert, der sortiert werden soll.

*_Beenden*<br/>
Ein zufälliger Eingabeiterator, der die Position des ersten Elements direkt hinter dem letzten Element in dem Bereich adressiert, der sortiert werden soll.

*_Alloc*<br/>
Eine Instanz einer C++-Standardbibliothek-kompatiblen Speicher-Zuweisung.

*_Proj_func*<br/>
Eine benutzerdefinierte Projektion Funktionsobjekt, das ein Element in einen ganzzahligen Wert konvertiert.

*_Chunk_size*<br/>
Die Mindestgröße des AutoBildlaufs ein Segment, das in zwei für die parallele Ausführung aufgeteilt werden soll.

### <a name="remarks"></a>Hinweise

Alle Überladungen erfordern `n * sizeof(T)` zusätzlichen Speicherplatz, in denen `n` ist die Anzahl der zu sortierenden Elemente und `T` ist der Typ des Elements. Ein unärer Projektion Funktionselement mit der Signatur `I _Proj_func(T)` ist erforderlich, um einen Schlüssel, wenn ein Element zurück, in denen `T` ist der Elementtyp und `I` ist ein nicht signierter Ganzzahl-ähnlicher Typ.

Wenn Sie eine Projektionsfunktion nicht angeben, wird eine Standard-Projektionsfunktion die einfach auf das Element zurückgibt, für ganzzahlige Typen verwendet. Die Funktion kann nicht kompiliert werden, wenn das Element nicht als ein ganzzahliger Typ in Abwesenheit einer Projektion-Funktion ist.

Wenn Sie kein Allocator-Typ oder die Instanz, die C++-Standardbibliothek-Speicherbelegungsfunktion angeben `std::allocator<T>` wird verwendet, um die Puffer zuzuweisen.

Der Algorithmus wird von den Eingabebereich geradzahlig in zwei Blöcke unterteilt und nacheinander wird jeder Block in zwei untergeordnete Blöcke unterteilt für die Ausführung parallel. Das optionale Argument `_Chunk_size` kann verwendet werden, für den Algorithmus an, wenn Blöcke Größe verarbeitet sollte < `_Chunk_size` Seriell.

##  <a name="parallel_reduce"></a>  parallel_reduce

Berechnet die Summe aller Elemente in einem angegebenen Bereich, indem aufeinander folgende Teilsummen berechnet werden, oder berechnet das Ergebnis der aufeinander folgenden Teilergebnisse, die auf ähnliche Weise mithilfe eines angegebenen binären Vorgangs (außer Summe) abgerufen werden parallel. `parallel_reduce` entspricht `std::accumulate` semantisch, außer dass der binäre Vorgang assoziativ sein muss und ein Identitätswert anstelle eines Anfangswerts erforderlich ist.

```
template<typename _Forward_iterator>
inline typename std::iterator_traits<_Forward_iterator>::value_type parallel_reduce(
    _Forward_iterator _Begin,
    _Forward_iterator _End,
    const typename std::iterator_traits<_Forward_iterator>::value_type& _Identity);

template<typename _Forward_iterator, typename _Sym_reduce_fun>
inline typename std::iterator_traits<_Forward_iterator>::value_type parallel_reduce(
    _Forward_iterator _Begin,
    _Forward_iterator _End,
    const typename std::iterator_traits<_Forward_iterator>::value_type& _Identity,
    _Sym_reduce_fun _Sym_fun);

template<typename _Reduce_type,
    typename _Forward_iterator,
    typename _Range_reduce_fun,
    typename _Sym_reduce_fun>
inline _Reduce_type parallel_reduce(
    _Forward_iterator _Begin,
    _Forward_iterator _End,
    const _Reduce_type& _Identity,
    const _Range_reduce_fun& _Range_fun,
    const _Sym_reduce_fun& _Sym_fun);
```

### <a name="parameters"></a>Parameter

*_Forward_iterator*<br/>
Der itertatortyp der Bereich für die Eingabe.

*_Sym_reduce_fun*<br/>
Der Typ des symmetrischen reduktionsfunktion. Dies muss ein Funktionstyp mit Signatur `_Reduce_type _Sym_fun(_Reduce_type, _Reduce_type)`, wobei _Reduce_type dasselbe wie der Typ der Identität und der Ergebnistyp der Reduzierung ist. Für die dritte Überladung, Dies dürfte konsistent mit den Ausgabetyp des `_Range_reduce_fun`.

*_Reduce_type*<br/>
Der Typ, mit dem die Eingabe, reduziert wird, der aus der Eingabe Elementtyp unterschiedlich sein kann. Den Rückgabewert und ein Identitätswert wird dieser Typ hat.

*_Range_reduce_fun*<br/>
Der Typ der reduktionsfunktion Bereich. Dies muss ein Funktionstyp mit Signatur `_Reduce_type _Range_fun(_Forward_iterator, _Forward_iterator, _Reduce_type)`, _Reduce_type entspricht der Typ der Identität und der Ergebnistyp der Reduzierung.

*_Begin*<br/>
Ein eingabeiterator, der das erste Element im Bereich reduziert werden sollen.

*_Beenden*<br/>
Ein eingabeiterator, der das Element, das eine Position hinter dem letzten Element im Bereich reduziert werden sollen.

*_Identity*<br/>
Der Identitätswert `_Identity` hat denselben Typ wie der Ergebnistyp der Reduzierung sowie die `value_type` des Iterators für die ersten und zweiten Überladungen. Für die dritte Überladung, der Identitätswert müssen denselben Typ wie der Ergebnistyp der Reduzierung, aber unterschiedlich sein können die `value_type` des Iterators. Muss einen entsprechenden Wert so, dass der Bereich Reduction-Operator `_Range_fun`, bei Anwendung auf einen Bereich eines einzelnen Elements vom Typ `value_type` und der Identitätswert, verhält sich wie eine Typumwandlung der Werte von Typ `value_type` in den Identitätstyp.

*_Sym_fun*<br/>
Die symmetrische-Funktion, die im 2. Teil die Verringerung der verwendet wird. Weitere Informationen finden Sie unter "Hinweise".

*_Range_fun*<br/>
Die Funktion, die in der ersten Phase der Reduzierung verwendet werden. Weitere Informationen finden Sie unter "Hinweise".

### <a name="return-value"></a>Rückgabewert

Das Ergebnis der Reduzierung.

### <a name="remarks"></a>Hinweise

Um eine parallele Reduzierung durchzuführen, wird die Funktion des Bereichs, in Blöcke unterteilt, die basierend auf der Anzahl von Workern für den zugrunde liegenden Planer verfügbar. Die Kürzung erfolgt in zwei Phasen, in der erste Phase führt eine Reduzierung innerhalb jeder Block und die zweite Phase führt eine Reduzierung zwischen den Teilergebnissen aus jeder Block.

Die erste Überladung erfordert, dass des Iterators die `value_type`, `T`identisch sein, als der Typ der Identität Wert sowie der Verringerung der Ergebnistyp. Der Elementtyp T muss den Operator bereitstellen `T T::operator + (T)` um Elemente in jedem Segment zu reduzieren. Denselben Operator wird in der zweiten Phase wird auch verwendet werden.

Die zweite Überladung erfordert außerdem, dass des Iterators die `value_type` identisch sein, als der Typ der Identität Wert sowie der Verringerung der Ergebnistyp. Der angegebene binäre Operator `_Sym_fun` wird in beiden Reduction-Phasen, mit der Identitätswert als Anfangswert für die erste Phase verwendet.

Für die dritte Überladung, die Identity-Werttyp muss identisch sein als der Verringerung der Ergebnistyp des Iterators `value_type` kann von beiden abweichen. Die Verringerung der Bereichsfunktion `_Range_fun` dient in der ersten Phase mit der Identitätswert als den ursprünglichen Wert und der binären Funktion `_Sym_reduce_fun` wird angewendet, um die Ergebnisse in der zweiten Phase sub.

##  <a name="parallel_sort"></a>  parallel_sort

Ordnet die Elemente in einem angegebenen Bereich in einer aufsteigenden Reihenfolge oder gemäß eines Sortierkriteriums an, das von einem binären Prädikat parallel angegeben wird. Diese Funktion entspricht `std::sort` semantisch insofern, dass sie eine vergleichsbasierte, instabile, direkte Sortierung ist.

```
template<typename _Random_iterator>
inline void parallel_sort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End);

template<typename _Random_iterator,typename _Function>
inline void parallel_sort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End,
    const _Function& _Func,
    const size_t _Chunk_size = 2048);
```

### <a name="parameters"></a>Parameter

*_Random_iterator*<br/>
Der iteratortyp, der den Eingabebereich geradzahlig werden soll.

*_Function*<br/>
Der Typ der binären Vergleich zu kennen.

*_Begin*<br/>
Ein zufälliger Eingabeiterator, der die Position des ersten Elements in dem Bereich adressiert, der sortiert werden soll.

*_Beenden*<br/>
Ein zufälliger Eingabeiterator, der die Position des ersten Elements direkt hinter dem letzten Element in dem Bereich adressiert, der sortiert werden soll.

*_Func*<br/>
Eine benutzerdefinierte prädikatfunktionsobjekt, das das Vergleichskriterium erfüllt werden muss, indem aufeinander folgende Elemente in der Reihenfolge definiert. Ein binäres Prädikat akzeptiert zwei Argumente und gibt bei Erfüllung **true** und bei Nichterfüllung **false** zurück. Diese Vergleichoperatorfunktion muss eine strikte schwache Sortierung auf Elementenpaare der Sequenz anwenden.

*_Chunk_size*<br/>
Die Mindestgröße des AutoBildlaufs ein Segment, das in zwei für die parallele Ausführung aufgeteilt werden soll.

### <a name="remarks"></a>Hinweise

Die erste Überladung wird verwendet, den binären Vergleichsoperator `std::less`.

Die zweite überladene verwendet die angegebenen binären-Vergleichsoperators, den die Signatur muss `bool _Func(T, T)` , in denen `T` ist der Typ der Elemente in den Bereich für die Eingabe.

Der Algorithmus wird von den Eingabebereich geradzahlig in zwei Blöcke unterteilt und nacheinander wird jeder Block in zwei untergeordnete Blöcke unterteilt für die Ausführung parallel. Das optionale Argument `_Chunk_size` kann verwendet werden, für den Algorithmus an, wenn Blöcke Größe verarbeitet sollte < `_Chunk_size` Seriell.

##  <a name="parallel_transform"></a>  parallel_transform

Wendet ein angegebenes Funktionsobjekt auf jedes Element in einem Quellbereich oder auf ein Elementpaar aus zwei Quellbereichen an und kopiert die Rückgabewerte des Funktionsobjekts parallel in einen Zielbereich. Diese Funktion entspricht semantisch `std::transform`.

```
template <typename _Input_iterator1,
    typename _Output_iterator,
    typename _Unary_operator>
_Output_iterator parallel_transform(
    _Input_iterator1 first1,
    _Input_iterator1 last1,
    _Output_iterator _Result,
    const _Unary_operator& _Unary_op,
    const auto_partitioner& _Part = auto_partitioner());

template <typename _Input_iterator1,
    typename _Output_iterator,
    typename _Unary_operator>
_Output_iterator parallel_transform(
    _Input_iterator1 first1,
    _Input_iterator1 last1,
    _Output_iterator _Result,
    const _Unary_operator& _Unary_op,
    const static_partitioner& _Part);

template <typename _Input_iterator1,
    typename _Output_iterator,
    typename _Unary_operator>
_Output_iterator parallel_transform(
    _Input_iterator1 first1,
    _Input_iterator1 last1,
    _Output_iterator _Result,
    const _Unary_operator& _Unary_op,
    const simple_partitioner& _Part);

template <typename _Input_iterator1,
    typename _Output_iterator,
    typename _Unary_operator>
_Output_iterator parallel_transform(
    _Input_iterator1 first1,
    _Input_iterator1 last1,
    _Output_iterator _Result,
    const _Unary_operator& _Unary_op,
    affinity_partitioner& _Part);

template <typename _Input_iterator1,
    typename _Input_iterator2,
    typename _Output_iterator,
    typename _Binary_operator,
    typename _Partitioner>
_Output_iterator parallel_transform(
    _Input_iterator1 first1,
    _Input_iterator1 last1,
    _Input_iterator2
first2,
    _Output_iterator _Result,
    const _Binary_operator& _Binary_op,
    _Partitioner&& _Part);

template <typename _Input_iterator1,
    typename _Input_iterator2,
    typename _Output_iterator,
    typename _Binary_operator>
_Output_iterator parallel_transform(
    _Input_iterator1 first1,
    _Input_iterator1 last1,
    _Input_iterator2
first2,
    _Output_iterator _Result,
    const _Binary_operator& _Binary_op);
```

### <a name="parameters"></a>Parameter

*_Input_iterator1*<br/>
Der Typ des ersten oder nur Eingabe-Iterator.

*_Output_iterator*<br/>
Der Typ des Ausgabeiterators.

*_Unary_operator*<br/>
Der Typ der unären kennen, die für jedes Element im Eingabebereich ausgeführt werden.

*_Input_iterator2*<br/>
Der Typ der zweiten Eingabe-Iterator.

*_Binary_operator*<br/>
Der Typ der binären kennen, die paarweise auf Elemente aus der beiden Quellbereiche ausgeführt werden soll.

*_Partitioner*<br/>
*first1*<br/>
Ein eingabeiterator, der die Position des ersten Elements in der ersten oder nur Quellbereich verarbeitet werden sollen.

*Last1*<br/>
Ein eingabeiterator, der die Position hinter dem letzten Element in der ersten oder den zu verarbeitenden nur Quellbereich adressiert.

*_Result*<br/>
Ein Ausgabeiterator, der die Position des ersten Elements im Zielbereich adressiert.

*_Unary_op*<br/>
Ein benutzerdefiniertes unäres Funktionsobjekt, das auf jedes Element im Quellbereich angewendet wird.

*_Part*<br/>
Ein Verweis auf das Objekt kann. Das Argument kann eine der `const` [Auto_partitioner](auto-partitioner-class.md)`&`, `const` [Static_partitioner](static-partitioner-class.md)`&`, `const` [Simple_ Partitionierer](simple-partitioner-class.md) `&` oder [Affinity_partitioner](affinity-partitioner-class.md) `&` Wenn ein [Affinity_partitioner](affinity-partitioner-class.md) Objekt wird verwendet, das der Verweis muss ein l-Wert der nicht konstant sein Verweis, damit der Algorithmus Status für zukünftige Schleifen auf, um die Wiederverwendung speichern kann.

*first2*<br/>
Ein Eingabeiterator, der die Position des ersten Elements im zweiten Quellbereich adressiert.

*_Binary_op*<br/>
Ein benutzerdefiniertes binäres Funktionsobjekt, das paarweise in aufsteigender Reihenfolge, um die zwei Quellbereiche angewendet wird.

### <a name="return-value"></a>Rückgabewert

Ein Ausgabeiterator, der die Position direkt hinter dem letzten Element im Zielbereich adressiert, der die vom Funktionsobjekt umgewandelten Ausgabeelemente erhält.

### <a name="remarks"></a>Hinweise

[Auto_partitioner](auto-partitioner-class.md) für die Überladungen ohne explizite Partitionierer Argument verwendet werden.

Für Iteratoren, die keine zufälligen unterstützen, nur zugreifen [Auto_partitioner](auto-partitioner-class.md) wird unterstützt.

Die Überladungen, die das Argument `_Unary_op` Eingabebereich in den Ausgabebereich durch Anwenden der unäre Funktionselement auf jedes Element im Eingabebereich zu transformieren. `_Unary_op` muss den Funktionsaufrufoperator mit Signatur unterstützen `operator()(T)` , in denen `T` ist der Werttyp des Bereichs durchlaufen wird.

Die Überladungen, die das Argument `_Binary_op` zwei Eingabe-Bereiche in den Ausgabebereich durch Anwenden von das binäre Funktionselement auf ein Element aus den ersten Eingabebereich geradzahlig und ein Element aus der zweiten Eingabebereich zu transformieren. `_Binary_op` muss den Funktionsaufrufoperator mit Signatur unterstützen `operator()(T, U)` , in denen `T`, `U` sind die Werttypen der eingabeiteratoren zwei.

Weitere Informationen finden Sie unter [parallele Algorithmen](../../../parallel/concrt/parallel-algorithms.md).

##  <a name="receive"></a>  Empfangen

Eine allgemeine Empfangsimplementierung, mit der ein Kontext auf Daten von genau einer Quelle warten und die akzeptierten Werte filtern kann.

```
template <class T>
T receive(
    _Inout_ ISource<T>* _Src,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);

template <class T>
T receive(
    _Inout_ ISource<T>* _Src,
    typename ITarget<T>::filter_method const& _Filter_proc,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);

template <class T>
T receive(
    ISource<T>& _Src,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);

template <class T>
T receive(
    ISource<T>& _Src,
    typename ITarget<T>::filter_method const& _Filter_proc,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der Typ der Ereignisnutzlast.

*_Src*<br/>
Ein Zeiger oder Verweis auf die von dem Daten erwartet werden.

*_Timeout*<br/>
Die maximale Zeit für die die Methode sollte für die Daten in Millisekunden.

*_Filter_proc*<br/>
Eine Filterfunktion, die bestimmt, ob Nachrichten akzeptiert werden sollen.

### <a name="return-value"></a>Rückgabewert

Ein Wert aus der Quelle, der den Typ der Nutzlast.

### <a name="remarks"></a>Hinweise

Wenn der Parameter `_Timeout` verfügt über einen anderen Wert als die Konstante `COOPERATIVE_TIMEOUT_INFINITE`, der die Ausnahme [Operation_timed_out](operation-timed-out-class.md) wird ausgelöst, wenn die angegebene Zeitspanne abläuft, bevor eine Nachricht empfangen wird. Wenn Sie einen Timeout mit der Länge 0 (null) möchten, verwenden Sie die [Try_receive](concurrency-namespace-functions.md) -Funktion im Gegensatz zu Aufrufen `receive` mit einem Timeout von `0` (null), wie es effizienter ist, und keine Ausnahmen bei Timeouts löst.

Weitere Informationen finden Sie unter [Message Passing Functions](../../../parallel/concrt/message-passing-functions.md).

##  <a name="run_with_cancellation_token"></a>  run_with_cancellation_token

Führt sofort synchron ein Funktionsobjekt im Kontext eines angegebenen Abbruchtokens aus.

```
template<typename _Function>
void run_with_cancellation_token(
    const _Function& _Func,
    cancellation_token _Ct);
```

### <a name="parameters"></a>Parameter

*_Function*<br/>
Der Typ des Funktionsobjekts, die aufgerufen wird.

*_Func*<br/>
Das Funktionsobjekt, das ausgeführt wird. Dieses Objekt muss es sich um den Funktionsaufruf-Operator mit einer Signatur von void(void) unterstützen.

*_Ct*<br/>
Das Abbruchtoken, das den impliziten Abbruch des Funktionsobjekts gesteuert wird. Verwendung `cancellation_token::none()` Wenn die Ausführung der Funktion ohne das Risiko einer impliziten Abbruch aus eine übergeordnete Aufgabengruppe, die abgebrochen werden sollen.

### <a name="remarks"></a>Hinweise

Der Unterbrechungspunkte in dem Funktionsobjekt werden ausgelöst, wenn die `cancellation_token` abgebrochen wird. Das explizite Token `_Ct` wird isolieren Sie `_Func` aus übergeordneten Abbruch, wenn das übergeordnete Element ein anderes Token "oder" kein Token verfügt.

##  <a name="send"></a>  Senden

Ein synchroner Sendevorgang, der wartet, bis das Ziel die Meldung akzeptiert oder ablehnt.

```
template <class T>
bool send(_Inout_ ITarget<T>* _Trg, const T& _Data);

template <class T>
bool send(ITarget<T>& _Trg, const T& _Data);
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der Typ der Ereignisnutzlast.

*_Trg*<br/>
Ein Zeiger oder Verweis auf das Ziel, an dem Daten gesendet werden.

*"_Data"*<br/>
Ein Verweis auf die Daten gesendet werden.

### <a name="return-value"></a>Rückgabewert

**"true"** , wenn die Meldung akzeptiert wurde, **"false"** andernfalls.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [Message Passing Functions](../../../parallel/concrt/message-passing-functions.md).

##  <a name="set_ambient_scheduler"></a>  set_ambient_scheduler

```
inline void set_ambient_scheduler(std::shared_ptr<::Concurrency::scheduler_interface> _Scheduler);
```

### <a name="parameters"></a>Parameter

*_Scheduler*<br/>
Der ambientenplaner festlegen.

##  <a name="set_task_execution_resources"></a>  set_task_execution_resources

Schränkt die Ausführungsressourcen, die von den internen Arbeitsthreads der Concurrency Runtime verwendet werden, auf den angegebenen Affinitätssatz ein.

Es ist nur gültig, diese Methode vor Erstellung des Ressourcen-Managers oder zwischen der Lebensdauer zweier Ressourcen-Manager aufzurufen. Sie kann mehrmals aufgerufen werden, solange der Ressourcen-Manager zum Zeitpunkt des Aufrufs nicht vorhanden ist. Nachdem eine Affinitätsgrenze eingerichtet wurde, bleibt diese bis zum nächsten gültigen Aufruf der `set_task_execution_resources`-Methode bestehen.

Die bereitgestellte Affinitätsmaske muss keine Teilmenge der Prozessaffinitätsmaske sein. Die Prozessaffinität wird bei Bedarf aktualisiert.

```
void __cdecl set_task_execution_resources(
    DWORD_PTR _ProcessAffinityMask);

void __cdecl set_task_execution_resources(
    unsigned short count,
    PGROUP_AFFINITY _PGroupAffinity);
```

### <a name="parameters"></a>Parameter

*_ProcessAffinityMask*<br/>
Die Affinity Mask, die die Concurrency Runtime-Arbeitsthreads auf beschränkt werden. Verwenden Sie diese Methode auf einem System mit mehr als 64 Hardwarethreads nur, wenn Sie die Concurrency Runtime auf einen Teil der aktuellen prozessorgruppe beschränken möchten. Im Allgemeinen sollten Sie die Version der Methode verwenden, die akzeptiert ein Array von Affinitäten zwischen Gruppe und als Parameter, um die Affinität auf Computern mit mehr als 64 Hardwarethreads zu beschränken.

*count*<br/>
Die Anzahl der `GROUP_AFFINITY` Einträge im Array durch den Parameter angegebene `_PGroupAffinity`.

*_PGroupAffinity*<br/>
Ein Array von `GROUP_AFFINITY` Einträge.

### <a name="remarks"></a>Hinweise

Die Methode löst eine [Invalid_operation](invalid-operation-class.md) -Ausnahme aus, wenn ein Ressourcen-Manager vorhanden ist, zu dem Zeitpunkt es aufgerufen wird ist, und ein [Invalid_argument](../../../standard-library/invalid-argument-class.md) -Ausnahme aus, wenn die Ergebnisse in einen leeren Satz von Affinität angegebene Ressourcen zu.

Die Version der Methode, die ein Array von Affinitäten zwischen Gruppe und als Parameter verwendet, sollte nur verwendet wird unter Betriebssystemen mit Version Windows 7 oder höher sein. Andernfalls ein [Invalid_operation](invalid-operation-class.md) Ausnahme ausgelöst.

Die Prozessaffinität programmgesteuert zu ändern, nachdem diese Methode aufgerufen wurde werden nicht dazu führen, dass der Ressourcen-Manager, die Affinität neu zu überdenken, die, der es auf beschränkt ist. Aus diesem Grund sollten alle Änderungen zum Verarbeiten von Affinität vorgenommen werden, vor dem Aufrufen dieser Methode.

##  <a name="swap"></a>  swap

Tauscht die Elemente zweier `concurrent_vector`-Objekte.

```
template<typename T, class _Ax>
inline void swap(
    concurrent_vector<T, _Ax>& _A,
    concurrent_vector<T, _Ax>& _B);
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der Datentyp der Elemente in gleichzeitigen Vektoren gespeichert werden soll.

*_Ax*<br/>
Der Zuweisungstyp der gleichzeitigen Vektoren.

*_A*<br/>
Der gleichzeitigen Vektor, dessen Elemente mit denen des Vektors gleichzeitige ausgetauscht werden sollen `_B`.

*_B HAT*<br/>
Den gleichzeitigen Vektor, in dem Elemente ausgetauscht werden sollen, oder der Vektor, dessen Elemente ausgetauscht werden, mit denen der gleichzeitigen Vektor `_A`.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion ist ein Algorithmus, spezialisiert auf die Containerklasse `concurrent_vector` , führen Sie die Memberfunktion `_A`. [concurrent_vector:: Swap](concurrent-vector-class.md#swap)( `_B`). Hierbei handelt es sich um Instanzen der partiellen Sortierung von Funktionsvorlagen durch den Compiler. Wenn Vorlagenfunktionen so überladen werden, dass die Übereinstimmung der Vorlage mit dem Funktionsaufruf nicht eindeutig ist, wählt der Compiler die spezialisierteste Version der Vorlagenfunktion. Die allgemeine Version der Vorlagenfunktion, `template <class T> void swap(T&, T&)`, in der Algorithmusklasse funktioniert per Zuweisung und ist ein langsamer Vorgang. Die spezialisierte Version in jedem Container ist viel schneller, da sie mit der internen Darstellung der Containerklasse verwendet werden kann.

Diese Methode ist nicht nebenläufigkeitssicher. Sie müssen sicherstellen, dass keine anderen Threads Vorgänge für einen der gleichzeitigen Vektoren ausführen, wenn Sie diese Methode aufrufen.

##  <a name="task_from_exception"></a>  task_from_exception

```
template<typename _TaskType, typename _ExType>
task<_TaskType> task_from_exception(
    _ExType _Exception,
    const task_options& _TaskOptions = task_options());
```

### <a name="parameters"></a>Parameter

*_TaskType*<br/>

*_ExType*<br/>

*_Exception*<br/>

*_TaskOptions*<br/>

### <a name="return-value"></a>Rückgabewert

##  <a name="task_from_result"></a>  task_from_result

```
template<typename T>
task<T> task_from_result(
    T _Param,
    const task_options& _TaskOptions = task_options());

inline task<bool> task_from_result(ool _Param);

inline task<void> task_from_result(
    const task_options& _TaskOptions = task_options());
```

### <a name="parameters"></a>Parameter

*T*<br/>

*_Param*<br/>

*_TaskOptions*<br/>

### <a name="return-value"></a>Rückgabewert

##  <a name="trace_agents_register_name"></a>  Trace_agents_register_name

Ordnet den angegebenen Namen dem Nachrichtenblock oder dem Agent in der ETW-Ablaufverfolgung zu.

```
template <class T>
void Trace_agents_register_name(
    _Inout_ T* _PObject,
    _In_z_ const wchar_t* _Name);
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der Typ des Objekts. Dies ist normalerweise ein Nachrichtenblock oder eines Agents.

*_PObject*<br/>
Ein Zeiger auf dem Nachrichtenblock oder dem Agent, der in der Ablaufverfolgung benannt ist.

*_Name*<br/>
Der Name für das angegebene Objekt.

##  <a name="try_receive"></a>  try_receive

Eine allgemeine try-receive-Implementierung, mit der ein Kontext Daten von genau einer Quelle suchen und die akzeptierten Werte filtern kann. Die Methode gibt zurück, wenn die Daten nicht bereit ist, **"false"**.

```
template <class T>
bool try_receive(_Inout_ ISource<T>* _Src, T& _value);

template <class T>
bool try_receive(
    _Inout_ ISource<T>* _Src,
    T& _value,
    typename ITarget<T>::filter_method const& _Filter_proc);

template <class T>
bool try_receive(ISource<T>& _Src, T& _value);

template <class T>
bool try_receive(
    ISource<T>& _Src,
    T& _value,
    typename ITarget<T>::filter_method const& _Filter_proc);
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der Typ der Ereignisnutzlast

*_Src*<br/>
Ein Zeiger oder Verweis auf die von dem Daten erwartet werden.

*"_value"*<br/>
Ein Verweis auf einen Speicherort, in dem das Ergebnis platziert werden.

*_Filter_proc*<br/>
Eine Filterfunktion, die bestimmt, ob Nachrichten akzeptiert werden sollen.

### <a name="return-value"></a>Rückgabewert

Ein `bool` Wert, der angibt, ob eine Nutzlast in abgelegt wurde `_value`.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [Message Passing Functions](../../../parallel/concrt/message-passing-functions.md).

##  <a name="wait"></a>  Warte

Hält den aktuellen Kontext für eine bestimmte Zeit an.

```
void __cdecl wait(unsigned int _Milliseconds);
```

### <a name="parameters"></a>Parameter

*_Milliseconds*<br/>
Die Anzahl der Millisekunden, denen für der aktuelle Kontext angehalten werden soll. Wenn die `_Milliseconds` Parametersatz wird auf den Wert `0`, der aktuelle Kontext sollten yield-Ausführung zu anderen Kontexten ausgeführt, bevor Sie fortfahren.

### <a name="remarks"></a>Hinweise

Wenn diese Methode für einen Scheduler-Kontext von Concurrency Runtime aufgerufen wird, findet das Zeitplanungsmodul einen anderen Kontext auf die zugrunde liegende Ressource ausführen. Da der Scheduler grundsätzlich kooperativ ist, kann nicht diesen Kontext genau nach der angegebenen Anzahl von Millisekunden fortgesetzt werden. Wenn der Scheduler mit dem Ausführen von anderen Aufgaben, die nicht an dem Scheduler kooperativ zurückgehalten werden ausgelastet ist, kann die Wartezeit auf unbestimmte sein.

##  <a name="when_all"></a>  when_all

Erstellt eine Aufgabe, die erfolgreich abgeschlossen wird, wenn alle als Argumente angegeben Aufgaben erfolgreich abgeschlossen werden.

```
template <typename _Iterator>
auto when_all(
    _Iterator _Begin,
    _Iterator _End,
    const task_options& _TaskOptions = task_options()) ->
    decltype (details::_WhenAllImpl<typename std::iterator_traits<_Iterator>::value_type::result_type,
    _Iterator>::_Perform(_TaskOptions, _Begin,  _End));
```

### <a name="parameters"></a>Parameter

*_Iterator*<br/>
Der Typ des Eingabeiterators.

*_Begin*<br/>
Die Position des ersten Elements in dem Bereich von Elementen, die mit der resultierenden Aufgabe kombiniert werden sollen.

*_Beenden*<br/>
Die Position des ersten Elements hinter dem Bereich von Elementen, die mit der resultierenden Aufgabe kombiniert werden sollen.

*_TaskOptions*<br/>
Das `task_options`-Objekt.

### <a name="return-value"></a>Rückgabewert

Eine Aufgabe, die erfolgreich abgeschlossen ist, wenn alle Eingabeaufgaben erfolgreich abgeschlossen wurden. Wenn die Eingabeaufgaben vom Typ `T` sind, wird die Ausgabe dieser Funktion `task<std::vector<T>>` sein. Wenn die Eingabeaufgaben vom Typ `void` sind, ist die Ausgabeaufgabe auch `task<void>`.

### <a name="remarks"></a>Hinweise

`when_all` ist eine nicht blockierende Funktion, die `task` als Ergebnis erzeugt. Im Gegensatz zu [Task:: wait](task-class.md#wait), es ist sicher, diese Funktion in einer UWP-app auf dem ASTA (Application STA-) Thread aufzurufen.

Wenn eine der Aufgaben abgebrochen wird oder eine Ausnahme auslöst, die zurückgegebene Aufgabe früh im abgebrochenen Zustand abgeschlossen wird und die Ausnahme, sofern Sie auftritt, wird ausgelöst wird, wenn Sie aufrufen [Task:: Get](task-class.md#get) oder `task::wait` für diese Aufgabe.

Weitere Informationen finden Sie unter [Aufgabenparallelität](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).

##  <a name="when_any"></a>  when_any

Erstellt eine Aufgabe, die erfolgreich abgeschlossen wird, wenn eine der als Argumente angegeben Aufgaben erfolgreich abgeschlossen wird.

```
template<typename _Iterator>
auto when_any(
    _Iterator _Begin,
    _Iterator _End,
    const task_options& _TaskOptions = task_options())
    -> decltype (
        details::_WhenAnyImpl<
            typename std::iterator_traits<_Iterator>::value_type::result_type,
            _Iterator>::_Perform(_TaskOptions, _Begin, _End));

template<typename _Iterator>
auto when_any(
    _Iterator _Begin,
    _Iterator _End,
    cancellation_token _CancellationToken)
       -> decltype (
           details::_WhenAnyImpl<
               typename std::iterator_traits<_Iterator>::value_type::result_type,
               _Iterator>::_Perform(_CancellationToken._GetImplValue(), _Begin, _End));
```

### <a name="parameters"></a>Parameter

*_Iterator*<br/>
Der Typ des Eingabeiterators.

*_Begin*<br/>
Die Position des ersten Elements in dem Bereich von Elementen, die mit der resultierenden Aufgabe kombiniert werden sollen.

*_Beenden*<br/>
Die Position des ersten Elements hinter dem Bereich von Elementen, die mit der resultierenden Aufgabe kombiniert werden sollen.

*_TaskOptions*<br/>
*_CancellationToken*<br/>
Das Abbruchtoken, das den Abbruch der zurückgegebenen Aufgabe steuert. Wenn Sie kein Abbruchtoken bereitstellen, erhält die resultierende Aufgabe das Abbruchtoken der Aufgabe, die ihren Abschluss verursacht.

### <a name="return-value"></a>Rückgabewert

Eine Aufgabe, die erfolgreich abgeschlossen ist, wenn eine der Eingabeaufgaben erfolgreich abgeschlossen wurde. Wenn die Eingabeaufgaben vom Typ `T` sind, ist die Ausgabe dieser Funktion `task<std::pair<T, size_t>>>`, wobei das erste Element des Paares das Ergebnis der letzten Aufgabe ist, und das zweite Element der Index der beendeten Aufgabe. Wenn die Eingabeaufgaben vom Typ `void` sind, ist die Ausgabe `task<size_t>`, wobei das Ergebnis der Index der abgeschlossenen Aufgabe ist.

### <a name="remarks"></a>Hinweise

`when_any` ist eine nicht blockierende Funktion, die `task` als Ergebnis erzeugt. Im Gegensatz zu [Task:: wait](task-class.md#wait), es ist sicher, diese Funktion in einer UWP-app auf dem ASTA (Application STA-) Thread aufzurufen.

Weitere Informationen finden Sie unter [Aufgabenparallelität](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)
