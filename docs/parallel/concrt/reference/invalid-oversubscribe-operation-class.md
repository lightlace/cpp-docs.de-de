---
title: Invalid_oversubscribe_operation-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- invalid_oversubscribe_operation
- CONCRT/concurrency::invalid_oversubscribe_operation
- CONCRT/concurrency::invalid_oversubscribe_operation::invalid_oversubscribe_operation
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 9263fd2bf7d4cfa3b1b8542b8a0bf8d2a3969326
ms.contentlocale: de-de
ms.lasthandoff: 03/17/2017

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
|[invalid_oversubscribe_operation](#ctor)|Überladen. Erstellt ein `invalid_oversubscribe_operation`-Objekt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `exception`  
  
 `invalid_oversubscribe_operation`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu  
  
 **Namespace:** Parallelität  
  
##  <a name="ctor"></a>invalid_oversubscribe_operation 

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

