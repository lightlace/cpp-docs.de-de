---
title: Structured_task_group-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- structured_task_group
- PPL/concurrency::structured_task_group
- PPL/concurrency::structured_task_group::structured_task_group
- PPL/concurrency::structured_task_group::cancel
- PPL/concurrency::structured_task_group::is_canceling
- PPL/concurrency::structured_task_group::run
- PPL/concurrency::structured_task_group::run_and_wait
- PPL/concurrency::structured_task_group::wait
dev_langs:
- C++
helpviewer_keywords:
- structured_task_group class
ms.assetid: 742afa8c-c7b6-482c-b0ba-04c809927b22
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5cca5d20b89df97e27529d656e9a6553fd8a1820
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
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
|[~ Structured_task_group-Destruktor](#dtor)|Zerstört ein `structured_task_group`-Objekt. Ihnen wird erwartet, rufen Sie entweder die `wait` oder `run_and_wait` Methode für das Objekt vor dem Ausführen der Destruktor, wenn der Destruktor ausgeführt wird als Ergebnis der Entladung des Stapels aufgrund einer Ausnahme.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[cancel](#cancel)|Macht die Teilstruktur des Arbeit als Stammknoten diese Aufgabengruppe abbrechen versucht. Jede Aufgabe, die für die Aufgabengruppe geplant wird transitiv abgebrochen, wenn möglich.|  
|[is_canceling](#is_canceling)|Informiert den Aufrufer, und zwar unabhängig davon, ob die Aufgabengruppe derzeit in ein Abbruch ist. Dies zeigt nicht notwendigerweise an, die die `cancel` Methode wurde aufgerufen, auf die `structured_task_group` Objekt (Obwohl z. B. diese Methode zurückzugebenden sicherlich qualifiziert `true`). Es kann der Fall sein, die die `structured_task_group` Objekt Inline ausführt, und eine Aufgabengruppe weiter oben in der Arbeitsstruktur wurde abgebrochen. In Fällen, z. B. diesen, in denen die Common Language Runtime voraus, die den Ablauf Abbruch über diesen bestimme `structured_task_group` Objekt `true` wird ebenfalls zurückgegeben werden.|  
|[run](#run)|Überladen. Plant eine Aufgabe, auf die `structured_task_group` Objekt. Der Aufrufer verwaltet die Lebensdauer der `task_handle` Objekt übergeben, der `_Task_handle` Parameter. Die Version, die den Parameter akzeptiert `_Placement` bewirkt, dass der Task Blockcontainer ausführen an der Position, die durch diesen Parameter angegeben werden.|  
|[run_and_wait](#run_and_wait)|Überladen. Plant eine Aufgabe Inline im aufrufenden Kontext ausgeführt werden, mit Unterstützung der `structured_task_group` für vollständige abbruchunterstützung Objekt. Wenn eine `task_handle` Objekt als Parameter an übergeben `run_and_wait`, der Aufrufer ist verantwortlich für das Verwalten der Lebensdauer der `task_handle` Objekt. Die Funktion wartet dann, bis die gesamte Arbeit der `structured_task_group` Objekt abgeschlossen oder abgebrochen wurde.|  
|[wait](#wait)|Wartet, bis die gesamte Arbeit der `structured_task_group` abgeschlossen oder abgebrochen wird.|  
  
## <a name="remarks"></a>Hinweise  
 Es gibt eine Reihe von schweren Einschränkungen zur Verwendung der eine `structured_task_group` Objekt, um die Leistung zu erhalten:  
  
-   Ein einzelnes `structured_task_group` Objekt kann nicht durch mehrere Threads verwendet werden. Alle Vorgänge für eine `structured_task_group` Objekt muss ausgeführt werden, durch den Thread, der das Objekt erstellt. Die zwei Ausnahmen von dieser Regel werden die Memberfunktionen `cancel` und `is_canceling`. Das Objekt möglicherweise nicht in der Erfassungsliste eines Lambda-Ausdrucks und innerhalb eines Tasks verwendet werden, es sei denn, der Task eine der Abbruchoperationen verwendet.  
  
-   Alle Aufgaben, die voraussichtlich ein `structured_task_group` -Objekt geplant sind, durch die Verwendung der `task_handle` Objekte, die Sie explizit die Lebensdauer des verwalten müssen.  
  
-   Mehrere Gruppen können nur in absolut geschachtelter Reihenfolge verwendet werden. Wenn zwei `structured_task_group` Objekte deklariert werden, das zweite Argument deklariert wird (eine innere) zerstört werden muss, bevor eine beliebige Methode, außer `cancel` oder `is_canceling` für die erste Vorlage aufgerufen wird (der äußere eine). Diese Bedingung gilt im Fall des Deklarierens einfach mehrere `structured_task_group` Objekte innerhalb der gleichen oder funktionell geschachtelten Bereiche als auch eine Aufgabe, die in die Warteschlange, die Groß-/Kleinschreibung der `structured_task_group` über die `run` oder `run_and_wait` Methoden.  
  
-   Im Gegensatz zu den allgemeinen `task_group` -Klasse sind alle Zustände, in der `structured_task_group` Klasse ist endgültig. Nachdem Sie die Aufgaben in der Gruppe in der Warteschlange und gewartet, bis sie abgeschlossen haben, können Sie die gleiche Gruppe nicht erneut verwenden.  
  
 Weitere Informationen finden Sie unter [Aufgabenparallelität](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `structured_task_group`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** ppl.h  
  
 **Namespace:** Parallelität  
  
##  <a name="cancel"></a> Abbrechen 

 Macht die Teilstruktur des Arbeit als Stammknoten diese Aufgabengruppe abbrechen versucht. Jede Aufgabe, die für die Aufgabengruppe geplant wird transitiv abgebrochen, wenn möglich.  
  
```
void cancel();
```  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Abbruch](../../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation).  
  
##  <a name="is_canceling"></a> is_canceling 

 Informiert den Aufrufer, und zwar unabhängig davon, ob die Aufgabengruppe derzeit in ein Abbruch ist. Dies zeigt nicht notwendigerweise an, die die `cancel` Methode wurde aufgerufen, auf die `structured_task_group` Objekt (Obwohl z. B. diese Methode zurückzugebenden sicherlich qualifiziert `true`). Es kann der Fall sein, die die `structured_task_group` Objekt Inline ausführt, und eine Aufgabengruppe weiter oben in der Arbeitsstruktur wurde abgebrochen. In Fällen, z. B. diesen, in denen die Common Language Runtime voraus, die den Ablauf Abbruch über diesen bestimme `structured_task_group` Objekt `true` wird ebenfalls zurückgegeben werden.  
  
```
bool is_canceling();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Angabe, ob die `structured_task_group` Objekt in ein Abbruch ist (oder in Kürze garantiert ist).  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Abbruch](../../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation).  
  
##  <a name="run"></a> Führen Sie 

 Plant eine Aufgabe, auf die `structured_task_group` Objekt. Der Aufrufer verwaltet die Lebensdauer der `task_handle` Objekt übergeben, der `_Task_handle` Parameter. Die Version, die den Parameter akzeptiert `_Placement` bewirkt, dass der Task Blockcontainer ausführen an der Position, die durch diesen Parameter angegeben werden.  
  
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
 `_Function`  
 Der Typ des Funktionsobjekts ab, das aufgerufen wird, um den Text der Aufgabenhandle auszuführen.  
  
 `_Task_handle`  
 Ein Handle für die Arbeit geplant. Beachten Sie, dass der Aufrufer die Verantwortung für die Lebensdauer dieses Objekts verfügt. Die Common Language Runtime wird fortgesetzt, bis entweder Gültigkeitsdauer voraus die `wait` oder `run_and_wait` für diese Methode aufgerufen wurde `structured_task_group` Objekt.  
  
 `_Placement`  
 Ein Verweis auf den Speicherort, in dem die Aufgabe, durch dargestellt, die `_Task_handle` Parameter ausgeführt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Die Common Language Runtime erstellt eine Kopie der Arbeitsfunktion, die Sie an diese Methode übergeben. Alle Zustandsänderungen, die in ein Funktionsobjekt auftreten, die Sie an diese Methode übergeben werden nicht in Ihrer Kopie des Funktionsobjekts angezeigt.  
  
 Wenn die `structured_task_group` Destructs als Ergebnis der stapelentladung nach einer Ausnahme, Sie müssen nicht garantieren, dass ein Aufruf entweder wurde die `wait` oder `run_and_wait` Methode. In diesem Fall der Destruktor wird entsprechend "Abbrechen", und warten Sie, bis die Aufgabe, dargestellt durch die `_Task_handle` Parameter abgeschlossen.  
  
 Löst ein [Invalid_multiple_scheduling](invalid-multiple-scheduling-class.md) -Ausnahme aus, wenn vom Task behandelt angegeben durch die `_Task_handle` Parameter wurde bereits auf einem Aufgabengruppenobjekt über geplant wurde die `run` Methode und es wurde keine zwischenzeitlichen Aufruf von entweder die `wait` oder `run_and_wait` -Methode für diese Aufgabengruppe.  
  
##  <a name="run_and_wait"></a> run_and_wait 

 Plant eine Aufgabe Inline im aufrufenden Kontext ausgeführt werden, mit Unterstützung der `structured_task_group` für vollständige abbruchunterstützung Objekt. Wenn eine `task_handle` Objekt als Parameter an übergeben `run_and_wait`, der Aufrufer ist verantwortlich für das Verwalten der Lebensdauer der `task_handle` Objekt. Die Funktion wartet dann, bis die gesamte Arbeit der `structured_task_group` Objekt abgeschlossen oder abgebrochen wurde.  
  
```
template<class _Function>
task_group_status run_and_wait(task_handle<_Function>& _Task_handle);

template<class _Function>
task_group_status run_and_wait(const _Function& _Func);
```  
  
### <a name="parameters"></a>Parameter  
 `_Function`  
 Der Typ des Funktionsobjekts ab, das aufgerufen wird, um den Task auszuführen.  
  
 `_Task_handle`  
 Ein Handle für die Aufgabe, die Inline im aufrufenden Kontext ausgeführt wird. Beachten Sie, dass der Aufrufer die Verantwortung für die Lebensdauer dieses Objekts verfügt. Die Common Language Runtime werden weiterhin bis live wie erwartet die `run_and_wait` -Methode beendet die Ausführung.  
  
 `_Func`  
 Eine Funktion, die aufgerufen wird, um den Text der Arbeit aufzurufen. Dies ist möglicherweise ein Lambda-Ausdruck oder ein anderes Objekt, das eine Version von den Funktionsaufrufoperator mit der Signatur unterstützt `void operator()()`.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Hinweis, ob der Wartezustand erfüllt wurde oder die Aufgabengruppe wurde, aufgrund eines expliziten Abbruchvorgangs oder eine Ausnahme ausgelöst wird, von einem ihrer Aufgaben abgebrochen. Weitere Informationen finden Sie unter [Task_group_status](concurrency-namespace-enums.md)  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass ein oder mehrere der Aufgaben geplant sind, dies `structured_task_group` Objekt möglicherweise Inline im aufrufenden Kontext ausgeführt.  
  
 Wenn eine oder mehrere dieser geplante Aufgaben `structured_task_group` -Objekt löst eine Ausnahme aus die Laufzeit wird, wählen Sie eine solche Ausnahme seiner Wahl und übertragen Sie sie aus dem Aufruf von der `run_and_wait` Methode.  
  
 Nachdem diese Funktion zurückgibt, die `structured_task_group` Objekt gilt als in einem abschließenden Zustand und sollte nicht verwendet werden. Beachten Sie, dass eine Verwendung nach der `run_and_wait` Methodenrückgabe führt zu nicht definiertem Verhalten.  
  
 In ohne Ausnahmen Ausführungspfad, verfügen Sie über eine datenbankabonnements entweder diese Methode aufrufen oder die `wait` Methode vor der Destruktor der der `structured_task_group` ausgeführt wird.  
  
##  <a name="ctor"></a> structured_task_group 

 Erstellt ein neues `structured_task_group`-Objekt.  
  
```
structured_task_group();

structured_task_group(cancellation_token _CancellationToken);
```  
  
### <a name="parameters"></a>Parameter  
 `_CancellationToken`  
 Ein Abbruchtoken, das diese strukturierten Aufgabengruppe zugeordnet werden soll. Die strukturierte Aufgabengruppe werden abgebrochen, wenn das Token abgebrochen wird.  
  
### <a name="remarks"></a>Hinweise  
 Der Konstruktor, der ein Abbruchtoken akzeptiert erstellt eine `structured_task_group` , werden abgebrochen, wenn die Quelle dem Token zugeordnet abgebrochen wird. Als explizites Abbruchtoken bereitstellen, werden auch diese strukturierten Aufgabengruppe aus der Einbeziehung in einer impliziten Abbruch der übergeordneten Gruppe mit einem anderen Token oder kein Token isoliert.  
  
##  <a name="dtor"></a> ~structured_task_group 

 Zerstört ein `structured_task_group`-Objekt. Ihnen wird erwartet, rufen Sie entweder die `wait` oder `run_and_wait` Methode für das Objekt vor dem Ausführen der Destruktor, wenn der Destruktor ausgeführt wird als Ergebnis der Entladung des Stapels aufgrund einer Ausnahme.  
  
```
~structured_task_group();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Destruktor ausgeführt wird, als das Ergebnis der normalen Ausführung (z. B. keine stapelentladung aufgrund einer Ausnahme) und weder die `wait` noch `run_and_wait` Methoden aufgerufen wurden, der Destruktor möglicherweise eine [Missing_wait](missing-wait-class.md) Diese Ausnahme.  
  
##  <a name="wait"></a> Warte 

 Wartet, bis die gesamte Arbeit der `structured_task_group` abgeschlossen oder abgebrochen wird.  
  
```
task_group_status wait();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Hinweis, ob der Wartezustand erfüllt wurde oder die Aufgabengruppe wurde, aufgrund eines expliziten Abbruchvorgangs oder eine Ausnahme ausgelöst wird, von einem ihrer Aufgaben abgebrochen. Weitere Informationen finden Sie unter [Task_group_status](concurrency-namespace-enums.md)  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass ein oder mehrere der Aufgaben geplant sind, dies `structured_task_group` Objekt möglicherweise Inline im aufrufenden Kontext ausgeführt.  
  
 Wenn eine oder mehrere dieser geplante Aufgaben `structured_task_group` -Objekt löst eine Ausnahme aus die Laufzeit wird, wählen Sie eine solche Ausnahme seiner Wahl und übertragen Sie sie aus dem Aufruf von der `wait` Methode.  
  
 Nachdem diese Funktion zurückgibt, die `structured_task_group` Objekt gilt als in einem abschließenden Zustand und sollte nicht verwendet werden. Beachten Sie, dass eine Verwendung nach der `wait` Methodenrückgabe führt zu nicht definiertem Verhalten.  
  
 In ohne Ausnahmen Ausführungspfad, verfügen Sie über eine datenbankabonnements entweder diese Methode aufrufen oder die `run_and_wait` Methode vor der Destruktor der der `structured_task_group` ausgeführt wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Task_group-Klasse](task-group-class.md)   
 [task_handle-Klasse](task-handle-class.md)
