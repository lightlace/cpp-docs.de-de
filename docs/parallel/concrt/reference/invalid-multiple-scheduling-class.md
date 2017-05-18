---
title: Invalid_multiple_scheduling-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- invalid_multiple_scheduling
- CONCRT/concurrency::invalid_multiple_scheduling
- CONCRT/concurrency::invalid_multiple_scheduling::invalid_multiple_scheduling
dev_langs:
- C++
helpviewer_keywords:
- invalid_multiple_scheduling class
ms.assetid: e9a47cb7-a778-4df7-92b0-3752119fd4c7
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 82f1046173ba1f2eebfc74e1121b01ba0ed46b04
ms.contentlocale: de-de
ms.lasthandoff: 03/17/2017

---
# <a name="invalidmultiplescheduling-class"></a>invalid_multiple_scheduling-Klasse
Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn ein `task_handle`-Objekt mehrmals mittels der `run`-Methode eines `task_group`-Objekts oder `structured_task_group`-Objekts ohne einen zwischenzeitlichen Aufruf der `wait`-Methode oder `run_and_wait`-Methode geplant wird.  
  
## <a name="syntax"></a>Syntax  
  
```
class invalid_multiple_scheduling : public std::exception;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[invalid_multiple_scheduling](#ctor)|Überladen. Erstellt ein `invalid_multiple_scheduling`-Objekt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `exception`  
  
 `invalid_multiple_scheduling`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu  
  
 **Namespace:** Parallelität  
  
##  <a name="ctor"></a>invalid_multiple_scheduling 

 Erstellt ein `invalid_multiple_scheduling`-Objekt.  
  
```
explicit _CRTIMP invalid_multiple_scheduling(_In_z_ const char* _Message) throw();

invalid_multiple_scheduling() throw();
```  
  
### <a name="parameters"></a>Parameter  
 `_Message`  
 Eine beschreibende Fehlermeldung.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Task_handle-Klasse](task-handle-class.md)   
 [Task_group-Klasse](task-group-class.md)   
 [Ausführen](task-group-class.md)   
 [Warte](task-group-class.md)   
 [run_and_wait](task-group-class.md)   
 [structured_task_group-Klasse](structured-task-group-class.md)

