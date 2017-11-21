---
title: Bad_target-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- bad_target
- CONCRT/concurrency::bad_target
- CONCRT/concurrency::bad_target::bad_target
dev_langs: C++
helpviewer_keywords: bad_target class
ms.assetid: e6dcddbf-9217-4fac-ac7f-7b8b4781d2f5
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4eb4f5158b3f8178bf34d5e5a27a8c28336b8946
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="badtarget-class"></a>bad_target-Klasse
Diese Klasse beschreibt eine Ausnahme, die dann ausgelöst wird, wenn einem Meldungsblock ein Zeiger auf ein Ziel zugeordnet wird, das für die auszuführende Operation ungültig ist.  
  
## <a name="syntax"></a>Syntax  
  
```
class bad_target : public std::exception;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[bad_target](#ctor)|Überladen. Erstellt ein `bad_target`-Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Ausnahme wird normalerweise aus Gründen, z. B. ein Ziel, bei dem Versuch, eine Nachricht entgegenzunehmen, die für ein anderes Ziel reserviert ist, oder eine Reservierung, die er nicht aufrechterhält freigeben.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `exception`  
  
 `bad_target`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu  
  
 **Namespace:** Parallelität  
  
##  <a name="ctor"></a>bad_target 

 Erstellt ein `bad_target`-Objekt.  
  
```
explicit _CRTIMP bad_target(_In_z_ const char* _Message) throw();

bad_target() throw();
```  
  
### <a name="parameters"></a>Parameter  
 `_Message`  
 Eine beschreibende Fehlermeldung.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Asynchrone Nachrichtenblöcke](../../../parallel/concrt/asynchronous-message-blocks.md)



