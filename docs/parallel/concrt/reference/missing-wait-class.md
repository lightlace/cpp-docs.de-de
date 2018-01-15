---
title: Missing_wait-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- missing_wait
- CONCRT/concurrency::missing_wait
- CONCRT/concurrency::missing_wait::missing_wait
dev_langs: C++
helpviewer_keywords: missing_wait class
ms.assetid: ff981875-bd43-47e3-806f-b03c9f418b18
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 952a2b88ebb91449341085a923e06d389aa10fe4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
 Fehlender ausnahmeverlaufs, Sie sind verantwortlich für das Aufrufen von entweder der `wait` oder `run_and_wait` Methode eine `task_group` oder `structured_task_group` Objekt vor dem und mit diesem Objekt zerstört. Löst die Runtime diese Ausnahme als eine Angabe über das Sie haben vergessen, rufen Sie die `wait` oder `run_and_wait` Methode.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `exception`  
  
 `missing_wait`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu  
  
 **Namespace:** Parallelität  
  
##  <a name="ctor"></a>missing_wait 

 Erstellt ein `missing_wait`-Objekt.  
  
```
explicit _CRTIMP missing_wait(_In_z_ const char* _Message) throw();

missing_wait() throw();
```  
  
### <a name="parameters"></a>Parameter  
 `_Message`  
 Eine beschreibende Fehlermeldung.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Task_group-Klasse](task-group-class.md)   
 [Warte](task-group-class.md)   
 [run_and_wait](task-group-class.md)   
 [structured_task_group-Klasse](structured-task-group-class.md)
