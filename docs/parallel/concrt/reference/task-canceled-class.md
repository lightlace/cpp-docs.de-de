---
title: Task_canceled-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- task_canceled
- CONCRT/concurrency::task_canceled
- CONCRT/concurrency::task_canceled::task_canceled
dev_langs:
- C++
helpviewer_keywords:
- task_canceled class
ms.assetid: c3f0b234-2cc1-435f-a48e-995f45b190be
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b349bdd1a4bc646e513d69c9c9297e313eacd94d
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="taskcanceled-class"></a>task_canceled-Klasse
Diese Klasse beschreibt eine Ausnahme, die von den PPL-Aufgaben ausgelöst wird, um das Abbrechen der aktuellen Aufgabe zu erzwingen. Es wird auch ausgelöst, durch die `get()` Methode auf [Aufgabe](/visualstudio/extensibility/debugger/task-class-internal-members), für eine abgebrochene Aufgabe.  
  
## <a name="syntax"></a>Syntax  
  
```
class task_canceled : public std::exception;
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[task_canceled](#ctor)|Überladen. Erstellt ein `task_canceled`-Objekt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `exception`  
  
 `task_canceled`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h  
  
 **Namespace:** Parallelität  
  
##  <a name="ctor"></a> task_canceled 

 Erstellt ein `task_canceled`-Objekt.  
  
```
explicit _CRTIMP task_canceled(_In_z_ const char* _Message) throw();

task_canceled() throw();
```  
  
### <a name="parameters"></a>Parameter  
 `_Message`  
 Eine beschreibende Fehlermeldung.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)
