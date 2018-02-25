---
title: Invalid_compute_domain-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cf8393e3af29c09376d4213bcdcec7642a593081
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
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
