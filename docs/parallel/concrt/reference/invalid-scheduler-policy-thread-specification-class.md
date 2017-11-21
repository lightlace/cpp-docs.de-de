---
title: Invalid_scheduler_policy_thread_specification-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: concrt/concurrency::invalid_scheduler_policy_thread_specification
dev_langs: C++
helpviewer_keywords: invalid_scheduler_policy_thread_specification class
ms.assetid: 2d0fafb2-18f8-4284-8040-3db640d33303
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 267f8fef7aa376105d7dfcaf4ac995a9fd272a7f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="invalidschedulerpolicythreadspecification-class"></a>invalid_scheduler_policy_thread_specification-Klasse
Diese Klasse beschreibt eine Ausnahme, die bei dem Versuch ausgelöst wird, die Parallelitätsgrenzen eines `SchedulerPolicy`-Objekts so festzulegen, dass der Wert des `MinConcurrency`-Schlüssels kleiner ist, als der Wert des `MaxConcurrency`-Schlüssels.  
  
## <a name="syntax"></a>Syntax  
  
```
class invalid_scheduler_policy_thread_specification : public std::exception;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Invalid_scheduler_policy_thread_specification] (Ungültiger-Scheduler-Policy-Wert-class.md #ctor|Überladen. Erstellt ein `invalid_scheduler_policy_value`-Objekt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `exception`  
  
 `invalid_scheduler_policy_thread_specification`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu  
  
 **Namespace:** Parallelität  
##  <a name="ctor"></a>invalid_scheduler_policy_thread_specification 

 Erstellt ein `invalid_scheduler_policy_value`-Objekt.  
  
```
explicit _CRTIMP invalid_scheduler_policy_thread_specification(_In_z_ const char* _Message) throw();

invalid_scheduler_policy_thread_specification() throw();
```  
  
### <a name="parameters"></a>Parameter  
 `_Message`  
 Eine beschreibende Fehlermeldung.  

## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [SchedulerPolicy-Klasse](schedulerpolicy-class.md)
