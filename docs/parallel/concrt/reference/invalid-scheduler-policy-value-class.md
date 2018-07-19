---
title: Invalid_scheduler_policy_value-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- concrt/concurrency::invalid_scheduler_policy_value
dev_langs:
- C++
helpviewer_keywords:
- invalid_scheduler_policy_value class
ms.assetid: 8c533e3f-2774-4192-8616-b2313b859bf7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ec11d7ebc7d2c074344e9651a7c548fe1ad01943
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33689726"
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
  
    
##  <a name="ctor"></a> invalid_scheduler_policy_value 

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
