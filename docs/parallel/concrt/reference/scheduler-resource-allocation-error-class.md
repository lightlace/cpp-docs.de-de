---
title: Scheduler_resource_allocation_error-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::scheduler_resource_allocation_error
dev_langs:
- C++
helpviewer_keywords:
- scheduler_resource_allocation_error class
ms.assetid: 8b40449a-7abb-4d0a-bb85-c0e9a495ae97
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
ms.openlocfilehash: 52233a99e1d1a715fc7d52599ffeff18a3c2c34b
ms.lasthandoff: 02/24/2017

---
# <a name="schedulerresourceallocationerror-class"></a>scheduler_resource_allocation_error-Klasse
Diese Klasse beschreibt eine Ausnahme, die aufgrund eines Fehlers ausgelöst wird, um in der Concurrency Runtime eine wichtige Ressource abzurufen.  
  
## <a name="syntax"></a>Syntax  
  
```
class scheduler_resource_allocation_error : public std::exception;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Scheduler_resource_allocation_error-Konstruktor](#ctor)|Überladen. Erstellt ein `scheduler_resource_allocation_error`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Get_error_code-Methode](#get_error_code)|Gibt den Fehlercode zurück, der die Ausnahme verursacht hat.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Ausnahme wird normalerweise ausgelöst, wenn ein Aufruf des Betriebssystems von innerhalb der Concurrency Runtime fehlschlägt. Der Fehlercode, die normalerweise von einem Aufruf der Win32-Methode zurückgegeben werden würde `GetLastError` ist ein Wert vom Typ konvertiert `HRESULT` und kann abgerufen werden, mit der `get_error_code` Methode.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `exception`  
  
 `scheduler_resource_allocation_error`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu  
  
 **Namespace:** Parallelität  
  
##  <a name="a-namegeterrorcodea-geterrorcode"></a><a name="get_error_code"></a>get_error_code 

 Gibt den Fehlercode zurück, der die Ausnahme verursacht hat.  
  
```
HRESULT get_error_code() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die `HRESULT` Wert des Fehlers, der die Ausnahme verursacht hat.  
  
##  <a name="a-namectora-schedulerresourceallocationerror"></a><a name="ctor"></a>scheduler_resource_allocation_error 

 Erstellt ein `scheduler_resource_allocation_error`-Objekt.  
  
```
scheduler_resource_allocation_error(
    _In_z_ const char* _Message,
    HRESULT _Hresult) throw();

explicit _CRTIMP scheduler_resource_allocation_error(
    HRESULT _Hresult) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `_Message`  
 Eine beschreibende Fehlermeldung.  
  
 `_Hresult`  
 Die `HRESULT` Wert des Fehlers, der die Ausnahme verursacht hat.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)

