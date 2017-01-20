---
title: "cancellation_token_registration-Klasse"
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
  - "pplcancellation_token/concurrency::cancellation_token_registration"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cancellation_token_registration-Klasse"
ms.assetid: 823d63f4-7233-4d65-8976-6152ccf12d0e
caps.latest.revision: 9
caps.handback.revision: "3"
ms.author: "mblome"
manager: "ghogen"
---
# cancellation_token_registration-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Die `cancellation_token_registration`\-Klasse stellt eine Rückrufbenachrichtigung von `cancellation_token` dar.  Bei Verwendung der `register`\-Methode auf `cancellation_token` zum Empfangen von Benachrichtigungen darüber, wann ein Abbruch auftritt, wird ein `cancellation_token_registration`\-Objekt als Handle an den Rückruf zurückgegeben, damit der Aufrufer mithilfe der `deregister`\-Methode anfordern kann, dass ein bestimmter Rückruf nicht mehr erfolgt.  
  
## Syntax  
  
```  
class cancellation_token_registration;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[cancellation\_token\_registration::cancellation\_token\_registration\-Konstruktor](../Topic/cancellation_token_registration::cancellation_token_registration%20Constructor.md)||  
|[cancellation\_token\_registration::~cancellation\_token\_registration\-Destruktor](../Topic/cancellation_token_registration::~cancellation_token_registration%20Destructor.md)||  
  
### Öffentliche Operatoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[cancellation\_token\_registration::operator\!\=\-Operator](../Topic/cancellation_token_registration::operator!=%20Operator.md)||  
|[cancellation\_token\_registration::operator\=\-Operator](../Topic/cancellation_token_registration::operator=%20Operator.md)||  
|[cancellation\_token\_registration::operator\=\=\-Operator](../Topic/cancellation_token_registration::operator==%20Operator.md)||  
  
## Vererbungshierarchie  
 `cancellation_token_registration`  
  
## Anforderungen  
 **Header:** pplcancellation\_token.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)