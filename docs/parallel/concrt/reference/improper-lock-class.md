---
title: Improper_lock-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::improper_lock
dev_langs:
- C++
helpviewer_keywords:
- improper_lock class
ms.assetid: 8f494942-7748-4a2a-8de2-23414bfe6346
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
ms.openlocfilehash: 5a68573b8963fed90a4346fd421ef479c35dc247
ms.lasthandoff: 02/24/2017

---
# <a name="improperlock-class"></a>improper_lock-Klasse
Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn eine Sperre nicht ordnungsgemäß abgerufen wird.  
  
## <a name="syntax"></a>Syntax  
  
```
class improper_lock : public std::exception;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Improper_lock-Konstruktor](#ctor)|Überladen. Konstruiert ein `improper_lock exception`.|  
  
## <a name="remarks"></a>Hinweise  
 In der Regel wird diese Ausnahme ausgelöst, wenn versucht wird, einen nicht wiedereintretende Sperre rekursiv im gleichen Kontext abzurufen.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `exception`  
  
 `improper_lock`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu  
  
 **Namespace:** Parallelität  
  
##  <a name="a-namectora-improperlock"></a><a name="ctor"></a>improper_lock 

 Konstruiert ein `improper_lock exception`.  
  
```
explicit _CRTIMP improper_lock(_In_z_ const char* _Message) throw();

improper_lock() throw();
```  
  
### <a name="parameters"></a>Parameter  
 `_Message`  
 Eine beschreibende Fehlermeldung.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Critical_section-Klasse](critical-section-class.md)   
 [Reader_writer_lock-Klasse](reader-writer-lock-class.md)

