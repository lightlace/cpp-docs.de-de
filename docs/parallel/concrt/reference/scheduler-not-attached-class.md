---
title: Scheduler_not_attached-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- scheduler_not_attached
- CONCRT/concurrency::scheduler_not_attached
- CONCRT/concurrency::scheduler_not_attached::scheduler_not_attached
dev_langs: C++
helpviewer_keywords: scheduler_not_attached class
ms.assetid: 26001970-b400-463b-be3d-8623359c399a
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1a7c76ed0c2b4291934914d3e6aa8d13b23580bc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="schedulernotattached-class"></a>scheduler_not_attached-Klasse
Diese Klasse beschreibt eine Ausnahme, die bei Ausführen eines Vorgangs ausgelöst wird, der erfordert, dass ein Planer an den aktuellen Kontext angefügt wird, und einer nicht.  
  
## <a name="syntax"></a>Syntax  
  
```
class scheduler_not_attached : public std::exception;
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[scheduler_not_attached](#ctor)|Überladen. Erstellt ein `scheduler_not_attached`-Objekt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `exception`  
  
 `scheduler_not_attached`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu  
  
 **Namespace:** Parallelität  
  
##  <a name="ctor"></a>scheduler_not_attached 

 Erstellt ein `scheduler_not_attached`-Objekt.  
  
```
explicit _CRTIMP scheduler_not_attached(_In_z_ const char* _Message) throw();

scheduler_not_attached() throw();
```  
  
### <a name="parameters"></a>Parameter  
 `_Message`  
 Eine beschreibende Fehlermeldung.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Scheduler-Klasse](scheduler-class.md)
