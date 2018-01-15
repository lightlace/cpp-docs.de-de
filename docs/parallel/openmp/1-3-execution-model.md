---
title: "1.3 Ausführungsmodell | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 85ae8bc4-5bf0-45e0-a45f-02de9adaf716
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ce9c2398b38effebbca428c811d86481ca94e7cd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="13-execution-model"></a>1.3 Ausführungsmodell
OpenMP verwendet der Fork-Join-Modell der parallelen Ausführung. Obwohl diese Fork-Join-Modell zur Lösung verschiedener Probleme hilfreich sein kann, ist es etwas für große Array-basierte Anwendungen angepasst werden. OpenMP ist dazu vorgesehen, Support-Programme, die ordnungsgemäß sowohl als parallele (mehrere Ausführungsthreads und eine vollständige OpenMP-Unterstützungsbibliothek) Programme ausgeführt werden und als sequenzielle Programme (Direktiven ignoriert und eine einfache Klassenbibliothek der OpenMP-Stubs). Es ist jedoch möglich und zulässig, um eine Anwendung entwickeln, die beim sequenziell ausgeführt, nicht ordnungsgemäß verhält. Darüber hinaus können verschiedene Grade der Parallelität aufgrund von Änderungen an der Zuordnung von numerischen Operationen verschiedene numerische Ergebnisse führen. Z. B. möglicherweise eine Reduzierung der seriellen Addition ein anderes Muster von Zuordnungen hinzufügen, als eine parallele Reduzierung. Diese verschiedenen Zuordnungen können es sich um die Ergebnisse der gleitkommaaddition ändern.  
  
 Mit der OpenMP-C-/C++-API geschriebenes Programm startet die Ausführung als ein einziger Thread der Ausführung aufgerufen, die *"master" Thread*. Bis das erste parallele Konstrukt ist in einer seriellen Region der master-Thread ausgeführt. In der OpenMP-C-/C++-API die **parallele** Richtlinie stellt eine parallele Konstrukt dar. Wenn ein paralleles Konstrukts erkannt wird, die master-Thread erstellt, ein Team von Threads, und der Master wird master des Teams. Jeder Thread in das Team führt die Anweisungen in der dynamischen Wertebereich eines parallelen Bereichs ist, mit Ausnahme der Arbeitsteilungskonstrukte. Arbeitsteilungskonstrukte müssen von allen Threads im Team in der gleichen Reihenfolge auftreten und die Anweisungen innerhalb der zugehörigen strukturierten Block von einer oder mehreren Threads ausgeführt werden. Die Grenze am Ende eines Konstrukts Freigeben von Arbeit ohne impliziert einen `nowait` -Klausel von allen Threads im Team ausgeführt wird.  
  
 Wenn ein Thread ein freigegebenes Objekt geändert werden, sind davon betroffen, nicht nur einen eigenen ausführungsumgebung, sondern auch die von anderen Threads im Programm. Die Änderung ist garantiert Vorgang abgeschlossen ist, aus der Sicht eines anderen Threads, am nächsten Sequenz (wie in der Basissprache definiert) nur, wenn das Objekt deklariert wurde, dass flüchtig sein. Hingegen die Änderung ist gewährleistet, dass abgeschlossen werden, nachdem zuerst thread die ändern, und anschließend (oder gleichzeitig) auftreten, die von anderen Threads eine **leeren** -Direktive, die das Objekt (entweder implizit oder explizit) angibt. Beachten Sie, dass bei der **leeren** Direktiven, die durch andere OpenMP-Direktiven impliziert werden sind nicht ausreichend, um sicherzustellen, dass die gewünschte Reihenfolge der Nebeneffekte, die es dem Programmierer ist dafür verantwortlich, geben Sie zusätzliche, explizite  **Flush** Direktiven.  
  
 Nach Abschluss des parallelen Konstrukts die Threads im Team eine implizite Barriere zu synchronisieren, und nur die master-Thread wird die Ausführung fortgesetzt. Eine beliebige Anzahl von parallelen Konstrukten kann in einem einzelnen Programm angegeben werden. Daher kann ein Programm Verzweigen (fork) und verknüpfen oft während der Ausführung.  
  
 OpenMP-C-/C++-API können Programmierer das zur Verwendung von Anweisungen in Funktionen, die aus den parallelen Konstrukten aufgerufen. Direktiven, die nicht im lexikalischen Block eines parallelen Konstrukts angezeigt, jedoch möglicherweise liegen in einem dynamischen Block heißen *verwaiste* Direktiven. Verwaiste Direktiven geben Programmierer die Möglichkeit, große Teile des Programms parallel mit nur minimale Änderungen an das sequenzielle Programm auszuführen. Benutzer können mit dieser Funktionalität können code auf den oberen Ebenen der Aufrufstruktur der Anwendung den parallele Konstrukten und Verwenden von Richtlinien zur Steuerung der Ausführung in der aufgerufenen Funktionen.  
  
 Nicht synchronisierte Aufrufe an C und C++ ausgegeben werden, dass Funktionen, die auf dieselbe Datei Schreiben in Ausgabe führen können, in der von anderen Threads geschriebene Daten nicht deterministisch nacheinander angezeigt wird. Nicht synchronisierte Aufrufe zur Eingabe von Funktionen, die aus der gleichen Datei lesen können auf ähnliche Weise Daten in nicht deterministisch Reihenfolge lesen. Nicht synchronisierte Verwendung von e/a erzeugt, dass jeder Thread eine andere Datei greift auf die gleichen Ergebnisse wie die serielle Ausführung der e/a-Funktionen.