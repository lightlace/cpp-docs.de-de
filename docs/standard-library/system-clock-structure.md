---
title: "system_clock-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "chrono/std::chrono::system_clock"
dev_langs: 
  - "C++"
ms.assetid: a97bd46e-267a-4836-9f7d-af1f664e99ae
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# system_clock-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellt einen auf der Echtzeituhr des Systems basierten *Uhrtyp* dar.  
  
## Syntax  
  
```  
struct system_clock;  
```  
  
## Hinweise  
 Ein *Uhrtyp* wird zum Abrufen der aktuellen Zeit \(UTC\) verwendet.  Der Typ stellt eine Instanziierung von [duration](../standard-library/duration-class.md) und der Klassenvorlage [time\_point](../standard-library/time-point-class.md) dar und definiert eine statische `now()`\-Memberfunktion, mit der die Zeit zurückgegeben wird.  
  
 Eine Uhr ist *monoton,*, wenn der von einem ersten Aufruf von `now()` zurückgegebene Wert immer kleiner oder gleich dem Wert ist, der über einen nachfolgenden Aufruf von `now()` zurückgegeben wird.  
  
 Eine Uhr ist *gleichmäßig*, wenn sie *monoton* und die Zeit zwischen den Teilstrichen konstant ist.  
  
 In dieser Implementierung, ist `system_clock` mit `high_resolution_clock` synonym.  
  
## Mitglieder  
  
### Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|------------------|  
|`system_clock::duration`|Ein Synonym für `duration<rep, period>`.|  
|`system_clock::period`|Ein Synonym für den Typ, der zum Darstellen der Teilstrichperiode in der enthaltenden Instanziierung von `duration` verwendet wird.|  
|`system_clock::rep`|Ein Synonym für den Typ zum Darstellen der Anzahl von Zeiteinheiten in der enthaltenden Instanziierung von `duration` verwendet wird.|  
|`system_clock::time_point`|Ein Synonym für `time_point<Clock, duration>`, wobei `Clock` entweder ein Synonym für den Uhrtyp selbst oder einen anderen Uhrtyp ist, der auf der gleichen Epoche basiert und über den gleichen geschachtelten `duration`\-Typ verfügt.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[system\_clock::from\_time\_t\-Methode](../Topic/system_clock::from_time_t%20Method.md)|Statisch  Gibt einen `time_point` zurück, der einer bestimmten Zeit am besten entspricht.|  
|[system\_clock::now\-Methode](../Topic/system_clock::now%20Method.md)|Statisch  Gibt die aktuelle Uhrzeit zurück.|  
|[system\_clock::to\_time\_t\-Methode](../Topic/system_clock::to_time_t%20Method.md)|Statisch  Gibt ein `time_t`\-Objekt zurück, das einer bestimmten `time_point` am besten entspricht.|  
  
### Öffentliche Konstanten  
  
|Name|Beschreibung|  
|----------|------------------|  
|[system\_clock::is\_monotonic\-Konstante](../Topic/system_clock::is_monotonic%20Constant.md)|Gibt an, ob der Uhrtyp monoton ist.|  
|[system\_clock::is\_steady Constant](../Topic/system_clock::is_steady%20Constant.md)|Gibt an, ob der Uhrtyp gleichmäßig ist.|  
  
## Anforderungen  
 **Header:** chrono  
  
 **Namespace:** std::chrono  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono\>](../standard-library/chrono.md)   
 [steady\_clock\-Struktur](../standard-library/steady-clock-struct.md)