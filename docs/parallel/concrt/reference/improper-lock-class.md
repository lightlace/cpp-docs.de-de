---
title: Improper_lock-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- improper_lock
- CONCRT/concurrency::improper_lock
- CONCRT/concurrency::improper_lock::improper_lock
dev_langs:
- C++
helpviewer_keywords:
- improper_lock class
ms.assetid: 8f494942-7748-4a2a-8de2-23414bfe6346
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 37cf615460cda6d0f33f0431e258cac843f456c4
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="improperlock-class"></a>improper_lock-Klasse
Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn eine Sperre nicht ordnungsgemäß abgerufen wird.  
  
## <a name="syntax"></a>Syntax  
  
```
class improper_lock : public std::exception;
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[improper_lock](#ctor)|Überladen. Konstruiert ein `improper_lock exception`.|  
  
## <a name="remarks"></a>Hinweise  
 In der Regel wird diese Ausnahme ausgelöst, bei dem Versuch, einen nicht wiedereintretende Sperre rekursiv im gleichen Kontext abzurufen.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `exception`  
  
 `improper_lock`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h  
  
 **Namespace:** Parallelität  
  
##  <a name="ctor"></a> improper_lock 

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
 [reader_writer_lock-Klasse](reader-writer-lock-class.md)
