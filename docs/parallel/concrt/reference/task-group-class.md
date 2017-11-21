Die `task_group` -Klasse stellt eine Auflistung der parallelen Arbeit dar, auf die gewartet oder die abgebrochen werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
class task_group;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[task_group](#ctor)|Überladen. Erstellt ein neues `task_group`-Objekt.|  
|[~ Task_group-Destruktor](#dtor)|Zerstört ein `task_group`-Objekt. Ihnen wird erwartet, die entweder Aufrufen der `wait` oder `run_and_wait` Methode für das Objekt vor dem Destruktor ausgeführt, es sei denn, der Destruktor als Ergebnis der stapelentladung aufgrund einer Ausnahme ausgeführt wird.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Abbrechen](#cancel)|Macht die Teilstruktur des Arbeit als Stammknoten diese Aufgabengruppe abbrechen versucht. Jede Aufgabe, die für die Aufgabengruppe geplant wird transitiv abgebrochen, wenn möglich.|  
|[is_canceling](#is_canceling)|Informiert den Aufrufer, und zwar unabhängig davon, ob die Aufgabengruppe derzeit in ein Abbruch ist. Dies zeigt nicht notwendigerweise an, die die `cancel` Methode wurde aufgerufen, auf die `task_group` Objekt (Obwohl z. B. diese Methode zurückzugebenden sicherlich qualifiziert `true`). Es kann der Fall sein, die die `task_group` Objekt Inline ausführt, und eine Aufgabengruppe weiter oben in der Arbeitsstruktur wurde abgebrochen. In Fällen, z. B. diesen, in denen die Common Language Runtime voraus, die den Ablauf Abbruch über diesen bestimme `task_group` Objekt `true` wird ebenfalls zurückgegeben werden.|  
|[run](#run)|Überladen. Plant eine Aufgabe, auf die `task_group` Objekt. Wenn eine `task_handle` Objekt als Parameter an übergeben `run`, der Aufrufer ist verantwortlich für das Verwalten der Lebensdauer der `task_handle` Objekt. Führen Sie die Version der Methode, die einen Verweis auf ein Funktionsobjekt akzeptiert, wie ein Parameter Heapzuordnung innerhalb der Runtime umfasst u. u. geringerer Leistung als die Version, die einen Verweis auf akzeptiert eine `task_handle` Objekt. Die Version, die den Parameter akzeptiert `_Placement` bewirkt, dass der Task Blockcontainer ausführen an der Position, die durch diesen Parameter angegeben werden.|  
|[run_and_wait](#run_and_wait)|Überladen. Plant eine Aufgabe Inline im aufrufenden Kontext ausgeführt werden, mit Unterstützung der `task_group` für vollständige abbruchunterstützung Objekt. Die Funktion wartet dann, bis die gesamte Arbeit der `task_group` Objekt abgeschlossen oder abgebrochen wurde. Wenn eine `task_handle` Objekt als Parameter an übergeben `run_and_wait`, der Aufrufer ist verantwortlich für das Verwalten der Lebensdauer der `task_handle` Objekt.|  
|[Warte](#wait)|Wartet, bis die gesamte Arbeit der `task_group` Objekt abgeschlossen oder abgebrochen wurde.|  
  
## <a name="remarks"></a>Hinweise  
 Im Gegensatz zu den stark eingeschränkten `structured_task_group` -Klasse, die `task_group` Klasse ist wesentlich allgemeineren Konstrukt. Er verfügt nicht über die Einschränkungen beschrieben, die von [Structured_task_group](structured-task-group-class.md). `task_group`Objekte können problemlos threadübergreifend verwendet und Freiform-Möglichkeiten genutzt. Den Nachteil, dass die `task_group` Konstrukt ist, dass er nicht ausgeführt werden kann, sowie die `structured_task_group` -Konstrukt für Aufgaben die kleine Mengen von Arbeit ausführen.  
  
 Weitere Informationen finden Sie unter [Aufgabenparallelität](../task-parallelism-concurrency-runtime.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `task_group`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** ppl.h  
  
 **Namespace:** Parallelität  
  
##  <a name="cancel"></a>Abbrechen 

 Macht die Teilstruktur des Arbeit als Stammknoten diese Aufgabengruppe abbrechen versucht. Jede Aufgabe, die für die Aufgabengruppe geplant wird transitiv abgebrochen, wenn möglich.  
  
```  
void cancel();  
```  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Abbruch](../cancellation-in-the-ppl.md).  
  
##  <a name="is_canceling"></a>is_canceling 

 Informiert den Aufrufer, und zwar unabhängig davon, ob die Aufgabengruppe derzeit in ein Abbruch ist. Dies zeigt nicht notwendigerweise an, die die `cancel` Methode wurde aufgerufen, auf die `task_group` Objekt (Obwohl z. B. diese Methode zurückzugebenden sicherlich qualifiziert `true`). Es kann der Fall sein, die die `task_group` Objekt Inline ausführt, und eine Aufgabengruppe weiter oben in der Arbeitsstruktur wurde abgebrochen. In Fällen, z. B. diesen, in denen die Common Language Runtime voraus, die den Ablauf Abbruch über diesen bestimme `task_group` Objekt `true` wird ebenfalls zurückgegeben werden.  
  
```  
bool is_canceling();  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Angabe, ob die `task_group` Objekt in ein Abbruch ist (oder in Kürze garantiert ist).  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Abbruch](../cancellation-in-the-ppl.md).  
  
##  <a name="run"></a>Führen Sie 

 Plant eine Aufgabe, auf die `task_group` Objekt. Wenn eine `task_handle` Objekt als Parameter an übergeben `run`, der Aufrufer ist verantwortlich für das Verwalten der Lebensdauer der `task_handle` Objekt. Führen Sie die Version der Methode, die einen Verweis auf ein Funktionsobjekt akzeptiert, wie ein Parameter Heapzuordnung innerhalb der Runtime umfasst u. u. geringerer Leistung als die Version, die einen Verweis auf akzeptiert eine `task_handle` Objekt. Die Version, die den Parameter akzeptiert `_Placement` bewirkt, dass der Task Blockcontainer ausführen an der Position, die durch diesen Parameter angegeben werden.  
  
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
 `_Function`  
 Der Typ des Funktionsobjekts ab, das aufgerufen wird, um den Text der Aufgabenhandle auszuführen.  
  
 `_Func`  
 Eine Funktion, die aufgerufen wird, um den Text der Aufgabe aufzurufen. Dies ist möglicherweise ein Lambda-Ausdruck oder ein anderes Objekt, das eine Version von den Funktionsaufrufoperator mit der Signatur unterstützt `void operator()()`.  
  
 `_Placement`  
 Ein Verweis auf den Speicherort, in dem die Aufgabe, durch dargestellt, die `_Func` Parameter ausgeführt werden soll.  
  
 `_Task_handle`  
 Ein Handle für die Arbeit geplant. Beachten Sie, dass der Aufrufer die Verantwortung für die Lebensdauer dieses Objekts verfügt. Die Common Language Runtime wird fortgesetzt, bis entweder Gültigkeitsdauer voraus die `wait` oder `run_and_wait` für diese Methode aufgerufen wurde `task_group` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die Runtime plant die bereitgestellte Arbeitsfunktion, die zu einem späteren Zeitpunkt ausgeführt werden kann, wenn die aufrufende Funktion zurückkehrt. Diese Methode verwendet eine [Task_handle](task-handle-class.md) Objekt, das eine Kopie der die bereitgestellte Arbeitsfunktion verfügen. Alle Zustandsänderungen, die in ein Funktionsobjekt auftreten, die Sie an diese Methode übergeben werden deshalb nicht in Ihrer Kopie des Funktionsobjekts angezeigt. Darüber hinaus stellen Sie sicher, dass die Lebensdauer von Objekten, die Sie per Zeiger oder Verweis auf die Arbeitsfunktion übergeben gültig bleiben, bis die Arbeitsfunktion zurückgibt.  
  
 Wenn die `task_group` Destructs als Ergebnis der stapelentladung nach einer Ausnahme, Sie müssen nicht garantieren, dass ein Aufruf entweder wurde die `wait` oder `run_and_wait` Methode. In diesem Fall der Destruktor wird entsprechend "Abbrechen", und warten Sie, bis die Aufgabe, dargestellt durch die `_Task_handle` Parameter abgeschlossen.  
  
 Löst die Methode eine [Invalid_multiple_scheduling](invalid-multiple-scheduling-class.md) -Ausnahme aus, wenn vom Task behandelt werden angegeben durch die `_Task_handle` Parameter wurde bereits auf einem Aufgabengruppenobjekt über geplant wurde die `run` Methode und es wurde keine dazwischen liegende rufen Sie entweder die `wait` oder `run_and_wait` -Methode für diese Aufgabengruppe.  
  
##  <a name="run_and_wait"></a>run_and_wait 

 Plant eine Aufgabe Inline im aufrufenden Kontext ausgeführt werden, mit Unterstützung der `task_group` für vollständige abbruchunterstützung Objekt. Die Funktion wartet dann, bis die gesamte Arbeit der `task_group` Objekt abgeschlossen oder abgebrochen wurde. Wenn eine `task_handle` Objekt als Parameter an übergeben `run_and_wait`, der Aufrufer ist verantwortlich für das Verwalten der Lebensdauer der `task_handle` Objekt.  
  
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
 `_Function`  
 Der Typ des Funktionsobjekts ab, das aufgerufen wird, um den Text der Aufgabe auszuführen.  
  
 `_Task_handle`  
 Ein Handle für die Aufgabe, die Inline im aufrufenden Kontext ausgeführt wird. Beachten Sie, dass der Aufrufer die Verantwortung für die Lebensdauer dieses Objekts verfügt. Die Common Language Runtime werden weiterhin bis live wie erwartet die `run_and_wait` -Methode beendet die Ausführung.  
  
 `_Func`  
 Eine Funktion, die aufgerufen wird, um den Text der Arbeit aufzurufen. Dies ist möglicherweise ein Lambda-Ausdruck oder ein anderes Objekt, das eine Version von den Funktionsaufrufoperator mit der Signatur unterstützt `void operator()()`.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Hinweis, ob der Wartezustand erfüllt wurde oder die Aufgabengruppe wurde, aufgrund eines expliziten Abbruchvorgangs oder eine Ausnahme ausgelöst wird, von einem ihrer Aufgaben abgebrochen. Weitere Informationen finden Sie unter [Task_group_status](concurrency-namespace-enums.md#task_group_status).  

  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass ein oder mehrere der Aufgaben geplant sind, dies `task_group` Objekt möglicherweise Inline im aufrufenden Kontext ausgeführt.  
  
 Wenn eine oder mehrere dieser geplante Aufgaben `task_group` -Objekt löst eine Ausnahme aus die Laufzeit wird, wählen Sie eine solche Ausnahme seiner Wahl und übertragen Sie sie aus dem Aufruf von der `run_and_wait` Methode.  
  
 Bei der Rückgabe aus der `run_and_wait` Methode auf eine `task_group` -Objekt, die Common Language Runtime setzt das Objekt auf einen fehlerfreien Zustand, in dem es wiederverwendet werden kann. Dies schließt die Groß-/Kleinschreibung, in denen die `task_group` Objekt wurde abgebrochen.  
  
 In ohne Ausnahmen Ausführungspfad, verfügen Sie über eine datenbankabonnements entweder diese Methode aufrufen oder die `wait` Methode vor der Destruktor der der `task_group` ausgeführt wird.  
  
##  <a name="ctor"></a>task_group 

 Erstellt ein neues `task_group`-Objekt.  
  
```  
task_group();  
  
task_group(  
   cancellation_token _CancellationToken  
);  
```  
  
### <a name="parameters"></a>Parameter  
 `_CancellationToken`  
 Ein Abbruchtoken, das diese Aufgabengruppe zugeordnet werden soll. Wenn das Token abgebrochen wird, wird die Aufgabengruppe abgebrochen werden.  
  
### <a name="remarks"></a>Hinweise  
 Der Konstruktor, der ein Abbruchtoken akzeptiert erstellt eine `task_group` , werden abgebrochen, wenn die Quelle dem Token zugeordnet abgebrochen wird. Als explizites Abbruchtoken bereitstellen, werden auch diese Aufgabengruppe aus der Einbeziehung in einer impliziten Abbruch der übergeordneten Gruppe mit einem anderen Token oder kein Token isoliert.  
  
##  <a name="dtor"></a>~ Task_group 

 Zerstört ein `task_group`-Objekt. Ihnen wird erwartet, die entweder Aufrufen der `wait` oder `run_and_wait` Methode für das Objekt vor dem Destruktor ausgeführt, es sei denn, der Destruktor als Ergebnis der stapelentladung aufgrund einer Ausnahme ausgeführt wird.  
  
```  
~task_group();  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Destruktor ausgeführt wird, als das Ergebnis der normalen Ausführung (z. B. keine stapelentladung aufgrund einer Ausnahme) und weder die `wait` noch `run_and_wait` Methoden aufgerufen wurden, der Destruktor möglicherweise eine [Missing_wait](missing-wait-class.md) Diese Ausnahme.  
  
##  <a name="wait"></a>Warte 

 Wartet, bis die gesamte Arbeit der `task_group` Objekt abgeschlossen oder abgebrochen wurde.  
  
```  
task_group_status wait();  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Hinweis, ob der Wartezustand erfüllt wurde oder die Aufgabengruppe wurde, aufgrund eines expliziten Abbruchvorgangs oder eine Ausnahme ausgelöst wird, von einem ihrer Aufgaben abgebrochen. Weitere Informationen finden Sie unter [Task_group_status](concurrency-namespace-enums.md#task_group_status).  

  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass ein oder mehrere der Aufgaben geplant sind, dies `task_group` Objekt möglicherweise Inline im aufrufenden Kontext ausgeführt.  
  
 Wenn eine oder mehrere dieser geplante Aufgaben `task_group` -Objekt löst eine Ausnahme aus die Laufzeit wird, wählen Sie eine solche Ausnahme seiner Wahl und übertragen Sie sie aus dem Aufruf von der `wait` Methode.  
  
 Aufrufen von `wait` auf eine `task_group` Objekt setzt es zurück in einen fehlerfreien Zustand, in dem es wiederverwendet werden kann. Dies schließt die Groß-/Kleinschreibung, in denen die `task_group` Objekt wurde abgebrochen.  
  
 In ohne Ausnahmen Ausführungspfad, verfügen Sie über eine datenbankabonnements entweder diese Methode aufrufen oder die `run_and_wait` Methode vor der Destruktor der der `task_group` ausgeführt wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Structured_task_group-Klasse](structured-task-group-class.md)   
 [task_handle-Klasse](task-handle-class.md)