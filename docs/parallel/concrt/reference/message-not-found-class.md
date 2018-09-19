---
title: Message_not_found-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- message_not_found
- CONCRT/concurrency::message_not_found
- CONCRT/concurrency::message_not_found::message_not_found
dev_langs:
- C++
helpviewer_keywords:
- message_not_found class
ms.assetid: a96b9995-5ad7-4600-83c8-c15e329ff10e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f28096fccae4f24b236631b3c27178bda7e22771
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46103983"
---
# <a name="messagenotfound-class"></a>message_not_found-Klasse
Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn ein Meldungsblock keine angeforderte Meldung finden kann.  
  
## <a name="syntax"></a>Syntax  
  
```
class message_not_found : public std::exception;
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[message_not_found](#ctor)|Überladen. Erstellt ein `message_not_found`-Objekt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `exception`  
  
 `message_not_found`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu  
  
 **Namespace:** Parallelität  
  
##  <a name="ctor"></a> message_not_found 

 Erstellt ein `message_not_found`-Objekt.  
  
```
explicit _CRTIMP message_not_found(_In_z_ const char* _Message) throw();

message_not_found() throw();
```  
  
### <a name="parameters"></a>Parameter  
*_Nachricht*<br/>
Eine beschreibende Fehlermeldung.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Asynchrone Nachrichtenblöcke](../../../parallel/concrt/asynchronous-message-blocks.md)



