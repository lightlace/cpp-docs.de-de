---
title: Bad_target-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- bad_target
- CONCRT/concurrency::bad_target
- CONCRT/concurrency::bad_target::bad_target
dev_langs:
- C++
helpviewer_keywords:
- bad_target class
ms.assetid: e6dcddbf-9217-4fac-ac7f-7b8b4781d2f5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 12e035a27693fcad095cd83880aba99c37ba1c1f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46027634"
---
# <a name="badtarget-class"></a>bad_target-Klasse
Diese Klasse beschreibt eine Ausnahme, die dann ausgelöst wird, wenn einem Meldungsblock ein Zeiger auf ein Ziel zugeordnet wird, das für die auszuführende Operation ungültig ist.  
  
## <a name="syntax"></a>Syntax  
  
```
class bad_target : public std::exception;
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[bad_target](#ctor)|Überladen. Erstellt ein `bad_target`-Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Ausnahme wird normalerweise aus Gründen, z. B. ein Ziel versucht, eine Nachricht zu verarbeiten, die für ein anderes Ziel reserviert ist, oder veröffentlichen eine Reservierung, die er nicht aufrechterhält.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `exception`  
  
 `bad_target`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu  
  
 **Namespace:** Parallelität  
  
##  <a name="ctor"></a> bad_target 

 Erstellt ein `bad_target`-Objekt.  
  
```
explicit _CRTIMP bad_target(_In_z_ const char* _Message) throw();

bad_target() throw();
```  
  
### <a name="parameters"></a>Parameter  
*_Nachricht*<br/>
Eine beschreibende Fehlermeldung.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Asynchrone Nachrichtenblöcke](../../../parallel/concrt/asynchronous-message-blocks.md)



