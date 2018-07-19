---
title: Nested_scheduler_missing_detach-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- nested_scheduler_missing_detach
- CONCRT/concurrency::nested_scheduler_missing_detach
- CONCRT/concurrency::nested_scheduler_missing_detach::nested_scheduler_missing_detach
dev_langs:
- C++
helpviewer_keywords:
- nested_scheduler_missing_detach class
ms.assetid: 65d3f277-6d43-4160-97ef-caf8b26c1641
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 26027693209bc5b4687686efeae5d190ed374607
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33687360"
---
# <a name="nestedschedulermissingdetach-class"></a>nested_scheduler_missing_detach-Klasse
Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn die Concurrency Runtime erkennt, dass versäumt wurde, die `CurrentScheduler::Detach`-Methode für einen Kontext aufzurufen, der mittels der `Attach`-Methode des `Scheduler`-Objekts an einen zweiten Planer angefügt wurde.  
  
## <a name="syntax"></a>Syntax  
  
```
class nested_scheduler_missing_detach : public std::exception;
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[nested_scheduler_missing_detach](#ctor)|Überladen. Erstellt ein `nested_scheduler_missing_detach`-Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Ausnahme wird ausgelöst, nur, wenn Sie einen Planer in einem anderen schachteln, die sich durch Aufrufen der `Attach` Methode eine `Scheduler` Objekt in einem Kontext, der bereits im Besitz von oder an ein anderes Zeitplanungsmodul angefügt ist. Die Concurrency Runtime löst diese Ausnahme opportunistische Ausführung ein, wenn das Szenario als Hilfe beim Auffinden des Problems erkannt werden können. Nicht jede Instanz des aufzurufenden versäumt die `CurrentScheduler::Detach` Methode wird sichergestellt, dass diese Ausnahme ausgelöst werden soll.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `exception`  
  
 `nested_scheduler_missing_detach`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu  
  
 **Namespace:** Parallelität  
  
##  <a name="ctor"></a> nested_scheduler_missing_detach 

 Erstellt ein `nested_scheduler_missing_detach`-Objekt.  
  
```
explicit _CRTIMP nested_scheduler_missing_detach(_In_z_ const char* _Message) throw();

nested_scheduler_missing_detach() throw();
```  
  
### <a name="parameters"></a>Parameter  
 `_Message`  
 Eine beschreibende Fehlermeldung.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Scheduler-Klasse](scheduler-class.md)
