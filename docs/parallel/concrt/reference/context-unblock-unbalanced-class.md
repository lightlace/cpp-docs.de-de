---
title: Context_unblock_unbalanced-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- context_unblock_unbalanced
- CONCRT/concurrency::context_unblock_unbalanced
- CONCRT/concurrency::context_unblock_unbalanced::context_unblock_unbalanced
dev_langs:
- C++
helpviewer_keywords:
- context_unblock_unbalanced class
ms.assetid: a76066c8-19dd-44fa-959a-6941ec1b0d2d
caps.latest.revision: 20
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
ms.openlocfilehash: 21c26658e347fa35209677e15ddcb48bbe8d1235
ms.contentlocale: de-de
ms.lasthandoff: 03/17/2017

---
# <a name="contextunblockunbalanced-class"></a>context_unblock_unbalanced-Klasse
Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn Aufrufe der `Block`-Methode und der `Unblock`-Methode eines `Context`-Objekts nicht ordnungsgemäß zugeordnet werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
class context_unblock_unbalanced : public std::exception;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[context_unblock_unbalanced](#ctor)|Überladen. Erstellt ein `context_unblock_unbalanced`-Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Aufrufe von der `Block` und `Unblock` Methoden eine `Context` -Objekts muss immer ordnungsgemäß zugeordnet. Die Concurrency Runtime ermöglicht die Vorgänge in beliebiger Reihenfolge auftreten. Z. B. einen Aufruf von `Block` kann durch einen Aufruf von folgen `Unblock`, oder umgekehrt. Würde diese Ausnahme ausgelöst werden, wenn z. B. zwei Aufrufe der `Unblock` Methode wurden in einer Zeile für ein `Context` Objekt, das nicht blockiert wurde.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `exception`  
  
 `context_unblock_unbalanced`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu  
  
 **Namespace:** Parallelität  
  
##  <a name="ctor"></a>context_unblock_unbalanced 

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

