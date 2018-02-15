---
title: Aufgabenklasse (Concurrency Runtime) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs:
- C++
helpviewer_keywords:
- task class
ms.assetid: cdc3a8c0-5cbe-45a0-b5d5-e9f81d94df1a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 350207512ee31d6c55b127984387e3e9af7912b2
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="task-class-concurrency-runtime"></a>Aufgabenklasse (Concurrency Runtime)
Die Parallel Patterns Library (PPL) `task`-Klasse. Ein `task`-Objekt stellt Arbeit dar, die asynchron und übereinstimmend mit anderen Tasks und paralleler Arbeit , die von parallelen Algorithmen in der Concurrency Runtime erzeugt wird, ausgeführt werden kann. Es enthält bei erfolgreichem Abschluss ein Ergebnis vom Typ `_ResultType`. Tasks des Typs `task<void>` führen zu keinem Ergebnis. Eine Aufgabe kann erwartet und unabhängig von anderen Aufgaben abgebrochen werden. Er kann auch mit anderen Tasks mithilfe von Fortsetzungen erstellt werden ( `then`), und Join ( `when_all`) und Auswahl ( `when_any`) Muster.  
  
## <a name="syntax"></a>Syntax  
  
```
template <typename T>
class task;

template <>
class task<void>;

template<typename _ReturnType>
class task;
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 `T`  
 `_ReturnType`  
 Der Ergebnistyp dieser Aufgabe.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`result_type`|Der Typ des von einem Objekt dieser Klasse erstellten Ergebnisses.|  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[task](#ctor)|Überladen. Erstellt ein `task`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[get](#get)|Überladen. Gibt das von diesem Task erstellte Ergebnis zurück. Wenn sich der Task nicht in einem abschließenden Zustand befindet, wird mit dem `get`-Aufruf gewartet, bis der Task fertig gestellt wurde. Diese Methode gibt bei dem Aufruf eines Tasks mit einem `result_type` von `void` keinen Wert zurück.|  
|[is_apartment_aware](#is_apartment_aware)|Bestimmt, ob der Task eine `IAsyncInfo`-Schnittstelle der Windows Runtime entpackt oder von einem solchen Task abgeleitet wurde.|  
|[is_done](#is_done)|Bestimmt, ob die Aufgabe abgeschlossen wurde.|  
|[scheduler](#scheduler)|Gibt den Planer für diese Aufgabe zurück.|  
|[then](#then)|Überladen. Fügt dieser Aufgabe eine Fortsetzungsaufgabe hinzu.|  
|[wait](#wait)|Erwartet, dass diese Aufgabe einen Terminalzustand erreicht. Es ist möglich, dass das `wait`-Element den Task inline ausführt, wenn alle Taskabhängigkeiten erfüllt sind und er nicht bereits zur Ausführung durch einen Hintergrundworker aufgehoben wurde.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[operator!=](#operator_neq)|Überladen. Bestimmt, ob zwei `task`-Objekte unterschiedliche interne Prozesse darstellen.|  
|[operator=](#operator_eq)|Überladen. Ersetzt den Inhalt eines `task`-Objekts durch einen anderen.|  
|[operator==](#operator_eq_eq)|Überladen. Bestimmt, ob zwei `task`-Objekte den gleichen internen Task darstellen.|  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Aufgabenparallelität](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `task`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** ppltasks.h  
  
 **Namespace:** Parallelität  
  
##  <a name="get"></a> Erhalten 

 Gibt das von dieser Aufgabe erstellte Ergebnis zurück. Wenn sich der Task nicht in einem abschließenden Zustand befindet, wird mit dem `get`-Aufruf gewartet, bis der Task fertig gestellt wurde. Diese Methode gibt bei dem Aufruf eines Tasks mit einem `result_type` von `void` keinen Wert zurück.  
  
```
_ReturnType get() const;

void get() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Ergebnis der Aufgabe.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Aufgabe abgebrochen wird, einen Aufruf von `get` löst eine [Task_canceled](task-canceled-class.md) Ausnahme. Wenn die Aufgabe eine Ausnahme während der Ausführung feststellt oder an sie eine Ausnahme aus einer vorherigen Aufgabe weitergegeben wurde, löst ein Aufruf von `get` diese Ausnahme aus.  
  
> [!IMPORTANT]
>  Rufen Sie in einer app (Universelle Windows Plattform) nicht [Concurrency::task::wait](#wait) oder `get` ( `wait` Aufrufe `get`) im Code, der auf dem STA ausgeführt wird. Andernfalls löst die Laufzeit [invalid_operation](invalid-operation-class.md) da diese Methoden den aktuellen Thread blockieren und dazu führen, die app dass können reagiert. Sie können jedoch die `get`-Methode aufrufen, um das Ergebnis der vorangegangenen Aufgabe in einer aufgabenbasierten Fortsetzung zu erhalten, da das Ergebnis sofort verfügbar ist.  
  
##  <a name="is_apartment_aware"></a> is_apartment_aware 

 Bestimmt, ob der Task eine `IAsyncInfo`-Schnittstelle der Windows Runtime entpackt oder von einem solchen Task abgeleitet wurde.  
  
```
bool is_apartment_aware() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn die Aufgabe eine `IAsyncInfo`-Schnittstelle entpackt oder von einer solchen Aufgabe abgeleitet wird, andernfalls `false`.  
  
##  <a name="is_done"></a>  Task:: is_done-Methode (Concurrency Runtime)   
 Bestimmt, ob die Aufgabe abgeschlossen wurde.  
  
```
bool is_done() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn die Aufgabe abgeschlossen wurde, andernfalls FALSE.  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion gibt TRUE zurück, wenn die Aufgabe abgeschlossen oder abgebrochen wurde (mit oder ohne Benutzerausnahme).  
  
##  <a name="operator_neq"></a> Operator! = 

 Bestimmt, ob zwei `task`-Objekte unterschiedliche interne Prozesse darstellen.  
  
```
bool operator!= (const task<_ReturnType>& _Rhs) const;

bool operator!= (const task<void>& _Rhs) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_Rhs`  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn die Objekte sich auf unterschiedliche zugrunde liegenden Aufgaben beziehen, und andernfalls `false`.  
  
##  <a name="operator_eq"></a> Operator = 

 Ersetzt den Inhalt eines `task`-Objekts durch einen anderen.  
  
```
task& operator= (const task& _Other);

task& operator= (task&& _Other);
```  
  
### <a name="parameters"></a>Parameter  
 `_Other`  
 Das `task`-Quellobjekt.  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
 Da sich `task` wie ein intelligenter Zeiger verhält, stellt dieses `task`-Objekt nach einer Kopierzuweisung die gleiche Aufgabe dar wie `_Other`.  
  
##  <a name="operator_eq_eq"></a> Operator == 

 Bestimmt, ob zwei `task`-Objekte den gleichen internen Task darstellen.  
  
```
bool operator== (const task<_ReturnType>& _Rhs) const;

bool operator== (const task<void>& _Rhs) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_Rhs`  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn die Objekte auf die gleiche zugrunde liegende Aufgabe verweisen, andernfalls `false`.  
  
##  <a name="scheduler"></a>  Task:: Scheduler-Methode (Concurrency Runtime)  
 Gibt den Planer für diese Aufgabe zurück.  
  
```
scheduler_ptr scheduler() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den Planer.  
  
##  <a name="ctor"></a> Aufgabe 

 Erstellt ein `task`-Objekt.  
  
```
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
 `T`  
 Der Typ des Parameters, von dem die Aufgabe erstellt werden soll.  
  
 `_Param`  
 Der Parameter, von dem die Aufgabe erstellt werden soll. Dies ist möglicherweise ein Lambda-Ausdruck, ein Funktionsobjekt, ein `task_completion_event<result_type>` Objekt oder eine iasyncinfo Sie Aufgaben in der Windows-Runtime-app. Das Objekt Lambda- oder Funktionsobjekt muss einen Typ entspricht `std::function<X(void)>`, wobei X eine Variable des Typs sein kann `result_type`, `task<result_type>`, oder eine Windows::Foundation::IAsyncInfo in Windows-Runtime-apps.  
  
 `_TaskOptions`  
 Die Aufgabenoptionen enthalten Abbruchtoken, Planer usw.  
  
 `_Other`  
 Das `task`-Quellobjekt.  
  
### <a name="remarks"></a>Hinweise  
 Der Standardkonstruktor für `task` ist nur vorhanden, damit Aufgaben in Containern verwendet werden können. Eine erstellte Standardaufgabe kann nicht verwendet werden, bis Sie ihr eine gültige Aufgabe zuweisen. Methoden, z. B. `get`, `wait` oder `then` löst ein [Invalid_argument](../../../standard-library/invalid-argument-class.md) -Ausnahme aus, wenn für eine erstellte Standardaufgabe aufgerufen.  
  
 Eine Aufgabe, die aus einem `task_completion_event` erstellt wird, wird abgeschlossen (und danach werden ihre Fortsetzungen geplant), wenn das Aufgabenabschlussereignis festgelegt ist.  
  
 Die Version des Konstruktors, die ein Abbruchtoken verwendet, erstellt eine Aufgabe, die mithilfe der `cancellation_token_source`, aus der das Token abgerufen wurde, abgebrochen werden kann. Die Aufgaben, die ohne ein Abbruchtoken erstellt werden, können nicht abgebrochen werden.  
  
 Die Aufgaben, die aus einer `Windows::Foundation::IAsyncInfo`-Schnittstelle oder einem Lambda-Ausdruck erstellt werden, der eine `IAsyncInfo`-Schnittstelle zurückgibt, erreichen den abgeschlossenen Zustand, wenn der enthaltene asynchrone Windows-Runtime-Vorgang oder die enthaltene Aktion abgeschlossen wurde. In ähnlicher Weise erreichen Aufgaben, die aus einem Lambda-Ausdruck erstellt werden, der einen `task<result_type>` zurückgibt, den abgeschlossenen Zustand, wenn die innere Aufgabe den abgeschlossenen Zustand erreicht, und nicht wenn die Rückgabe vom Lambda-Ausdruck erfolgt.  
  
 `task` verhält sich wie ein intelligenter Zeiger und kann mehrmals als Wert übergeben werden. Ein Zugriff ist durch mehrere Threads ohne Sperren möglich.  
  
 Die Konstruktorüberladung, die eine Schnittstelle Windows::Foundation::IAsyncInfo oder einen Lambda-Ausdruck, der eine solche Schnittstelle zurückgibt, sind nur für Windows-Runtime-apps verfügbar.  
  
 Weitere Informationen finden Sie unter [Aufgabenparallelität](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
##  <a name="then"></a> Klicken Sie dann 

 Fügt dieser Aufgabe eine Fortsetzungsaufgabe hinzu.  
  
```
template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func) const -> typename details::_ContinuationTypeTraits<_Function,
    _ReturnType>::_TaskOfType;

template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func,
    const task_options& _TaskOptions) const -> typename details::_ContinuationTypeTraits<_Function,
    _ReturnType>::_TaskOfType;

template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func,
    cancellation_token _CancellationToken,
    task_continuation_context _ContinuationContext) const -> typename details::_ContinuationTypeTraits<_Function,
    _ReturnType>::_TaskOfType;

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
 `_Function`  
 Der Typ des Funktionsobjekts, das von dieser Aufgabe aufgerufen wird.  
  
 `_Func`  
 Die Fortsetzungsfunktion, die ausgeführt werden soll, wenn diese Aufgabe abgeschlossen ist. Diese Fortsetzungsfunktion muss als Eingabe die Variable `result_type` oder `task<result_type>` verwenden, wobei `result_type` der Ergebnistyp ist, den diese Aufgabe erzeugt.  
  
 `_TaskOptions`  
 Die Aufgabenoptionen umfassen das Abbruchtoken, den Planer und den Fortsetzungskontext. Standardmäßig werden die vorherigen drei Optionen von der Vorgängeraufgabe geerbt.  
  
 `_CancellationToken`  
 Das Abbruchtoken, das der Fortsetzungsaufgabe zugeordnet werden soll. Eine Fortsetzungsaufgabe, die ohne ein Abbruchtoken erstellt wird, erbt das Token von der Vorgängeraufgabe.  
  
 `_ContinuationContext`  
 Eine Variable, die angibt, wo die Fortsetzung ausgeführt werden soll. Diese Variable ist nur nützlich, wenn in einer uwp-app verwendet. Weitere Informationen finden Sie unter [Task_continuation_context](task-continuation-context-class.md)  
  
### <a name="return-value"></a>Rückgabewert  
 Die neu erstellte Fortsetzungsaufgabe. Der Ergebnistyp der zurückgegebenen Aufgabe wird von dem bestimmt, was `_Func` zurückgibt.  
  
### <a name="remarks"></a>Hinweise  
 Überladungen der `then` , dass nehmen einen Lambda-Ausdruck oder ein Funktionselement ist, eine Windows::Foundation::IAsyncInfo-Schnittstelle zurückgibt, sind nur für Windows-Runtime-apps verfügbar.  
  
 Weitere Informationen zum Task Fortsetzungen zu verwenden, um asynchrone Aufgaben zu erstellen, finden Sie unter [Aufgabenparallelität](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
##  <a name="wait"></a> Warte 

 Erwartet, dass diese Aufgabe einen Terminalzustand erreicht. Es ist möglich, dass das `wait`-Element den Task inline ausführt, wenn alle Taskabhängigkeiten erfüllt sind und er nicht bereits zur Ausführung durch einen Hintergrundworker aufgehoben wurde.  
  
```
task_status wait() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `task_status`-Wert, der entweder `completed` oder `canceled` ist. Wenn die Aufgabe eine Ausnahme während der Ausführung feststellt oder an sie eine Ausnahme aus einer vorherigen Aufgabe weitergegeben wurde, löst `wait` diese Ausnahme aus.  
  
### <a name="remarks"></a>Hinweise  
  
> [!IMPORTANT]
>  Rufen Sie in einer app (Universelle Windows Plattform) nicht `wait` im Code, der auf dem STA ausgeführt wird. Andernfalls löst die Laufzeit [invalid_operation](invalid-operation-class.md) daran, dass diese Methode den aktuellen Thread blockiert und dazu führen, die app dass können reagiert. Sie können jedoch Aufrufen der [Concurrency](#get) Methode, um das Ergebnis der Vorgängeraufgabe in einer aufgabenbasierten Fortsetzung zu erhalten.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)
