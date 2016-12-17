---
title: "C++-Bibliothekskonventionen"
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
  - "Klassen [C++]"
  - "Codekonventionen, C++-Standardbibliothek"
  - "Konventionen [C++], C++-Standardbibliothek"
  - "Funktionsnamen [C++]"
  - "Funktionen [C++], Bibliotheks-Benennungskonventionen"
  - "Benennungskonventionen [C++], C++-Bibliothek"
  - "Benennungskonventionen [C++], C++-Standardbibliothek"
  - "C++-Standardbibliothek, Konventionen"
ms.assetid: bf41b79a-2d53-4f46-8d05-779358335146
caps.latest.revision: 9
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# C++-Bibliothekskonventionen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die C\+\+\-Bibliothek entspricht viel die gleichen Konventionen wie der C\-Standardbibliothek, sowie einige, die hier beschriebenen.  
  
 Eine Implementierung enthält bestimmte Breite in, wie diese Typen und Funktionen in der C\+\+\-Bibliothek deklariert:  
  
-   Namen der Funktionen in der C\-Standardbibliothek haben möglicherweise entweder extern \# " C\+\+" oder externen C" binden.  Schließen Sie die entsprechende Standard\-C\-Kopfzeile anstatt deklarieren eine Bibliotheksentität inline ein.  
  
-   Ein Memberfunktionsname in einer Bibliothek hat möglicherweise Zusatzfunktionsunterzeichnungen über denen, die in diesem Dokument aufgeführten.  Sie können sicherstellen, dass ein Funktionsaufruf, der hier beschriebenen, sich wie erwartet verhält, aber Sie können die Adresse einer Bibliotheksmemberfunktion nicht zuverlässig nehmen. \(Der Typ möglicherweise ist nicht, was Sie erwarten.\)  
  
-   Eine Bibliothek verfügt möglicherweise nicht dokumentierten \(nicht virtuelle Basisklassen\).  Eine Klasse, die dokumentiert wird, wie von einer anderen Klasse abgeleitete, tatsächlich wird von dieser Klasse durch andere nicht dokumentierten Klassen abgeleitet werden.  
  
-   Ein Typ, der als Synonym für einen ganzzahligen Typ definiert wird, kann der gleiche ist, das einer binden ganzzahligen eingibt.  
  
-   Ein Bitmaskentyp kann als jedes implementiert werden ein ganzzahliger Typ oder Enumeration.  In beiden Fällen können Sie bitweisen Operationen \(wie `AND` und `OR`\) für Werte des gleichen Bitmaskentyps ausführen.  Die Elemente `A` und `B` eines Bitmaskentyps sind Werte ungleich 0 \(null\) so, dass `A` &`B` ist.  
  
-   Eine Bibliotheksfunktion, die Ausnahmespezifikationen keine enthält, kann eine beliebige, Ausnahme auslösen, sofern ihre Definition eindeutig eine solche Möglichkeit einschränkt.  
  
 Umgekehrt gibt es einige Beschränkungen:  
  
-   Die C\-Standardbibliothek verwendet keine maskierenden Makros.  Nur Signaturen der angegebenen Funktion werden, nicht jedoch die Namen der Funktionen selbst reserviert.  
  
-   Ein Bibliotheksfunktionsname außerhalb einer Klasse hat nicht zusätzliche, nicht dokumentiert, Funktionssignaturen.  Sie können die Adresse zuverlässig nehmen.  
  
-   Basisklassen und Memberfunktionen beschriebenes so virtuelles sicherlich sind virtuell, wie jene, die beschrieben werden wie nicht virtuell, sicherlich nicht virtuell sind.  
  
-   Zwei Typen, die von der C\+\+\-Bibliothek definiert werden, sind immer unterscheiden, es sei denn, dass dieses Dokument explizit andernfalls vorsieht.  
  
-   Die Funktionen, die durch die Bibliothek, einschließlich der Standardversionen von austauschbaren Funktionen angegeben werden, können diese Ausnahmen *höchstens* auslösen, die in beliebiger Ausnahmespezifikation aufgeführt werden.  keine Destruktoren, die durch die Bibliothek angegeben sind, lösen Ausnahmen aus.  Funktionen in der C\-Standardbibliothek weitergeben eine Ausnahme, wie wenn `qsort` eine Vergleichsfunktion aufruft, die eine Ausnahme auslöst, jedoch andernfalls nicht lösen Ausnahmen aus.  
  
## Siehe auch  
 [STL\-Übersicht](../standard-library/cpp-standard-library-overview.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)