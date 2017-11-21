---
title: Scheduler_interface-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- scheduler_interface
- PPLINTERFACE/concurrency::scheduler_interface
- PPLINTERFACE/concurrency::scheduler_interface::scheduler_interface::schedule
dev_langs: C++
ms.assetid: 4de61c78-a2c6-4698-bd47-964baf7fa287
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 99d7db566ab9073b48ba445a407420556e480d9f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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
|[scheduler_interface:: Schedule](#schedule)||  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `scheduler_interface`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** pplinterface.h  
  
 **Namespace:** Parallelität  
  
##  <a name="schedule"></a>scheduler_interface:: Schedule-Methode  
  
```
virtual void schedule(
    TaskProc_t,
 void*) = 0;
```  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)
