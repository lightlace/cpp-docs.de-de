---
title: "Gewusst wie: Verbessern der Arbeitsspeicherleistung mithilfe von Alloc und Free | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Alloc und Free, Verwenden [Concurrency Runtime]"
  - "Verwenden von Alloc und Free [Concurrency Runtime]"
ms.assetid: e1fab9e8-a97d-4104-bead-e95958db79f9
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Gewusst wie: Verbessern der Arbeitsspeicherleistung mithilfe von Alloc und Free
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Dokument wird gezeigt, wie sich mit der [concurrency::Alloc](../Topic/Alloc%20Function.md)\-Funktion und der [concurrency::Free](../Topic/Free%20Function.md)\-Funktion die Arbeitsspeicherleistung steigern lässt.  In ihm wird die Zeit verglichen, die erforderlich ist, um die Elemente eines Arrays parallel für drei verschiedene Typen umzukehren, für die jeweils die Operatoren `new` und `delete` angegeben sind.  
  
 Die Funktionen `Alloc` und `Free` sind besonders dann nützlich, wenn mehrere Threads häufig sowohl `Alloc` als auch `Free` aufrufen.  Die Laufzeit besitzt für jeden Thread einen separaten Arbeitsspeichercache. Aus diesem Grund verwaltet die Laufzeit Arbeitsspeicher, ohne dabei Sperren oder Arbeitsspeicherbarrieren zu verwenden.  
  
## Beispiel  
 Das folgende Beispiel zeigt drei Typen, die jeweils über die Operatoren `new` und `delete` verfügen.  Von der `new_delete`\-Klasse werden die globalen Operatoren `new` und `delete` verwendet, von der `malloc_free`\-Klasse die C\-Laufzeitfunktionen [malloc](../../c-runtime-library/reference/malloc.md) und [free](../../c-runtime-library/reference/free.md) sowie von der `Alloc_Free`\-Klasse die Concurrency Runtime\-Funktionen `Alloc` und `Free`.  
  
 [!CODE [concrt-allocators#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-allocators#1)]  
  
## Beispiel  
 Im folgenden Beispiel werden die Funktionen `swap` und `reverse_array` dargestellt.  Die `swap`\-Funktion tauscht den Inhalt des Arrays bei den angegebenen Indizes aus.  Sie weist Speicher vom Heap für die temporäre Variable zu.  Die `reverse_array`\-Funktion erstellt ein großes Array und berechnet die Zeit, die erforderlich ist, um dieses Array mehrmals parallel umzukehren.  
  
 [!CODE [concrt-allocators#2](../CodeSnippet/VS_Snippets_ConcRT/concrt-allocators#2)]  
  
## Beispiel  
 Im folgenden Beispiel wird die `wmain`\-Funktion angezeigt, mit der man die Zeit berechnet, die erforderlich ist, damit die `reverse_array`\-Funktion auf die Typen `new_delete`, `malloc_free` und `Alloc_Free` reagiert, von denen jeweils ein anderes Speicherbelegungsschema verwendet wird.  
  
 [!CODE [concrt-allocators#3](../CodeSnippet/VS_Snippets_ConcRT/concrt-allocators#3)]  
  
## Beispiel  
 Im Folgenden finden Sie das vollständige Beispiel.  
  
 [!CODE [concrt-allocators#4](../CodeSnippet/VS_Snippets_ConcRT/concrt-allocators#4)]  
  
 In diesem Beispiel wird folgende Beispielausgabe für einen Computer mit vier Prozessoren erzeugt.  
  
  **Took 2031 ms with new\/delete.**  
**Took 1672 ms with malloc\/free.**  
**Took 656 ms with Alloc\/Free.** In diesem Beispiel stellt der Typ, der die Funktionen `Alloc` und `Free` verwendet, die beste Arbeitsspeicherleistung bereit, da die Funktionen `Alloc` und `Free` zum häufigen Zuordnen und Befreien von Speicherblöcken von mehreren Threads optimiert werden.  
  
## Kompilieren des Codes  
 Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio\-Projekt ein. Alternativ dazu können Sie ihn auch in eine Datei mit dem Namen `allocators.cpp` einfügen und dann folgenden Befehl in einem Visual Studio\-Eingabeaufforderungsfenster ausführen.  
  
 **cl.exe \/EHsc allocators.cpp**  
  
## Siehe auch  
 [Speicherverwaltungsfunktionen](../../parallel/concrt/memory-management-functions.md)   
 [Alloc\-Funktion](../Topic/Alloc%20Function.md)   
 [Free\-Funktion](../Topic/Free%20Function.md)