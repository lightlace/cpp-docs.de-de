---
title: 2.3 parallel-Konstrukt | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 190eacdf-2c16-4c06-8cb7-ac60eb211425
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 89167547085682a81cc1d281f4f32ab55022d27c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="23-parallel-construct"></a>2.3 parallel-Konstrukt
Die folgende Direktive definiert ein paralleles Bereichs, das einer Region des Programms ist, die durch mehrere Threads parallel ausgeführt werden soll. Dies ist das grundlegende Konstrukt, das mit der parallelen Ausführung beginnt.  
  
```  
#pragma omp parallel [clause[ [, ]clause] ...] new-line   structured-block  
```  
  
 Die *Klausel* ist eines der folgenden:  
  
 **Wenn (** *Ausdruck für skalare* **)**  
  
 **Private (** *Variablenliste* **)**  
  
 **Firstprivate (** *Variablenliste* **)**  
  
 **Standard (freigegebenen & #124; none)**  
  
 **Freigegebene (** *Variablenliste* **)**  
  
 **Copyin (** *Variablenliste* **)**  
  
 **Verringerung (** *Operator* **:***Variablenliste* **)  **  
  
 **Num_threads (** *Ganzzahlausdruck* **)**  
  
 Wenn ein Thread ein paralleles Konstrukts auftritt, wird ein Team von Threads erstellt, wenn eine der folgenden Fälle zutrifft:  
  
-   Nicht **Wenn** -Klausel vorhanden ist.  
  
-   Die **Wenn** Ausdruck einen Wert ungleich NULL ausgewertet wird.  
  
 Dieser Thread wird die master-Thread des Teams, mit der eine Thread-Anzahl 0 (null), und alle Threads im Team, einschließlich der master-Thread die Region parallel ausgeführt. Wenn der Wert der **Wenn** Ausdruck NULL ist, wird der Bereich wird serialisiert.  
  
 Um die Anzahl der Threads zu bestimmen, die angefordert werden, werden die folgenden Regeln in der Reihenfolge angesehen. Die erste Regel, deren Bedingung erfüllt ist, werden angewendet werden:  
  
1.  Wenn die **Num_threads** -Klausel vorhanden ist, und klicken Sie dann der Wert des Ausdrucks ganze Zahl ist die Anzahl der angeforderten Threads.  
  
2.  Wenn die **Omp_set_num_threads** Library-Funktion aufgerufen wurde, und klicken Sie dann der Wert des Arguments in den zuletzt ausgeführten Aufruf wird die Anzahl der Threads angefordert.  
  
3.  Wenn die Umgebungsvariable **OMP_NUM_THREADS** definiert ist, und klicken Sie dann der Wert dieser Umgebungsvariablen die Anzahl der Threads, die angefordert wird.  
  
4.  Wenn keine der oben genannten Methoden verwendet wurden, wird die Anzahl der angeforderten Threads Implementierung definiert.  
  
 Wenn die **Num_threads** -Klausel vorhanden ist, und klicken Sie dann die Anzahl der Threads, die vom angeforderten ersetzende der **Omp_set_num_threads** Bibliotheksfunktion oder das **OMP_NUM_THREADS** nur für den parallelen Bereich-Umgebungsvariablen angegeben wird, angewendet. Nachfolgende parallele Bereiche sind nicht betroffen.  
  
 Die Anzahl der Threads, die den parallelen Bereich ausführen auch hängt davon ab, und zwar unabhängig davon, ob die dynamische Anpassung der Anzahl der Threads aktiviert ist. Wenn dynamische Anpassung deaktiviert ist, wird die angeforderte Anzahl von Threads die parallelen Bereichs ausgeführt. Wenn die dynamische Anpassung aktiviert ist, ist die angeforderte Anzahl von Threads die maximale Anzahl von Threads, die den parallelen Bereich ausführen kann.  
  
 Wenn es sich bei ein paralleler Bereich gefunden wird, während dynamische Anpassung der Anzahl von Threads ist deaktiviert, und die Anzahl der Threads, die für den parallelen Bereich angeforderten überschreitet die Anzahl, die das Laufzeitsystem bereitstellen kann, ist das Verhalten des Programms Implementierung definiert. Eine Implementierung kann z. B. die Ausführung des Programms unterbrechen oder des parallelen Bereichs serialisieren kann.  
  
 Die **Omp_set_dynamic** Library-Funktion und die **OMP_DYNAMIC** Umgebungsvariable aktivieren und deaktivieren die dynamische Anpassung der Anzahl von Threads verwendet werden kann.  
  
 Die Anzahl der physischen Prozessoren, die tatsächlich hosting Threads zu einem beliebigen Zeitpunkt ist die Implementierung definiert. Nach der Erstellung bleibt die Anzahl der Threads im Team für die Dauer von dieser parallelen Bereichs konstant. Sie können entweder explizit vom Benutzer oder automatisch vom System zur Laufzeit aus einem parallelen Bereich in eine andere geändert werden.  
  
 Die Anweisungen, die als Bestandteil der dynamischen Wertebereich des parallelen Bereichs durch alle Threads ausgeführt werden, und jeder Thread einen Pfad von Anweisungen, die sich von anderen Threads ausgeführt werden kann. Anweisungen, die außerhalb der lexikalische Wertebereich eines parallelen Bereichs gefunden werden als verwaiste Direktiven bezeichnet.  
  
 Es gibt eine implizite Barriere am Ende eines parallelen Bereichs ein. Nur die master-Thread des Teams wird die Ausführung am Ende eines parallelen Bereichs fortgesetzt.  
  
 Wenn ein Thread in einem Team Ausführen eines parallelen Bereichs ein anderes paralleles Konstrukt trifft, erstellt ein neues Team und wird als übergeordneter das neue Team. Geschachtelte parallele Bereiche werden standardmäßig serialisiert. Standardmäßig wird daher ein geschachtelten paralleles Bereichs von einem Team besteht aus einem Thread ausgeführt. Das Standardverhalten kann geändert werden, mit der Common Language Runtime-Bibliotheksfunktion **Omp_set_nested** oder die Umgebungsvariable **OMP_NESTED**. Die Anzahl der Threads in einem Team, die ausführen ein geschachtelten paralleles Bereichs ist jedoch die Implementierung definiert.  
  
 Einschränkungen für die **parallele** Richtlinie lauten wie folgt:  
  
-   Darf höchstens ein **Wenn** Klausel kann auf die Richtlinie angezeigt werden.  
  
-   Es ist nicht angegeben, ob alle Effekte innerhalb der If clientseitigen Ausdruck oder **Num_threads** Ausdruck auftreten.  
  
-   Ein **auslösen** innerhalb ein paralleles Bereichs muss dazu führen, dass in der dynamischen Wertebereich denselben strukturierten Block Fortsetzen der Ausführung ausgeführt, und sie müssen dem gleichen Thread, der die Ausnahme ausgelöst hat abgefangen werden.  
  
-   Nur ein einzelner **Num_threads** Klausel kann auf die Richtlinie angezeigt werden. Die **Num_threads** Ausdruck wird außerhalb des Kontexts des parallelen Bereichs ausgewertet, und muss eine positive ganze Zahl ergeben.  
  
-   Die Reihenfolge der Auswertung der **Wenn** und **Num_threads** Klauseln ist nicht angegeben.  
  
## <a name="cross-references"></a>Referenzen:  
  
-   **private**, **Firstprivate**, **Standard**, **freigegebenen**, **Copyin**, und **Verringerung**-Klausel finden Sie unter [Abschnitt 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) auf Seite "25".  
  
-   **OMP_NUM_THREADS** Umgebungsvariablen [Abschnitt 4.2](../../parallel/openmp/4-2-omp-num-threads.md) auf Seite 48.  
  
-   **Omp_set_dynamic** Library-Funktion finden Sie unter [Abschnitt 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) auf Seite 39.  
  
-   **OMP_DYNAMIC** Umgebung-Variable verwenden, finden Sie unter [Abschnitt 4.3](../../parallel/openmp/4-3-omp-dynamic.md) auf Seite "49".  
  
-   **Omp_set_nested** funktionieren, finden Sie unter [Abschnitt 3.1.9](../../parallel/openmp/3-1-9-omp-set-nested-function.md) auf der Seite "40".  
  
-   **OMP_NESTED** Umgebung-Variable verwenden, finden Sie unter [Abschnitt 4.4](../../parallel/openmp/4-4-omp-nested.md) auf Seite "49".  
  
-   **Omp_set_num_threads** Library-Funktion finden Sie unter [Abschnitt 3.1.1](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) auf Seite 36.