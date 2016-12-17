---
title: "Verwenden von C++-Bibliotheksheadern"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Kopfzeilen"
  - "Kopfzeilen, Benennung in C++-Include-Direktive"
  - "Kopfzeilen, C++-Standardbibliothek"
  - "INCLUDE-Direktive"
  - "Bibliothek-Header"
  - "C++-Standardbibliothek, Kopfzeilen"
  - "Standard-Header in C++"
ms.assetid: a36e889e-1af2-4cd9-a211-bfc7a3fd8e85
caps.latest.revision: 10
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Verwenden von C++-Bibliotheksheadern
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie schließen den Inhalt einer Standardheader ein, indem Sie sie in einer benennen.  
  
```  
#include <iostream>   // include I/O facilities  
```  
  
 Fügen Sie die Standardheader Sie können in jeder Reihenfolge mehrmals einschließen, einen Standardheader, oder mindestens zwei Standardkopfzeilen, die dasselbe Makro oder gleich definieren, geben ein.  Schließen Sie keine Standardheader in einer Deklaration ein.  Definieren Sie keine Makros, die dieselben Namen, die Schlüsselwörter, bevor Sie einen Standardheader einschließen.  
  
 Bibliothekskopfzeile eine C\+\+\-Headerdatei schließt alle anderen C\+\+\-Bibliothekskopfzeilen ein, die die erforderliche Typen definieren muss. \(Stellen sind explizit alle C\+\+\-Bibliothekskopfzeilen erfordert in einer Übersetzungseinheit jedoch aus Angst falsch, dass Sie über die tatsächlichen Abhängigkeiten schätzen.\) Eine Standard\-C\-Kopfzeile enthält niemals eine andere Standardheader ein.  Eine Standardheader deklariert oder definiert nur die Entitäten, die für diese in diesem Dokument beschriebenen.  
  
 Jede Funktion in der Bibliothek wird in einer Standardheader deklariert.  Anders als in Standard\-C stellt die Standardheader nie ein maskierendes Makro mit dem Namen der Funktion, die die Funktionsdeklaration maskiert und dieselben Auswirkungen erreicht.  Weitere Informationen zum Maskieren von Makros, finden Sie unter [C\+\+\-Bibliothekskonventionen](../standard-library/cpp-library-conventions.md).  
  
 Alle Namen als `operator delete` und `operator new` in den C\+\+\-Bibliothekskopfzeilen werden im `std`\-Namespace oder in einem Namespace definiert, der sich innerhalb des `std` geschachtelt. Namespace  Sie verweisen auf den Namen beispielsweise `cin` als `std::cin` an.  Beachten Sie jedoch dass Makronamen nicht für Namespacequalifikation sind, das Sie schreiben immer `__STD_COMPLEX` ohne einen Namespacequalifizierer.  
  
 In einigen Übersetzungsumgebung einschließlich Bibliothekskopfzeile einer C\+\+ kann die externen Namen herausheben, die ebenfalls im Namespace `std` im globalen Namespace, mit einzelnen `using`\-Deklarationen für jeden der Namen deklariert werden.  Andernfalls stellt die Header Bibliotheksnamen keine in den aktuellen Namespace vor.  
  
 Der C\+\+\-Standard erfordert, dass die C\-Standardkopfzeilen alle externen Namen im `std` deklarieren, dann werden sie in den globalen Namespace mit Personen `using`\-Deklarationen für die Namen aus.  Aber in einer Übersetzungsumgebung schließen die C\-Standardkopfzeilen keine Namespacedeklarationen ein und deklarieren alle Namen direkt im globalen Namespace.  Daher ist die portabelste Methode, Namespaces zu begegnen, zwei Regeln befolgen:  
  
-   Um im `std` zu deklarieren sicherlich schließen ein externer Name der normalerweise in \<stdlib.h beispielsweise\>deklariert wird das cstdlib \<Header.\>  Kenntnis Sie, dass der Name möglicherweise auch im globalen Namespace deklariert wird.  
  
-   Um im globalen Namespace einen externen Namen sicherlich zu deklarieren, der in \<stdlib.h deklariert wird, schließen Sie\>den Header stdlib.h \<direkt\> ein.  Kenntnis Sie, dass der Name möglicherweise auch im `std` deklariert wäre.  
  
 Wenn Sie `std::abort` aufrufen möchten, nicht ordnungsgemäß beendet zur Folge haben, sollten Sie cstdlib \>einschließen \<.  Wenn Sie `abort` aufrufen möchten, sollten Sie stdlib.h \<einschließen.\>  
  
 Alternativ können Sie eine Deklaration schreiben:  
  
```  
using namespace std;  
```  
  
 Bibliotheksnamen das alle im aktuellen Namespace öffnet.  Wenn Sie z dieser Deklaration sofort schließlich schreiben, markieren Sie die Namen in den globalen Namespace aus.  Sie können Namespaceüberlegungen im Rest der Übersetzungseinheit anschließend ignorieren.  Sie vermeiden auch die meisten Unterschiede über unterschiedliche Übersetzungsumgebung.  
  
 Sofern, dass ausdrücklich angegeben, definieren Sie möglicherweise keine Namen im `std`\-Namespace oder einem Namespace, der im Namespace `std`, innerhalb des Programms geschachtelt wird.  
  
## Siehe auch  
 [STL\-Übersicht](../standard-library/cpp-standard-library-overview.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)