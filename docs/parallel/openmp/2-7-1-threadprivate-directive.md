---
title: "2.7.1 threadprivate Directive"
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
ms.assetid: 08e0b70f-5359-4607-b0ca-38c2d570d7b3
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# 2.7.1 threadprivate Directive
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `threadprivate`\-Direktive machen den benannten Dateigültigkeitsbereich, den Namespacebereich Blockbereichs oder statischen Variablen die *Variable* in der *Liste* angegeben sind, die zu einem Thread privat ist.  *Variable Liste* ist eine durch Trennzeichen getrennte Liste von Variablen, die nicht über einen unvollständigen Typ aufweisen.  Die Syntax der `threadprivate`\-Direktive sieht wie folgt aus:  
  
```  
#pragma omp threadprivate(variable-list) new-line  
```  
  
 Jede Kopie einer `threadprivate`\-Variable wird einmal an einem angegebenen Punkt im Programm nicht vor dem ersten Verweis auf diese Kopie als auch in der üblichen Weise initialisiert \(das heißt die als Masterkopie in einer serielle Ausführung des Programms erneut initialisiert wird.\)  Beachten Sie, dass, wenn ein Objekt in ein expliziter Initialisierer einer `threadprivate`\-Variable \(verwiesen wird und der Wert des Objekts vor dem ersten Verweis auf eine Kopie der Variablen geändert wird. Anschließend wird das Verhalten nicht angegeben ist.  
  
 Wie bei allen privaten Variable darf kein Thread die Kopie eines Objekts `threadprivate` eines anderen Threads nicht verweisen.  Während der seriellen Bereiche und Vorlagen Bereiche des Programms sind Verweise auf die Kopie des Masterthreads des Objekts.  
  
 Nach der ersten parallelen Bereich ausführt, wird die Daten in den `threadprivate` sichergestellt, dass Objekte beibehalten werden sollen, wenn der dynamischen Mechanismus für den Thread deaktiviert wurde, und sobald die Anzahl blockierter Threads für alle parallelen Bereiche unverändert bleibt.  
  
 Die Einschränkungen auf `threadprivate`\-Direktive lauten wie folgt:  
  
-   `threadprivate`\-Direktive für Dateigültigkeitsbereichs\- oder Namespacebereichs variablen müssen außerhalb einer Definition oder Deklaration werden und müssen allen Verweisen zu den Variablen in der Liste lexikalisch stehen.  
  
-   Jede Variablen in der *Liste Variablen*`threadprivate`\-Direktive in der Datei oder dem Namespacebereich muss eine Variablendeklaration an der Datei oder dem Namespacebereich verweisen, die lexikalisch der Direktive vorangeht.  
  
-   Blockbereichs `threadprivate`\-Direktive für statische Variablen müssen im Gültigkeitsbereich der Variablen und nicht in einem geschachtelten Bereich angezeigt werden.  Diese Direktiven müssen allen Verweisen auf einen der Variablen in der Liste lexikalisch stehen.  
  
-   Jede Variablen in der *Liste Variablen*`threadprivate`\-Direktive im Blockbereich muss eine Variablendeklaration im gleichen Bereich verweisen, die lexikalisch der Direktive vorangeht.  Die Variablendeklaration muss den statischen Speicherklassenspezifizierer verwenden.  
  
-   Wenn eine Variable in `threadprivate`\-Direktive in einer Übersetzungseinheit angegeben ist, muss sie in `threadprivate`\-Direktive in jeder Übersetzungseinheit angegeben werden, in der sie deklariert wurde.  
  
-   Eine `threadprivate`\-Variable darf in keiner \- Klausel `copyin`, es sei denn, `copyprivate``schedule`, `num_threads`oder die **If**\-Klausel angegeben werden.  
  
-   Die Adresse einer `threadprivate`\-Variable ist keine Adressen konstant.  
  
-   Eine `threadprivate`\-Variable darf einen unvollständigen Typ oder einen Verweistyp enthalten.  
  
-   Eine `threadprivate`\-Variable mit Nicht HÜLSE Klassentyp muss über einen zugreifbaren, eindeutigen Kopierkonstruktor verfügen, wenn sie mit einem expliziten Initialisierers deklariert ist.  
  
 Das folgende Beispiel zeigt, wie das Ändern einer Variablen, die in einer Initialisierung wird, nicht definiertes Verhalten zur Folge haben und kann auch die Verwendung dieses Problem vermeiden, indem ein zusätzliches Objekt und einen Kopierkonstruktor verwendet.  
  
```  
int x = 1;  
T a(x);  
const T b_aux(x); /* Capture value of x = 1 */  
T b(b_aux);  
#pragma omp threadprivate(a, b)  
  
void f(int n) {  
   x++;  
   #pragma omp parallel for  
   /* In each thread:  
   * Object a is constructed from x (with value 1 or 2?)  
   * Object b is copy-constructed from b_aux  
   */  
   for (int i=0; i<n; i++) {  
      g(a, b); /* Value of a is unspecified. */  
   }  
}  
```  
  
## Querverweise:  
  
-   Dynamische Threads finden [3.1.7 Abschnitt](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) auf Seite 39.  
  
-   `OMP_DYNAMIC` Umgebungsvariablen finden [Abschnitt 4.3](../../parallel/openmp/4-3-omp-dynamic.md) auf Seite 49.