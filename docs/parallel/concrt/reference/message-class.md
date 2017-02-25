---
title: "message-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::message"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "message-Klasse"
ms.assetid: 3e1f3505-6c0c-486c-8191-666d0880ec62
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# message-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Der grundlegende Nachrichtenumschlag, der die zwischen den Meldungsblöcken übergebene Datennutzlast enthält.  
  
## Syntax  
  
```  
template<  
   class _Type  
>  
class message : public ::Concurrency::details::_Runtime_object;  
```  
  
#### Parameter  
 `_Type`  
 Der Datentyp der Nutzlast in der Meldung.  
  
## Member  
  
### Öffentliche Typedefs  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|`type`|Ein Typalias für `_Type`.|  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[message::message\-Konstruktor](../Topic/message::message%20Constructor.md)|Überladen.  Erstellt ein `message`\-Objekt.|  
|[message::~message\-Destruktor](../Topic/message::~message%20Destructor.md)|Zerstört das `message`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[message::add\_ref\-Methode](../Topic/message::add_ref%20Method.md)|Fügt der Verweisanzahl auf das `message`\-Objekt hinzu.  Wird für Meldungsblöcke verwendet, die eine Verweiszählung benötigen, um Meldungslebensdauern zu bestimmen.|  
|[message::msg\_id\-Methode](../Topic/message::msg_id%20Method.md)|Gibt die ID des `message`\-Objekts zurück.|  
|[message::remove\_ref\-Methode](../Topic/message::remove_ref%20Method.md)|Subtrahiert vom Verweiszähler für das `message`\-Objekt.  Wird für Meldungsblöcke verwendet, die eine Verweiszählung benötigen, um Meldungslebensdauern zu bestimmen.|  
  
### Öffentliche Datenmember  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[message::payload\-Datenmember](../Topic/message::payload%20Data%20Member.md)|Die Nutzlast des `message`\-Objekts.|  
  
## Hinweise  
 Weitere Informationen finden Sie unter [Asynchrone Nachrichtenblöcke](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## Vererbungshierarchie  
 `message`  
  
## Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)