---
title: Nested_scheduler_missing_detach-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- nested_scheduler_missing_detach
- CONCRT/concurrency::nested_scheduler_missing_detach
- CONCRT/concurrency::nested_scheduler_missing_detach::nested_scheduler_missing_detach
dev_langs:
- C++
helpviewer_keywords:
- nested_scheduler_missing_detach class
ms.assetid: 65d3f277-6d43-4160-97ef-caf8b26c1641
caps.latest.revision: 19
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
ms.openlocfilehash: 7ab8dc3761c6f11529b70ec4d71bbaebdfea0493
ms.lasthandoff: 03/17/2017

---
# <a name="nestedschedulermissingdetach-class"></a>nested_scheduler_missing_detach-Klasse
Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn die Concurrency Runtime erkennt, dass versäumt wurde, die `CurrentScheduler::Detach`-Methode für einen Kontext aufzurufen, der mittels der `Attach`-Methode des `Scheduler`-Objekts an einen zweiten Planer angefügt wurde.  
  
## <a name="syntax"></a>Syntax  
  
```
class nested_scheduler_missing_detach : public std::exception;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[nested_scheduler_missing_detach](#ctor)|Überladen. Erstellt ein `nested_scheduler_missing_detach`-Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Ausnahme wird ausgelöst, nur, wenn Sie einen Planer in einem anderen, durch Aufrufen Schachteln der `Attach` Methode ein `Scheduler` Objekt in einem Kontext, der bereits im Besitz von oder an einen anderen Planer angefügt ist. Die Concurrency Runtime löst diese Ausnahme opportunistisch aus, wenn sie das Szenario als Hilfe beim Auffinden des Problems erkennen kann. Nicht jede Instanz fehlenden rufen Sie die `CurrentScheduler::Detach` Methode ist sichergestellt, dass diese Ausnahme auslöst.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `exception`  
  
 `nested_scheduler_missing_detach`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu  
  
 **Namespace:** Parallelität  
  
##  <a name="ctor"></a>nested_scheduler_missing_detach 

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

