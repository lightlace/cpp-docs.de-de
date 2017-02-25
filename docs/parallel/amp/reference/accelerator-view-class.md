---
title: "accelerator_view-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amprt/Concurrency::accelerator_view"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "accelerator_view-Klasse"
ms.assetid: 9f298c21-bf62-46e0-88b8-01c5c78ef144
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# accelerator_view-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Stellt die Abstraktion eines virtuellen Geräts für einen datenparallelen C\+\+ AMP\-Beschleuniger dar.  
  
## Syntax  
  
```  
class accelerator_view;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[accelerator\_view::accelerator\_view\-Konstruktor](../Topic/accelerator_view::accelerator_view%20Constructor.md)|Initialisiert eine neue Instanz der `accelerator_view`\-Klasse.|  
|[accelerator\_view::~accelerator\_view\-Destruktor](../Topic/accelerator_view::~accelerator_view%20Destructor.md)|Zerstört das `accelerator_view`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[accelerator\_view::create\_marker\-Methode](../Topic/accelerator_view::create_marker%20Method.md)|Gibt ein future\-Objekt zurück, um den Abschluss aller Befehle nachzuverfolgen, die bis jetzt zu diesem `accelerator_view`\-Objekt gesendet wurden.|  
|[accelerator\_view::flush\-Methode](../Topic/accelerator_view::flush%20Method.md)|Sendet alle ausstehenden Befehle, die im `accelerator_view`\-Objekt zur Ausführung der Zugriffstaste in die Warteschlange gestellt werden.|  
|[accelerator\_view::get\_accelerator\-Methode](../Topic/accelerator_view::get_accelerator%20Method.md)|Gibt das `accelerator`\-Objekt für das `accelerator_view`\-Objekt zurück.|  
|[accelerator\_view::get\_is\_auto\_selection\-Methode](../Topic/accelerator_view::get_is_auto_selection%20Method.md)|Gibt einen booleschen Wert zurück, der angibt, ob die Laufzeit automatisch eine entsprechende Zugriffstaste auswählt, wenn das `accelerator_view`\-Objekt an ein [parallel\_for\_each](../Topic/parallel_for_each%20Function%20\(C++%20AMP\).md)\-Objekt übergeben wird.|  
|[accelerator\_view::get\_is\_debug\-Methode](../Topic/accelerator_view::get_is_debug%20Method.md)|Gibt einen booleschen Wert zurück, der angibt, ob für das `accelerator_view`\-Objekt die DEBUG\-Ebene für eine umfangreiche Fehlerberichterstattung aktiviert ist.|  
|[accelerator\_view::get\_queuing\_mode\-Methode](../Topic/accelerator_view::get_queuing_mode%20Method.md)|Gibt den Queuingmodus für das `accelerator_view`\-Objekt zurück.|  
|[accelerator\_view::get\_version\-Methode](../Topic/accelerator_view::get_version%20Method.md)|Gibt die Version des `accelerator_view`\-Objekts zurück.|  
|[accelerator\_view::wait\-Methode](../Topic/accelerator_view::wait%20Method.md)|Wartet, bis alle an das `accelerator_view`\-Objekt gesendeten Befehle abgeschlossen sind.|  
  
### Öffentliche Operatoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[accelerator\_view::operator\!\=\-Operator](../Topic/accelerator_view::operator!=%20Operator.md)|Vergleicht dieses `accelerator_view`\-Objekt mit einem anderen und gibt `false` zurück, wenn sie identisch sind; gibt andernfalls `true` zurück.|  
|[accelerator\_view::operator\=\-Operator](../Topic/accelerator_view::operator=%20Operator.md)|Kopiert den Inhalt des angegebenen `accelerator_view`\-Objekts in dieses Objekt.|  
|[accelerator\_view::operator\=\=\-Operator](../Topic/accelerator_view::operator==%20Operator.md)|Vergleicht dieses `accelerator_view`\-Objekt mit einem anderen und gibt `true` zurück, wenn sie identisch sind; gibt andernfalls `false` zurück.|  
  
### Öffentliche Datenmember  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[accelerator\_view::accelerator\-Datenmember](../Topic/accelerator_view::accelerator%20Data%20Member.md)|Ruft das `accelerator`\-Objekt für das `accelerator_view`\-Objekt ab.|  
|[accelerator\_view::is\_auto\_selection\-Datenmember](../Topic/accelerator_view::is_auto_selection%20Data%20Member.md)|Ruft einen booleschen Wert ab, der angibt, ob die Laufzeit automatisch eine entsprechende Zugriffstaste auswählt, wenn das `accelerator_view`\-Objekt an ein [parallel\_for\_each](../Topic/parallel_for_each%20Function%20\(C++%20AMP\).md)\-Objekt übergeben wird.|  
|[accelerator\_view::is\_debug\-Datenmember](../Topic/accelerator_view::is_debug%20Data%20Member.md)|Ruft einen booleschen Wert ab, der angibt, ob für das `accelerator_view`\-Objekt die DEBUG\-Ebene für eine umfangreiche Fehlerberichterstattung aktiviert ist.|  
|[accelerator\_view::queuing\_mode\-Datenmember](../Topic/accelerator_view::queuing_mode%20Data%20Member.md)|Ruft den Queuingmodus für das `accelerator_view`\-Objekt ab.|  
|[accelerator\_view::version\-Datenmember](../Topic/accelerator_view::version%20Data%20Member.md)|Ruft die Version der Zugriffstaste ab.|  
  
## Vererbungshierarchie  
 `accelerator_view`  
  
## Hinweise  
 Ein `accelerator_view`\-Objekt stellt eine logische, isolierte Ansicht einer Zugriffstaste dar.  Ein einzelnes physisches Berechnungsgerät kann über viele logische, isolierte `accelerator_view`\-Objekte verfügen.  Jede Zugriffstaste verfügt über ein Standard\-`accelerator_view`\-Objekt.  Zusätzliche `accelerator_view`\-Objekte können erstellt werden.  
  
 Physische Geräte können für viele Clientthreads freigegeben werden.  Clientthreads können dasselbe `accelerator_view`\-Objekt einer Zugriffstaste kooperativ verwenden oder jeder Client kann mit einem Berechnungsgerät über ein unabhängiges `accelerator_view`\-Objekt zur Abgrenzung gegenüber anderen Clientthreads kommunizieren.  
  
 Für ein `accelerator_view`\-Objekt sind zwei [queuing\_mode\-Enumeration](../../../parallel/amp/reference/queuing-mode-enumeration.md)\-Status möglich.  Wenn der Queuingmodus `immediate` ist, werden Befehle wie `copy` und `parallel_for_each` an das entsprechende Zugriffstastengerät gesendet, sobald sie zum Aufrufer zurückkehren.  Wenn der Queuingmodus `deferred` ist, werden solche Befehle in die Warteschlange einer Befehlswarteschlange gestellt, die dem `accelerator_view`\-Objekt entspricht.  Die Befehle werden erst an das Gerät gesendet, wenn `flush()` aufgerufen wird.  
  
## Anforderungen  
 **Header:** amprt.h  
  
 **Namespace:** Nebenläufigkeit  
  
## Siehe auch  
 [Concurrency\-Namespace \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)