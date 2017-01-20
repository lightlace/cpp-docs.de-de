---
title: "combinable-Klasse"
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
  - "ppl/concurrency::combinable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "combinable-Klasse"
ms.assetid: fe0bfbf6-6250-47da-b8d0-f75369f0b5be
caps.latest.revision: 20
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# combinable-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Das `combinable<T>`\-Objekt ist dazu gedacht, threadprivate Kopien von Daten bereitzustellen, mit denen sperrenfreie, threadlokale Unterberechnungen in parallelen Algorithmen durchgeführt werden können.  Am Ende des Parallelvorgangs können die threadprivaten Unterbrechungen in einem Endergebnis zusammengeführt werden.  Diese Klasse kann anstelle einer freigegebenen Variable verwendet werden, und sie kann zu einer Leistungsverbesserung führen, wenn andernfalls Konflikte mit dieser freigegebenen Variable entstehen würden.  
  
## Syntax  
  
```  
template<  
   typename _Ty  
>  
class combinable;  
```  
  
#### Parameter  
 `_Ty`  
 Der Datentyp des endgültigen zusammengeführten Ergebnisses.  Der Typ muss über einen Kopier\- und einen Standardkonstruktor verfügen.  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[combinable::combinable\-Konstruktor](../Topic/combinable::combinable%20Constructor.md)|Überladen.  Erstellt ein neues `combinable`\-Objekt.|  
|[combinable::~combinable\-Destruktor](../Topic/combinable::~combinable%20Destructor.md)|Zerstört ein `combinable`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[combinable::clear\-Methode](../Topic/combinable::clear%20Method.md)|Löscht alle berechneten Zwischenergebnisse aus einer vorherigen Verwendung.|  
|[combinable::combine\-Methode](../Topic/combinable::combine%20Method.md)|Berechnet einen endgültigen Wert aus dem Satz lokaler Unterberechnungen im Thread, indem die bereitgestellte combine\-Funktion aufgerufen wird.|  
|[combinable::combine\_each\-Methode](../Topic/combinable::combine_each%20Method.md)|Berechnet einen endgültigen Wert aus dem Satz lokaler Unterberechnungen im Thread, indem die bereitgestellte combine\-Funktion einmal für jede lokale Unterberechnung im Thread aufgerufen wird.  Das Endergebnis wird vom Funktionsobjekt akkumuliert.|  
|[combinable::local\-Methode](../Topic/combinable::local%20Method.md)|Überladen.  Gibt einen Verweis auf die private Unterberechnung in einem Thread zurück.|  
  
### Öffentliche Operatoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[combinable::operator\=\-Operator](../Topic/combinable::operator=%20Operator.md)|Weist einem `combinable`\-Objekt von einem anderen `combinable`\-Objekt zu.|  
  
## Hinweise  
 Weitere Informationen finden Sie unter [Parallele Container und Objekte](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## Vererbungshierarchie  
 `combinable`  
  
## Anforderungen  
 **Header:** ppl.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)