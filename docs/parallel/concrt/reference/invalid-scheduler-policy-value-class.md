---
title: Invalid_scheduler_policy_value-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: concrt/concurrency::invalid_scheduler_policy_value
dev_langs: C++
helpviewer_keywords: invalid_scheduler_policy_value class
ms.assetid: 8c533e3f-2774-4192-8616-b2313b859bf7
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 08ecdc6e63f5a95ab271a95b083d6c35c67eeffb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="invalidschedulerpolicyvalue-class"></a>invalid_scheduler_policy_value-Klasse
Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn der Richtlinienschlüssel eines `SchedulerPolicy`-Objekts auf einen ungültigen Wert für diesen Schlüssel festgelegt wird.  
  
## <a name="syntax"></a>Syntax  
  
```
class invalid_scheduler_policy_value : public std::exception;
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Invalid_scheduler_policy_value] (invalid-scheduler-policy-thread-specification-class.md#ctor|Überladen. Erstellt ein `invalid_scheduler_policy_value`-Objekt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `exception`  
  
 `invalid_scheduler_policy_value`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu  
  
 **Namespace:** Parallelität  
  
    
##  <a name="ctor"></a>invalid_scheduler_policy_value 

 Erstellt ein `invalid_scheduler_policy_value`-Objekt.  
  
```
explicit _CRTIMP invalid_scheduler_policy_value(_In_z_ const char* _Message) throw();

invalid_scheduler_policy_value() throw();
```  
  
### <a name="parameters"></a>Parameter  
 `_Message`  
 Eine beschreibende Fehlermeldung.  
  

## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [SchedulerPolicy-Klasse](schedulerpolicy-class.md)
