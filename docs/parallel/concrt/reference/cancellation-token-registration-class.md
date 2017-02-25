---
title: "cancellation_token_registration-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "pplcancellation_token/concurrency::cancellation_token_registration"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cancellation_token_registration-Klasse"
ms.assetid: 823d63f4-7233-4d65-8976-6152ccf12d0e
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
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