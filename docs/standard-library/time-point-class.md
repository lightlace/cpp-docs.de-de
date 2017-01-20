---
title: "time_point-Klasse"
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
  - "chrono/std::chrono::time_point"
dev_langs: 
  - "C++"
ms.assetid: 18be1e52-57b9-489a-8a9b-f58894f0aaad
caps.latest.revision: 10
caps.handback.revision: "4"
ms.author: "corob"
manager: "ghogen"
---
# time_point-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mit `time_point` wird ein Typ beschrieben, der einen bestimmten Zeitpunkt darstellt.  Er enthält ein Objekt des Typs [Dauer](../standard-library/duration-class.md), in dem die verstrichene Zeit seit der vom Vorlagenargument `Clock` dargestellten Epoche enthalten ist.  
  
## Syntax  
  
```  
template<  
   class Clock,  
   class Duration = typename Clock::duration  
>  
class time_point;  
```  
  
## Member  
  
### Öffentliche Typedefs  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|`time_point::clock`|Synonym für den Vorlagenparameter `Clock`.|  
|`time_point::duration`|Synonym für den Vorlagenparameter `Duration`.|  
|`time_point::period`|Synonym für den Namen `duration::period` des geschachtelten Typ.|  
|`time_point::rep`|Synonym für den Namen `duration::rep` des geschachtelten Typ.|  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[time\_point::time\_point\-Konstruktor](../Topic/time_point::time_point%20Constructor.md)|Erstellt ein `time_point`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[time\_point::max\-Methode](../Topic/time_point::max%20Method.md)|Gibt die Obergrenze für `time_point::ref` an.|  
|[time\_point::min\-Methode](../Topic/time_point::min%20Method.md)|Gibt die Untergrenze für `time_point::ref` an.|  
|[time\_point::time\_since\_epoch\-Methode](../Topic/time_point::time_since_epoch%20Method.md)|Gibt den gespeicherten `duration`\-Wert zurück.|  
  
### Öffentliche Operatoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[time\_point::operator\+\= Operator](../Topic/time_point::operator+=%20Operator.md)|Fügt der gespeicherten Dauer einen angegebenen Wert hinzu.|  
|[time\_point::operator\-\= Operator](../Topic/time_point::operator-=%20Operator.md)|Subtrahiert einen angegebenen Wert von der gespeicherten Dauer.|  
  
## Anforderungen  
 **Header:** chrono  
  
 **Namespace:** std::chrono  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono\>](../standard-library/chrono.md)