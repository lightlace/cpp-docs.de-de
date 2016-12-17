---
title: "1.2 Definition of Terms"
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
ms.assetid: fcaa8eb8-bbbf-4a24-ad0e-e299c442db79
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# 1.2 Definition of Terms
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die folgenden Begriffe werden in diesem Dokument verwendet wird:  
  
 Barriere  
 Ein Synchronisierung das Popup, der von allen Threads in einem Team erreicht werden muss.  Jeder Thread wartet, bis alle Threads im Team an dieser Stelle eintreffen.  Es gibt den expliziten Barrieren, die von Direktiven identifiziert und die impliziten Barrieren, die durch die Implementierung erstellt werden.  
  
 Konstrukt  
 Ein Konstrukt ist eine Anweisung.  Es besteht aus den folgenden Direktiven und strukturierten Block.  Beachten Sie, dass einige Direktiven nicht Teil eines Konstrukts sind.  \(Siehe *OpenMP \- Direktive* in [Anhang C](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md)\).  
  
 Direktive  
 **\#pragma** C oder C\+\+ Bezeichner, gefolgt vom **omp** von anderem Text und einer neuen Zeile.  Die Direktive geben das Programm an.  
  
 dynamischer Wertebereich  
 Alle Anweisungen im *lexikalischen Wertebereich*, plus einer beliebigen Anweisung in einer Funktion, die als Ergebnis der Ausführung von Anweisungen innerhalb des lexikalischen Wertebereichs ausgeführt wird.  Ein dynamischer Wertebereich auch als *Bereich*bezeichnet.  
  
 lexikalischer Wertebereich  
 lexikalisch enthalten Anweisungen innerhalb eines *strukturierten Blocks*.  
  
 Masterthread  
 Der Thread, der ein Team erstellt, wenn ein *paralleler Gültigkeitsbereich* eingeführt wird.  
  
 parallelen Bereich  
 Anweisungen, die eine Bindung zu OpenMP kann ein Konstrukt und parallel von mehreren Threads ausgeführt werden.  
  
 private  
 Private Variablennamen ein Block Speicher, der dem Thread eindeutig ist, der den Verweis macht.  Beachten Sie, dass es mehrere Möglichkeiten gibt an, dass eine Variable privat ist: Innerhalb einer Definition eines parallelen Bereichs, **threadprivate**\-Direktive, **private**, **firstprivate**, **lastprivate**oder **Verringerung** Klausel oder Verwendung der Variablen als **nach**in einer Schleifensteuerungsvariablen **nach** \- Schleife unmittelbar nach **nach** oder **für Ähnlichkeit** \- Direktive.  
  
 Bereich  
 Ein dynamischer Wertebereichs.  
  
 serieller Bereich  
 *Masterthread* nur durch den Anweisungen ausgeführt, die außerhalb des dynamischen Wertebereichs eines *parallelen Bereichs*.  
  
 serialisieren Sie  
 Um ein paralleles Konstrukt mit einem Team aus Threads auszuführen, die nur aus einem Thread bestehen \(das der Masterthread für dieses Konstrukt ist\) mit paralleler serieller Ausführungsreihenfolge für die Anweisungen innerhalb des Blocks \(strukturierten der Reihenfolge als wäre der Block nicht Teil eines parallelen Konstrukt waren\) und ohne Auswirkung auf den Wert von **omp\_in\_parallel \(\)** zurück \(abgesehen von den Effekten eines geschachtelten parallelen Konstrukte\).  
  
 shared  
 Freigegebene Variablennamen ein einzelnen Block Speicher.  Alle Threads in einem Team, die diese Variablen zugreifen, greifen auf den einzelnen Block zu speichern.  
  
 strukturierter \- Block  
 Ein strukturierter Block ist eine Anweisung \(einzeln oder Zusammengesetzte\), die einen einzelnen Eintrag, und eine einzelne Beenden verfügt.  Es werden keine Anweisung ist ein Block strukturierter wenn ist ein Sprung in oder aus dieser Anweisung out \(einschließlich Aufruf von **longjmp**3C \(\) oder die Verwendung von **Wurf**, aber ein Aufruf von **Beenden** ist zulässig\).  Eine strukturierte Verbundanweisung ist ein Block, wenn ihre Ausführung immer am ersten **{** gestartet und beendet **}**schließt immer beibehalten.  Eine Ausdrucksanweisung, Selektionsangabe, Iterationsanweisung oder try\-Block folgt ein Block, wenn die entsprechende strukturierte abgerufenen Verbundanweisung, indem Sie ihn in **{** einschloss und strukturierter ein **}**Block wäre.  Eine Sprungs der Anweisung, Anweisung mit Marke oder Deklarationsanweisung ist kein strukturierter Block.  
  
 Team  
 Eine oder mehrere Threads, die bei der Ausführung eines Konstrukts kooperieren.  
  
 Thread  
 Eine führen entität, die über den seriellen Ablaufsteuerung einen Satz private Variablen und den Zugriff auf freigegebene Variablen enthält.  
  
 variable  
 Ein Bezeichner, optional gekennzeichnet durch die Namespacenamen, diese Namen eines Objekts.