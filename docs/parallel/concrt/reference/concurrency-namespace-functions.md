---
title: Concurrency-Namespace Funktionen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
ms.assetid: 520a6dff-9324-4df2-990d-302e3050af6a
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 66cf776e02d286b04c4fe9338d74d6a9db196a68
ms.sourcegitcommit: 0523c88b24d963c33af0529e6ba85ad2c6ee5afb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/10/2018
---
# <a name="concurrency-namespace-functions"></a>Concurrency-Namespace-Funktionen
||||  
|-|-|-|  
|[Alloc](#alloc)|[CreateResourceManager](#createresourcemanager)|[DisableTracing](#disabletracing)|  
|[EnableTracing](#enabletracing)|[Frei](#free)|[GetExecutionContextId](#getexecutioncontextid)|  
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
 `_NumBytes`  
 Die Anzahl der Bytes an Arbeitsspeicher zugewiesen werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den neu reservierten Speicher.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen darüber, welche Szenarien in Ihrer Anwendung profitieren könnten, von der Verwendung der Unterbelegungsfunktion für die Zwischenspeicherung finden Sie unter [Taskplaner](../../../parallel/concrt/task-scheduler-concurrency-runtime.md).  
  
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
 `T`  
 Der Typ der Daten, die gesendet werden.  
  
 `_Trg`  
 Ein Zeiger oder Verweis auf das Ziel, an den Daten gesendet werden.  
  
 `_Data`  
 Ein Verweis auf die Daten gesendet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 `true` Wenn die Meldung akzeptiert wurde, bevor die Methode zurückgegeben, `false` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Message Passing Functions](../../../parallel/concrt/message-passing-functions.md).  
  
##  <a name="cancel_current_task"></a>  cancel_current_task  
 Bricht die gerade ausgeführte Aufgabe ab. Diese Funktion kann aus dem Text einer Aufgabe aufgerufen werden, um die Ausführung der Aufgabe abzubrechen und ihn dabei in den `canceled` Zustand übergehen zu lassen.  
  
 Der Aufruf dieser Funktion, wenn Sie sich nicht innerhalb des Texts von einem `task` befinden, ist kein unterstütztes Szenario. Dies würde zu nicht definiertem Verhalten, wie einem Absturz oder einem Hänger in der Anwendung, führen.  
  
```
inline __declspec(noreturn) void __cdecl cancel_current_task();
```  
  
##  <a name="clear"></a>  Deaktivieren  
 Löscht die gleichzeitige Warteschlange, zerstört alle derzeit in die Warteschlange eingereihten Elemente. Diese Methode ist nicht nebenläufigkeitssicher.  
  
```
template<typename T, class _Ax>
void concurrent_queue<T, _Ax>::clear();
```   
  
### <a name="parameters"></a>Parameter  
 `T`  
 `_Ax`  
  
##  <a name="create_async"></a>  create_async  
 Erstellt ein asynchrones Konstrukt der Windows Runtime auf einem vom Benutzer angegebenes Lambda oder Funktionsobjekt. Der Rückgabetyp von `create_async` ist entweder `IAsyncAction^`, `IAsyncActionWithProgress<TProgress>^`, `IAsyncOperation<TResult>^` oder `IAsyncOperationWithProgress<TResult, TProgress>^` auf Grundlage der Signatur des Lambda-Ausdrucks, der an die Methode übergeben wurde.  
  
```
template<typename _Function>
__declspec(noinline) auto create_async(const _Function& _Func)
    -> decltype(ref new details::_AsyncTaskGeneratorThunk<_Function>(_Func));
```  
  
### <a name="parameters"></a>Parameter  
 `_Function`  
 `_Func`  
 Der Lambda-Ausdruck oder das Funktionsobjekt, aus dem ein asynchrones Windows-Runtime-Konstrukt erstellt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein asynchrones Konstrukt, dargestellt durch IAsyncAction ^, IAsyncActionWithProgress\<TProgress > ^, IAsyncOperation\<TResult > ^, oder IAsyncOperationWithProgress\<TResult, TProgress > ^. Die Schnittstelle, die zurückgegeben wird, hängt von der Signatur des Lambda-Ausdrucks ab, der an die Funktion übergeben wird.  
  
### <a name="remarks"></a>Hinweise  
 Der Rückgabetyp des Lambdaausdrucks bestimmt, ob das Konstrukt eine Aktion oder ein Vorgang ist.  
  
 Lambda-Ausdrücke, die "void" zurückgeben, führen zur Erstellung von Aktionen. Lambda-Ausdrücke, die ein Ergebnis vom Typ `TResult` zurückgeben, führen zur Erstellung von TResult-Vorgängen.  
  
 Der Lambda-Ausdruck kann auch `task<TResult>` zurückgeben, was die asynchronen Abläufe kapselt, oder die Fortsetzung einer Kette von Aufgaben ist, die die asynchronen Abläufe darstellen. In diesem Fall wird der Lambda-Ausdruck selbst inline ausgeführt, da die Aufgaben asynchron ausgeführt werden, und der Rückgabetyp des Lambda-Ausdrucks wird entpackt, um das von `create_async` zurückgegebene asynchrone Konstrukt zu erstellen. Dies bedeutet, dass ein Lambda-Ausdruck, der eine Aufgabe zurückgibt\<"void" > führt dazu, dass die Erstellung von Aktionen und ein Lambda-Ausdruck, der eine Aufgabe zurückgibt\<TResult > führt dazu, dass die Erstellung von TResult-Vorgängen.  
  
 Der Lambda-Ausdruck akzeptiert null, ein oder zwei Argumente. Die gültigen Argumente sind `progress_reporter<TProgress>` und `cancellation_token` in dieser Reihenfolge, wenn beide verwendet werden. Ein Lambda-Ausdruck ohne Argumente bewirkt die Erstellung eines asynchronen Konstrukts ohne die Möglichkeit der Statusberichterstellung. Ein Lambda-Ausdruck, der eine Progress_reporter akzeptiert\<TProgress > führt dazu, dass `create_async` ein asynchrones Konstrukt zurückgeben, die Bearbeitung des Typs TProgress jedes Mal meldet die `report` -Methode Progress_reporter-Objekt aufgerufen wird. Ein Lambda-Ausdruck, der ein „cancellation_token“ verwendet, kann dieses Token verwenden, um auf einen Abbruch zu prüfen, oder es an Aufgaben übergeben, die er erstellt, sodass ein Abbruch des asynchronen Konstrukts den Abbruch dieser Aufgaben verursacht.  
  
 Wenn der Text des Lambda-Ausdrucks oder der Funktion ein Ergebnis zurückgibt (und keiner anderen Aufgabe\<TResult >), wird der Lambda-Ausdruck innerhalb des Prozesses MTA im Kontext einer Aufgabe die Common Language Runtime implizit dafür erstellt asynchron ausgeführt werden. Die `IAsyncInfo::Cancel`-Methode verursacht den Abbruch der impliziten Aufgabe.  
  
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
 Mehrere nachfolgende Aufrufe dieser Methode geben die gleiche Instanz des Ressourcen-Managers zurück. Bei jedem Aufruf der Methode inkrementiert ein Verweis auf die Ressourcen-Manager, und muss mit einem Aufruf von abgeglichen werden die [IResourceManager:: Release](http://msdn.microsoft.com/en-us/5d1356ec-fbd3-4284-a361-1e9e20bbb522) Methode, wenn der Planer erfolgt Kommunikation mit dem Ressourcen-Manager.  
  
 [Unsupported_os](unsupported-os-class.md) wird ausgelöst, wenn das Betriebssystem nicht von der Concurrency Runtime unterstützt wird.  
  
##  <a name="create_task"></a>  create_task  
 Erstellt ein PPL- [Aufgabe](http://msdn.microsoft.com/en-us/5389e8a5-5038-40b6-844a-55e9b58ad35f) Objekt. Das Element `create_task` kann überall dort verwendet werden, wo Sie einen Aufgabenkonstruktor verwendet hätten. Es wird hauptsächlich der Einfachheit halber bereitgestellt, da es beim Erstellen eines Tasks die Verwendung des `auto`-Schlüsselwort ermöglicht.  
  
```
template<typename T>
__declspec(noinline) auto create_task(T _Param, const task_options& _TaskOptions = task_options())
    -> task<typename details::_TaskTypeFromParam<T>::T>;

template<typename _ReturnType>
__declspec( noinline) task<_ReturnType> create_task(const task<_ReturnType>& _Task);
```  
  
### <a name="parameters"></a>Parameter  
 `T`  
 Der Typ des Parameters, von dem die Aufgabe erstellt werden soll.  
  
 `_ReturnType`  
 `_Param`  
 Der Parameter, von dem die Aufgabe erstellt werden soll. Dies ist möglicherweise ein Lambda- oder Funktionsobjekt-Objekt, eine `task_completion_event` -Objekt, ein anderes `task` Objekt oder eine Windows::Foundation::IAsyncInfo-Schnittstelle, die bei Verwendung von Aufgaben in Ihrer uwp-app.  
  
 `_TaskOptions`  
 `_Task`  
  
### <a name="return-value"></a>Rückgabewert  
 Ein neuer Task des Typs `T`, der von `_Param` abgeleitet wird.  
  
### <a name="remarks"></a>Hinweise  
 Die erste Überladung verhält sich wie ein Aufgabenkonstruktor, der einen einzelnen Parameter akzeptiert.  
  
 Die zweite Überladung weist das Abbruchtoken, das der neu erstellten Aufgabe bereitgestellt wird, zu. Wenn Sie diese Überladung verwenden, ist die Übergabe eines anderen `task`-Objekts als erster Parameter nicht zulässig.  
  
 Der Typ des zurückgegebenen Tasks wird vom ersten Parameter zur Funktion abgeleitet. Wenn `_Param` ein `task_completion_event<T>`, ein `task<T>` oder ein Funktionselement ist, das entweder den Typ `T` oder `task<T>` zurückgibt, ist der Typ des erstellten Tasks `task<T>`.  
  
 In einer uwp-app Wenn `_Param` ist vom Typ iasyncoperation\<T > ^ oder Windows::Foundation::IAsyncOperationWithProgress\<T, P > ^, oder ein Funktionselement ist, das einen dieser Typen zurückgibt, das der erstellte Aufgabe durchgeführt werden kann Typ `task<T>`. Wenn `_Param` ist vom Typ iasyncaction ^ oder Windows::Foundation::IAsyncActionWithProgress\<P > ^, oder ein Funktionselement ist, das einen dieser Typen zurückgibt, das der erstellte Aufgabe Typ `task<void>`.  
  
##  <a name="disabletracing"></a>  DisableTracing  
 Deaktiviert die Ablaufverfolgung in der Concurrency Runtime. Diese Funktion ist veraltet, da die Registrierung der ETW-Ablaufverfolgung standardmäßig aufgehoben wird.  
  
```
__declspec(deprecated("Concurrency::DisableTracing is a deprecated function.")) _CRTIMP HRESULT __cdecl DisableTracing();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Ablaufverfolgung ordnungsgemäß deaktiviert wurde, `S_OK` wird zurückgegeben. Wenn die Ablaufverfolgung nicht zuvor initiiert wurde, `E_NOT_STARTED` zurückgegeben  
  
##  <a name="enabletracing"></a>  EnableTracing  
 Aktiviert die Ablaufverfolgung in der Concurrency Runtime. Diese Funktion ist veraltet, da die Registrierung der ETW-Ablaufverfolgung jetzt standardmäßig erfolgt.  
  
```
__declspec(deprecated("Concurrency::EnableTracing is a deprecated function.")) _CRTIMP HRESULT __cdecl EnableTracing();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn Tracing ordnungsgemäß initiiert wurde, `S_OK` zurückgegeben andernfalls, `E_NOT_STARTED` wird zurückgegeben.  
  
##  <a name="free"></a>  Frei  
 Gibt einen Speicherblock frei, der zuvor mit der `Alloc`-Methode der Unterbelegungsfunktion für die Zwischenspeicherung der Concurrency Runtime reserviert wurde.  
  
```
void __cdecl Free(_Pre_maybenull_ _Post_invalid_ void* _PAllocation);
```  
  
### <a name="parameters"></a>Parameter  
 `_PAllocation`  
 Ein Zeiger auf den Arbeitsspeicher, der zuvor mit der `Alloc`-Methode reserviert wurde und jetzt freigegeben werden soll. Wenn der `_PAllocation`-Parameter auf den Wert `NULL` festgelegt wurde, ignoriert diese Methode den Parameter und kehrt sofort zurück.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen darüber, welche Szenarien in Ihrer Anwendung profitieren könnten, von der Verwendung der Unterbelegungsfunktion für die Zwischenspeicherung finden Sie unter [Taskplaner](../../../parallel/concrt/task-scheduler-concurrency-runtime.md).  
  
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
 Mit dieser Methode können Sie um einen Bezeichner für den Ausführungskontext zu erhalten, bevor Sie übergeben ein `IExecutionContext` Schnittstelle als Parameter an eine der Methoden, die vom Ressourcen-Manager angeboten.  
  
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
 Mit dieser Methode können Sie um einen Bezeichner für den Planer zu erhalten, bevor Sie übergeben ein `IScheduler` Schnittstelle als Parameter an eine der Methoden, die vom Ressourcen-Manager angeboten.  
  
##  <a name="internal_assign_iterators"></a>  internal_assign_iterators  
  
```
template<typename T, class _Ax>
template<class _I> 
void concurrent_vector<T, _Ax>::internal_assign_iterators(
   _I first,
   _I last);
```   
  
### <a name="parameters"></a>Parameter  
 `T`  
 `_Ax`  
 `_I`  
 `first`  
 `last`  
  
##  <a name="interruption_point"></a>  interruption_point  
 Erstellt einen Unterbrechungspunkt für den Abbruch. Wenn ein Abbruch im Kontext, in dem diese Funktion aufgerufen wird, ausgeführt wird, löst diese eine interne Ausnahme aus, mit der die Ausführung der aktuell ausgeführten parallelen Verarbeitung abgebrochen wird. Wenn kein Abbruch ausgeführt wird, bleibt die Funktion untätig.  
  
```
inline void interruption_point();
```  
  
### <a name="remarks"></a>Hinweise  
 Sie sollten nicht Abfangen von ausgelöste Ausnahme interner Abbruch der `interruption_point()` Funktion. Die Ausnahme abgefangen und von der Laufzeit behandelt werden, und abfangen kann dazu führen, dass das Programm nicht normal verhält.  
  
##  <a name="is_current_task_group_canceling"></a>  is_current_task_group_canceling  
 Gibt zurück, ob die Aufgabengruppe, die gerade inline auf dem aktuellen Kontext ausgeführt wird, in diesem Moment (oder in Kürze) einen Abbruch durchführt. Beachten Sie, dass `false` zurückgegeben wird, wenn auf dem aktuellen Kontext zurzeit inline keine Aufgabengruppe ausgeführt wird.  
  
```
bool __cdecl is_current_task_group_canceling();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true` Wenn die Aufgabengruppe, die gerade ausgeführt wird, abgebrochen wird, `false` andernfalls.  
  
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
 `T1`  
 Der Meldungsblocktyp der ersten Quelle.  
  
 `T2`  
 Der Meldungsblocktyp der zweiten Quelle.  
  
 `_PScheduler`  
 Das `Scheduler` -Objekt, in dem die Weiterleitungsaufgabe für den `choice` -Meldungsblock geplant ist.  
  
 `_Item1`  
 Die erste Quelle.  
  
 `_Item2`  
 Die zweite Quelle.  
  
 `_Items`  
 Zusätzliche Quellen.  
  
 `_PScheduleGroup`  
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
 `T1`  
 Der Meldungsblocktyp der ersten Quelle.  
  
 `T2`  
 Der Meldungsblocktyp der zweiten Quelle.  
  
 `_PScheduler`  
 Das `Scheduler` -Objekt, in dem die Weiterleitungsaufgabe für den `multitype_join` -Meldungsblock geplant ist.  
  
 `_Item1`  
 Die erste Quelle.  
  
 `_Item2`  
 Die zweite Quelle.  
  
 `_Items`  
 Zusätzliche Quellen.  
  
 `_PScheduleGroup`  
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
 `T1`  
 Der Meldungsblocktyp der ersten Quelle.  
  
 `T2`  
 Der Meldungsblocktyp der zweiten Quelle.  
  
 `_PScheduler`  
 Das `Scheduler` -Objekt, in dem die Weiterleitungsaufgabe für den `multitype_join` -Meldungsblock geplant ist.  
  
 `_Item1`  
 Die erste Quelle.  
  
 `_Item2`  
 Die zweite Quelle.  
  
 `_Items`  
 Zusätzliche Quellen.  
  
 `_PScheduleGroup`  
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
 `_Function`  
 Der Typ des Funktionsobjekts ab, das aufgerufen wird, um die Arbeit, dargestellt durch Ausführen der `task_handle` Objekt.  
  
 `_Func`  
 Die Funktion, die aufgerufen wird, um die Arbeit, dargestellt durch Ausführen der `task_handle` Objekt. Dies ist möglicherweise eine Lambda-Funktion, ein Zeiger auf eine Funktion oder ein anderes Objekt, das eine Version von den Funktionsaufrufoperator mit der Signatur unterstützt `void operator()()`.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `task_handle`-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist nützlich, wenn Sie erstellen ein `task_handle` -Objekt mit einem Lambdaausdruck sein, da es Ihnen ermöglicht, das Objekt zu erstellen, ohne zu wissen, welche das Lambda Funktionselement "true".  
  
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
 `_Random_iterator`  
 Der itertatortyp der Eingabebereich adressiert.  
  
 `_Allocator`  
 Der Typ des eine speicherbelegung der C++-Standardbibliothek kompatibel.  
  
 `_Function`  
 Der Typ des binären Vergleichsoperator.  
  
 `_Begin`  
 Ein zufälliger Eingabeiterator, der die Position des ersten Elements in dem Bereich adressiert, der sortiert werden soll.  
  
 `_End`  
 Ein zufälliger Eingabeiterator, der die Position des ersten Elements direkt hinter dem letzten Element in dem Bereich adressiert, der sortiert werden soll.  
  
 `_Alloc`  
 Eine Instanz einer kompatiblen Speicherbelegungsfunktion C++-Standardbibliothek.  
  
 `_Func`  
 Eine benutzerdefinierte Prädikatfunktion-Objekt, das Kriterium Vergleich von aufeinander folgenden Elementen in der Reihenfolge aufweist erfüllt werden definiert. Ein binäres Prädikat akzeptiert zwei Argumente und gibt bei Erfüllung `true` und bei Nichterfüllung `false` zurück. Diese Vergleichoperatorfunktion muss eine strikte schwache Sortierung auf Elementenpaare der Sequenz anwenden.  
  
 `_Chunk_size`  
 Die Mindestgröße des AutoBildlaufs einen Abschnitt aus, der in zwei für die parallele Ausführung aufgeteilt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Alle Überladungen erfordern `n * sizeof(T)` zusätzlichen Speicherplatz, auf dem `n` ist die Anzahl der zu sortierenden Elemente und `T` ist der Elementtyp. In den meisten Fällen Parallel_buffered_sort zeigt eine Verbesserung der Leistung über [Parallel_sort](concurrency-namespace-functions.md), und Sie sollten dann über Parallel_sort verwenden, wenn Sie den verfügbaren Arbeitsspeicher haben.  
  
 Wenn Sie keinen binären Vergleichsoperator angeben `std::less` dient als Standard, der Typ des Elements, geben Sie den Operator erfordert `operator<()`.  
  
 Wenn Sie kein Allocator-Typ oder die Instanz, die C++-Standardbibliothek Speicherbelegungsfunktion angeben `std::allocator<T>` wird verwendet, um den Puffer zuzuweisen.  
  
 Der Algorithmus wird von der Eingabebereich in zwei Blöcke unterteilt und nacheinander wird jeder Block in zwei untergeordnete Blöcke unterteilt für die parallele Ausführung. Das optionale Argument `_Chunk_size` können verwendet werden, um den Algorithmus angeben, dass Segmente der Größe sollte verarbeitet < `_Chunk_size` Seriell.  
  
##  <a name="parallel_for"></a>  "parallel_for" verwenden  
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
 `_Index_type`  
 Der Typ des Indexes für die Iteration verwendet wird.  
  
 `_Function`  
 Der Typ der Funktion, die bei jeder Iteration ausgeführt werden soll.  
  
 `_Partitioner`  
 Der Typ des mit dem Partitionierer, der verwendet wird, um den angegebenen Bereich zu partitionieren.  
  
 `first`  
 Der erste Index, in der Iteration eingeschlossen werden sollen.  
  
 `last`  
 Der Index eine Stelle hinter dem letzten Index, in einer Iteration einbezogen werden.  
  
 `_Step`  
 Der Wert für die Schritte beim Durchlaufen von `first` auf `last`. Der Schritt muss positiv sein. [Invalid_argument](../../../standard-library/invalid-argument-class.md) wird ausgelöst, wenn der Schritt kleiner als 1 ist.  
  
 `_Func`  
 Die Funktion, die bei jeder Iteration ausgeführt werden. Dies kann ein Lambda-Ausdruck, ein Funktionszeiger sein oder ein anderes Objekt, das eine Version von den Funktionsaufrufoperator mit der Signatur unterstützt `void operator()(_Index_type)`.  
  
 `_Part`  
 Ein Verweis auf das Partitionierer-Objekt. Das Argument kann eine der `const` [Auto_partitioner](auto-partitioner-class.md)`&`, `const` [Static_partitioner](static-partitioner-class.md)`&`, `const` [Simple_ Partitionierer](simple-partitioner-class.md) `&` oder [Affinity_partitioner](affinity-partitioner-class.md) `&` Wenn ein [Affinity_partitioner](affinity-partitioner-class.md) Objekt verwendet wird, der Verweis muss ein nicht konstantes l-Wert verweisen Sie, sodass der Algorithmus Status für zukünftige Schleifen erneut zu verwenden speichern kann.  
  
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
 `_Iterator`  
 Der Typ des Iterators, der zum Durchlaufen des Containers verwendet wird.  
  
 `_Function`  
 Der Typ der Funktion, die auf jedes Element innerhalb des Bereichs angewendet werden soll.  
  
 `_Partitioner`  
 `first`  
 Ein Iterator, der die Position des ersten Elements, in die parallele Iteration eingeschlossen werden sollen.  
  
 `last`  
 Ein Iterator, der die Position hinter dem letzten Element in paralleler Iteration aufgenommen werden.  
  
 `_Func`  
 Ein User-defined Function,-Objekt, das auf jedes Element im Bereich angewendet wird.  
  
 `_Part`  
 Ein Verweis auf das Partitionierer-Objekt. Das Argument kann eine der `const` [Auto_partitioner](auto-partitioner-class.md)`&`, `const` [Static_partitioner](static-partitioner-class.md)`&`, `const` [Simple_ Partitionierer](simple-partitioner-class.md) `&` oder [Affinity_partitioner](affinity-partitioner-class.md) `&` Wenn ein [Affinity_partitioner](affinity-partitioner-class.md) Objekt verwendet wird, der Verweis muss ein nicht konstantes l-Wert verweisen Sie, sodass der Algorithmus Status für zukünftige Schleifen erneut zu verwenden speichern kann.  
  
### <a name="remarks"></a>Hinweise  
 [Auto_partitioner](auto-partitioner-class.md) für die Überladung ohne eine explizite Partitionierer verwendet werden.  
  
 Iteratoren, die nicht zufälligen unterstützen, nur Zugriff auf den [Auto_partitioner](auto-partitioner-class.md) wird unterstützt.  
  
 Weitere Informationen finden Sie unter [parallele Algorithmen](../../../parallel/concrt/parallel-algorithms.md).  
  
##  <a name="parallel_invoke"></a>  parallel_invoke  
 Führt die als Parameter angegebenen Funktionsobjekte parallel aus, und blockiert, bis die Ausführung beendet ist. Jedes Funktionsobjekt kann ein Lambda-Ausdruck, ein Zeiger auf eine Funktion oder ein anderes Objekt sein, das den Funktionsaufrufoperator mit der Signatur `void operator()()` unterstützt.  
  
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
 `_Function1`  
 Der Typ des ersten Funktionsobjekts parallel ausgeführt werden.  
  
 `_Function2`  
 Der Typ des zweiten Funktionsobjekts parallel ausgeführt werden.  
  
 `_Function3`  
 Der Typ des dritten Funktionsobjekts parallel ausgeführt werden.  
  
 `_Function4`  
 Der Typ des vierten Funktionsobjekts parallel ausgeführt werden.  
  
 `_Function5`  
 Der Typ des fünften Funktionsobjekts parallel ausgeführt werden.  
  
 `_Function6`  
 Der Typ des sechsten Funktionsobjekts parallel ausgeführt werden.  
  
 `_Function7`  
 Der Typ des siebten Funktionsobjekts parallel ausgeführt werden.  
  
 `_Function8`  
 Der Typ des achten Funktionsobjekts parallel ausgeführt werden.  
  
 `_Function9`  
 Der Typ des neunten Funktionsobjekts parallel ausgeführt werden.  
  
 `_Function10`  
 Der Typ des zehnten Funktionsobjekts parallel ausgeführt werden.  
  
 `_Func1`  
 Das erste Funktionsobjekt parallel ausgeführt werden.  
  
 `_Func2`  
 Das zweite Funktionsobjekt parallel ausgeführt werden.  
  
 `_Func3`  
 Das dritte Funktionsobjekt parallel ausgeführt werden.  
  
 `_Func4`  
 Das vierte Funktionsobjekt parallel ausgeführt werden.  
  
 `_Func5`  
 Das fünfte Funktionsobjekt parallel ausgeführt werden.  
  
 `_Func6`  
 Das sechste Funktionsobjekt parallel ausgeführt werden.  
  
 `_Func7`  
 Das siebte Funktionsobjekt parallel ausgeführt werden.  
  
 `_Func8`  
 Das achte Funktionsobjekt parallel ausgeführt werden.  
  
 `_Func9`  
 Das neunte Funktionsobjekt parallel ausgeführt werden.  
  
 `_Func10`  
 Das zehnte Funktionsobjekt parallel ausgeführt werden.  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass eine oder mehrere der Funktionsobjekte bereitgestellt werden, wie Parameter Inline im aufrufenden Kontext ausgeführt werden können.  
  
 Wenn eine oder mehrere der Funktionsobjekte, die als Parameter übergeben wird, um diese Funktion eine Ausnahme auslöst, die Common Language Runtime wählen Sie eine solche Ausnahme seiner Wahl und übertragen Sie sie aus dem Aufruf von `parallel_invoke`.  
  
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
 `_Random_iterator`  
 Der itertatortyp der Eingabebereich adressiert.  
  
 `_Allocator`  
 Der Typ des eine speicherbelegung der C++-Standardbibliothek kompatibel.  
  
 `_Function`  
 Der Typ der Projektionsfunktion.  
  
 `_Begin`  
 Ein zufälliger Eingabeiterator, der die Position des ersten Elements in dem Bereich adressiert, der sortiert werden soll.  
  
 `_End`  
 Ein zufälliger Eingabeiterator, der die Position des ersten Elements direkt hinter dem letzten Element in dem Bereich adressiert, der sortiert werden soll.  
  
 `_Alloc`  
 Eine Instanz einer kompatiblen Speicherbelegungsfunktion C++-Standardbibliothek.  
  
 `_Proj_func`  
 Eine Projektion eine benutzerdefinierte Funktionsobjekt, das ein Element in einen ganzzahligen Wert konvertiert.  
  
 `_Chunk_size`  
 Die Mindestgröße des AutoBildlaufs einen Abschnitt aus, der in zwei für die parallele Ausführung aufgeteilt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Alle Überladungen erfordern `n * sizeof(T)` zusätzlichen Speicherplatz, auf dem `n` ist die Anzahl der zu sortierenden Elemente und `T` ist der Elementtyp. Eine unäre Projektion Funktionselement mit der Signatur `I _Proj_func(T)` ist erforderlich, um ein Schlüssel, wenn ein Element zurückgegeben, in dem `T` ist der Elementtyp und `I` ist ein Integer-ähnliche-Typ ohne Vorzeichen.  
  
 Wenn Sie eine Projektionsfunktion nicht angeben, wird eine Projektion Standardfunktion die einfach das Element zurückgibt, für ganzzahlige Typen verwendet. Die Funktion kann nicht kompiliert, wenn das Element nicht auf einen ganzzahligen Typ in Ermangelung einer Projektion-Funktion ist.  
  
 Wenn Sie kein Allocator-Typ oder die Instanz, die C++-Standardbibliothek Speicherbelegungsfunktion angeben `std::allocator<T>` wird verwendet, um den Puffer zuzuweisen.  
  
 Der Algorithmus wird von der Eingabebereich in zwei Blöcke unterteilt und nacheinander wird jeder Block in zwei untergeordnete Blöcke unterteilt für die parallele Ausführung. Das optionale Argument `_Chunk_size` können verwendet werden, um den Algorithmus angeben, dass Segmente der Größe sollte verarbeitet < `_Chunk_size` Seriell.  
  
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
 `_Forward_iterator`  
 Der itertatortyp der Eingabebereich adressiert.  
  
 `_Sym_reduce_fun`  
 Der Typ der symmetrischen Reduction-Funktion. Diese Angabe muss ein Funktionstyp mit Signatur `_Reduce_type _Sym_fun(_Reduce_type, _Reduce_type)`, wobei _Reduce_type identisch als der Identity-Typ und die Verringerung der Ergebnistyp ist. Für die dritte Überladung werden dies konsistent mit der Ausgabetyp des `_Range_reduce_fun`.  
  
 `_Reduce_type`  
 Der Typ, der die Eingabe, zu reduzieren, wird vom Typ Eingabeelement abweichen kann. Den Rückgabewert und einen Identitätswert wird dieser Typ hat.  
  
 `_Range_reduce_fun`  
 Der Typ der Bereich Reduction-Funktion. Diese Angabe muss ein Funktionstyp mit Signatur `_Reduce_type _Range_fun(_Forward_iterator, _Forward_iterator, _Reduce_type)`, _Reduce_type ist identisch mit der Identity-Typ und der Ergebnistyp der Reduzierung.  
  
 `_Begin`  
 Ein eingabeiterator, der das erste Element im Bereich reduziert werden sollen.  
  
 `_End`  
 Ein eingabeiterator, der das Element, das eine Position hinter dem letzten Element im Bereich reduziert werden sollen.  
  
 `_Identity`  
 Der Identitätswert `_Identity` hat denselben Typ wie der Ergebnistyp der Reduzierung sowie die `value_type` des Iterators für die ersten und zweiten Überladung. Für die dritte Überladung der Identitätswert benötigen denselben Typ wie der Ergebnistyp der Reduzierung, aber nicht identisch sein kann die `value_type` des Iterators. Muss einen geeigneten Wert so, dass der Bereich Reduction-Operator `_Range_fun`, wenn auf einen Bereich, der ein einzelnes Element des Typs angewendet `value_type` und der Identitätswert verhält sich wie eine Typumwandlung des Werts vom Typ `value_type` in den Identitätstyp.  
  
 `_Sym_fun`  
 Die symmetrischen-Funktion, die im zweiten der Verkürzung der Dauer verwendet werden. Weitere Informationen finden Sie in "Hinweise".  
  
 `_Range_fun`  
 Die Funktion, die in der ersten Phase der Reduzierung verwendet werden. Weitere Informationen finden Sie in "Hinweise".  
  
### <a name="return-value"></a>Rückgabewert  
 Das Ergebnis der Reduzierung.  
  
### <a name="remarks"></a>Hinweise  
 Um eine parallele Reduzierung durchzuführen, wird die Funktion den Bereich in Blöcke unterteilt, die basierend auf der Anzahl von Arbeitsthreads, die auf den zugrunde liegenden Planer verfügbar. Die Verkürzung der Dauer erfolgt in zwei Phasen, in der ersten Phase führt eine Reduzierung innerhalb jedes Blocks und die zweite Phase führt eine Reduzierung zwischen die Teilergebnisse aus jeder Block.  
  
 Die erste Überladung erfordert, dass des Iterators `value_type`, `T`müssen identisch sein, als der Identity-Wert-Typ als auch in der Reduction-Ergebnistyp. Der Elementtyp T muss den Operator bieten `T T::operator + (T)` Elemente in jeder Block reduzieren. Denselben Operator wird in der zweiten Phase verwendet.  
  
 Die zweite Überladung erfordert außerdem, dass des Iterators `value_type` identisch sein, als der Identity-Wert-Typ als auch in der Reduction-Ergebnistyp. Die angegebenen binären Operator `_Sym_fun` wird in beiden Reduction-Phase, mit der Identitätswert als Anfangswert für die erste Phase verwendet.  
  
 Für die dritte Überladung der Identity-Wert-Typ muss identisch sein wie der Reduction-Ergebnistyp, jedoch mit des Iterators `value_type` kann nicht mit den beiden abweichen. Der Bereich Reduction-Funktion `_Range_fun` dient in der ersten Phase mit der Identitätswert als der ursprüngliche Wert und der binären Funktion `_Sym_reduce_fun` wird angewendet, um die Ergebnisse in der zweiten Phase sub.  
  
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
 `_Random_iterator`  
 Der itertatortyp der Eingabebereich adressiert.  
  
 `_Function`  
 Der Typ, der das Funktionselement binärer Vergleich.  
  
 `_Begin`  
 Ein zufälliger Eingabeiterator, der die Position des ersten Elements in dem Bereich adressiert, der sortiert werden soll.  
  
 `_End`  
 Ein zufälliger Eingabeiterator, der die Position des ersten Elements direkt hinter dem letzten Element in dem Bereich adressiert, der sortiert werden soll.  
  
 `_Func`  
 Eine benutzerdefinierte Prädikatfunktion-Objekt, das Kriterium Vergleich von aufeinander folgenden Elementen in der Reihenfolge aufweist erfüllt werden definiert. Ein binäres Prädikat akzeptiert zwei Argumente und gibt bei Erfüllung `true` und bei Nichterfüllung `false` zurück. Diese Vergleichoperatorfunktion muss eine strikte schwache Sortierung auf Elementenpaare der Sequenz anwenden.  
  
 `_Chunk_size`  
 Die Mindestgröße des AutoBildlaufs einen Abschnitt aus, der in zwei für die parallele Ausführung aufgeteilt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Die erste Überladung wird verwendet, die den binären Vergleichsoperator `std::less`.  
  
 Die zweite überladen verwendet den angegebenen binären Vergleichsoperator mit der Signatur `bool _Func(T, T)` , in dem `T` ist der Typ der Elemente im Eingabebereich adressiert.  
  
 Der Algorithmus wird von der Eingabebereich in zwei Blöcke unterteilt und nacheinander wird jeder Block in zwei untergeordnete Blöcke unterteilt für die parallele Ausführung. Das optionale Argument `_Chunk_size` können verwendet werden, um den Algorithmus angeben, dass Segmente der Größe sollte verarbeitet < `_Chunk_size` Seriell.  
  
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
 `_Input_iterator1`  
 Der Typ des ersten oder nur input-Iterator.  
  
 `_Output_iterator`  
 Der Typ des Ausgabeiterators.  
  
 `_Unary_operator`  
 Der Typ der unären kennen, die für jedes Element im Eingabebereich adressiert ausgeführt werden.  
  
 `_Input_iterator2`  
 Der Typ des zweiten input-Iterator.  
  
 `_Binary_operator`  
 Der Typ, der das binäre Funktionselement paarweise für Elemente aus der beiden Quellbereiche ausgeführt werden soll.  
  
 `_Partitioner`  
 `first1`  
 Ein eingabeiterator, der die Position des ersten Elements in der ersten oder nur Quellbereich verarbeitet werden sollen.  
  
 `last1`  
 Ein eingabeiterator, der die Position hinter dem letzten Element in der ersten oder verarbeitet werden sollen nur Quellbereich adressiert.  
  
 `_Result`  
 Ein Ausgabeiterator, der die Position des ersten Elements im Zielbereich adressiert.  
  
 `_Unary_op`  
 Eine benutzerdefinierte unäres Funktionsobjekt, das auf jedes Element im Quellbereich angewendet wird.  
  
 `_Part`  
 Ein Verweis auf das Partitionierer-Objekt. Das Argument kann eine der `const` [Auto_partitioner](auto-partitioner-class.md)`&`, `const` [Static_partitioner](static-partitioner-class.md)`&`, `const` [Simple_ Partitionierer](simple-partitioner-class.md) `&` oder [Affinity_partitioner](affinity-partitioner-class.md) `&` Wenn ein [Affinity_partitioner](affinity-partitioner-class.md) Objekt verwendet wird, der Verweis muss ein nicht konstantes l-Wert verweisen Sie, sodass der Algorithmus Status für zukünftige Schleifen erneut zu verwenden speichern kann.  
  
 `first2`  
 Ein Eingabeiterator, der die Position des ersten Elements im zweiten Quellbereich adressiert.  
  
 `_Binary_op`  
 Ein User-defined Function, binäre-Objekt, das in einer vorwärtsreihenfolge, um die beiden Quellbereiche paarweise, angewendet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Ausgabeiterator, der die Position direkt hinter dem letzten Element im Zielbereich adressiert, der die vom Funktionsobjekt umgewandelten Ausgabeelemente erhält.  
  
### <a name="remarks"></a>Hinweise  
 [Auto_partitioner](auto-partitioner-class.md) für die Überladungen ohne explizite Partitionierer Argument verwendet werden.  
  
 Iteratoren, die nicht zufälligen unterstützen, nur Zugriff auf den [Auto_partitioner](auto-partitioner-class.md) wird unterstützt.  
  
 Die Überladungen, die die Argumente `_Unary_op` Transformieren der Eingabebereich in der Ausgabetabelle durch Anwenden der unäre Funktionselement auf jedes Element im Eingabebereich adressiert. `_Unary_op` muss den Funktionsaufrufoperator mit der Signatur unterstützen `operator()(T)` , in dem `T` ist der Werttyp des durchlaufenen Bereichs.  
  
 Die Überladungen, die die Argumente `_Binary_op` zwei Eingabebereiche in den Ausgabebereich durch Anwenden von binären Funktionselement auf ein Element aus der ersten Eingabebereich und ein Element aus der zweiten Eingabebereich zu transformieren. `_Binary_op` muss den Funktionsaufrufoperator mit der Signatur unterstützen `operator()(T, U)` , in denen `T`, `U` sind Werttypen der eingabeiteratoren zwei.  
  
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
 `T`  
 Der Nutzlasttyp.  
  
 `_Src`  
 Ein Zeiger oder Verweis auf die Quelle, von der Daten erwartet werden.  
  
 `_Timeout`  
 Die maximale Zeit für die die Methode sollte für die Daten in Millisekunden.  
  
 `_Filter_proc`  
 Eine Filterfunktion, die bestimmt, ob Nachrichten akzeptiert werden sollen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert aus der Quelle, der den Typ der Nutzlast.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Parameter `_Timeout` verfügt über einen anderen Wert als die Konstante `COOPERATIVE_TIMEOUT_INFINITE`, die Ausnahme [Operation_timed_out](operation-timed-out-class.md) wird ausgelöst, wenn die angegebene Zeitspanne abläuft, bevor eine Nachricht empfangen wird. Wenn Sie möchten, dass einen Timeout der Länge 0 (null), sollten Sie verwenden die [Try_receive](concurrency-namespace-functions.md) -Funktion im Gegensatz zu Aufrufen `receive` mit einem Timeout von `0` (null), es ist jedoch effizienter, und löst keine Ausnahmen auf Timeouts.  
  
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
 `_Function`  
 Der Typ des Funktionsobjekts ab, das aufgerufen wird.  
  
 `_Func`  
 Das Funktionsobjekt, das ausgeführt wird. Dieses Objekt muss den Funktionsaufrufoperator mit einer Signatur der void(void) unterstützen.  
  
 `_Ct`  
 Das Abbruchtoken, das impliziten Abbruch des Funktionsobjekts gesteuert wird. Verwendung `cancellation_token::none()` gegebenenfalls ohne jede Möglichkeit einer impliziten Abbruch aus eine übergeordnete Aufgabengruppe abgebrochen wird. Führen Sie die Funktion aus.  
  
### <a name="remarks"></a>Hinweise  
 Alle Unterbrechungspunkte in das Funktionsobjekt wird ausgelöst, wenn die `cancellation_token` abgebrochen wird. Das explizite Token `_Ct` zu isolieren dies `_Func` aus übergeordneten Abbruch, wenn das übergeordnete Element ein anderes Token oder keine Token verfügt.  
  
##  <a name="send"></a>  Senden  
 Ein synchroner Sendevorgang, der wartet, bis das Ziel die Meldung akzeptiert oder ablehnt.  
  
```
template <class T>
bool send(_Inout_ ITarget<T>* _Trg, const T& _Data);

template <class T>
bool send(ITarget<T>& _Trg, const T& _Data);
```  
  
### <a name="parameters"></a>Parameter  
 `T`  
 Der Nutzlasttyp.  
  
 `_Trg`  
 Ein Zeiger oder Verweis auf das Ziel, an den Daten gesendet werden.  
  
 `_Data`  
 Ein Verweis auf die Daten gesendet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 `true` Wenn die Nachricht akzeptiert wurde, `false` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Message Passing Functions](../../../parallel/concrt/message-passing-functions.md).  
  
##  <a name="set_ambient_scheduler"></a>  set_ambient_scheduler  
  
```
inline void set_ambient_scheduler(std::shared_ptr<::Concurrency::scheduler_interface> _Scheduler);
```  
  
### <a name="parameters"></a>Parameter  
 `_Scheduler`  
  
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
 `_ProcessAffinityMask`  
 Die Affinitätsmaske, die Arbeitsthreads der Concurrency Runtime auf beschränkt werden. Verwenden Sie diese Methode auf einem System mit mehr als 64 Hardwarethreads nur, wenn Sie die Concurrency Runtime auf eine Teilmenge der aktuellen Gruppe "Prozessor" beschränken möchten. Im Allgemeinen sollten Sie die Version der Methode verwenden, die ein Array von Affinitäten zwischen Gruppe und, als Parameter verwendet akzeptiert, um die Affinität auf Computern mit mehr als 64 Hardwarethreads zu beschränken.  
  
 `count`  
 Die Anzahl der `GROUP_AFFINITY` Einträge in das Array durch den Parameter angegebene `_PGroupAffinity`.  
  
 `_PGroupAffinity`  
 Ein Array von `GROUP_AFFINITY` Einträge.  
  
### <a name="remarks"></a>Hinweise  
 Die Methode löst eine [Invalid_operation](invalid-operation-class.md) -Ausnahme aus, wenn ein Ressourcen-Manager zu dem Zeitpunkt vorhanden er aufgerufen wird ist, und ein [Invalid_argument](../../../standard-library/invalid-argument-class.md) -Ausnahme aus, wenn die Ergebnisse in eine leere Menge von Affinität angegebene Ressourcen.  
  
 Die Version der Methode, die ein Array von Gruppe Affinitäten als Parameter verwendet, darf nur verwendet, die unter Betriebssystemen mit Version Windows 7 oder höher sein. Andernfalls ein [Invalid_operation](invalid-operation-class.md) Ausnahme wird ausgelöst.  
  
 Die Prozessaffinität programmgesteuert ändern, nach dem Aufruf dieser Methode verursacht keine der Ressourcen-Manager, um die Affinität neu zu bewerten, der es beschränkt ist. Aus diesem Grund sollten alle Affinität verarbeitet Änderungen werden vor dem Aufrufen dieser Methode.  
  
##  <a name="swap"></a>  swap  
 Tauscht die Elemente zweier `concurrent_vector`-Objekte.  
  
```
template<typename T, class _Ax>
inline void swap(
    concurrent_vector<T, _Ax>& _A,
    concurrent_vector<T, _Ax>& _B);
```  
  
### <a name="parameters"></a>Parameter  
 `T`  
 Der Datentyp der Elemente in der gleichzeitigen Vektoren gespeichert.  
  
 `_Ax`  
 Die Allocator-Typ der gleichzeitigen Vektoren.  
  
 `_A`  
 Den gleichzeitigen Vektor, dessen Elemente sind mit denen von den gleichzeitigen Vektor ausgetauscht werden sollen `_B`.  
  
 `_B`  
 Den gleichzeitigen Vektor, der die auszutauschenden Elemente bereitgestellt, oder der Vektor, dessen Elemente mit denen von den gleichzeitigen Vektor ausgetauscht werden sollen `_A`.  
  
### <a name="remarks"></a>Hinweise  
 Die Vorlagenfunktion ist ein Algorithmus für die Container-Klasse spezialisierten `concurrent_vector` , führen Sie die Memberfunktion `_A`. [concurrent_vector::swap](concurrent-vector-class.md#swap)( `_B`). Hierbei handelt es sich um Instanzen der partiellen Sortierung von Funktionsvorlagen durch den Compiler. Wenn Vorlagenfunktionen so überladen werden, dass die Übereinstimmung der Vorlage mit dem Funktionsaufruf nicht eindeutig ist, wählt der Compiler die spezialisierteste Version der Vorlagenfunktion. Die allgemeine Version der Vorlagenfunktion `template <class T> void swap(T&, T&)`, klicken Sie im verwendeten Algorithmus Klasse durch Zuweisung funktioniert, und ist ein langsamer Vorgang. Die spezialisierte Version in jedem Container ist viel schneller, da sie mit der internen Darstellung der Containerklasse verwendet werden kann.  
  
 Diese Methode ist nicht nebenläufigkeitssicher. Sie müssen sicherstellen, dass keine anderen Threads Operationen für einen der gleichzeitigen Vektoren ausführen, wenn Sie diese Methode aufrufen.  
  
##  <a name="task_from_exception"></a>  task_from_exception  
  
```
template<typename _TaskType, typename _ExType>
task<_TaskType> task_from_exception(
    _ExType _Exception,
    const task_options& _TaskOptions = task_options());
```  
  
### <a name="parameters"></a>Parameter  
 `_TaskType`  
 `_ExType`  
 `_Exception`  
 `_TaskOptions`  
  
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
 `T`  
 `_Param`  
 `_TaskOptions`  
  
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
 `T`  
 Der Typ des Objekts. Dies ist normalerweise ein Nachrichtenblock oder einen Agent.  
  
 `_PObject`  
 Ein Zeiger auf dem Nachrichtenblock oder dem Agent, der in der Ablaufverfolgung heißt.  
  
 `_Name`  
 Der Name für das angegebene Objekt.  
  
##  <a name="try_receive"></a>  try_receive  
 Eine allgemeine try-receive-Implementierung, mit der ein Kontext Daten von genau einer Quelle suchen und die akzeptierten Werte filtern kann. Wenn die Daten nicht bereit sind, gibt die Methode "false" zurück.  
  
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
 `T`  
 Der Typ der Ereignisnutzlast  
  
 `_Src`  
 Ein Zeiger oder Verweis auf die Quelle, von der Daten erwartet werden.  
  
 `_value`  
 Ein Verweis auf einen Speicherort, in dem das Ergebnis platziert wird.  
  
 `_Filter_proc`  
 Eine Filterfunktion, die bestimmt, ob Nachrichten akzeptiert werden sollen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `bool` -Wert, der angibt, und zwar unabhängig davon, ob eine Nutzlast in abgelegt wurde `_value`.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Message Passing Functions](../../../parallel/concrt/message-passing-functions.md).  
  
##  <a name="wait"></a>  Warte  
 Hält den aktuellen Kontext für eine bestimmte Zeit an.  
  
```
void __cdecl wait(unsigned int _Milliseconds);
```  
  
### <a name="parameters"></a>Parameter  
 `_Milliseconds`  
 Die Anzahl der Millisekunden, denen für der aktuelle Kontext angehalten werden soll. Wenn die `_Milliseconds` Parameter festgelegt ist, auf den Wert `0`, der aktuelle Kontext sollte vor dem Fortsetzen der Ausführung anderer ausführbarer Kontexte ergeben.  
  
### <a name="remarks"></a>Hinweise  
 Wenn diese Methode für einen Concurrency Runtime-Planer-Kontext aufgerufen wird, findet das Zeitplanungsmodul einen anderen Kontext auf die zugrunde liegende Ressource ausführen. Da der Planer grundsätzlich kooperativ ist, kann nicht diesem Kontext genau nach der angegebenen Anzahl von Millisekunden fortgesetzt. Ist der Planer ausgelastet ausgeführter andere Aufgaben, die nicht auf dem Planer kooperativ zurückgehalten werden, ist möglicherweise die Wartezeit unbegrenzt.  
  
##  <a name="when_all"></a>  "when_all"  
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
 `_Iterator`  
 Der Typ des Eingabeiterators.  
  
 `_Begin`  
 Die Position des ersten Elements in dem Bereich von Elementen, die mit der resultierenden Aufgabe kombiniert werden sollen.  
  
 `_End`  
 Die Position des ersten Elements hinter dem Bereich von Elementen, die mit der resultierenden Aufgabe kombiniert werden sollen.  
  
 `_TaskOptions`  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Aufgabe, die erfolgreich abgeschlossen ist, wenn alle Eingabeaufgaben erfolgreich abgeschlossen wurden. Wenn die Eingabeaufgaben vom Typ `T` sind, wird die Ausgabe dieser Funktion `task<std::vector<T>>` sein. Wenn die Eingabeaufgaben vom Typ `void` sind, ist die Ausgabeaufgabe auch `task<void>`.  
  
### <a name="remarks"></a>Hinweise  
 `when_all` ist eine nicht blockierende Funktion, die `task` als Ergebnis erzeugt. Im Gegensatz zu [Task:: wait](task-class.md#wait), es ist sicher, diese Funktion in einer uwp-app auf dem ASTA-(Application STA-) Thread aufzurufen.  
  
 Wenn eine der Aufgaben abgebrochen wird oder eine Ausnahme auslöst, die zurückgegebene Aufgabe früh im Zustand "abgebrochen" abgeschlossen wird und die Ausnahme, sofern Sie auftritt, wird ausgelöst wird, wenn Sie aufrufen [Task:: Get](task-class.md#get) oder `task::wait` für diese Aufgabe.  
  
 Weitere Informationen finden Sie unter [Aufgabenparallelität](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
##  <a name="when_any"></a>  "when_any"  
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
 `_Iterator`  
 Der Typ des Eingabeiterators.  
  
 `_Begin`  
 Die Position des ersten Elements in dem Bereich von Elementen, die mit der resultierenden Aufgabe kombiniert werden sollen.  
  
 `_End`  
 Die Position des ersten Elements hinter dem Bereich von Elementen, die mit der resultierenden Aufgabe kombiniert werden sollen.  
  
 `_TaskOptions`  
 `_CancellationToken`  
 Das Abbruchtoken, das den Abbruch der zurückgegebenen Aufgabe steuert. Wenn Sie kein Abbruchtoken bereitstellen, erhält die resultierende Aufgabe das Abbruchtoken der Aufgabe, die ihren Abschluss verursacht.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Aufgabe, die erfolgreich abgeschlossen ist, wenn eine der Eingabeaufgaben erfolgreich abgeschlossen wurde. Wenn die Eingabeaufgaben vom Typ `T` sind, ist die Ausgabe dieser Funktion `task<std::pair<T, size_t>>>`, wobei das erste Element des Paares das Ergebnis der letzten Aufgabe ist, und das zweite Element der Index der beendeten Aufgabe. Wenn die Eingabeaufgaben vom Typ `void` sind, ist die Ausgabe `task<size_t>`, wobei das Ergebnis der Index der abgeschlossenen Aufgabe ist.  
  
### <a name="remarks"></a>Hinweise  
 `when_any` ist eine nicht blockierende Funktion, die `task` als Ergebnis erzeugt. Im Gegensatz zu [Task:: wait](task-class.md#wait), es ist sicher, diese Funktion in einer uwp-app auf dem ASTA-(Application STA-) Thread aufzurufen.  
  
 Weitere Informationen finden Sie unter [Aufgabenparallelität](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)
