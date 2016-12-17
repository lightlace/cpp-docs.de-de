---
title: "ISource-Klasse"
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
  - "agents/concurrency::ISource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ISource-Klasse"
ms.assetid: c7b73463-42f6-4dcc-801a-81379b12d35a
caps.latest.revision: 20
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# ISource-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Die `ISource`\-Klasse ist die Schnittstelle für alle Quellblöcke.  Quellblöcke geben Meldungen an `ITarget`\-Blöcke weiter.  
  
## Syntax  
  
```  
template<  
   class _Type  
>  
class ISource;  
```  
  
#### Parameter  
 `_Type`  
 Der Datentyp der Nutzlast innerhalb der Meldungen, die vom Quellblock erstellt werden.  
  
## Member  
  
### Öffentliche Typedefs  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|`source_type`|Ein Typalias für `_Type`.|  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[ISource::~ISource\-Destruktor](../Topic/ISource::~ISource%20Destructor.md)|Zerstört das `ISource`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[ISource::accept\-Methode](../Topic/ISource::accept%20Method.md)|Akzeptiert beim Überschreiben in einer abgeleiteten Klasse eine Meldung, die von diesem `ISource`\-Block angeboten wurde, und überträgt den Besitz an den Aufrufer.|  
|[ISource::acquire\_ref\-Methode](../Topic/ISource::acquire_ref%20Method.md)|Ruft beim Überschreiben in einer abgeleiteten Klasse eine Verweisanzahl für diesen `ISource`\-Block ab, um das Löschen zu verhindern.|  
|[ISource::consume\-Methode](../Topic/ISource::consume%20Method.md)|Verwendet beim Überschreiben in einer abgeleiteten Klasse eine Meldung, die zuvor von diesem `ISource`\-Block angeboten und vom Ziel erfolgreich reserviert wurde, und überträgt den Besitz an den Aufrufer.|  
|[ISource::link\_target\-Methode](../Topic/ISource::link_target%20Method.md)|Verknüpft beim Überschreiben in einer abgeleiteten Klasse einen angegebenen Zielblock mit diesem `ISource`\-Block.|  
|[ISource::release\-Methode](../Topic/ISource::release%20Method.md)|Gibt beim Überschreiben in einer abgeleiteten Klasse eine frühere erfolgreiche Meldungsreservierung frei.|  
|[ISource::release\_ref\-Methode](../Topic/ISource::release_ref%20Method.md)|Gibt beim Überschreiben in einer abgeleiteten Klasse eine Verweisanzahl für diesen `ISource`\-Block frei.|  
|[ISource::reserve\-Methode](../Topic/ISource::reserve%20Method.md)|Reserviert beim Überschreiben in einer abgeleiteten Klasse eine Meldung, die von diesem `ISource`\-Block angeboten wurde.|  
|[ISource::unlink\_target\-Methode](../Topic/ISource::unlink_target%20Method.md)|Hebt beim Überschreiben in einer abgeleiteten Klasse die Verknüpfung eines Zielblocks mit einem `ISource`\-Block auf, sofern zuvor eine Verknüpfung bestand.|  
|[ISource::unlink\_targets\-Methode](../Topic/ISource::unlink_targets%20Method.md)|Hebt beim Überschreiben in einer abgeleiteten Klasse die Verknüpfung aller Zielblöcke mit diesem `ISource`\-Block auf.|  
  
## Hinweise  
 Weitere Informationen finden Sie unter [Asynchrone Nachrichtenblöcke](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## Vererbungshierarchie  
 `ISource`  
  
## Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [ITarget\-Klasse](../../../parallel/concrt/reference/itarget-class.md)