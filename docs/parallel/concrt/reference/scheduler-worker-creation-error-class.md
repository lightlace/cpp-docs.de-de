---
title: Scheduler_worker_creation_error-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c04a6b3c55920739a8c9bce70a147951edbf935a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
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
 Diese Ausnahme wird in der Regel ausgelöst, wenn ein Aufruf an das Betriebssystem zum Erstellen von Ausführungskontexte aus in der Concurrency Runtime fehlschlägt. Ausführungskontexte sind Threads, die Aufgaben in der Concurrency Runtime ausgeführt werden. Der Fehlercode, die normalerweise von einem Aufruf der Win32-Methode zurückgegeben werden würde `GetLastError` wird auf einen Wert vom Typ konvertiert `HRESULT` und können mithilfe der Methode der Basisklasse abgerufen werden `get_error_code`.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `exception`  
  
 [scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md)  
  
 `scheduler_worker_creation_error`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h  
  
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
 `_Message`  
 Eine beschreibende Fehlermeldung.  
  
 `_Hresult`  
 Die `HRESULT` Wert des Fehlers, der die Ausnahme verursacht hat.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)
