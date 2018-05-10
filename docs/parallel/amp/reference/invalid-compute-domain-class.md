---
title: Invalid_compute_domain-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- invalid_compute_domain
- AMPRT/invalid_compute_domain
- AMPRT/Concurrency::invalid_compute_domain::invalid_compute_domain
dev_langs:
- C++
helpviewer_keywords:
- invalid_compute_domain class
ms.assetid: ac7a7166-8bdb-4db1-8caf-ea129ab5117e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 588f12e04f3a2833da6d67c07ab41929d916a4b5
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
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

## <a name="ctor"></a> invalid_compute_domain 

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
