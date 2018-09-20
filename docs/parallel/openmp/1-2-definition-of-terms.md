---
title: 1.2. Begriffsdefinition | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: fcaa8eb8-bbbf-4a24-ad0e-e299c442db79
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e95ad940aac14892ac14e8d56ba64f49d0bbf7c0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46423831"
---
# <a name="12-definition-of-terms"></a>1.2. Begriffsdefinition

Die folgenden Begriffe werden in diesem Dokument verwendet:

- barrier

   Ein Synchronisierungspunkt,, der von allen Threads in einem Team erreicht werden muss.  Jeder Thread wartet, bis alle Threads im Team, das an dieser Stelle eingehen. Es sind explizite Barrieren identifizierte Direktiven und implizite Hindernisse, die durch die Implementierung erstellt.

- Konstrukt

   Ein Konstrukt ist eine Anweisung an. Es besteht aus einer Richtlinie und die nachfolgenden strukturierten Block. Beachten Sie, dass einige Direktiven nicht Teil eines Konstrukts sind. (Finden Sie unter *-Direktive von Openmp* in [Anhang C](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md)).

- Anweisung

   Eine C- oder C++ **#pragma** gefolgt von der **Omp** Bezeichner, andere Text und eine neue Zeile. Die Richtlinie gibt Verhalten des Programms an.

- Dynamische Block

   Alle Anweisungen in der *lexikalische Block*, und jede Anweisung innerhalb einer Funktion, die als Ergebnis der Ausführung von Anweisungen innerhalb der lexikalischen Block ausgeführt wird. Einem dynamischen Grad wird auch als bezeichnet ein *Region*.

- lexikalische Block

   Lexikalisch enthaltenen Anweisungen eine *vor einem strukturierten Block*.

-  Master-thread

   Der Thread, der ein Team erstellt bei einer *parallelen Bereichs* eingegeben wird.

- parallelen Bereichs

   Anweisungen, die an einer parallelen OpenMP-Konstrukt gebunden und können von mehreren Threads ausgeführt werden.

- private

   Eine private Variable benennt einen Block von Speicher, der für den Thread, der den Verweis eindeutig ist. Beachten Sie, dass es mehrere Möglichkeiten gibt, um anzugeben, dass eine Variable privat ist: eine Definition innerhalb eines parallelen Bereichs ist, eine **Threadprivate** -Direktive einer **private**, **Firstprivate**, **Lastprivate**, oder **Verringerung** -Klausel, oder Verwenden der Variable als einen **für**Loop-Steuerelementvariable in einer **für** Schleife unmittelbar nach einem **für** oder **für parallele** Richtlinie.

- Bereich

   Eine dynamische Umfang.

- serielle region

   Nur ausgeführte Anweisungen der *master-Thread* außerhalb der dynamischen Wertebereich einer *parallelen Bereichs*.

- Serialisieren

   Zum Ausführen eines parallelen Konstrukts mit einem Team besteht aus nur einem Thread (der die master-Thread für das parallele Konstrukt ist), mit der Reihenfolge der Ausführung für die Anweisungen in einem strukturierten Block Threads (dieselbe Reihenfolge, als wäre der Block nicht Teil eines parallelen Konstrukts) und hat keine Auswirkungen auf den Rückgabewert von **omp_in_parallel()** (abgesehen von den Auswirkungen einer parallele Konstrukten geschachtelt).

- Freigegeben

   Eine freigegebene Variable benennt einen einzelnen Block des Speichers. Alle Threads in einem Team, die auf diese Variable zugreifen, werden diese einzelnen Block Storage zugreifen.

- vor einem strukturierten block

   Ein strukturierter Block ist eine Anweisung aus (einzelne oder zusammengesetzte), die einen einzelnen Eintrag, und eine einzelne beenden. Keine Anweisung ist einem strukturierten Block bei ein Sprung in oder aus dieser Anweisung (einschließlich einen Aufruf von **Longjmp**(3 C) oder die Verwendung der **auslösen**, aber ein Aufruf von **beenden** ist zulässig). Eine verbundanweisung ist einem strukturierten Block aus, wenn die Ausführung immer an das öffnende beginnt **{** und immer endet mit dem schließenden **}**. Eine Ausdrucksanweisung, auswahlanweisung, iterationsanweisung oder **versuchen** Block ist einem strukturierten Block auf, wenn die entsprechende verbundanweisung erworben haben, schließen Sie ihn in **{** und **}** ein strukturierter Block wäre. Eine Jump-Anweisung, die Anweisung mit Bezeichnung oder die deklarationsanweisung ist keinem strukturierten Block.

-  Team

   Ein oder mehrere Threads, die bei der Ausführung eines Konstrukts darstellen.

- Thread

   Eine Ausführung-Entität mit einem seriellen Kontrollfluss, ein Satz von privaten Variablen und Zugriff auf freigegebene Variablen.

- -Variable

   Ein Bezeichner, der optional von Namespace-Namen qualifizierten Namen, die ein Objekt.
