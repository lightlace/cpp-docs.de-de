---
title: "ITarget-Klasse"
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
  - "agents/concurrency::ITarget"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ITarget-Klasse"
ms.assetid: 5678db25-112a-4f72-be13-42e16b67c48b
caps.latest.revision: 22
caps.handback.revision: "16"
ms.author: "mblome"
manager: "ghogen"
---
# ITarget-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Die `ITarget`\-Klasse ist die Schnittstelle für alle Zielblöcke.  Zielblöcke nehmen Meldungen auf, die von `ISource`\-Blöcken angeboten werden.  
  
## Syntax  
  
```  
template<  
   class _Type  
>  
class ITarget;  
```  
  
#### Parameter  
 `_Type`  
 Der Datentyp der Nutzlast innerhalb der Meldungen, die vom Zielblock akzeptiert werden.  
  
## Member  
  
### Öffentliche Typedefs  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|`filter_method`|Die Signatur einer beliebigen Methode, die vom Block verwendet wurde, der einen `bool`\-Wert zurückgibt, um zu bestimmen, ob eine bereitgestellte Meldung akzeptiert werden soll.|  
|`type`|Ein Typalias für `_Type`.|  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[ITarget::~ITarget\-Destruktor](../Topic/ITarget::~ITarget%20Destructor.md)|Zerstört das `ITarget`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[ITarget::propagate\-Methode](../Topic/ITarget::propagate%20Method.md)|Übergibt beim Überschreiben in einer abgeleiteten Klasse asynchron eine Meldung von einem Quellblock an diesen Zielblock.|  
|[ITarget::send\-Methode](../Topic/ITarget::send%20Method.md)|Übergibt beim Überschreiben in einer abgeleiteten Klasse eine Meldung synchron an einen Zielblock.|  
|[ITarget::supports\_anonymous\_source\-Methode](../Topic/ITarget::supports_anonymous_source%20Method.md)|Wenn Sie in einer abgeleiteten Klasse, in den true oder false in Abhängigkeit davon überschrieben werden, ob der Nachrichtenblock die Nachrichten akzeptiert, die von einer Quelle bereitgestellt werden, die nicht darauf bezieht.  Wenn die überschriebene Methode `true` zurückgibt, kann das Ziel eine angebotene Nachricht nicht deren Priorität ändern, da er eine hinausgeschobenen Meldung zu einem späteren Zeitpunkt die Quelle erforderlich, in der sourse Linkregistrierung identifiziert werden.|  
  
### Geschützte Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[ITarget::link\_source\-Methode](../Topic/ITarget::link_source%20Method.md)|Verknüpft beim Überschreiben in einer abgeleiteten Klasse einen angegebenen Quellblock mit diesem `ITarget`\-Block.|  
|[ITarget::unlink\_source\-Methode](../Topic/ITarget::unlink_source%20Method.md)|Hebt beim Überschreiben in einer abgeleiteten Klasse die Verknüpfung eines angegebenen Quellblocks mit diesem `ITarget`\-Block auf.|  
|[ITarget::unlink\_sources\-Methode](../Topic/ITarget::unlink_sources%20Method.md)|Hebt beim Überschreiben in einer abgeleiteten Klasse die Verknüpfung aller Quellblöcke mit diesem `ITarget`\-Block auf.|  
  
## Hinweise  
 Weitere Informationen finden Sie unter [Asynchrone Nachrichtenblöcke](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## Vererbungshierarchie  
 `ITarget`  
  
## Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [ISource\-Klasse](../../../parallel/concrt/reference/isource-class.md)