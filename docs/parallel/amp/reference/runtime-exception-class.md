---
title: "runtime_exception-Klasse"
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
  - "amp/Concurrency::direct3d_abort"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "runtime_exception-Klasse"
ms.assetid: 8fe3ce2c-3d4c-4b9c-95e8-e592f37adefd
caps.latest.revision: 10
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# runtime_exception-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Der Basistyp für Ausnahmen in der C\+\+ Accelerated Massive Parallelism \(AMP\)\-Bibliothek.  
  
## Syntax  
  
```  
class runtime_exception : public std::exception;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[runtime\_exception::runtime\_exception\-Konstruktor](../Topic/runtime_exception::runtime_exception%20Constructor.md)|Initialisiert eine neue Instanz der `runtime_exception`\-Klasse.|  
|[runtime\_exception::~runtime\_exception\-Destruktor](../Topic/runtime_exception::~runtime_exception%20Destructor.md)|Zerstört das `runtime_exception`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[runtime\_exception::get\_error\_code\-Methode](../Topic/runtime_exception::get_error_code%20Method.md)|Gibt den Fehlercode zurück, der die Ausnahme ausgelöst hat.|  
  
### Öffentliche Operatoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[runtime\_exception::operator\=\-Operator](../Topic/runtime_exception::operator=%20Operator.md)|Kopiert den Inhalt des angegebenen `runtime_exception`\-Objekts in dieses Objekt.|  
  
## Vererbungshierarchie  
 `exception`  
  
 `runtime_exception`  
  
## Anforderungen  
 **Header:** amprt.h  
  
 **Namespace:** Nebenläufigkeit  
  
## Siehe auch  
 [Concurrency\-Namespace \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)