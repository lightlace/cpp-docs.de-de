---
title: Scheduler_interface-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- pplinterface/concurrency::scheduler_interface
dev_langs:
- C++
ms.assetid: 4de61c78-a2c6-4698-bd47-964baf7fa287
caps.latest.revision: 7
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
ms.sourcegitcommit: fa774c7f025b581d65c28d65d83e22ff2d798230
ms.openlocfilehash: 1b05a0f6954e501d3b0362cb7c68794422ee97fd
ms.lasthandoff: 02/24/2017

---
# <a name="schedulerinterface-structure"></a>scheduler_interface-Struktur
Planerschnittstelle  
  
## <a name="syntax"></a>Syntax  
  
```
struct __declspec(novtable) scheduler_interface;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[scheduler_interface:: Schedule-Methode](#schedule)||  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `scheduler_interface`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** pplinterface.h  
  
 **Namespace:** Parallelität  
  
##  <a name="a-nameschedulea--schedulerinterfaceschedule-method"></a><a name="schedule"></a>scheduler_interface:: Schedule-Methode  
  
```
virtual void schedule(
    TaskProc_t,
 void*) = 0;
```  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)

