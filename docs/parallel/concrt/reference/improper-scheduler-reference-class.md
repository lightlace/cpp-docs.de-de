---
title: Improper_scheduler_reference-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::improper_scheduler_reference
dev_langs:
- C++
helpviewer_keywords:
- improper_scheduler_reference class
ms.assetid: 434a7512-7796-4255-92a7-f3bf71c6a7a7
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
ms.openlocfilehash: fef830b502f43473bc683fdcb246be526bfb6db8
ms.lasthandoff: 02/24/2017

---
# <a name="improperschedulerreference-class"></a>improper_scheduler_reference-Klasse
Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn die `Reference`-Methode für ein `Scheduler`-Objekt aufgerufen wird, das aus einem Kontext heruntergefahren wird, der nicht Teil dieses Planers ist.  
  
## <a name="syntax"></a>Syntax  
  
```
class improper_scheduler_reference : public std::exception;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Improper_scheduler_reference-Konstruktor](#ctor)|Überladen. Erstellt ein `improper_scheduler_reference`-Objekt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `exception`  
  
 `improper_scheduler_reference`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu  
  
 **Namespace:** Parallelität  
  
##  <a name="a-namectora-improperschedulerreference"></a><a name="ctor"></a>improper_scheduler_reference 

 Erstellt ein `improper_scheduler_reference`-Objekt.  
  
```
explicit _CRTIMP improper_scheduler_reference(_In_z_ const char* _Message) throw();

improper_scheduler_reference() throw();
```  
  
### <a name="parameters"></a>Parameter  
 `_Message`  
 Eine beschreibende Fehlermeldung.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Scheduler-Klasse](scheduler-class.md)

