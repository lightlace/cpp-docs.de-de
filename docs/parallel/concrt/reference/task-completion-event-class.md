---
title: Task_completion_event-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ppltasks/concurrency::task_completion_event
dev_langs:
- C++
helpviewer_keywords:
- task_completion_event class
ms.assetid: fb19ed98-f245-48dc-9ba5-487ba879b28a
caps.latest.revision: 11
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 2cd3e7381402cc65f3220010a71c969cda1c7e2d
ms.lasthandoff: 02/24/2017

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
|[Task_completion_event-Konstruktor](#ctor)|Erstellt ein `task_completion_event`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Set-Methode](#set)|Überladen. Legt das Aufgabenabschlussereignis fest.|  
|[Set_exception-Methode](#set_exception)|Überladen. Gibt eine Ausnahme an alle Aufgaben weiter, die dem Ereignis zugeordnet sind.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie eine Aufgabe, die aus einem Aufgabenabschlussereignis erstellt wird, wenn Ihr Szenario die Erstellung einer Aufgabe erfordert, die abgeschlossen wird, und planen Sie die Ausführung ihrer Fortsetzungen für einen späteren Zeitpunkt. `task_completion_event` muss den gleichen Typ haben, wie die Aufgabe, die Sie erstellen, und das Aufrufen der set-Methode für das Aufgabenabschlussereignis mit einem Wert dieses Typs führt zu einem Abschluss der zugeordneten Aufgabe und liefert diesen Wert als Ergebnis ihrer Fortsetzungen.  
  
 Wenn das Aufgabenabschlussereignis kein Signal erhält, werden alle Aufgaben, die daraus erstellt wurden, abgebrochen, wenn es zerstört wird.  
  
 `task_completion_event` verhält sich wie ein intelligenter Zeiger und sollte von einem Wert übergeben werden.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `task_completion_event`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** ppltasks.h  
  
 **Namespace:** Parallelität  
  
##  <a name="a-nameseta-set"></a><a name="set"></a>Festlegen 

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
 Bei mehrfachen oder gleichzeitigen Aufrufen von `set` ist nur der erste Aufruf erfolgreich, und sein Ergebnis (falls vorhanden) wird im Aufgabenabschlussereignis gespeichert. Die verbleibenden Sätze werden ignoriert, und die Methode gibt "false" zurück. Wenn Sie ein Aufgabenabschlussereignis festlegen, werden alle Aufgaben, die aus diesem Ereignis erstellt wurden, abgeschlossen, und ihre Fortsetzungen, falls vorhanden, werden geplant. Aufgabenabschlussobjekte, die über eine `_ResultType` als `void` übergeben den Wert an ihre Fortsetzungen.  
  
##  <a name="a-namesetexceptiona-setexception"></a><a name="set_exception"></a>set_exception 

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
  
##  <a name="a-namectora-taskcompletionevent"></a><a name="ctor"></a>task_completion_event 

 Erstellt ein `task_completion_event`-Objekt.  
  
```
task_completion_event();
```  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)

