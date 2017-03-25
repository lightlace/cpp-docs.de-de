---
title: Structured_task_group-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 21
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: a1817080506150a8a25918988e18b76dd7a04def
ms.lasthandoff: 03/17/2017

---
# <a name="structuredtaskgroup-class"></a>structured_task_group-Klasse
Die `structured_task_group`-Klasse stellt eine stark strukturierte Auflistung paralleler Arbeit dar. Sie können einzelne parallele Aufgaben mithilfe von `structured_task_group`-Objekten in eine `task_handle` stellen und warten, bis sie abgeschlossen werden, oder Sie können die Aufgabengruppe abbrechen, bevor deren Ausführung beendet wird, wodurch auch alle Aufgaben abgebrochen werden, deren Ausführung nicht gestartet wurde.  
  
## <a name="syntax"></a>Syntax  
  
```
class structured_task_group;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[structured_task_group](#ctor)|Überladen. Erstellt ein neues `structured_task_group`-Objekt.|  
|[~ Structured_task_group-Destruktor](#dtor)|Zerstört ein `structured_task_group`-Objekt. Ihnen wird erwartet, rufen Sie entweder die `wait` oder `run_and_wait` Methode für das Objekt vor dem Ausführen der Destruktor, wenn der Destruktor ausgeführt wird als Ergebnis des Entladung des Stapels aufgrund einer Ausnahme.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Abbrechen](#cancel)|Wird versucht, die Teilstruktur der Arbeit als Stammknoten diese Aufgabengruppe abzubrechen. Jede in der Aufgabengruppe geplante Aufgabe wird transitiv abgebrochen, wenn möglich.|  
|[is_canceling](#is_canceling)|Informiert den Aufrufer, ob die Aufgabengruppe derzeit in ein Abbruch ist. Dies bedeutet nicht unbedingt, die die `cancel` Methode wurde aufgerufen, auf die `structured_task_group` Objekt (Obwohl z. B. diese Methode zurückgibt sicherlich qualifiziert `true`). Es kann der Fall sein, die die `structured_task_group` -Objekt Inline ausführt und eine Aufgabengruppe weiter oben in der Arbeitsstruktur wurde abgebrochen. In Fällen wie diesen, in denen die Laufzeit vorzeitig Abbruch durch diesen Fluss bestimmen kann `structured_task_group` Objekt `true` wird ebenfalls zurückgegeben werden.|  
|[run](#run)|Überladen. Plant eine Aufgabe für die `structured_task_group` Objekt. Der Aufrufer verwaltet die Lebensdauer der `task_handle` Objekt übergeben, der `_Task_handle` Parameter. Die Version, die die Parameter `_Placement` bewirkt, dass der Task Blockcontainer ausführen an der Position, die durch diesen Parameter angegeben werden.|  
|[run_and_wait](#run_and_wait)|Überladen. Plant eine Aufgabe Inline auf dem aufrufenden Kontext ausgeführt werden, mit Unterstützung der `structured_task_group` -Objekt für vollständige Abbruch-Unterstützung. Wenn ein `task_handle` Objekt als Parameter übergeben `run_and_wait`, der Aufrufer ist verantwortlich für die Verwaltung der Lebensdauer der `task_handle` Objekt. Die Funktion wartet dann, bis die gesamte Arbeit der `structured_task_group` Objekt abgeschlossen oder abgebrochen wurde.|  
|[Warte](#wait)|Wartet, bis die gesamte Arbeit der `structured_task_group` abgeschlossen oder abgebrochen wird.|  
  
## <a name="remarks"></a>Hinweise  
 Es gibt eine Reihe von schweren Einschränkungen zur Verwendung der platziert ein `structured_task_group` Objekt, um die Leistung zu erhalten:  
  
-   Ein einzelnes `structured_task_group` Objekt kann von mehreren Threads verwendet werden. Alle Vorgänge für ein `structured_task_group` Objekt muss durchgeführt werden, indem der Thread, der das Objekt erstellt. Zwei Ausnahmen von dieser Regel werden die Memberfunktionen `cancel` und `is_canceling`. Das Objekt möglicherweise nicht in der Erfassungsliste eines Lambda-Ausdrucks und innerhalb einer Aufgabe verwendet werden, es sei denn, die Aufgabe der Abbruch Vorgänge verwendet wird.  
  
-   Alle Vorgänge geplant ein `structured_task_group` -Objekt geplant sind, durch die Verwendung von `task_handle` Objekte, die Sie explizit die Lebensdauer des verwalten müssen.  
  
-   Mehrere Gruppen können nur in absolut geschachtelter Reihenfolge verwendet werden. Wenn zwei `structured_task_group` Objekte deklariert werden, im zweiten Beispiel deklarierte (das innere) zerstört werden muss, bevor eine beliebige Methode außer `cancel` oder `is_canceling` für den ersten aufgerufen wird (die äußere eins). Diese Bedingung gilt im Fall einfach Deklarieren mehrerer `structured_task_group` Objekte innerhalb der gleichen oder funktionell geschachtelten Bereiche als auch im Fall einer Aufgabe, die in die Warteschlange gestellt wurde der `structured_task_group` über die `run` oder `run_and_wait` Methoden.  
  
-   Im Gegensatz zu den allgemeinen `task_group` -Klasse sind alle Zustände in der `structured_task_group` Klasse ist endgültig. Nachdem Sie die Aufgaben der Gruppe und gewartet, bis sie abgeschlossen haben, können Sie dieselbe Gruppe nicht erneut verwenden.  
  
 Weitere Informationen finden Sie unter [Aufgabenparallelität](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `structured_task_group`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** ppl.h  
  
 **Namespace:** Parallelität  
  
##  <a name="cancel"></a>Abbrechen 

 Wird versucht, die Teilstruktur der Arbeit als Stammknoten diese Aufgabengruppe abzubrechen. Jede in der Aufgabengruppe geplante Aufgabe wird transitiv abgebrochen, wenn möglich.  
  
```
void cancel();
```  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Abbruch](../../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation).  
  
##  <a name="is_canceling"></a>is_canceling 

 Informiert den Aufrufer, ob die Aufgabengruppe derzeit in ein Abbruch ist. Dies bedeutet nicht unbedingt, die die `cancel` Methode wurde aufgerufen, auf die `structured_task_group` Objekt (Obwohl z. B. diese Methode zurückgibt sicherlich qualifiziert `true`). Es kann der Fall sein, die die `structured_task_group` -Objekt Inline ausführt und eine Aufgabengruppe weiter oben in der Arbeitsstruktur wurde abgebrochen. In Fällen wie diesen, in denen die Laufzeit vorzeitig Abbruch durch diesen Fluss bestimmen kann `structured_task_group` Objekt `true` wird ebenfalls zurückgegeben werden.  
  
```
bool is_canceling();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Angabe, ob die `structured_task_group` Objekt in ein Abbruch ist (oder in Kürze garantiert).  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Abbruch](../../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation).  
  
##  <a name="run"></a>Ausführen 

 Plant eine Aufgabe für die `structured_task_group` Objekt. Der Aufrufer verwaltet die Lebensdauer der `task_handle` Objekt übergeben, der `_Task_handle` Parameter. Die Version, die die Parameter `_Placement` bewirkt, dass der Task Blockcontainer ausführen an der Position, die durch diesen Parameter angegeben werden.  
  
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
 Der Typ des Funktionsobjekts, das aufgerufen wird, um den Text des Aufgabenhandles auszuführen.  
  
 `_Task_handle`  
 Ein Handle für die Arbeit. Beachten Sie, dass der Aufrufer die Verantwortung für die Lebensdauer dieses Objekts hat. Die Laufzeit erwartet weiterhin, es erst dann aktiv die `wait` oder `run_and_wait` für diese Methode aufgerufen wurde `structured_task_group` Objekt.  
  
 `_Placement`  
 Ein Verweis auf den Speicherort, in dem die Aufgabe, durch dargestellt, den `_Task_handle` -Parameter sollte ausgeführt werden.  
  
### <a name="remarks"></a>Hinweise  
 Die Common Language Runtime erstellt eine Kopie der Arbeitsfunktion, die an diese Methode übergeben. Zustandsänderungen, die in ein Funktionsobjekt auftreten, die an diese Methode übergeben werden nicht in der Kopie dieses Funktionsobjekts angezeigt.  
  
 Wenn die `structured_task_group` Destructs als Ergebnis der Stapel entladen aus einer Ausnahme, Sie müssen nicht garantieren, dass ein Aufruf entweder wurde der `wait` oder `run_and_wait` Methode. In diesem Fall der Destruktor wird entsprechend Abbrechen und warten, bis die Aufgabe darstellt, durch die `_Task_handle` Parameter abgeschlossen.  
  
 Löst ein [Invalid_multiple_scheduling](invalid-multiple-scheduling-class.md) -Ausnahme aus, wenn der Task behandeln vom der `_Task_handle` Parameter wurde ein Aufgabengruppenobjekt über bereits geplant der `run` Methode und es keinen zwischenzeitlichen Aufruf der `wait` oder `run_and_wait` -Methode für diese Aufgabengruppe.  
  
##  <a name="run_and_wait"></a>run_and_wait 

 Plant eine Aufgabe Inline auf dem aufrufenden Kontext ausgeführt werden, mit Unterstützung der `structured_task_group` -Objekt für vollständige Abbruch-Unterstützung. Wenn ein `task_handle` Objekt als Parameter übergeben `run_and_wait`, der Aufrufer ist verantwortlich für die Verwaltung der Lebensdauer der `task_handle` Objekt. Die Funktion wartet dann, bis die gesamte Arbeit der `structured_task_group` Objekt abgeschlossen oder abgebrochen wurde.  
  
```
template<class _Function>
task_group_status run_and_wait(task_handle<_Function>& _Task_handle);

template<class _Function>
task_group_status run_and_wait(const _Function& _Func);
```  
  
### <a name="parameters"></a>Parameter  
 `_Function`  
 Der Typ des Funktionsobjekts, das aufgerufen wird, um die Aufgabe auszuführen.  
  
 `_Task_handle`  
 Ein Handle für die Aufgabe, die Inline auf dem aufrufenden Kontext ausgeführt wird. Beachten Sie, dass der Aufrufer die Verantwortung für die Lebensdauer dieses Objekts hat. Die Laufzeit erwartet weiterhin, es erst aktiv die `run_and_wait` -Methode die Ausführung beendet.  
  
 `_Func`  
 Eine Funktion, die aufgerufen wird, um den Text der Arbeit aufzurufen. Möglicherweise wird ein Lambda-Ausdruck oder anderes Objekt, das eine Version des Funktionsaufrufoperators mit der Signatur unterstützt `void operator()()`.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Hinweis darauf, ob der Wartevorgang erfüllt wurde oder die Aufgabengruppe, aufgrund eines expliziten Abbruchvorgangs oder eine Ausnahme ausgelöst wird, eine der Aufgaben abgebrochen. Weitere Informationen finden Sie unter [Task_group_status](concurrency-namespace-enums.md)  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass eine oder mehrere dieser geplante Aufgaben `structured_task_group` Objekt möglicherweise Inline auf dem aufrufenden Kontext ausgeführt.  
  
 Wenn eine oder mehrere dieser geplante Aufgaben `structured_task_group` -Objekt löst eine Ausnahme aus der Common Language Runtime wird, wählen Sie eine dieser Ausnahmen von der Auswahl und gibt sie aus dem Aufruf von der `run_and_wait` Methode.  
  
 Nachdem die Funktion zurückgibt, das `structured_task_group` Objekt wird in einem abschließenden Zustand betrachtet und sollte nicht verwendet werden. Beachten Sie, dass eine Verwendung nach der `run_and_wait` Methodenrückgabe führt zu nicht definiertem Verhalten.  
  
 In ohne Ausnahmen Ausführungspfad, haben Sie die Pflicht, entweder diese Methode aufzurufen oder `wait` -Methode auf, bevor der Destruktor der `structured_task_group` ausgeführt wird.  
  
##  <a name="ctor"></a>structured_task_group 

 Erstellt ein neues `structured_task_group`-Objekt.  
  
```
structured_task_group();

structured_task_group(cancellation_token _CancellationToken);
```  
  
### <a name="parameters"></a>Parameter  
 `_CancellationToken`  
 Ein Abbruchtoken, diese strukturierten Aufgabengruppe zugeordnet werden soll. Wenn das Token abgebrochen wird, wird die strukturierte Aufgabengruppe abgebrochen.  
  
### <a name="remarks"></a>Hinweise  
 Der Konstruktor, der ein Abbruchtoken akzeptiert erstellt eine `structured_task_group` , wenn die Quelle des Tokens abgebrochen wird abgebrochen. Bereitstellen als explizites Abbruchtoken isoliert auch diese strukturierten Aufgabengruppe aus der Einbeziehung in einen impliziten Abbruch der übergeordneten Gruppe mit einem anderen Token oder kein Token.  
  
##  <a name="dtor"></a>~ Structured_task_group 

 Zerstört ein `structured_task_group`-Objekt. Ihnen wird erwartet, rufen Sie entweder die `wait` oder `run_and_wait` Methode für das Objekt vor dem Ausführen der Destruktor, wenn der Destruktor ausgeführt wird als Ergebnis des Entladung des Stapels aufgrund einer Ausnahme.  
  
```
~structured_task_group();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Destruktor ausgeführt wird, als Ergebnis einer normalen Ausführung (z. B. keine stapelentladung aufgrund einer Ausnahme) und weder die `wait` noch `run_and_wait` Methoden aufgerufen wurden, kann der Destruktor Auslösen einer [Missing_wait](missing-wait-class.md) Ausnahme.  
  
##  <a name="wait"></a>Warte 

 Wartet, bis die gesamte Arbeit der `structured_task_group` abgeschlossen oder abgebrochen wird.  
  
```
task_group_status wait();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Hinweis darauf, ob der Wartevorgang erfüllt wurde oder die Aufgabengruppe, aufgrund eines expliziten Abbruchvorgangs oder eine Ausnahme ausgelöst wird, eine der Aufgaben abgebrochen. Weitere Informationen finden Sie unter [Task_group_status](concurrency-namespace-enums.md)  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass eine oder mehrere dieser geplante Aufgaben `structured_task_group` Objekt möglicherweise Inline auf dem aufrufenden Kontext ausgeführt.  
  
 Wenn eine oder mehrere dieser geplante Aufgaben `structured_task_group` -Objekt löst eine Ausnahme aus der Common Language Runtime wird, wählen Sie eine dieser Ausnahmen von der Auswahl und gibt sie aus dem Aufruf von der `wait` Methode.  
  
 Nachdem die Funktion zurückgibt, das `structured_task_group` Objekt wird in einem abschließenden Zustand betrachtet und sollte nicht verwendet werden. Beachten Sie, dass eine Verwendung nach der `wait` Methodenrückgabe führt zu nicht definiertem Verhalten.  
  
 In ohne Ausnahmen Ausführungspfad, haben Sie die Pflicht, entweder diese Methode aufzurufen oder `run_and_wait` -Methode auf, bevor der Destruktor der `structured_task_group` ausgeführt wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Task_group-Klasse](task-group-class.md)   
 [task_handle-Klasse](task-handle-class.md)

