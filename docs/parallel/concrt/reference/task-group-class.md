Die `task_group` -Klasse stellt eine Auflistung der parallelen Arbeit dar, auf die gewartet werden kann oder die abgebrochen werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
class task_group;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Task_group-Konstruktor](#ctor)|Überladen. Erstellt ein neues `task_group`-Objekt.|  
|[~ Task_group-Destruktor](#dtor)|Zerstört ein `task_group`-Objekt. Ihnen wird erwartet, rufen Sie entweder die `wait` oder `run_and_wait` Methode für das Objekt vor der Destruktor ausgeführt, es sei denn, das Ergebnis der stapelentladung aufgrund einer Ausnahme der Destruktor ausgeführt wird.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Cancel-Methode](#cancel)|Wird versucht, die Teilstruktur der Arbeit als Stammknoten diese Aufgabengruppe abzubrechen. Jede in der Aufgabengruppe geplante Aufgabe wird transitiv abgebrochen, wenn möglich.|  
|[Is_canceling-Methode](#is_canceling)|Informiert den Aufrufer, ob die Aufgabengruppe derzeit in ein Abbruch ist. Dies bedeutet nicht unbedingt, die die `cancel` Methode wurde aufgerufen, auf die `task_group` Objekt (Obwohl z. B. diese Methode zurückgibt sicherlich qualifiziert `true`). Es kann der Fall sein, die die `task_group` -Objekt Inline ausführt und eine Aufgabengruppe weiter oben in der Arbeitsstruktur wurde abgebrochen. In Fällen wie diesen, in denen die Laufzeit vorzeitig Abbruch durch diesen Fluss bestimmen kann `task_group` Objekt `true` wird ebenfalls zurückgegeben werden.|  
|[Run-Methode](#run)|Überladen. Plant eine Aufgabe für die `task_group` Objekt. Wenn ein `task_handle` Objekt als Parameter übergeben `run`, der Aufrufer ist verantwortlich für die Verwaltung der Lebensdauer der `task_handle` Objekt. Die Version der Methode, die einen Verweis auf ein Funktionsobjekt akzeptiert, wie ein Parameter Heapbelegung in der Laufzeit umfasst die möglicherweise weniger gut als die Version, die einen Verweis auf akzeptiert führen eine `task_handle` Objekt. Die Version, die den Parameter akzeptiert `_Placement` bewirkt, dass der Task Blockcontainer ausführen an der Position, die durch diesen Parameter angegeben werden.|  
|[Run_and_wait-Methode](#run_and_wait)|Überladen. Plant eine Aufgabe Inline auf dem aufrufenden Kontext ausgeführt werden, mit Unterstützung der `task_group` -Objekt für vollständige Abbruch-Unterstützung. Die Funktion wartet dann, bis die gesamte Arbeit der `task_group` Objekt abgeschlossen oder abgebrochen wurde. Wenn ein `task_handle` Objekt als Parameter übergeben `run_and_wait`, der Aufrufer ist verantwortlich für die Verwaltung der Lebensdauer der `task_handle` Objekt.|  
|[Wait-Methode](#wait)|Wartet, bis die gesamte Arbeit der `task_group` Objekt abgeschlossen oder abgebrochen wurde.|  
  
## <a name="remarks"></a>Hinweise  
 Im Gegensatz zu stark eingeschränktes `structured_task_group` -Klasse, die `task_group` Klasse ist viel allgemeineres Konstrukt. Er verfügt über keine der beschriebenen Einschränkungen [Structured_task_group](structured-task-group-class.md). `task_group`Objekte können problemlos threadübergreifend verwendet und in frei genutzt. Den Nachteil, dass die `task_group` Konstrukt ist, dass es nicht als auch die `structured_task_group` für Aufgaben, die kleine Mengen an Arbeit ausführen zu erstellen.  
  
 Weitere Informationen finden Sie unter [Aufgabenparallelität](../task-parallelism-concurrency-runtime.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `task_group`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** ppl.h  
  
 **Namespace:** Parallelität  
  
##  <a name="a-namecancela-cancel"></a><a name="cancel"></a>Abbrechen 

 Wird versucht, die Teilstruktur der Arbeit als Stammknoten diese Aufgabengruppe abzubrechen. Jede in der Aufgabengruppe geplante Aufgabe wird transitiv abgebrochen, wenn möglich.  
  
```  
void cancel();  
```  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Abbruch](../cancellation-in-the-ppl.md).  
  
##  <a name="a-nameiscancelinga-iscanceling"></a><a name="is_canceling"></a>is_canceling 

 Informiert den Aufrufer, ob die Aufgabengruppe derzeit in ein Abbruch ist. Dies bedeutet nicht unbedingt, die die `cancel` Methode wurde aufgerufen, auf die `task_group` Objekt (Obwohl z. B. diese Methode zurückgibt sicherlich qualifiziert `true`). Es kann der Fall sein, die die `task_group` -Objekt Inline ausführt und eine Aufgabengruppe weiter oben in der Arbeitsstruktur wurde abgebrochen. In Fällen wie diesen, in denen die Laufzeit vorzeitig Abbruch durch diesen Fluss bestimmen kann `task_group` Objekt `true` wird ebenfalls zurückgegeben werden.  
  
```  
bool is_canceling();  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Angabe, ob die `task_group` Objekt in ein Abbruch ist (oder in Kürze garantiert).  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Abbruch](../cancellation-in-the-ppl.md).  
  
##  <a name="a-nameruna-run"></a><a name="run"></a>Ausführen 

 Plant eine Aufgabe für die `task_group` Objekt. Wenn ein `task_handle` Objekt als Parameter übergeben `run`, der Aufrufer ist verantwortlich für die Verwaltung der Lebensdauer der `task_handle` Objekt. Die Version der Methode, die einen Verweis auf ein Funktionsobjekt akzeptiert, wie ein Parameter Heapbelegung in der Laufzeit umfasst die möglicherweise weniger gut als die Version, die einen Verweis auf akzeptiert führen eine `task_handle` Objekt. Die Version, die den Parameter akzeptiert `_Placement` bewirkt, dass der Task Blockcontainer ausführen an der Position, die durch diesen Parameter angegeben werden.  
  
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
 Der Typ des Funktionsobjekts, das aufgerufen wird, um den Text des Aufgabenhandles auszuführen.  
  
 `_Func`  
 Eine Funktion, die aufgerufen wird, um den Text der Aufgabe aufzurufen. Möglicherweise wird ein Lambda-Ausdruck oder anderes Objekt, das eine Version des Funktionsaufrufoperators mit der Signatur unterstützt `void operator()()`.  
  
 `_Placement`  
 Ein Verweis auf den Speicherort, in dem die Aufgabe, durch dargestellt, den `_Func` -Parameter sollte ausgeführt werden.  
  
 `_Task_handle`  
 Ein Handle für die Arbeit. Beachten Sie, dass der Aufrufer die Verantwortung für die Lebensdauer dieses Objekts hat. Die Laufzeit erwartet weiterhin, es erst dann aktiv die `wait` oder `run_and_wait` für diese Methode aufgerufen wurde `task_group` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die Runtime plant die bereitgestellte Arbeitsfunktion zu einem späteren Zeitpunkt ausgeführt werden kann, nachdem die aufrufende Funktion zurückgegeben. Diese Methode verwendet einen [Task_handle](task-handle-class.md) Objekt, das eine Kopie der bereitgestellten Arbeitsfunktion verfügen. Zustandsänderungen, die in ein Funktionsobjekt auftreten, die Sie an diese Methode übergeben, werden daher nicht in der Kopie dieses Funktionsobjekts angezeigt. Stellen Sie außerdem sicher, dass die Lebensdauer der Objekte, die Sie per Zeiger oder Verweis auf die Arbeitsfunktion übergeben, gültig bleiben, bis die Arbeitsfunktion zurückgibt.  
  
 Wenn die `task_group` Destructs als Ergebnis der Stapel entladen aus einer Ausnahme, Sie müssen nicht garantieren, dass ein Aufruf entweder wurde der `wait` oder `run_and_wait` Methode. In diesem Fall der Destruktor wird entsprechend Abbrechen und warten, bis die Aufgabe darstellt, durch die `_Task_handle` Parameter abgeschlossen.  
  
 Löst die Methode eine [Invalid_multiple_scheduling](invalid-multiple-scheduling-class.md) -Ausnahme aus, wenn der Task behandeln vom der `_Task_handle` Parameter wurde ein Aufgabengruppenobjekt über bereits geplant der `run` Methode und es keinen zwischenzeitlichen Aufruf der `wait` oder `run_and_wait` -Methode für diese Aufgabengruppe.  
  
##  <a name="a-namerunandwaita-runandwait"></a><a name="run_and_wait"></a>run_and_wait 

 Plant eine Aufgabe Inline auf dem aufrufenden Kontext ausgeführt werden, mit Unterstützung der `task_group` -Objekt für vollständige Abbruch-Unterstützung. Die Funktion wartet dann, bis die gesamte Arbeit der `task_group` Objekt abgeschlossen oder abgebrochen wurde. Wenn ein `task_handle` Objekt als Parameter übergeben `run_and_wait`, der Aufrufer ist verantwortlich für die Verwaltung der Lebensdauer der `task_handle` Objekt.  
  
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
 Der Typ des Funktionsobjekts, das aufgerufen wird, um den Text der Aufgabe ausführen.  
  
 `_Task_handle`  
 Ein Handle für die Aufgabe, die Inline auf dem aufrufenden Kontext ausgeführt wird. Beachten Sie, dass der Aufrufer die Verantwortung für die Lebensdauer dieses Objekts hat. Die Laufzeit erwartet weiterhin, es erst aktiv die `run_and_wait` -Methode die Ausführung beendet.  
  
 `_Func`  
 Eine Funktion, die aufgerufen wird, um den Text der Arbeit aufzurufen. Möglicherweise wird ein Lambda-Ausdruck oder anderes Objekt, das eine Version des Funktionsaufrufoperators mit der Signatur unterstützt `void operator()()`.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Hinweis darauf, ob der Wartevorgang erfüllt wurde oder die Aufgabengruppe, aufgrund eines expliziten Abbruchvorgangs oder eine Ausnahme ausgelöst wird, eine der Aufgaben abgebrochen. Weitere Informationen finden Sie unter [Task_group_status](concurrency-namespace-enums.md#task_group_status).  

  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass eine oder mehrere dieser geplante Aufgaben `task_group` Objekt möglicherweise Inline auf dem aufrufenden Kontext ausgeführt.  
  
 Wenn eine oder mehrere dieser geplante Aufgaben `task_group` -Objekt löst eine Ausnahme aus der Common Language Runtime wird, wählen Sie eine dieser Ausnahmen von der Auswahl und gibt sie aus dem Aufruf von der `run_and_wait` Methode.  
  
 Bei der Rückgabe aus der `run_and_wait` -Methode für ein `task_group` -Objekt, die Laufzeit setzt das Objekt auf einen fehlerfreien Zustand, in dem es wiederverwendet werden kann. Dies umfasst auch den Fall, in dem die `task_group` -Objekt wurde abgebrochen.  
  
 In ohne Ausnahmen Ausführungspfad, haben Sie die Pflicht, entweder diese Methode aufzurufen oder `wait` -Methode auf, bevor der Destruktor der `task_group` ausgeführt wird.  
  
##  <a name="a-namectora-taskgroup"></a><a name="ctor"></a>task_group 

 Erstellt ein neues `task_group`-Objekt.  
  
```  
task_group();  
  
task_group(  
   cancellation_token _CancellationToken  
);  
```  
  
### <a name="parameters"></a>Parameter  
 `_CancellationToken`  
 Ein Abbruchtoken, diese Aufgabengruppe zugeordnet werden soll. Wenn das Token abgebrochen wird, wird die Aufgabengruppe abgebrochen.  
  
### <a name="remarks"></a>Hinweise  
 Der Konstruktor, der ein Abbruchtoken akzeptiert erstellt eine `task_group` , wenn die Quelle des Tokens abgebrochen wird abgebrochen. Als explizites Abbruchtoken bereitstellen, werden auch diese Aufgabengruppe aus der Einbeziehung in einen impliziten Abbruch der übergeordneten Gruppe mit einem anderen Token oder kein Token isoliert.  
  
##  <a name="a-namedtora-taskgroup"></a><a name="dtor"></a>~ Task_group 

 Zerstört ein `task_group`-Objekt. Ihnen wird erwartet, rufen Sie entweder die `wait` oder `run_and_wait` Methode für das Objekt vor der Destruktor ausgeführt, es sei denn, das Ergebnis der stapelentladung aufgrund einer Ausnahme der Destruktor ausgeführt wird.  
  
```  
~task_group();  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Destruktor ausgeführt wird, als Ergebnis einer normalen Ausführung (z. B. keine stapelentladung aufgrund einer Ausnahme) und weder die `wait` noch `run_and_wait` Methoden aufgerufen wurden, kann der Destruktor Auslösen einer [Missing_wait](missing-wait-class.md) Ausnahme.  
  
##  <a name="a-namewaita-wait"></a><a name="wait"></a>Warte 

 Wartet, bis die gesamte Arbeit der `task_group` Objekt abgeschlossen oder abgebrochen wurde.  
  
```  
task_group_status wait();  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Hinweis darauf, ob der Wartevorgang erfüllt wurde oder die Aufgabengruppe, aufgrund eines expliziten Abbruchvorgangs oder eine Ausnahme ausgelöst wird, eine der Aufgaben abgebrochen. Weitere Informationen finden Sie unter [Task_group_status](concurrency-namespace-enums.md#task_group_status).  

  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass eine oder mehrere dieser geplante Aufgaben `task_group` Objekt möglicherweise Inline auf dem aufrufenden Kontext ausgeführt.  
  
 Wenn eine oder mehrere dieser geplante Aufgaben `task_group` -Objekt löst eine Ausnahme aus der Common Language Runtime wird, wählen Sie eine dieser Ausnahmen von der Auswahl und gibt sie aus dem Aufruf von der `wait` Methode.  
  
 Aufrufen von `wait` auf ein `task_group` -Objekt setzt es zurück in einen sauberen Zustand, in dem es wiederverwendet werden kann. Dies umfasst auch den Fall, in dem die `task_group` -Objekt wurde abgebrochen.  
  
 In ohne Ausnahmen Ausführungspfad, haben Sie die Pflicht, entweder diese Methode aufzurufen oder `run_and_wait` -Methode auf, bevor der Destruktor der `task_group` ausgeführt wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Structured_task_group-Klasse](structured-task-group-class.md)   
 [Task_handle-Klasse](task-handle-class.md)