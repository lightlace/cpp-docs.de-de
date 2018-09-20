---
title: 2.3 parallel-Konstrukt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 190eacdf-2c16-4c06-8cb7-ac60eb211425
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4be5bdc40f69cfa0a326ffa6a7f8465e401cfd33
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46448232"
---
# <a name="23-parallel-construct"></a>2.3 parallel-Konstrukt

Die folgende Anweisung definiert ein paralleles Bereichs, das in einem Bereich des Programms ist, die von mehreren Threads gleichzeitig ausgeführt werden soll. Dies ist das grundlegende Konstrukt, das die parallele Ausführung beginnt.

```
#pragma omp parallel [clause[ [, ]clause] ...] new-line   structured-block
```

Die *Klausel* ist eine der folgenden:

**if(** *scalar-expression* **)**

**Private (** *Variablenliste* **)**

**Firstprivate (** *Variablenliste* **)**

**default(shared &#124; none)**

**Freigegebene (** *Variablenliste* **)**

**Copyin (** *Variablenliste* **)**

**Verringerung der (** *Operator* **:***Variablenliste* **)** 

**num_threads(** *integer-expression* **)**

Wenn in ein Thread ein paralleles Konstrukts auftritt, wird ein Team von Threads erstellt, wenn eine der folgenden Fälle zutrifft:

- Keine **Wenn** -Klausel vorhanden ist.

- Die **Wenn** Ausdruck ausgewertet wird, einen Wert ungleich NULL.

Dieser Thread wird die master-Thread des Teams, mit einer Thread-Anzahl von 0 (null), und alle Threads in der master-Thread, einschließlich die Region parallel ausgeführt. Wenn der Wert des der **Wenn** Ausdruck NULL ist, wird die Region wird serialisiert.

Um die Anzahl der Threads zu bestimmen, die angefordert werden, werden die folgenden Regeln in der Reihenfolge betrachtet. Die erste Regel, deren Bedingung erfüllt ist, werden angewendet werden:

1. Wenn die **Num_threads** -Klausel vorhanden ist, und klicken Sie dann der Wert des der ganzzahlige Ausdruck wird die Anzahl der Threads angefordert.

1. Wenn die **Omp_set_num_threads** Library-Funktion aufgerufen wurde, und klicken Sie dann der Wert des Arguments in der zuletzt ausgeführten Aufruf wird die Anzahl der Threads angefordert.

1. Wenn die Umgebungsvariable **OMP_NUM_THREADS** definiert ist, wird der Wert dieser Umgebungsvariablen die Anzahl der Threads, die angefordert wird.

1. Wenn keine der oben genannten Methoden verwendet wurden, wird die Anzahl der angeforderten Threads Implementierung definiert.

Wenn die **Num_threads** -Klausel vorhanden ist, und klicken Sie dann die Anzahl der Threads, die vom angeforderten ersetzt die **Omp_set_num_threads** Bibliotheksfunktion oder das **OMP_NUM_THREADS** die Umgebungsvariable nur für den parallelen Bereich, die, dem es angewendet wird. Nachfolgende parallele Bereichen sind davon nicht betroffen.

Die Anzahl der Threads, die den parallelen Bereich ausführen auch hängt davon ab, ob die dynamische Anpassung der Anzahl der Threads aktiviert ist. Wenn dynamische platzierungseinstellung deaktiviert ist, wird die angeforderte Anzahl von Threads die parallelen Bereichs ausgeführt. Wenn die dynamische Anpassung aktiviert ist, ist die angeforderte Anzahl von Threads die maximale Anzahl von Threads, die den parallelen Bereich ausgeführt werden können.

Wenn es sich bei ein paralleler Bereich gefunden wird, während dynamische Anpassung der Anzahl von Threads ist deaktiviert, und die Anzahl der Threads, die für den parallelen Bereich angeforderten überschreitet die Anzahl, die das System zur Laufzeit bereitstellen kann, ist das Verhalten des Programms Implementierung definiert. Eine Implementierung kann z. B. die Ausführung des Programms unterbrechen, oder den parallelen Bereich serialisieren kann.

Die **Omp_set_dynamic** Library-Funktion und die **OMP_DYNAMIC** Umgebungsvariable zum Aktivieren und deaktivieren die dynamische Anpassung der Anzahl von Threads verwendet werden kann.

Die Anzahl der physischen Prozessoren tatsächlich die Threads hosten, zu jedem Zeitpunkt wird die Implementierung definiert. Nach der Erstellung bleibt die Anzahl der Threads im Team für die Dauer der parallelen Region konstant. Er kann entweder explizit vom Benutzer oder automatisch vom System zur Laufzeit aus einer parallel-Region in eine andere geändert werden.

Die Anweisungen in der dynamischen Wertebereich des parallelen Bereichs enthaltenen von allen Threads ausgeführt werden, und einen Pfad von Anweisungen, der sich von anderen Threads wird von jeder Thread ausgeführt werden kann. Anweisungen, die außerhalb der lexikalischen Wertebereich eines parallelen Bereichs gefunden werden als verwaiste Direktiven bezeichnet.

Es gibt eine implizite Barriere am Ende eines parallelen Bereichs ein. Nur die master-Thread des Teams wird die Ausführung am Ende eines parallelen Bereichs fortgesetzt.

Wenn ein Thread in einem Team, das Ausführen eines parallelen Bereichs ein anderes paralleles Konstrukt auftritt, erstellt ein neues Team, und es wird als übergeordneter das neue Team. Standardmäßig werden die geschachtelten parallele Bereichen serialisiert. Daher wird in der Standardeinstellung ein geschachtelten paralleles Bereichs von einem Team besteht aus einem Thread ausgeführt. Das Standardverhalten kann geändert werden, mit der Common Language Runtime-Bibliotheksfunktion **Omp_set_nested** oder die Umgebungsvariable **OMP_NESTED**. Die Anzahl der Threads in einem Team, die ausführen ein geschachtelten paralleles Bereichs ist jedoch die Implementierung definiert.

Einschränkungen für die **parallele** Richtlinie lauten wie folgt:

- Höchstens ein **Wenn** Klausel kann in der Richtlinie angezeigt werden.

- Es ist nicht angegeben, ob alle Effekte in der If Seite Ausdruck oder **Num_threads** Ausdruck auftreten.

- Ein **auslösen** innerhalb ein paralleles Bereichs muss dazu führen, dass in der dynamischen Wertebereich denselben strukturierten Block Fortsetzen der Ausführung ausgeführt, und es muss abgefangen werden, von dem gleichen Thread, der die Ausnahme ausgelöst hat.

- Nur eine einzige **Num_threads** Klausel kann in der Richtlinie angezeigt werden. Die **Num_threads** Ausdruck im Kontext des parallelen Bereichs ausgewertet wird, und muss zu einer positiven Ganzzahl ausgewertet.

- Die Reihenfolge der Auswertung der **Wenn** und **Num_threads** Klauseln ist nicht angegeben.

## <a name="cross-references"></a>Datenbankübergreifende Verweise:

- **private**, **Firstprivate**, **Standard**, **freigegebenen**, **Copyin**, und **Verringerung**Klauseln finden Sie unter [Abschnitt 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) auf Seite 25.

- **OMP_NUM_THREADS** Umgebungsvariablen [Abschnitt 4.2](../../parallel/openmp/4-2-omp-num-threads.md) auf 48.

- **Omp_set_dynamic** Library-Funktion finden Sie unter [Abschnitt 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) auf Seite 39.

- **OMP_DYNAMIC** Umgebung Variablen, finden Sie unter [Abschnitt-4.3](../../parallel/openmp/4-3-omp-dynamic.md) auf 49.

- **Omp_set_nested** funktionieren, finden Sie unter [Abschnitt 3.1.9](../../parallel/openmp/3-1-9-omp-set-nested-function.md) auf Seite "40".

- **OMP_NESTED** Umgebung Variablen, finden Sie unter [Abschnitt 4.4](../../parallel/openmp/4-4-omp-nested.md) auf 49.

- **Omp_set_num_threads** Library-Funktion finden Sie unter [Abschnitt 3.1.1](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) auf 36.