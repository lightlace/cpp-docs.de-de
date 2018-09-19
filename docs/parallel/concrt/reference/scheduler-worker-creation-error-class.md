---
title: Scheduler_worker_creation_error-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- scheduler_worker_creation_error
- CONCRT/concurrency::scheduler_worker_creation_error
- CONCRT/concurrency::scheduler_worker_creation_error::scheduler_worker_creation_error
dev_langs:
- C++
helpviewer_keywords:
- scheduler_worker_creation_error class
ms.assetid: 4aec1c3e-c32a-41b2-899d-2d898f23b3c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9c81b62cee3a8c26b0d4ace61b8104f6eaee9db6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46114383"
---
# <a name="schedulerworkercreationerror-class"></a>scheduler_worker_creation_error-Klasse
Diese Klasse beschreibt eine Ausnahme, die aufgrund eines Fehlers bei der Erstellung eines Workerausführungskontexts in der Concurrency Runtime ausgelöst wird.  
  
## <a name="syntax"></a>Syntax  
  
```
class scheduler_worker_creation_error : public scheduler_resource_allocation_error;
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[scheduler_worker_creation_error](#ctor)|Überladen. Erstellt ein `scheduler_worker_creation_error`-Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Ausnahme wird in der Regel ausgelöst, wenn ein Aufruf an das Betriebssystem zum Erstellen der Ausführungskontexte aus in der Concurrency Runtime fehlschlägt. Ausführungskontexte sind Threads, die Aufgaben in der Concurrency Runtime ausführen. Der Fehlercode, die normalerweise von einem Aufruf der Win32-Methode zurückgegeben werden sollen `GetLastError` wird in einen Wert vom Typ konvertiert `HRESULT` und können abgerufen werden, mithilfe der Methode der Basisklasse `get_error_code`.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `exception`  
  
 [scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md)  
  
 `scheduler_worker_creation_error`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu  
  
 **Namespace:** Parallelität  
  
##  <a name="ctor"></a> scheduler_worker_creation_error 

 Erstellt ein `scheduler_worker_creation_error`-Objekt.  
  
```
scheduler_worker_creation_error(
    _In_z_ const char* _Message,
    HRESULT _Hresult) throw();

explicit _CRTIMP scheduler_worker_creation_error(
    HRESULT _Hresult) throw();
```  
  
### <a name="parameters"></a>Parameter  
*_Nachricht*<br/>
Eine beschreibende Fehlermeldung.  
  
*_Hresult*<br/>
Die `HRESULT` Wert des Fehlers, der die Ausnahme verursacht hat.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)
