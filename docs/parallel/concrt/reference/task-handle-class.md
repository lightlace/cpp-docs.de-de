---
title: Task_handle-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- task_handle
- PPL/concurrency::task_handle
- PPL/concurrency::task_handle::task_handle
dev_langs:
- C++
helpviewer_keywords:
- task_handle class
ms.assetid: 74a34b15-708b-4231-a509-947874292b13
caps.latest.revision: 23
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 0fef1ef7b1c02287a0113eb80be413e4a17dc1a4
ms.contentlocale: de-de
ms.lasthandoff: 03/17/2017

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
 Der Typ des Funktionsobjekts, das aufgerufen wird, um die Arbeit durch Ausführen der `task_handle` Objekt.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[task_handle](#ctor)|Erstellt ein neues `task_handle`-Objekt. Die Arbeit der Aufgabe wird ausgeführt, durch den Aufruf der Funktion, die als Parameter an den Konstruktor angegeben.|  
|[~ Task_handle-Destruktor](#dtor)|Zerstört das `task_handle`-Objekt.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Operator()](#task_handle__operator_call)|Der Funktionsaufrufoperator, den von der Laufzeit aufgerufen, um die Arbeit des Aufgabenhandles auszuführen.|  
  
## <a name="remarks"></a>Hinweise  
 `task_handle`Objekte können verwendet werden, zusammen mit einem `structured_task_group` oder eine allgemeinere `task_group` -Objekt, um die Arbeit in Parallele Aufgaben aufzuteilen. Weitere Informationen finden Sie unter [Aufgabenparallelität](../../../parallel/concrt/task-parallelism-concurrency-runtime.md).  
  
 Beachten Sie, dass der Ersteller einer `task_handle` -Objekt ist verantwortlich für das Verwalten der Lebensdauer des erstellten `task_handle` Objekt, bis sie nicht mehr von der Concurrency Runtime benötigt wird. In der Regel bedeutet dies, dass die `task_handle` Objekt erst zerstört werden darf, bis entweder der `wait` oder `run_and_wait` Methode der `task_group` oder `structured_task_group` , die in die Warteschlange aufgenommen wird aufgerufen wurde.  
  
 `task_handle`Objekte werden in der Regel in Verbindung mit C++-Lambdas verwendet. Da Sie nicht, dass den tatsächliche Typ des Lambda-Ausdrucks wissen, der [Make_task](concurrency-namespace-functions.md#make_task) Funktion wird in der Regel zum Erstellen einer `task_handle` Objekt.  
  
 Die Common Language Runtime erstellt eine Kopie der Arbeitsfunktion, die Sie übergeben ein `task_handle` Objekt. Übergeben Sie daher alle Zustandsänderungen, die in einer Funktion auftreten Objekt ein `task_handle` Objekt wird nicht in der Kopie dieses Funktionsobjekts angezeigt.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `task_handle`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** ppl.h  
  
 **Namespace:** Parallelität  
  
##  <a name="task_handle__operator_call"></a>Operator() 

 Der Funktionsaufrufoperator, den von der Laufzeit aufgerufen, um die Arbeit des Aufgabenhandles auszuführen.  
  
```  
void operator()() const;

 
```  
  
##  <a name="task_handle__ctor"></a>task_handle 

 Erstellt ein neues `task_handle`-Objekt. Die Arbeit der Aufgabe wird ausgeführt, durch den Aufruf der Funktion, die als Parameter an den Konstruktor angegeben.  
  
```  
task_handle(const _Function& _Func);
```  
  
### <a name="parameters"></a>Parameter  
 `_Func`  
 Die Funktion, die aufgerufen wird, um die Arbeit durch Ausführen der `task_handle` Objekt. Dies ist möglicherweise eine Lambda-Funktion, ein Zeiger auf eine Funktion oder ein beliebiges Objekt, das eine Version des Funktionsaufrufoperators mit der Signatur unterstützt `void operator()()`.  
  
### <a name="remarks"></a>Hinweise  
 Die Common Language Runtime erstellt eine Kopie der Arbeitsfunktion, die an den Konstruktor übergeben. Übergeben Sie daher alle Zustandsänderungen, die in einer Funktion auftreten Objekt ein `task_handle` Objekt wird nicht in der Kopie dieses Funktionsobjekts angezeigt.  
  
##  <a name="dtor"></a>~ Task_handle 

 Zerstört das `task_handle`-Objekt.  
  
```  
~task_handle();
```  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Task_group-Klasse](task-group-class.md)   
 [structured_task_group-Klasse](structured-task-group-class.md)

