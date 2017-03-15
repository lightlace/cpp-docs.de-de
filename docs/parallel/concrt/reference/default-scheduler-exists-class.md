---
title: Default_scheduler_exists-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::default_scheduler_exists
dev_langs:
- C++
helpviewer_keywords:
- default_scheduler_exists class
ms.assetid: f6e575e2-4e0f-455a-9e06-54f462ce0c1c
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 527d02e6b79d86c8a194fffa30351efc944db441
ms.lasthandoff: 02/24/2017

---
# <a name="defaultschedulerexists-class"></a>default_scheduler_exists-Klasse
Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, sobald die `Scheduler::SetDefaultSchedulerPolicy`-Methode aufgerufen wird, sofern ein Standardplaner bereits innerhalb des Prozesses vorhanden ist.  
  
## <a name="syntax"></a>Syntax  
  
```
class default_scheduler_exists : public std::exception;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Default_scheduler_exists-Konstruktor](#ctor)|Überladen. Erstellt ein `default_scheduler_exists`-Objekt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `exception`  
  
 `default_scheduler_exists`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu  
  
 **Namespace:** Parallelität  
  
##  <a name="a-namectora-defaultschedulerexists"></a><a name="ctor"></a>default_scheduler_exists 

 Erstellt ein `default_scheduler_exists`-Objekt.  
  
```
explicit _CRTIMP default_scheduler_exists(_In_z_ const char* _Message) throw();

default_scheduler_exists() throw();
```  
  
### <a name="parameters"></a>Parameter  
 `_Message`  
 Eine beschreibende Fehlermeldung.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)

