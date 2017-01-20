---
title: "cancellation_token-Klasse"
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
  - "pplcancellation_token/concurrency::cancellation_token"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cancellation_token-Klasse"
ms.assetid: 2787df2b-e9d3-440e-bfd0-841a46a9835f
caps.latest.revision: 10
caps.handback.revision: "4"
ms.author: "mblome"
manager: "ghogen"
---
# cancellation_token-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Mit der `cancellation_token`\-Klasse kann bestimmt werden, ob für einen Vorgang ein Abbruch angefordert wurde.  Dem angegebenen Token kann `task_group`, `structured_task_group` oder `task` zugeordnet werden, um einen impliziten Abbruch bereitzustellen.  Es kann auch zum Abbruch abgerufen oder für einen Rückruf registriert werden, wenn das zugeordnete `cancellation_token_source`\-Element abgebrochen wird.  
  
## Syntax  
  
```  
class cancellation_token;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[cancellation\_token::cancellation\_token\-Konstruktor](../Topic/cancellation_token::cancellation_token%20Constructor.md)||  
|[cancellation\_token::~cancellation\_token\-Destruktor](../Topic/cancellation_token::~cancellation_token%20Destructor.md)||  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[cancellation\_token::deregister\_callback\-Methode](../Topic/cancellation_token::deregister_callback%20Method.md)|Entfernt einen Rückruf, der zuvor über die Methode `register` registriert wurde, auf Grundlage des `cancellation_token_registration`\-Objekts, das zum Zeitpunkt der Registrierung zurückgegeben wurde.|  
|[cancellation\_token::is\_cancelable\-Methode](../Topic/cancellation_token::is_cancelable%20Method.md)|Gibt einen Hinweis zurück, ob dieses Token abgebrochen werden kann oder nicht.|  
|[cancellation\_token::is\_canceled\-Methode](../Topic/cancellation_token::is_canceled%20Method.md)|Gibt `true` zurück, wenn das Token abgebrochen wurde.|  
|[cancellation\_token::none\-Methode](../Topic/cancellation_token::none%20Method.md)|Gibt ein Abbruchtoken zurück, das nie abgebrochen werden kann.|  
|[cancellation\_token::register\_callback\-Methode](../Topic/cancellation_token::register_callback%20Method.md)|Verknüpft eine Rückruffunktion mit dem Token.  Wenn das Token abgebrochen wird, wird der Rückruf vorgenommen.  Wurde das Token bereits abgebrochen, wenn diese Methode aufgerufen wird, wird der Rückruf sofort und synchron ausgeführt.|  
  
### Öffentliche Operatoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[cancellation\_token::operator\!\=\-Operator](../Topic/cancellation_token::operator!=%20Operator.md)||  
|[cancellation\_token::operator\=\-Operator](../Topic/cancellation_token::operator=%20Operator.md)||  
|[cancellation\_token::operator\=\=\-Operator](../Topic/cancellation_token::operator==%20Operator.md)||  
  
## Vererbungshierarchie  
 `cancellation_token`  
  
## Anforderungen  
 **Header:** pplcancellation\_token.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)