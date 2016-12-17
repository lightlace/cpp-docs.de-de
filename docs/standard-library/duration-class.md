---
title: "duration-Klasse"
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
  - "chrono/std::chrono::duration"
dev_langs: 
  - "C++"
ms.assetid: 06b863b3-65be-4ded-a72e-6e1eb1531077
caps.latest.revision: 10
caps.handback.revision: "4"
ms.author: "corob"
manager: "ghogen"
---
# duration-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt einen Typ, der ein *Zeitintervall* enthält, bei dem es sich um die verstrichene Zeit zwischen zwei Situationen handelt.  
  
## Syntax  
  
```  
template<  
   class Rep,  
   class Period = ratio<1>  
>  
class duration;  
template<  
   class Rep,  
   class Period  
>  
class duration;  
template<  
   class Rep,  
   class Period1,  
   class Period2  
>  
class duration  
   <duration<Rep, Period1>, Period2>;  
```  
  
## Hinweise  
 Mit dem Vorlagenargument `Rep` wird der Typ beschrieben, der zum Aufnehmen der Anzahl von Zeiteinheiten im Intervall verwendet wird.  Das Vorlagenargument `Period` ist eine Instanziierung von [ratio](../standard-library/ratio.md), mit dem die Größe des von jedem Takt dargestellten Intervalls beschrieben wird.  
  
## Member  
  
### Öffentliche Typedefs  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[duration::period Typedef](assetId:///ebf2a1b9-769f-475f-8c66-cf9ed12015f2)|Stellt ein Synonym für den Vorlagenparameter `Period` dar.|  
|[duration::rep Typedef](assetId:///f47b8abb-ae2c-4dc8-858a-f44695156950)|Stellt ein Synonym für den Vorlagenparameter `Rep` dar.|  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[duration::duration\-Konstruktor](../Topic/duration::duration%20Constructor.md)|Erstellt ein `duration`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[duration::count\-Methode](../Topic/duration::count%20Method.md)|Gibt die Anzahl von Zeiteinheiten im Zeitintervall zurück.|  
|[duration::max\-Methode](../Topic/duration::max%20Method.md)|Statisch  Gibt den maximal zulässigen Wert des Vorlagenparameters `Ref` zurück.|  
|[duration::min\-Methode](../Topic/duration::min%20Method.md)|Statisch  Gibt den niedrigsten zulässigen Wert des Vorlagenparameters `Ref` zurück.|  
|[duration::zero\-Methode](../Topic/duration::zero%20Method.md)|Statisch  Tatsächlich wird `Rep`\(0\) zurückgegeben.|  
  
### Öffentliche Operatoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[duration::operator\- Operator](../Topic/duration::operator-%20Operator.md)|Gibt eine Kopie des `duration`\-Objekts zusammen mit einer negierten Taktanzahl zurück.|  
|[duration::operator\-\- Operator](../Topic/duration::operator--%20Operator.md)|Verringert die gespeicherte Taktanzahl.|  
|[duration::operator\= Operator](../Topic/duration::operator=%20Operator.md)|Reduziert die gespeicherte Taktanzahl\-Modulo um einen angegebenen Wert.|  
|[duration::operator\*\= Operator](../Topic/duration::operator*=%20Operator.md)|Multipliziert die gespeicherte Taktanzahl mit einem angegebenen Wert.|  
|[duration::operator\/\= Operator](../Topic/duration::operator-=%20Operator1.md)|Dividiert die gespeicherte Taktanzahl durch die Taktanzahl eines angegebenen `duration`\-Objekts.|  
|[duration::operator\+ Operator](../Topic/duration::operator+%20Operator.md)|Gibt `*this` zurück.|  
|[duration::operator\+\+ Operator](../Topic/duration::operator++%20Operator.md)|Erhöht die gespeicherte Taktanzahl.|  
|[duration::operator\+\= Operator](../Topic/duration::operator+=%20Operator.md)|Fügt der gespeicherten Taktanzahl die Taktanzahl eines angegebenen `duration`\-Objekts hinzu.|  
|[duration::operator\-\= Operator](../Topic/duration::operator-=%20Operator2.md)|Subtrahiert die Taktanzahl eines angegebenen `duration`\-Objekts von der gespeicherten Taktanzahl.|  
  
## Anforderungen  
 **Header:** chrono  
  
 **Namespace:** std::chrono  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono\>](../standard-library/chrono.md)   
 [duration\_values\-Struktur](../standard-library/duration-values-structure.md)