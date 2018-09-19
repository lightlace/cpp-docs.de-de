---
title: Missing_wait-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- missing_wait
- CONCRT/concurrency::missing_wait
- CONCRT/concurrency::missing_wait::missing_wait
dev_langs:
- C++
helpviewer_keywords:
- missing_wait class
ms.assetid: ff981875-bd43-47e3-806f-b03c9f418b18
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a2a44cbdb5abeed7d5dbd7be7dfaba37ba1d0145
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46024948"
---
# <a name="missingwait-class"></a>missing_wait-Klasse
Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn es Aufgaben gibt, die noch für ein `task_group`-Objekt oder `structured_task_group`-Objekt geplant sind, während der Destruktor des Objekts ausgeführt wird. Diese Ausnahme wird nie ausgelöst, wenn der Destruktor aufgrund einer Stapelentladung als Ergebnis einer Ausnahme erreicht wird.  
  
## <a name="syntax"></a>Syntax  
  
```
class missing_wait : public std::exception;
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[missing_wait](#ctor)|Überladen. Erstellt ein `missing_wait`-Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Fehlende ausnahmeverlaufs, Sie sind verantwortlich für das Aufrufen von entweder die `wait` oder `run_and_wait` Methode eine `task_group` oder `structured_task_group` Objekt vor, dass dieses Objekt zerstört. Löst die Runtime diese Ausnahme als Hinweis auf, die Sie vergessen haben, rufen Sie die `wait` oder `run_and_wait` Methode.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `exception`  
  
 `missing_wait`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu  
  
 **Namespace:** Parallelität  
  
##  <a name="ctor"></a> missing_wait 

 Erstellt ein `missing_wait`-Objekt.  
  
```
explicit _CRTIMP missing_wait(_In_z_ const char* _Message) throw();

missing_wait() throw();
```  
  
### <a name="parameters"></a>Parameter  
*_Nachricht*<br/>
Eine beschreibende Fehlermeldung.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Task_group-Klasse](task-group-class.md)   
 [wait](task-group-class.md)   
 [run_and_wait](task-group-class.md)   
 [structured_task_group-Klasse](structured-task-group-class.md)
