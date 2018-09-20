---
title: 2.7.1 Threadprivate-Direktive | Microsoft-Dokumentation
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
ms.openlocfilehash: 31c9c70940b558d0b4cc3f77677665235417694d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46398143"
---
# <a name="271-threadprivate-directive"></a>2.7.1 threadprivate-Anweisung

Die `threadprivate` Direktive macht der benannten Datei-Bereich, Namespace-Gültigkeitsbereich oder Blockbereiche mit statischen Variablen in der *Variablenliste* einem Thread zugehörig. *Variablenliste* ist eine durch Trennzeichen getrennte Liste von Variablen, die nicht über einen unvollständigen Typ verfügen. Die Syntax der `threadprivate` Richtlinie lautet wie folgt:

```
#pragma omp threadprivate(variable-list) new-line
```

Jeder Kopie eine `threadprivate` Variable initialisiert wird einmal an einem nicht angegebenen Punkt im Programm vor dem ersten Verweis auf diese Kopie, und klicken Sie auf die übliche Weise (d. h., wie die Masterkopie in einer seriellen Ausführung des Programms initialisiert werden würde). Beachten Sie, dass ein Objekt verwiesen wird, in eine explizite Initialisierung von einer `threadprivate` Variablen und der Wert des Objekts vor dem ersten Verweis auf eine Kopie der Variable geändert wird, dann ist das Verhalten undefiniert.

Wie mit eine private Variable, ein Thread nicht ein anderer Thread Kopie verweisen muss eine `threadprivate` Objekt. Bei der seriellen Bereichen und masterregionen des Programms werden die Verweise auf die master-Thread-Kopie des Objekts.

Nachdem die erste Region für die parallele ausgeführt wird, die Daten in die `threadprivate` ist gewährleistet, dass Objekte beibehalten werden, nur wenn threads von dynamischen Mechanismus deaktiviert wurde, und wenn die Anzahl der Threads für alle parallelen Bereichen unverändert bleibt.

Die Einschränkungen fest, die `threadprivate` Richtlinie lauten wie folgt:

- Ein `threadprivate` Richtlinie für Datei-Gültigkeitsbereich oder im Namespace-Gültigkeitsbereich von Variablen muss außerhalb beliebige Definition oder Deklaration angezeigt werden, und alle Verweise auf Variablen in der Liste muss lexikalisch vorangestellt sein.

- Jede Variable in der *Variablenliste* von einer `threadprivate` Richtlinie auf Datei- oder Namespacebereich muss die Deklaration einer Variablen auf Datei- oder Namespacebereich, der die Direktive lexikalisch vorausgeht finden Sie unter.

- Ein `threadprivate` Richtlinie für Blockbereiche mit statischen Variablen muss im Gültigkeitsbereich der Variablen und nicht in einem geschachtelten Bereich angezeigt werden. Die Richtlinie muss lexikalisch alle Verweise auf Variablen in der Liste der vorangestellt sein.

- Jede Variable in der *Variablenliste* von eine `threadprivate` Richtlinie im Blockbereich muss auf eine Variablendeklaration im gleichen Bereich, der die Direktive lexikalisch vorausgeht verweisen. Die Deklaration von Variable muss den static-Speicherklassenspezifizierer verwenden.

- Wenn eine Variable, in angegeben wird eine `threadprivate` -Direktive in einer Übersetzungseinheit, es muss angegeben werden eine `threadprivate` -Direktive in jeder Übersetzungseinheit, die in der sie deklariert ist.

- Ein `threadprivate` Variable darf nicht in jeder Klausel nur erscheinen die `copyin`, `copyprivate`, `schedule`, `num_threads`, oder die **Wenn** Klausel.

- Die Adresse einer `threadprivate` Variable ist nicht mit einer Adresse konstant.

- Ein `threadprivate` Variable darf keinen, einen unvollständigen Typ oder ein Verweistyp.

- Ein `threadprivate` Variablen keine POD-Klassentyp muss eine erreichbare, eindeutige Kopierkonstruktor verfügen, wenn er mit einem expliziten Initialisierer deklariert wird.

Im folgende Beispiel wird veranschaulicht, wie ändern eine Variable, die in einer Initialisierung wird angezeigt, nicht definiertes Verhalten verursachen kann, und wie dieses Problem zu vermeiden, indem Sie ein zusätzliches Objekt und einen Kopierkonstruktor.

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

## <a name="cross-references"></a>Datenbankübergreifende Verweise:

- Dynamische Threads finden Sie unter [Abschnitt 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) auf Seite 39.

- `OMP_DYNAMIC` Umgebung-Variable, finden Sie unter [Abschnitt-4.3](../../parallel/openmp/4-3-omp-dynamic.md) auf 49.