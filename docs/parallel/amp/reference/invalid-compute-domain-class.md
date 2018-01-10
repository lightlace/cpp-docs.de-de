---
title: Invalid_compute_domain-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- invalid_compute_domain
- AMPRT/invalid_compute_domain
- AMPRT/Concurrency::invalid_compute_domain::invalid_compute_domain
dev_langs: C++
helpviewer_keywords: invalid_compute_domain class
ms.assetid: ac7a7166-8bdb-4db1-8caf-ea129ab5117e
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9dc142b921efb6b52fd5b5ce7a89432b4727951c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="invalidcomputedomain-class"></a>invalid_compute_domain-Klasse
Die Ausnahme, die ausgelöst wird, wenn die Laufzeit einen Kernel gestartet werden kann, mit der Compute-Domäne angegeben, an die [Parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each) Aufrufsite.  

  
## <a name="syntax"></a>Syntax  
  
```  
class invalid_compute_domain : public runtime_exception;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Invalid_compute_domain-Konstruktor](#ctor)|Initialisiert eine neue Instanz der `invalid_compute_domain`-Klasse.|  

  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `exception`  
  
 `runtime_exception`  
  
 `invalid_compute_domain`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** amprt.h  
  
 **Namespace:** Parallelität  

## <a name="ctor"></a>invalid_compute_domain 

Initialisiert eine neue Instanz der Klasse.  
  
## <a name="syntax"></a>Syntax  
  
```  
explicit invalid_compute_domain(  
    const char * _Message ) throw();  
  
invalid_compute_domain() throw();  
```  
  
### <a name="parameters"></a>Parameter  
 `_Message`  
 Eine Beschreibung des Fehlers.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Instanz der `invalid_compute_domain`-Klasse  
    
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)
