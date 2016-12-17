---
title: "2.3 parallel Construct"
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
ms.assetid: 190eacdf-2c16-4c06-8cb7-ac60eb211425
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# 2.3 parallel Construct
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die folgende Direktive definieren einen parallelen Bereichs, der ein Bereich des Programms ist, das durch mehrere Threads parallel ausgeführt werden soll.  Dies ist das grundlegende Konstrukt, das die parallele Ausführung beginnt.  
  
```  
#pragma omp parallel [clause[ [, ]clause] ...] new-line  
   structured-block  
```  
  
 Die *Klausel* ist eine der folgenden Aktionen aus:  
  
 **\(falls** *Ausdruck* **\)**  
  
 **\(privat**Variable*Liste***\)**  
  
 **\(firstprivate**Variable*Liste***\)**  
  
 **default \(Shared &#124; keine\)**  
  
 **\(Shared**Variable*Liste***\)**  
  
 **\(copyin**Variable*Liste***\)**  
  
 *Operator* **\(Verringerung :**  *Variable Liste* **\)**  
  
 **\(num\_threads**Zahl*Ausdruck***\)**  
  
 Wenn ein Thread ein paralleles Konstrukt entdeckt, wird ein Team von Threads erstellt, wenn einer der folgenden Fälle zutrifft:  
  
-   Keine **If**\-Klausel vorhanden ist.  
  
-   Der **If** Ausdruck wird auf einen Wert ungleich 0 \(null\) aus.  
  
 Dieser Thread wird der Masterthread des Teams mit einer Zahl von 0 Threads sowie alle Threads im Team, einschließlich des Masterthread, führen den Bereich parallel aus.  Wenn der Wert des **If** Ausdrucks \(null\) ist, wird der Bereich serialisiert.  
  
 Um die Anzahl der Threads zu ermitteln, die angefordert werden, werden die folgenden Regeln in der angegebenen Reihenfolge betrachtet.  Die erste Regel, deren Bedingung erfüllt ist, wird:  
  
1.  Wenn die **num\_threads**\-Klausel vorhanden ist, ist der ganzzahlige Wert des Ausdrucks, der die Anzahl der angeforderten Threads.  
  
2.  Wenn die **omp\_set\_num\_threads** Bibliotheksfunktion aufgerufen wurde, ist der Wert des Arguments des zuletzt ausgeführten Aufruf die Anzahl der angeforderten Threads.  
  
3.  Wenn die Umgebungsvariable **OMP\_NUM\_THREADS** definiert ist, ist der Wert dieser Umgebungsvariablen die Anzahl der angeforderten Threads.  
  
4.  Wenn keiner der oben beschriebenen Methoden verwendet wurden, wird die Anzahl der angeforderten Implementierung\-definiert Threads.  
  
 Wenn die **num\_threads**\-Klausel vorhanden ist, wird die Anzahl der Threads ab, die von der **omp\_set\_num\_threads** Bibliotheksfunktion oder die **OMP\_NUM\_THREADS** Umgebungsvariable nur für den parallelen Bereich angefordert werden, den sie angewendet wird.  Der nächste parallele Bereiche werden durch sie nicht betroffen.  
  
 Die Anzahl von Threads, die den parallelen Bereichs ebenfalls ausgeführt werden, hängt auf ab, ob dynamische Anpassung der Anzahl von Threads aktiviert ist.  Wenn dynamische Anpassung deaktiviert ist, verhält sich die angeforderte Anzahl von Threads den parallelen Bereich aus.  Wenn dynamische Anpassung dann aktiviert ist, ist die angeforderte Anzahl von Threads die maximale Anzahl von Threads, die möglicherweise den parallelen Bereich ausführen.  
  
 Wenn ein paralleler Bereich auftritt, während dynamische Anpassung der Anzahl von Threads deaktiviert ist und die Anzahl der Threads, die für den parallelen Bereich angefordert werden, die Zahl übersteigt, die das Laufzeitsystem bereitstellen kann, wird das Verhalten des Programms Implementierung\-definiert.  Eine Implementierung führt möglicherweise zum Beispiel die Ausführung des Programms serialisiert, oder sie kann den parallelen Bereich.  
  
 Die **omp\_set\_dynamic** Bibliotheksfunktion und die **OMP\_DYNAMIC** Umgebungsvariablen können verwendet werden, um dynamische Anpassung der Anzahl von Threads zu aktivieren und zu deaktivieren.  
  
 Die Anzahl der physischen Prozessoren, welche Threads tatsächlich zu einem bestimmten Zeitpunkt hosten, wird Implementierung\-definiert.  Sobald erstellt wird, bleibt die Anzahl der Threads im Team für die Dauer des parallelen Bereichs konstant.  Sie können entweder vom Benutzer oder automatisch vom Laufzeitsystem eines parallelen Bereichs explizit in eine andere geändert werden.  
  
 Die Anweisungen, die innerhalb des dynamischen Wertebereichs eines parallelen Bereichs enthalten sind, werden durch jeden Thread ausgeführt, und jeder Thread kann einen Pfad von Anweisungen aus, der für die anderen Threads verschieden ist.  Die Direktive, die außerhalb des lexikalischen Wertebereichs eines parallelen Bereichs aufgetreten sind, werden als verwaiste Direktive.  
  
 Es gibt eine implizite Grenze am Ende eines parallelen Bereichs.  Nur der Masterthread des Teams wird die Ausführung am Ende eines parallelen Bereichs fort.  
  
 Wenn ein Thread in einem Team, das einen parallelen Bereich ausgeführt werden, parallel ein anderes Konstrukt entdeckt, stellt er ein neues Team erstellt, und es wird dem Master\- dieses neuen Teams.  Geschachtelte parallele Bereiche sind standardmäßig serialisiert.  Folglich wird standardmäßig ein geschachtelter parallelen Bereich von einem Team ausgeführt, das aus einem Thread besteht.  Das Standardverhalten wird geändert werden, indem entweder die Ablaufzeit bibliotheksfunktion **omp\_set\_nested** oder die Umgebungsvariable **OMP\_NESTED**verwendet.  Allerdings wird die Anzahl von Threads in einem Team, die einen geschachtelten parallelen Bereich ausführen, Implementierung\-definiert.  
  
 Einschränkungen für **Ähnlichkeit**\-Direktive lauten wie folgt:  
  
-   Höchstens kann eine **If**\-Klausel in der Direktive angezeigt werden.  
  
-   Sie ist ob alle Nebeneffekte in Unspecified, wenn Ausdruck oder **num\_threads** Ausdruck auftreten.  
  
-   **Wurf** , das sich innerhalb eines parallelen Bereichs ausgeführt wird, muss dazu führen, dass die Ausführung innerhalb des dynamischen Wertebereichs desselben strukturierten Block fortgesetzt, und er muss vom gleichen Thread abgefangen werden, der die Ausnahme ausgelöst hat.  
  
-   Nur eine einzige **num\_threads**\-Klausel kann in der Direktive angezeigt werden.  Der Ausdruck wird **num\_threads** außerhalb des Kontexts des parallelen Bereichs ausgewertet und muss auf einen positiven ganzzahligen Wert ausgewertet werden.  
  
-   Die Reihenfolge der Auswertung der **If** und **num\_threads**\-Klauseln ist nicht angegeben.  
  
## Querverweise:  
  
-   **private**, **firstprivate**, **Standardwert**, **Shared**, **copyin**und **Verringerung** Klauseln finden [2.7.2 Abschnitt](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) auf Seite 25.  
  
-   **OMP\_NUM\_THREADS** Umgebungsvariablen [Abschnitt 4.2](../../parallel/openmp/4-2-omp-num-threads.md) auf Seite 48.  
  
-   **omp\_set\_dynamic** Bibliotheksfunktion finden [3.1.7 Abschnitt](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) auf Seite 39.  
  
-   **OMP\_DYNAMIC** Umgebungsvariablen finden [Abschnitt 4.3](../../parallel/openmp/4-3-omp-dynamic.md) auf Seite 49.  
  
-   **omp\_set\_nested**\-Funktion finden [3.1.9 Abschnitt](../../parallel/openmp/3-1-9-omp-set-nested-function.md) auf Seite 40.  
  
-   **OMP\_NESTED** Umgebungsvariablen finden [Abschnitt 4.4](../../parallel/openmp/4-4-omp-nested.md) auf Seite 49.  
  
-   **omp\_set\_num\_threads** Bibliotheksfunktion finden [3.1.1 Abschnitt](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) auf Seite 36.