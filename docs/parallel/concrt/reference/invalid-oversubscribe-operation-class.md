---
title: Invalid_oversubscribe_operation-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::invalid_oversubscribe_operation
dev_langs:
- C++
helpviewer_keywords:
- invalid_oversubscribe_operation class
ms.assetid: 0a9c5f08-d5e6-4ad0-90a9-517472b3ac28
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
ms.openlocfilehash: becb02cfd6a052a019ee73e182804c63a286403e
ms.lasthandoff: 02/24/2017

---
# <a name="invalidoversubscribeoperation-class"></a>invalid_oversubscribe_operation-Klasse
Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn die `Context::Oversubscribe`-Methode mit dem auf `_BeginOversubscription` festgelegten `false`-Parameter ohne einen vorherigen Aufruf der `Context::Oversubscribe`-Methode mit dem auf `_BeginOversubscription` festgelegten `true`-Parameter aufgerufen wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
class invalid_oversubscribe_operation : public std::exception;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Invalid_oversubscribe_operation-Konstruktor](#ctor)|Überladen. Erstellt ein `invalid_oversubscribe_operation`-Objekt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `exception`  
  
 `invalid_oversubscribe_operation`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu  
  
 **Namespace:** Parallelität  
  
##  <a name="a-namectora-invalidoversubscribeoperation"></a><a name="ctor"></a>invalid_oversubscribe_operation 

 Erstellt ein `invalid_oversubscribe_operation`-Objekt.  
  
```  
explicit _CRTIMP invalid_oversubscribe_operation(_In_z_ const char* _Message) throw();

 
invalid_oversubscribe_operation() throw();
```  
  
### <a name="parameters"></a>Parameter  
 `_Message`  
 Eine beschreibende Fehlermeldung.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)

