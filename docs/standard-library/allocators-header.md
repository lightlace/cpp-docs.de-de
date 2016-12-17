---
title: "&lt;allocators&gt;"
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
  - "stdext::<allocators>"
  - "allocators/stdext::allocators"
  - "<allocators>"
  - "stdext.<allocators>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "allocators-Header"
ms.assetid: 4393a607-4df8-4278-bbb2-c8ec52e60b83
caps.latest.revision: 19
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# &lt;allocators&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Definiert mehrere Vorlagen, die Speicherblöcken, für Knoten\-basierte Container unterstützen und freizugeben.  
  
## Syntax  
  
```  
#include <allocators>  
```  
  
## Hinweise  
 Die \<Zuweisungskopfzeile\> stellt sechs Zuweisungsvorlagen, die verwendet werden können, um Speicherverwaltungsstrategien für Knoten\-basierte Container auszuwählen.  Bei Verwendung mit diesen Vorlagen, stellt auch sie mehrere verschiedene Synchronisierungsfilter, um die Speicherverwaltungsstrategie zu einer Vielzahl verschiedener Multithreadingschemas anzupassen \(einschließlich keine\).  Die Anpassung einer Speicherverwaltungsstrategie mit der bekannten Speicherauslastungsmuster und der Synchronisierungsanforderungen, einer bestimmten Anwendung kann die Geschwindigkeit häufig erhöhen oder die Gesamtarbeitsspeicheranforderungen einer Anwendung verringern.  
  
 Die Zuweisungsvorlagen werden mit wiederverwendbaren Komponenten implementiert, die angepasst werden oder ersetzt werden können, um zusätzliche Speicherverwaltungsstrategien bereitzustellen.  
  
 Die Knoten\-basierten Container in der C\+\+\-Standardbibliothek \(std::list, std::set, std::multiset, std::map und std::multimap\) speichern ihre Elemente in den einzelnen Knoten.  Alle Knoten für einen bestimmten Containertyp sind die gleiche Größe, daher wird die Flexibilität eines allgemeinen Speicher\-Managers nicht benötigt.  Da die Größe eines Speicherblocks zur Kompilierzeit bekannt ist, kann der Speicher\-Manager viel einfacher sein und schneller.  
  
 Wenn sie mit Containern, die nicht Knoten\-basiert sind \(wie das C\+\+\-Standardbibliotheks\-Container std::vector std::deque und Std::basic\_string\) verwendet werden, verfügen die alllocator Vorlagen ordnungsgemäß, jedoch werden sich, keine Leistungsverbesserung über die Standardzuweisung bereitzustellen.  
  
 Eine Zuweisung ist eine Vorlagenklasse, die ein Objekt beschrieben wird, das Speicherzuweisung und Freigeben für Objekte und Objektarrays eines festgelegten Typ verwaltet.  Zuweisungsobjekte werden von mehreren Containervorlagenklassen in der C\+\+\-Standardbibliothek verwendet.  
  
 Die Zuweisungen sind alle Vorlagen dieses Typs:  
  
 `template<class`  `Type` `>`  
  
 `class allocator;`  
  
 wobei das Vorlagenargument `Type` der Typ ist, der durch die Zuweisungsinstanz verwaltet wird.  Die C\+\+\-Standardbibliothek enthält eine Vorlagenklasse Standardzuweisung, [Zuweisung](../standard-library/allocator-class.md), die in [\<memory\>](../standard-library/memory.md) definiert wird.  Die \<Zuweisungskopfzeile\> stellt die folgenden Zuweisungen:  
  
-   [allocator\_newdel](../standard-library/allocator-newdel-class.md)  
  
-   [allocator\_unbounded](../standard-library/allocator-unbounded-class.md)  
  
-   [allocator\_fixed\_size](../standard-library/allocator-fixed-size-class.md)  
  
-   [allocator\_variable\_size](../standard-library/allocator-variable-size-class.md)  
  
-   [allocator\_suballoc](../standard-library/allocator-suballoc-class.md)  
  
-   [allocator\_chunklist](../standard-library/allocator-chunklist-class.md)  
  
 Verwenden Sie eine entsprechende Instanziierung einer Zuweisung als zweites Typargument, wenn Sie einen Container, wie im folgenden Codebeispiel erstellen.  
  
 `#include <list>`  
  
 `#include <allocators>`  
  
 `std::list<int, stdext::allocators::allocator_chunklist<int> > _List0;`  
  
 \_List0 ordnet Knoten mit `allocator_chunklist` und dem Standardsynchronisierungsfilter zu.  
  
 Verwenden Sie das Makro [ALLOCATOR\_DECL](../Topic/ALLOCATOR_DECL%20\(%3Callocators%3E\).md), um Zuweisungsvorlagen mit Synchronisierungsfiltern Standardtrennzeichen abweichendes zu erstellen:  
  
 `#include <list>`  
  
 `#include <allocators>`  
  
 `ALLOCATOR_DECL(CACHE_CHUNKLIST, stdext::allocators::sync_per_thread, Alloc);`  
  
 `std::list<int, alloc<int> > _List1;`  
  
 \_Lst1 ordnet Knoten mit `allocator_chunklist` und der [synchronization\_per\_thread](../standard-library/sync-per-thread-class.md) Synchronisierungsfilter zu.  
  
 Eine Blocks\-Zuweisung ist ein Cache oder ein Filter.  Ein Cache ist eine Vorlagenklasse, die ein Argument std::size\_t Typ akzeptiert.  Er definiert eine Blocks\-Zuweisung Speicherblöcken, die einer einzelnen Größe zuordnet und freigibt.  Er muss Arbeitsspeicher mit dem Operator `new` abgerufen, aber er muss, keinen zusätzlichen Aufruf zu machen den Operator `new` für jeden Block.  Er kann, beispielsweise, suballocate von einem größeren Block oder Cache von freigegebenen Blöcke für nachfolgende Neuzuordnung.  
  
 Mit einem Compiler, der nicht kompilieren kann, binden Sie den Wert des verwendeten std::size\_t Arguments, als Vorlage instanziiert wurde, ist nicht unbedingt der Wert des Arguments \_Sz erneut Memberfunktionen eines Cache übergeben wird, zuordnen und freigeben.  
  
 \<Zuweisungen\> stellt die folgenden Cachevorlagen:  
  
-   [cache\_freelist](../standard-library/cache-freelist-class.md)  
  
-   [cache\_suballoc](../standard-library/cache-suballoc-class.md)  
  
-   [cache\_chunklist](../standard-library/cache-chunklist-class.md)  
  
 Ein Filter ist eine Blocks\-Zuweisung, deren Memberfunktionen mit einer anderen Blocks\-Zuweisung implementiert, die dorthin als Vorlagenargument übergeben wird.  Die häufigste Nutzungsform des Filters ist ein Synchronisierungsfilter, der eine Synchronisierungsrichtlinie anwenden, um Zugriff auf die Memberfunktionen einer Instanz einer anderen Blocks\-Zuweisung zu steuern. \<Zuweisungen\> stellt die folgenden Synchronisierungsfilter:  
  
-   [synchronization\_none](../standard-library/sync-none-class.md)  
  
-   [synchronization\_per\_container](../standard-library/sync-per-container-class.md)  
  
-   [synchronization\_per\_thread](../standard-library/sync-per-thread-class.md)  
  
-   [synchronization\_shared](../standard-library/sync-shared-class.md)  
  
 \<Zuweisungen\> stellt auch den Filter [rts\_alloc](../standard-library/rts-alloc-class.md), der mehrere Blocks\-Zuweisung als Generatorinstanziierung und bestimmt enthält, die einer Instanz, um für Zuordnungs\- oder Freigabe statt zur Kompilierzeit zur Laufzeit verwenden zu können.  Es wird mit Compilern verwendet, die nicht kompiliert können erneut binden.  
  
 Eine Synchronisierungsrichtlinie bestimmt z Instanzenhandles gleichzeitige Zuordnung einer Zuweisung und Freigabenanforderungen von mehreren Threads.  Die einfachste Richtlinie ist, alle Anforderungen nach dem zugrunde liegenden Cacheobjekt direkt übergeben und belässt Synchronisierungsverwaltung dem Benutzer.  Eine komplexere Richtlinie kann, einen Mutex zu verwenden sein, um Zugriff auf das zugrunde liegenden Cacheobjekt zu serialisieren.  
  
 Wenn ein Compiler die Kompilierung von Singlethreadanwendung und Multithreadanwendungen unterstützt, ist der Standardsynchronisierungsfilter für einfädige Anwendungen `sync_none`; für alle anderen Fällen ist es `sync_shared`.  
  
 Die Cachevorlage `cache_freelist` akzeptiert ein maximales Klassenargument, das die maximale Anzahl der bestimmt in der Liste der freien Blöcke zu speichernden Elemente.  
  
 \<Zuweisungen\> maximale stellt die folgenden Klassen:  
  
-   [max\_none](../standard-library/max-none-class.md)  
  
-   [max\_unbounded](../standard-library/max-unbounded-class.md)  
  
-   [max\_fixed\_size](../standard-library/max-fixed-size-class.md)  
  
-   [max\_variable\_size](../standard-library/max-variable-size-class.md)  
  
### Makros  
  
|||  
|-|-|  
|[ALLOCATOR\_DECL](../Topic/ALLOCATOR_DECL%20\(%3Callocators%3E\).md)|Ergibt eine Zuweisungsvorlagenklasse.|  
|[CACHE\_CHUNKLIST](../Topic/CACHE_CHUNKLIST%20\(%3Callocators%3E\).md)|Ergibt `stdext::allocators::cache_chunklist<sizeof(Type)>`.|  
|[CACHE\_FREELIST](../Topic/CACHE_FREELIST%20\(%3Callocators%3E\).md)|Ergibt `stdext::allocators::cache_freelist<sizeof(Type), max>`.|  
|[CACHE\_SUBALLOC](../Topic/CACHE_SUBALLOC%20\(%3Callocators%3E\).md)|Ergibt `stdext::allocators::cache_suballoc<sizeof(Type)>`.|  
|[SYNC\_DEFAULT](../Topic/SYNC_DEFAULT%20\(%3Callocators%3E\).md)|Ergibt einen Synchronisierungsfilter.|  
  
### Operatoren  
  
|||  
|-|-|  
|[Operator\!\=](../Topic/operator!=%20\(%3Callocators%3E\).md)|Es wird auf Ungleichheit zwischen Zuweisungsobjekten einer bestimmten Klasse getestet.|  
|[Operator\=\=](../Topic/operator==%20\(%3Callocators%3E\).md)|Es wird auf Gleichheit zwischen Zuweisungsobjekten einer bestimmten Klasse getestet.|  
  
### Klassen  
  
|||  
|-|-|  
|[allocator\_base](../standard-library/allocator-base-class.md)|Definiert die Basisklasse und Common funktioniert erforderlich, um eine benutzerdefinierte Zuordnung von einem Synchronisierungsfilter zu erstellen.|  
|[allocator\_chunklist](../standard-library/allocator-chunklist-class.md)|Beschreibt ein Objekt, das Speicherzuweisung und Freigeben für Objekte mithilfe eines Cache Typs [cache\_chunklist](../standard-library/cache-chunklist-class.md).|  
|[allocator\_fixed\_size](../standard-library/allocator-fixed-size-class.md)|Beschreibt ein Objekt, das Speicherzuweisung und Freigeben für Objekte des Typs `Type` mit einem Cache Typ [cache\_freelist](../standard-library/cache-freelist-class.md) mit einer Länge verwaltet, die durch [max\_fixed\_size](../standard-library/max-fixed-size-class.md) verwaltet wird.|  
|[allocator\_newdel](../standard-library/allocator-newdel-class.md)|Implementiert eine Zuweisung, die `operator delete` verwendet, um einen Speicherblock freizugeben und `operator new`, um einen Speicherblock zuzuordnen.|  
|[allocator\_suballoc](../standard-library/allocator-suballoc-class.md)|Beschreibt ein Objekt, das Speicherzuweisung und Freigeben für Objekte des Typs `Type` mit einem Cache Typs [cache\_suballoc](../standard-library/cache-suballoc-class.md).|  
|[allocator\_unbounded](../standard-library/allocator-unbounded-class.md)|Beschreibt ein Objekt, das Speicherzuweisung und Freigeben für Objekte des Typs `Type` mit einem Cache Typ [cache\_freelist](../standard-library/cache-freelist-class.md) mit einer Länge verwaltet, die durch [max\_unbounded](../standard-library/max-unbounded-class.md) verwaltet wird.|  
|[allocator\_variable\_size](../standard-library/allocator-variable-size-class.md)|Beschreibt ein Objekt, das Speicherzuweisung und Freigeben für Objekte des Typs `Type` mit einem Cache Typ [cache\_freelist](../standard-library/cache-freelist-class.md) mit einer Länge verwaltet, die durch [max\_variable\_size](../standard-library/max-variable-size-class.md) verwaltet wird.|  
|[cache\_chunklist](../standard-library/cache-chunklist-class.md)|Definiert eine Blocks\-Zuweisung Speicherblöcken, die einer einzelnen Größe zuordnet und freigibt.|  
|[cache\_freelist](../standard-library/cache-freelist-class.md)|Definiert eine Blocks\-Zuweisung Speicherblöcken, die einer einzelnen Größe zuordnet und freigibt.|  
|[cache\_suballoc](../standard-library/cache-suballoc-class.md)|Definiert eine Blocks\-Zuweisung Speicherblöcken, die einer einzelnen Größe zuordnet und freigibt.|  
|[freelist](../standard-library/freelist-class.md)|Verwaltet eine Liste von Speicherblöcken.|  
|[max\_fixed\_size](../standard-library/max-fixed-size-class.md)|Beschreibt ein maximales Klassenobjekt, das ein [freelist](../standard-library/freelist-class.md)\-Objekt einer festen maximale Länge eingeschränkt.|  
|[max\_none](../standard-library/max-none-class.md)|Beschreibt ein maximales Klassenobjekt, das ein [freelist](../standard-library/freelist-class.md)\-Objekt auf eine maximale Länge von null einschränkt.|  
|[max\_unbounded](../standard-library/max-unbounded-class.md)|Beschreibt ein maximales Klassenobjekt, das nicht die maximale Länge eines [freelist](../standard-library/freelist-class.md)\-Objekts beschränkt.|  
|[max\_variable\_size](../standard-library/max-variable-size-class.md)|Beschreibt ein maximales Klassenobjekt, das ein [freelist](../standard-library/freelist-class.md)\-Objekt auf eine maximale Länge eingeschränkt, die zur Anzahl von reservierten Speicherblöcken ungefähr proportional ist.|  
|[rts\_alloc](../standard-library/rts-alloc-class.md)|Die rts\_alloc Vorlagenklasse [Filter](../standard-library/allocators-header.md) beschreibt, die ein Array Cacheinstanzen enthält und bestimmt, die als eine Instanz, um für Zuordnungs\- und Freigabe statt zur Kompilierzeit zur Laufzeit verwenden zu können.|  
|[synchronization\_none](../standard-library/sync-none-class.md)|Beschreibt einen Synchronisierungsfilter, der keine Synchronisierung bietet.|  
|[synchronization\_per\_container](../standard-library/sync-per-container-class.md)|Beschreibt einen Synchronisierungsfilter, wofür ein separates Cacheobjekt für jedes Zuweisungsobjekt bereitstellt.|  
|[synchronization\_per\_thread](../standard-library/sync-per-thread-class.md)|Beschreibt einen Synchronisierungsfilter, wofür ein separates Cacheobjekt für jeden Thread enthält.|  
|[synchronization\_shared](../standard-library/sync-shared-class.md)|Beschreibt einen Synchronisierungsfilter, der einen Mutex verwendet, um Zugriff auf einen Cacheobjekt zu steuern, auf das alle Zuweisungen freigegeben wird.|  
  
## Anforderungen  
 Zuweisungen **Header:** \<\>  
  
 **Namespace:** stdext  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)