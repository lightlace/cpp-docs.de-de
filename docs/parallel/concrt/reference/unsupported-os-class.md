---
title: Unsupported_os-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- unsupported_os
- CONCRT/concurrency::unsupported_os
- CONCRT/concurrency::unsupported_os::unsupported_os
dev_langs:
- C++
helpviewer_keywords:
- unsupported_os class
ms.assetid: 6fa57636-341b-4b51-84cc-261d283ff736
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a147bc429268c7342667e770de083dc6660fa955
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="unsupportedos-class"></a>unsupported_os-Klasse
Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn ein nicht unterstütztes Betriebssystem verwendet wird.  
  
## <a name="syntax"></a>Syntax  
  
```
class unsupported_os : public std::exception;
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[unsupported_os](#ctor)|Überladen. Erstellt ein `unsupported_os`-Objekt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `exception`  
  
 `unsupported_os`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h  
  
 **Namespace:** Parallelität  
  
##  <a name="ctor"></a> unsupported_os 

 Erstellt ein `unsupported_os`-Objekt.  
  
```
explicit _CRTIMP unsupported_os(_In_z_ const char* _Message) throw();

unsupported_os() throw();
```  
  
### <a name="parameters"></a>Parameter  
 `_Message`  
 Eine beschreibende Fehlermeldung.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)
