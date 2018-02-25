---
title: Task_completion_event-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- task_completion_event
- PPLTASKS/concurrency::task_completion_event
- PPLTASKS/concurrency::task_completion_event::task_completion_event
- PPLTASKS/concurrency::task_completion_event::set
- PPLTASKS/concurrency::task_completion_event::set_exception
dev_langs:
- C++
helpviewer_keywords:
- task_completion_event class
ms.assetid: fb19ed98-f245-48dc-9ba5-487ba879b28a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2ec810fdb897a9a80dc803cdcc3f229bab186f09
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="taskcompletionevent-class"></a>task_completion_event-Klasse
Mit der `task_completion_event`-Klasse können Sie die Ausführung einer Aufgabe verzögern, bis eine Bedingung erfüllt ist, oder eine Aufgabe als Reaktion auf ein externes Ereignis starten.  
  
## <a name="syntax"></a>Syntax  
  
```
template<typename _ResultType>
class task_completion_event;

template<>
class task_completion_event<void>;
```  
  
#### <a name="parameters"></a>Parameter  
 `_ResultType`  
 Der Ergebnistyp dieser `task_completion_event`-Klasse.  
  
 `T`  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[task_completion_event](#ctor)|Erstellt ein `task_completion_event`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[set](#set)|Überladen. Legt das Aufgabenabschlussereignis fest.|  
|[set_exception](#set_exception)|Überladen. Gibt eine Ausnahme an alle Aufgaben weiter, die dem Ereignis zugeordnet sind.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie eine Aufgabe, die aus einem Aufgabenabschlussereignis erstellt wird, wenn Ihr Szenario die Erstellung einer Aufgabe erfordert, die abgeschlossen wird, und planen Sie die Ausführung ihrer Fortsetzungen für einen späteren Zeitpunkt. `task_completion_event` muss den gleichen Typ haben, wie die Aufgabe, die Sie erstellen, und das Aufrufen der set-Methode für das Aufgabenabschlussereignis mit einem Wert dieses Typs führt zu einem Abschluss der zugeordneten Aufgabe und liefert diesen Wert als Ergebnis ihrer Fortsetzungen.  
  
 Wenn das Aufgabenabschlussereignis kein Signal erhält, werden alle Aufgaben, die daraus erstellt wurden, abgebrochen, wenn es zerstört wird.  
  
 `task_completion_event` verhält sich wie ein intelligenter Zeiger und sollte von einem Wert übergeben werden.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `task_completion_event`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** ppltasks.h  
  
 **Namespace:** Parallelität  
  
##  <a name="set"></a> set 

 Legt das Aufgabenabschlussereignis fest.  
  
```
bool set(_ResultType _Result) const ;

bool set() const ;
```  
  
### <a name="parameters"></a>Parameter  
 `_Result`  
 Das Ergebnis, das für dieses Ereignis festgelegt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Methode gibt `true` zurück, wenn die Festlegung des Ereignisses erfolgreich war. Sie gibt `false` zurück, wenn das Ereignis bereits festgelegt ist.  
  
### <a name="remarks"></a>Hinweise  
 Bei mehrfachen oder gleichzeitigen Aufrufen von `set` ist nur der erste Aufruf erfolgreich, und sein Ergebnis (falls vorhanden) wird im Aufgabenabschlussereignis gespeichert. Die verbleibenden Sätze werden ignoriert, und die Methode gibt "false" zurück. Wenn Sie ein Aufgabenabschlussereignis festlegen, werden alle Aufgaben, die aus diesem Ereignis erstellt wurden, abgeschlossen, und ihre Fortsetzungen, falls vorhanden, werden geplant. Aufgabenabschlussobjekte, die über eine `_ResultType` außer `void` übergeben den Wert an ihre Fortsetzungen.  
  
##  <a name="set_exception"></a> set_exception 

 Gibt eine Ausnahme an alle Aufgaben weiter, die dem Ereignis zugeordnet sind.  
  
```
template<typename _E>
__declspec(noinline) bool set_exception(_E _Except) const;

__declspec(noinline) bool set_exception(std::exception_ptr _ExceptionPtr) const ;
```  
  
### <a name="parameters"></a>Parameter  
 `_E`  
 `_Except`  
 `_ExceptionPtr`  
  
### <a name="return-value"></a>Rückgabewert  
  
##  <a name="ctor"></a> task_completion_event 

 Erstellt ein `task_completion_event`-Objekt.  
  
```
task_completion_event();
```  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)
