---
title: "DCOM-Geschichte | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DCOM"
  - "DCOM, Informationen über DCOM"
  - "Remoteautomatisierung, DCOM"
ms.assetid: c21aa0ea-1396-4b52-b77f-88fb0fdd2a5c
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# DCOM-Geschichte
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Als Automatisierung zuerst Anfang 1993 eingeführt wurde, war es nur zwischen Anwendungen verwendet werden kann, die auf dem gleichen Computer ausgeführt werden.  Da er den gleichen Untermauerung wie der Rest von OLE d. h oder COM \(Component Object Model\) freigegeben hat, wurde es immer beabsichtigt, dass es "remotefähig" werden würde, COM als auch aktualisiert wurde, um Remotingfunktionen einzuschließen.  Es wurde außerdem geplant, dass der Übergang vom rein lokalen Vorgang den verteilten Vorgang wenige oder keine Änderungen am vorhandenen Code erforderlich wäre.  
  
 Daher geschieht was "Remoting" Durchschnitt?  COM local geschrieben hat vor, dass der Consumer eine Schnittstelle auf dem gleichen Computer wie der Anbieter dieser Schnittstelle befinden und ausführen.  Beispielsweise kann Microsoft Visual Basic eine Kopie von Microsoft Excel auf dem Tischplattencomputer steuern, jedoch konnte keine zur Richtung der Ausführung von Excel auf einem anderen Computer geeignet.  Bei der Entwicklung verteilter COM, muss der Consumer einer Schnittstelle nicht mehr auf dem gleichen Computer wie die befinden, auf der der Schnittstellenanbieter ausführt.  
  
 Sobald COM Arbeit über ein Netzwerk angepasst wurde, dann verfügen jede Schnittstelle, die nicht an einem lokalen Ausführungsmodell gebunden wurde \(einige Schnittstellen inhärentes Vertrauen auf Funktionen des lokalen Computerkontos, wie diese Zeichnungsschnittstellen, deren Methoden Handles für den Gerätekontexten als Parameter\) müssen über die Funktion von verteilt sind.  Ein Schnittstellenconsumer würde eine Anforderung für eine angegebene Schnittstelle stellen; Diese Schnittstelle wird einer Instanz eines laufenden Objekts \(oder ausgeführt werden\) auf einem anderen Computer bereitgestellt werden.  Der Verteilungsmechanismus in COM würde den Consumer an den Anbieter herstellen, dass die Methode, die vom Consumer vorgenommen wurden, am Anbieterende angezeigt würden, in dem sie ausgeführt werden.  Alle Werte stehen dann dem Consumer zurückgesendet sein.  In jeder Hinsicht ist die Aktion der Verteilung an den Consumer und den Anbieter transparent.  
  
 Solch eine Vielzahl von COM ist jetzt.  DCOM \(für "verteilte COM"\), hat mit den Versionen von Windows NT beginnend mit Version 4.0 und Windows 2000 umfassend enthalten.  Seit Ende 1996 ist auch für Windows 9x verfügbar sind.  In beiden Fällen enthält DCOM einen Satz aus Ersetzung und aus weiteren DLLs, mit einigen Dienstprogramme, die lokale und Remote COM\-Funktionen stellen.  Deshalb jetzt ein festes Bestandteil Win32\-basierte Plattformen, und wird auf anderen Plattformen von anderen Organisationen im Zeitverlauf bereitgestellt werden.  
  
## In diesem Abschnitt  
 [Wo passt Remoteautomatisierung in an?](../mfc/where-does-remote-automation-fit-in-q.md)  
  
 [Was bietet die Automatisierung?](../mfc/what-does-remote-automation-provide-q.md)  
  
## Siehe auch  
 [Remoteautomatisierung](../mfc/remote-automation.md)