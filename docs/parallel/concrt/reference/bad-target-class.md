---
title: Bad_target-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::bad_target
dev_langs:
- C++
helpviewer_keywords:
- bad_target class
ms.assetid: e6dcddbf-9217-4fac-ac7f-7b8b4781d2f5
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
ms.openlocfilehash: a22ebb69195dcea91799dc1c2e301a578dd227bc
ms.lasthandoff: 02/24/2017

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
|[Bad_target-Konstruktor](#ctor)|Überladen. Erstellt ein `bad_target`-Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Ausnahme wird normalerweise aus Gründen, z. B. ein Ziel, bei dem Versuch, eine Nachricht zu nutzen, die für ein anderes Ziel reserviert ist oder eine Reservierung, die er nicht aufrechterhält freigibt.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `exception`  
  
 `bad_target`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu  
  
 **Namespace:** Parallelität  
  
##  <a name="a-namectora-badtarget"></a><a name="ctor"></a>bad_target 

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




