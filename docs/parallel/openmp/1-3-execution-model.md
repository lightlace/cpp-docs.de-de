---
title: "1.3 Execution Model"
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
ms.assetid: 85ae8bc4-5bf0-45e0-a45f-02de9adaf716
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# 1.3 Execution Model
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OpenMP fork Join verwendet das Modell der parallelen Ausführung.  Obwohl dies fork Join Modell zum Auslösen einer Vielzahl von Problemen nützlich sein kann, wird er etwas für große Array\-basierte Anwendungen geeignet.  OpenMP ist für Dienstprogramme für die korrekt als parallele Programme \(mehrere Ausführungsthreads und der vollständigen OpenMP\-Stütz Library\) und als Ablaufprogramme ausführen \(die OpenMP einfache Direktiven und ignoriert rodet Bibliothek\).  Es ist jedoch möglich, und kann ein Programm zu entwickeln, das nicht ordnungsgemäß verhält, wenn es sequenziell ausgeführt wird.  Darüber hinaus führen möglicherweise andere Maße an Parallelität verschiedene numerische Ergebnisse aufgrund von Änderungen in der Zuordnung numerische Vorgänge.  Zum Beispiel kann eine Verringerung der seriellen zusätzlich ein weiteres Muster von Hinzufügungs von Namespacezuordnungen als eine parallele Verringerung.  Diese verschiedenen Zuordnungen ändern sich die Ergebnisse der Gleitkommaaddition.  
  
 Ein Programm, das mit OpenMP C\/C\+\+ API geschrieben wird, startet die Ausführung, wie ein Thread die Ausführung *Masterthread*aufgerufen haben.  Der Masterthread führt in einem seriellen Bereich aus, bis die erste parallelen Konstrukt gefunden wird.  In C\/C\+\+ OpenMP APIs, die **Ähnlichkeit**\-Direktive ein paralleles Konstrukt fest.  Wenn ein paralleles Konstrukt gefunden wird, stellt der Masterthread ein Team von Threads erstellt, und der Master\- wird Master des Teams.  Jeder Thread im Team führt die Anweisungen im dynamischen Wertebereich eines parallelen Bereichs mit Ausnahme der Arbeitsteilungs konstrukten aus.  Arbeitsteilungs Konstrukte müssen alle Threads im Team in der gleichen Reihenfolge auftreten, und die Anweisungen innerhalb des zugeordneten strukturierten Blocks werden von einer oder mehrere Threads ausgeführt.  Die Barriere, die am Ende eines Arbeitsteilungs konstrukts ohne eine `nowait`\-Klausel impliziert wird, wird von allen Threads im Team ausgeführt.  
  
 Wenn ein Thread ein freigegebenes Objekt geändert wird, wirkt sich dies nicht nur ihre eigene Ausführungsumgebung, sondern auch die anderen Threads im Programm.  Die Änderung wird garantiert, entsprechend einem der anderen Threads abgeschlossen sind, am nächsten Sequenzpunkt \(wie in der Sprache definiert\) nur wenn das Objekt deklariert wird, um flüchtige sein.  Andernfalls wird sichergestellt, dass die Änderung zunächst nach dem Thread abgeschlossen sein, der geändert wird. Anschließend \(oder anderen Threads gleichzeitig\) gelten, **leer**\-Direktiven an, die das Objekt angibt \(entweder implizit oder explizit\).  Beachten Sie, dass, wenn die **leer**\-Direktive, die von anderen OpenMP\-Direktive werden, bedeutet nicht ausreichen, um die gewünschte Reihenfolge von Nebeneffekten sichergestellt, es in der Verantwortung des Programmierers ist, zusätzliche explizite **leer**\-Direktive anzugeben.  
  
 Bei Abschluss des parallelen Konstrukt synchronisieren die Threads im Team an einer impliziten Barriere, und nur der Masterthread setzt die Ausführung fort.  Parallele beliebig viele Konstrukte können in einem einzelnen Programm angegeben werden.  Folglich ein Programm sich viele Male während der Ausführung zu erzeugen und hergestellt werden.  
  
 OpenMP C\/C\+\+ können Programmierer APIs verwenden, die in Funktionen direktiven aus parallelen Konstrukte aufgerufen werden.  Direktiven, die nicht im lexikalischen Wertebereich eines parallelen Konstrukt angezeigt werden, jedoch möglicherweise im dynamischen Wertebereichs liegen, werden als *verwaiste* Direktive.  Verwaiste Direktiven geben Programmierer die Möglichkeit, wesentliche Teile des Programms parallel mit nur minimalen Änderungen am Ablaufprogramm auszuführen.  Mit dieser Funktion können Benutzer Ebenen der Code parallelen Konstrukte der Programm \- Struktur und rufen Direktiven verwenden, führen Sie in einem der aufgerufenen Funktionen oben steuern.  
  
 Unsynchronisierte Aufrufe von C\- und C\+\+\-Ausgabefunktionen, die auf dieselbe Datei schreiben, treten möglicherweise Ausgabe, in der die Daten, die von verschiedenen Threads geschrieben werden, in der Reihenfolge nicht deterministisch.  Entsprechend lesen unsynchronisierte Aufrufe möglicherweise zu den Eingaben, die von derselben Datei lesen, Daten in der Reihenfolge nicht deterministisch.  Unsynchronisierte Verwendung der E\/A, sodass jeder Thread eine andere Datei zugreift, stellt die gleichen Ergebnisse wie serielle Ausführung der E\/A\-Funktionen.