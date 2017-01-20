---
title: "packaged_task-Klasse"
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
  - "future/std::packaged_task"
dev_langs: 
  - "C++"
ms.assetid: 0a72cbe3-f22a-4bfe-8e50-dcb268c98780
caps.latest.revision: 9
caps.handback.revision: "3"
ms.author: "corob"
manager: "ghogen"
---
# packaged_task-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt einen *asynchronen Anbieter,* der ein Aufrufswrapper ist, dessen Aufrufsunterzeichnung `Ty(ArgTypes...)` ist.  Der *zugeordnete asynchrone Zustand* enthält eine Kopie seines aufrufbaren Objekts zusätzlich zum beliebigen Ergebnis.  
  
## Syntax  
  
```  
template<class>  
class packaged_task;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[packaged\_task::packaged\_task\-Konstruktor](../Topic/packaged_task::packaged_task%20Constructor.md)|Erstellt ein `packaged_task`\-Objekt.|  
|[packaged\_task::~packaged\_task\-Destruktor](../Topic/packaged_task::~packaged_task%20Destructor.md)|Zerstört ein `packaged_task`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[packaged\_task::get\_future\-Methode](../Topic/packaged_task::get_future%20Method.md)|[Zukunft](../standard-library/future-class.md) Gibt ein Objekt zurück, das denselben zugeordneten asynchronen Zustand hat.|  
|[packaged\_task::make\_ready\_at\_thread\_exit\-Methode](../Topic/packaged_task::make_ready_at_thread_exit%20Method.md)|Ruft das aufrufbare Objekt, das im zugeordneten asynchronen Zustand gespeichert wird auf und speichert atomar den zurückgegebenen Wert.|  
|[packaged\_task::reset\-Methode](../Topic/packaged_task::reset%20Method.md)|Ersetzt den zugeordneten asynchronen Zustand.|  
|[packaged\_task::swap\-Methode](../Topic/packaged_task::swap%20Method.md)|Vertauscht den zugeordneten Zustand mit dem asynchronen eines bestimmten Objekts aus.|  
|[packaged\_task::valid\-Methode](../Topic/packaged_task::valid%20Method.md)|Gibt an, ob das Objekt einen zugeordneten asynchronen Zustand hat.|  
  
### Öffentliche Operatoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[packaged\_task::operator\= Operator](../Topic/packaged_task::operator=%20Operator.md)|Überträgt einen zugeordneten asynchronen Zustand von einem angegebenen Objekt.|  
|[packaged\_task::operator\(\) Operator](../Topic/packaged_task::operator\(\)%20Operator.md)|Ruft das aufrufbare Objekt, das im zugeordneten asynchronen Zustand gespeichert wird, speichert atomar den zurückgegebenen Wert und setzt den Zustand, um *vorzubereiten* auf.|  
|[packaged\_task::operator bool Operator](../Topic/packaged_task::operator%20bool%20Operator.md)|Gibt an, ob das Objekt einen zugeordneten asynchronen Zustand hat.|  
  
## Anforderungen  
 **Header:** future  
  
 **Namespace:** std  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<future\>](../standard-library/future.md)