---
title: Context_unblock_unbalanced-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- context_unblock_unbalanced
- CONCRT/concurrency::context_unblock_unbalanced
- CONCRT/concurrency::context_unblock_unbalanced::context_unblock_unbalanced
dev_langs:
- C++
helpviewer_keywords:
- context_unblock_unbalanced class
ms.assetid: a76066c8-19dd-44fa-959a-6941ec1b0d2d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c964701f9a26c655bbb9529a112f036c7c9f0bf5
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33685748"
---
# <a name="contextunblockunbalanced-class"></a>context_unblock_unbalanced-Klasse
Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn Aufrufe der `Block`-Methode und der `Unblock`-Methode eines `Context`-Objekts nicht ordnungsgemäß zugeordnet werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
class context_unblock_unbalanced : public std::exception;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[context_unblock_unbalanced](#ctor)|Überladen. Erstellt ein `context_unblock_unbalanced`-Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Aufrufe von der `Block` und `Unblock` Methoden eine `Context` -Objekts muss immer ordnungsgemäß zugeordnet. Die Concurrency Runtime ermöglicht die Vorgänge in beliebiger Reihenfolge durchgeführt werden soll. Z. B. einen Aufruf von `Block` kann durch einen Aufruf von folgen `Unblock`, oder umgekehrt. Diese Ausnahme wird ausgelöst, wenn, z. B. zwei Aufrufe der `Unblock` Methode in einer Zeile vorgenommen wurden, auf ein `Context` Objekt, das nicht blockiert wurde.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `exception`  
  
 `context_unblock_unbalanced`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu  
  
 **Namespace:** Parallelität  
  
##  <a name="ctor"></a> context_unblock_unbalanced 

 Erstellt ein `context_unblock_unbalanced`-Objekt.  
  
```  
explicit _CRTIMP context_unblock_unbalanced(_In_z_ const char* _Message) throw();

 
context_unblock_unbalanced() throw();
```  
  
### <a name="parameters"></a>Parameter  
 `_Message`  
 Eine beschreibende Fehlermeldung.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)
