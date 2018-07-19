---
title: Task_handle-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- task_handle
- PPL/concurrency::task_handle
- PPL/concurrency::task_handle::task_handle
dev_langs:
- C++
helpviewer_keywords:
- task_handle class
ms.assetid: 74a34b15-708b-4231-a509-947874292b13
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3fa72ed19a691015214fe263033e07f8d6a74c34
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33688205"
---
# <a name="taskhandle-class"></a>task_handle-Klasse
Die `task_handle`-Klasse stellt eine einzelne parallele Arbeitsaufgabe dar. Sie kapselt die Anweisungen und die zum Ausführen eines Teils der Arbeit erforderlichen Daten.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<
    typename _Function  
>  
class task_handle : public ::Concurrency::details::_UnrealizedChore;  
```  
  
#### <a name="parameters"></a>Parameter  
 `_Function`  
 Der Typ des Funktionsobjekts ab, das aufgerufen wird, um die Arbeit, dargestellt durch Ausführen der `task_handle` Objekt.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[task_handle](#ctor)|Erstellt ein neues `task_handle`-Objekt. Die Aktionen der Aufgabe wird ausgeführt, durch den Aufruf der Funktion, die als Parameter an den Konstruktor angegeben.|  
|[~ Task_handle-Destruktor](#dtor)|Zerstört das `task_handle`-Objekt.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[operator()](#task_handle__operator_call)|Der Funktionsaufrufoperator, den von der Laufzeit, zum Ausführen der Aktionen des Task-Handle aufgerufen.|  
  
## <a name="remarks"></a>Hinweise  
 `task_handle` Objekte können verwendet werden, zusammen mit einem `structured_task_group` oder ein allgemeinerer `task_group` -Objekt, um die Arbeit in Parallele Aufgaben aufzuteilen. Weitere Informationen finden Sie unter [Aufgabenparallelität](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
 Beachten Sie, dass der Ersteller des eine `task_handle` -Objekt ist verantwortlich für das Verwalten der Lebensdauer des erstellten `task_handle` Objekt, bis er von der Concurrency Runtime nicht mehr erforderlich ist. In der Regel bedeutet dies, dass die `task_handle` Objekt nicht zerstört werden darf, bis entweder der `wait` oder `run_and_wait` Methode der `task_group` oder `structured_task_group` , die es in die Warteschlange eingereiht wird aufgerufen wurde.  
  
 `task_handle` Objekte werden in der Regel in Verbindung mit C++-Lambda-Ausdrücke verwendet. Da Sie nicht, dass den tatsächliche Typ des Lambda-Ausdrucks wissen, der [Make_task](concurrency-namespace-functions.md#make_task) Funktion dient gewöhnlich zum Erstellen einer `task_handle` Objekt.  
  
 Die Common Language Runtime erstellt eine Kopie der Arbeitsfunktion, die Sie zum Übergeben einer `task_handle` Objekt. Aus diesem Grund alle Zustandsänderungen, die in einer Funktion auftreten-Objekt, wenn Sie zum Übergeben einer `task_handle` Objekt wird nicht in Ihrer Kopie des Funktionsobjekts angezeigt.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `task_handle`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** ppl.h  
  
 **Namespace:** Parallelität  
  
##  <a name="task_handle__operator_call"></a> Operator() 

 Der Funktionsaufrufoperator, den von der Laufzeit, zum Ausführen der Aktionen des Task-Handle aufgerufen.  
  
```  
void operator()() const;

 
```  
  
##  <a name="task_handle__ctor"></a> task_handle 

 Erstellt ein neues `task_handle`-Objekt. Die Aktionen der Aufgabe wird ausgeführt, durch den Aufruf der Funktion, die als Parameter an den Konstruktor angegeben.  
  
```  
task_handle(const _Function& _Func);
```  
  
### <a name="parameters"></a>Parameter  
 `_Func`  
 Die Funktion, die aufgerufen wird, um die Arbeit, dargestellt durch Ausführen der `task_handle` Objekt. Dies ist möglicherweise eine Lambda-Funktion, ein Zeiger auf eine Funktion oder ein anderes Objekt, das eine Version von den Funktionsaufrufoperator mit der Signatur unterstützt `void operator()()`.  
  
### <a name="remarks"></a>Hinweise  
 Die Common Language Runtime erstellt eine Kopie der Arbeitsfunktion, die Sie an den Konstruktor übergeben. Aus diesem Grund alle Zustandsänderungen, die in einer Funktion auftreten-Objekt, wenn Sie zum Übergeben einer `task_handle` Objekt wird nicht in Ihrer Kopie des Funktionsobjekts angezeigt.  
  
##  <a name="dtor"></a> ~ Task_handle 

 Zerstört das `task_handle`-Objekt.  
  
```  
~task_handle();
```  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Task_group-Klasse](task-group-class.md)   
 [structured_task_group-Klasse](structured-task-group-class.md)
