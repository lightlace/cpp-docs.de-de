---
title: Scheduler_resource_allocation_error-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- scheduler_resource_allocation_error
- CONCRT/concurrency::scheduler_resource_allocation_error
- CONCRT/concurrency::scheduler_resource_allocation_error::scheduler_resource_allocation_error
- CONCRT/concurrency::scheduler_resource_allocation_error::get_error_code
dev_langs:
- C++
helpviewer_keywords:
- scheduler_resource_allocation_error class
ms.assetid: 8b40449a-7abb-4d0a-bb85-c0e9a495ae97
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9ede37cec7b654c2d5ead32f117e4fe76f28fa60
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46101695"
---
# <a name="schedulerresourceallocationerror-class"></a>scheduler_resource_allocation_error-Klasse
Diese Klasse beschreibt eine Ausnahme, die aufgrund eines Fehlers ausgelöst wird, um in der Concurrency Runtime eine wichtige Ressource abzurufen.  
  
## <a name="syntax"></a>Syntax  
  
```
class scheduler_resource_allocation_error : public std::exception;
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[scheduler_resource_allocation_error](#ctor)|Überladen. Erstellt ein `scheduler_resource_allocation_error`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[get_error_code](#get_error_code)|Gibt den Fehlercode zurück, der die Ausnahme verursacht hat.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Ausnahme wird in der Regel ausgelöst, wenn ein Aufruf an das Betriebssystem aus, in der Concurrency Runtime fehlschlägt. Der Fehlercode, die normalerweise von einem Aufruf der Win32-Methode zurückgegeben werden würde `GetLastError` wird in einen Wert vom Typ konvertiert `HRESULT` und können abgerufen werden, mithilfe der `get_error_code` Methode.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `exception`  
  
 `scheduler_resource_allocation_error`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu  
  
 **Namespace:** Parallelität  
  
##  <a name="get_error_code"></a> get_error_code 

 Gibt den Fehlercode zurück, der die Ausnahme verursacht hat.  
  
```
HRESULT get_error_code() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die `HRESULT` Wert des Fehlers, der die Ausnahme verursacht hat.  
  
##  <a name="ctor"></a> scheduler_resource_allocation_error 

 Erstellt ein `scheduler_resource_allocation_error`-Objekt.  
  
```
scheduler_resource_allocation_error(
    _In_z_ const char* _Message,
    HRESULT _Hresult) throw();

explicit _CRTIMP scheduler_resource_allocation_error(
    HRESULT _Hresult) throw();
```  
  
### <a name="parameters"></a>Parameter  
*_Nachricht*<br/>
Eine beschreibende Fehlermeldung.  
  
*_Hresult*<br/>
Die `HRESULT` Wert des Fehlers, der die Ausnahme verursacht hat.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)
