---
title: 2.7.1 Threadprivate-Direktive | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 08e0b70f-5359-4607-b0ca-38c2d570d7b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c9912ccbfa6f5773ec1e523245f75e675bb82244
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33692651"
---
# <a name="271-threadprivate-directive"></a>2.7.1 threadprivate-Anweisung
Die `threadprivate` -Direktive macht die benannte Dateigültigkeitsbereich, Namespace-Gültigkeitsbereich oder Blockbereiche statische Variablen in der *Variablenliste* einem Thread zugehörig. *Variablenliste* ist eine durch Trennzeichen getrennte Liste von Variablen, die nicht über einen unvollständigen Typ verfügen. Die Syntax der `threadprivate` Richtlinie lautet wie folgt:  
  
```  
#pragma omp threadprivate(variable-list) new-line  
```  
  
 Jede Kopie einer `threadprivate` Variable initialisiert wird einmal an ein nicht angegebener Punkt im Programm vor dem ersten Verweis auf diese Kopie, und klicken Sie auf die übliche Weise (d. h., wie die Masterkopie in eine serielle Ausführung des Programms initialisiert werden, würde). Beachten Sie, dass, wenn ein Objekt, in eine explizite Initialisierung von verwiesen wird einer `threadprivate` Variablen und den Wert des Objekts vor dem ersten Verweis auf eine Kopie der Variablen geändert wird, dann ist das Verhalten undefiniert.  
  
 Wie mit eine private Variable, ein Thread nicht einem anderen Thread Kopie verweisen muss ein `threadprivate` Objekt. Während der seriellen Regionen und master Bereiche des Programms werden die Verweise auf die master-Thread-Kopie des Objekts.  
  
 Nach der Ausführung des ersten parallelen Bereichs, der der Daten in der `threadprivate` wird sichergestellt, dass Objekte beibehalten werden, nur wenn dynamischen Mechanismus threads deaktiviert wurde, und wenn die Anzahl der Threads für parallele Vertriebsgebieten unverändert bleibt.  
  
 Die Einschränkungen fest, die `threadprivate` Richtlinie lauten wie folgt:  
  
-   Ein `threadprivate` Richtlinie für Datei- oder Namespace-Gültigkeitsbereich Variablen müssen außerhalb einer Definition oder Deklaration angezeigt werden, und alle Verweise auf eine der Variablen muss lexikalisch in der Liste vor.  
  
-   Jede Variable in der *Variablenliste* von einer `threadprivate` -Direktive am Datei- oder Namespacebereich muss finden Sie in einer Variablendeklaration auf Datei- oder Namespacebereich, der die Richtlinie lexikalisch vorausgeht.  
  
-   Ein `threadprivate` Richtlinie für Blockbereiche mit statischen Variablen muss im Gültigkeitsbereich der Variablen und nicht in einen verschachtelten Bereich angezeigt. Die Direktive muss lexikalisch alle Verweise auf Variablen einen in der Liste der vorangehen.  
  
-   Jede Variable in der *Variablenliste* von einer `threadprivate` Richtlinie im Blockbereich muss finden Sie in einer Variablendeklaration im gleichen Bereich, der die Richtlinie lexikalisch vorausgeht. Die Variablendeklaration festlegen, muss die statische Speicherklassenspezifizierer verwenden.  
  
-   Wenn eine Variable, in angegeben wird eine `threadprivate` -Direktive in einer Übersetzungseinheit, er muss angegeben werden einer `threadprivate` -Direktive in jeder Übersetzungseinheit, die in der sie deklariert ist.  
  
-   Ein `threadprivate` Variable muss nicht angezeigt werden, in jede beliebige Klausel, mit Ausnahme der `copyin`, `copyprivate`, `schedule`, `num_threads`, oder die **Wenn** Klausel.  
  
-   Die Adresse von einem `threadprivate` Variable ist nicht mit einer Adresse-Konstante.  
  
-   Ein `threadprivate` Variable muss einen unvollständigen Typ oder ein Verweistyp nicht aufweisen.  
  
-   Ein `threadprivate` Variable mit nicht-POD-Klassentyp benötigen eine erreichbare, eindeutige Kopierkonstruktor, wenn er mit einem expliziten Initialisierer deklariert wird.  
  
 Im folgende Beispiel wird veranschaulicht, wie ändern eine Variable, die in einer Initialisierung nicht definiertes Verhalten verursachen kann, sowie Informationen zu diesem Problem zu vermeiden, indem Sie ein zusätzliches Objekt und einen Kopierkonstruktor.  
  
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
  
## <a name="cross-references"></a>Referenzen:  
  
-   Dynamische Threads finden Sie unter [Abschnitt 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) auf Seite 39.  
  
-   `OMP_DYNAMIC` Umgebung-Variable verwenden, finden Sie unter [Abschnitt 4.3](../../parallel/openmp/4-3-omp-dynamic.md) auf Seite "49".