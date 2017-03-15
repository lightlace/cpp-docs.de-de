---
title: Context_unblock_unbalanced-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::context_unblock_unbalanced
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
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 7341ff5d10b7f7752c49f18ea9b810824e347b1c
ms.lasthandoff: 02/24/2017

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
|[Context_unblock_unbalanced-Konstruktor](#ctor)|Überladen. Erstellt ein `context_unblock_unbalanced`-Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Aufrufe von der `Block` und `Unblock` Methoden eine `Context` -Objekts muss immer ordnungsgemäß zugeordnet. Die Concurrency Runtime ermöglicht die Vorgänge in beliebiger Reihenfolge auftreten. Z. B. einen Aufruf von `Block` kann durch einen Aufruf von folgen `Unblock`, oder umgekehrt. Würde diese Ausnahme ausgelöst werden, wenn z. B. zwei Aufrufe der `Unblock` Methode wurden in einer Zeile für ein `Context` Objekt, das nicht blockiert wurde.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `exception`  
  
 `context_unblock_unbalanced`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu  
  
 **Namespace:** Parallelität  
  
##  <a name="a-namectora-contextunblockunbalanced"></a><a name="ctor"></a>context_unblock_unbalanced 

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

