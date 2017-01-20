---
title: "context_unblock_unbalanced-Klasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::context_unblock_unbalanced"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "context_unblock_unbalanced-Klasse"
ms.assetid: a76066c8-19dd-44fa-959a-6941ec1b0d2d
caps.latest.revision: 20
caps.handback.revision: "20"
ms.author: "mblome"
manager: "ghogen"
---
# context_unblock_unbalanced-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn Aufrufe der `Block`-Methode und der `Unblock`-Methode eines `Context`-Objekts nicht ordnungsgemäß zugeordnet werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
class context_unblock_unbalanced : public std::exception;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[context_unblock_unbalanced:: context_unblock_unbalanced-Konstruktor](#context_unblock_unbalanced__context_unblock_unbalanced_constructor)|Überladen. Erstellt ein `context_unblock_unbalanced`-Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Aufrufe von der `Block` und `Unblock` Methoden eine `Context` -Objekts muss immer ordnungsgemäß zugeordnet. Die Concurrency Runtime ermöglicht die Vorgänge in beliebiger Reihenfolge auftreten. Z. B. einen Aufruf von `Block` kann durch einen Aufruf von folgen `Unblock`, oder umgekehrt. Würde diese Ausnahme ausgelöst werden, wenn z. B. zwei Aufrufe der `Unblock` Methode wurden in einer Zeile für ein `Context` Objekt, das nicht blockiert wurde.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `exception`  
  
 `context_unblock_unbalanced`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu  
  
 **Namespace:** Parallelität  
  
##  <a name="a-namecontextunblockunbalancedcontextunblockunbalancedconstructora-contextunblockunbalancedcontextunblockunbalanced-constructor"></a><a name="context_unblock_unbalanced__context_unblock_unbalanced_constructor"></a>  context_unblock_unbalanced:: context_unblock_unbalanced-Konstruktor  
 Erstellt ein `context_unblock_unbalanced`-Objekt.  
  
```  
explicit _CRTIMP context_unblock_unbalanced(_In_z_ const char* _Message) throw();

 
context_unblock_unbalanced() throw();
```  
  
### <a name="parameters"></a>Parameter  
 `_Message`  
 Eine beschreibende Fehlermeldung.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)
