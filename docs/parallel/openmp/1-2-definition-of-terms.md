---
title: 1.2. Begriffsdefinition | Microsoft Docs
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
ms.assetid: fcaa8eb8-bbbf-4a24-ad0e-e299c442db79
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ab188c32c633092efc562d0432ebb7c5662b5ff8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="12-definition-of-terms"></a>1.2. Begriffsdefinition
In diesem Dokument werden die folgenden Begriffe verwendet:  
  
 barrier  
 Ein Synchronisierungspunkt,, der von allen Threads in einem Team erreicht werden muss.  Jeder Thread wartet, bis alle Threads im Team zu diesem Zeitpunkt eingehen. Es sind explizite Barrieren identifizierte Direktiven und implizite Barrieren, die durch die Implementierung erstellt.  
  
 Konstrukt  
 Ein Konstrukt ist eine Anweisung an. Er besteht aus einer Richtlinie und die nachfolgenden strukturierten Block. Beachten Sie, dass einige Direktiven nicht Teil eines Konstrukts sind. (Siehe *-Direktive von Openmp* in [Anhang C](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md)).  
  
 Anweisung  
 Eine C- oder C++ **#pragma** gefolgt von der **Omp** Bezeichner, Text und eine neue Zeile. Die Richtlinie gibt Verhalten des Programms an.  
  
 Dynamische Block  
 Alle Anweisungen in der *lexikalischen Block*, sowie jede Anweisung innerhalb einer Funktion, die als Ergebnis der Ausführung von Anweisungen innerhalb der lexikalische Block ausgeführt wird. Ein dynamische Block wird auch als bezeichnet eine *Region*.  
  
 lexikalische Block  
 Lexikalisch enthaltenen Anweisungen eine *strukturierten Block*.  
  
 Master-thread  
 Der Thread, der ein Team erstellt bei einer *parallelen Bereichs* eingegeben wird.  
  
 parallelen Bereichs  
 Anweisungen, die mit einer parallelen OpenMP-Konstrukt gebunden und können von mehreren Threads ausgeführt werden.  
  
 private  
 Eine private Variable benennt einen Block von Speicher, der an den Thread, der den Verweis eindeutig ist. Beachten Sie, dass es mehrere Möglichkeiten gibt, um anzugeben, dass eine Variable privat ist: eine Definition innerhalb eines parallelen Bereichs ein **Threadprivate** Richtlinie eine **private**, **Firstprivate**, **Lastprivate**, oder **Verringerung** -Klausel oder der Nutzung von Variablen, so wie eine **für**Loop-Steuerelementvariable in einem **für** Schleife unmittelbar nach einem **für** oder **für parallele** Richtlinie.  
  
 Bereich  
 Eine dynamische Block.  
  
 serielle region  
 Nur von ausgeführte Anweisungen der *"master" Thread* außerhalb der dynamischen Ausmaß eines beliebigen *parallelen Bereichs*.  
  
 Serialisieren  
 Zum Ausführen eines parallelen Konstrukts mit einem Team von Threads, bestehend aus nur einem einzelnen Thread (also die master-Thread für das parallele Konstrukt) mit seriellen Ausführungsreihenfolge für die Anweisungen in einem strukturierten Block (dieselbe Reihenfolge, als wäre der Block nicht Teil eines parallelen Konstrukts) und hat keine Auswirkungen auf den Rückgabewert von **omp_in_parallel()** (abgesehen von den Auswirkungen eines beliebigen geschachtelte den parallele Konstrukten).  
  
 Freigegeben  
 Eine freigegebene Variable benennt einen einzelnen Block Storage. Alle Threads in einem Team, die diese Variable zugreifen, werden dieser einzelnen Block Storage zugreifen.  
  
 strukturierten block  
 Ein strukturierter Block ist eine Anweisung (einzelne oder zusammengesetzte) an, die einen einzelnen Eintrag und einer einzelnen Beendigung verfügt. Keine Anweisung wird, ist einem strukturierten Block bei ein Sprung in oder aus dieser Anweisung (einschließlich eines Aufrufs von **Longjmp**(3 C) oder die Verwendung von **auslösen**, aber einen Aufruf von **beenden** ist zulässig). Eine verbundanweisung ist einem strukturierten Block aus, wenn seine Ausführung immer an das öffnende beginnt **{** und endet immer mit dem schließenden **}**. Eine Ausdrucksanweisung, selektionsanweisung,-iterationsanweisung, oder **versuchen** Block ist einem strukturierten Block aus, wenn die entsprechende verbundanweisung erworben haben, schließen Sie ihn in **{** und **}** ein strukturierter Block wäre. Eine Jump-Anweisung, eine Anweisung mit Bezeichnung oder eine deklarationsanweisung ist keinem strukturierten Block.  
  
 Team  
 Einen oder mehrere Threads, die bei der Ausführung eines Konstrukts zusammenarbeiten.  
  
 Thread  
 Eine Ausführung-Entität mit einem seriellen Kontrollfluss, einen Satz von private Variablen und Zugriff auf freigegebene Variablen.  
  
 -Variable  
 Ein Bezeichner, die optional durch den Namespace-Namen qualifiziert benennt, die ein Objekt.