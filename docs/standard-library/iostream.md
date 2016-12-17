---
title: "&lt;iostream&gt;"
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
  - "std.<iostream>"
  - "std::<iostream>"
  - "<iostream>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "iostream-Header"
ms.assetid: de5d39e1-7e77-4b55-bcd1-7c77b41515c8
caps.latest.revision: 23
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# &lt;iostream&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Deklariert Objekte, die das Auslesen und Schreiben in Standard\-Streams steuern.  Dies ist oftmals der einzige Header, den Sie aufnehmen müssen, um die Ein\- und Ausgabe aus einem C\+\+\-Programm auszuführen.  
  
## Syntax  
  
```  
  
#include <iostream>  
  
```  
  
## Hinweise  
 Die Objekte können in zwei Gruppen unterteilt werden:  
  
-   [cin](../Topic/cin.md), [cout](../Topic/cout.md), [cerr](../Topic/cerr.md) und [clog](../Topic/clog.md) sind byte\-orientiert, und führen konventionelle beitweise Übertragungen aus.  
  
-   [wcin](../Topic/wcin.md), [wcout](../Topic/wcout.md), [wcerr](../Topic/wcerr.md) und [clog](../Topic/wclog.md) sind breit ausgerichtet, und übersetzen aus und in Breitzeichen, die intern von der Anwendung intern bearbeitet werden.  
  
 Nachdem Sie bestimmte Operationen an einem Stream vornehmen, z. B. die Standardeingabe, können Sie keine Operationen für eine andere Ausrichtung für den gleichen Stream ausführen.  Aus diesem Grund kann ein Programm beispielsweise nicht gleichermaßen für [cin](../Topic/cin.md) und  [wcin](../Topic/wcin.md) ausgeführt werden.  
  
 Alle in diesem Header deklarierte Objekte besitzen eine spezielle Eigenschaft – Sie können davon ausgehen, dass sie erstellt werden, bevor Sie statische Objekte festlegen, in einer Übersetzungseinheit, die \< Iostream \> enthält.  Ebenso können Sie davon ausgehen, dass diese Objekte nicht verworfen werden, bevor Sie die Destruktoren für statische Objekte definieren.  \(Die Ausgabe\-Streams werden jedoch während der Beendigung des Programms geleert\). Aus diesem Grund können Sie Standardstream vor Programmstart oder nach Beendigung des Programms sicher auslesen oder darin schreiben.  
  
 Diese Garantie ist jedoch nicht universell.  Ein statischer Konstruktor kann eine Funktion in einer anderen Übersetzungseinheit aufrufen.  Die aufgerufene Funktion kann nicht davon ausgehen, dass die Objekte in diesem Header erstellt wurden, angesichts der unsicheren Reihenfolge, in der die Übersetzungseinheiten an dieser statischen Konstruktion teilnehmen.  Um diese Objekte in diesem Zusammenhang zu verwenden, müssen Sie zuerst ein Objekt der Klasse [ios\_base:: Init](../Topic/ios_base::Init.md) erstellen.  
  
### Globale Streamobjekte  
  
|||  
|-|-|  
|[cerr](../Topic/cerr.md)|Gibt den globalen `cerr`\-Stream an.|  
|[cin](../Topic/cin.md)|Gibt den globalen `cin`\-Stream an.|  
|[clog](../Topic/clog.md)|Gibt den globalen `clog`\-Stream an.|  
|[cout](../Topic/cout.md)|Gibt den globalen `cout`\-Stream an.|  
|[wcerr](../Topic/wcerr.md)|Gibt den globalen `wcerr`\-Stream an.|  
|[wcin](../Topic/wcin.md)|Gibt den globalen `wcin`\-Stream an.|  
|[wclog](../Topic/wclog.md)|Gibt den globalen `wclog`\-Stream an.|  
|[wcout](../Topic/wcout.md)|Gibt den globalen `wcout`\-Stream an.|  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream\-Programmierung](../standard-library/iostream-programming.md)   
 [iostreams\-Konventionen](../standard-library/iostreams-conventions.md)