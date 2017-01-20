---
title: "Wie das Framework Code aufruft"
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
helpviewer_keywords: 
  - "Anwendungsspezifische Ereignisse [C++]"
  - "Befehlsbehandlung, Aufrufen von Handlern und Code in MFC"
  - "Befehlsrouting, Framework"
  - "Befehlsrouting, MFC"
  - "Ablaufsteuerung [C++], MFC-Framework und der Code"
  - "Ereignisse [C++], Befehlsrouting in MFC"
  - "Ereignisse [C++], Ereignisgesteuerte Programmierung"
  - "MFC [C++], Aufrufen von Code"
  - "MFC [C++], Aufrufen von Code aus"
ms.assetid: 39e68189-a580-40d0-9e35-bf5cd24a8ecf
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Wie das Framework Code aufruft
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Es ist entscheidend, die Beziehung zwischen Quellcode und dem Code im MFC\-Framework zu verstehen.  Wenn die Anwendung ausgeführt wird, befindet sich die meisten des Programmablaufs im Code des Frameworks.  Das Framework verwaltet die Nachrichtenschleife, die Meldungen von Windows veranschaulicht, während der Benutzer auswählt Befehle und Daten in einer Ansicht bearbeitet.  Ereignisse, die das Framework an behandeln kann, hängen nicht im Code vorhanden.  Beispielsweise kann das Framework, wie Fenster und die Anwendung als Reaktion für Benutzerbefehle beenden enthält.  Da diese Aufgaben behandelt, verwendet das Framework Meldungshandler und virtuelle Funktionen C\+\+, um Ihnen Möglichkeiten zu geben, auf diese Ereignisse ebenfalls zu reagieren.  Der Code ist nicht in Steuerelement, jedoch; das Framework ist.  
  
 Das Framework ruft der Code für diese Ereignisse auf.  Wenn der Benutzer einen Menübefehl auswählt, leitet das Framework den Befehl an einer Sequenz von C\+\+\-Objekten weiter: die aktuelle Ansicht und das Rahmenfenster, das Dokument zugeordnet mit der Ansicht, die Normal\-Vorlage des Dokuments und das Anwendungsobjekt.  Wenn eines dieser Objekte den Befehl behandeln kann, verwendet er das und die entsprechende Meldungshandlerfunktion auf.  Für jeden angegebenen Befehl kann der aufgerufene Code, das oder ggf. des Frameworks.  
  
 Diese Anordnung eignet sich an Programmierer etwas vertraut, die mit herkömmlicher Programmierung für Windows oder ereignisgesteuerte Programmierung verfügen.  
  
 In den zugehörigen Themen lesen Sie, welche Aufgaben das Framework durchführt, wie die Anwendung initialisiert und ausführen und dann bereinigt, während die Anwendung beendet wird.  Sie wissen auch, wo der Code Sie in Anpassungen schreiben.  
  
 Weitere Informationen finden Sie unter [Klasse CWinApp: Die Application\-Klasse](../mfc/cwinapp-the-application-class.md) und [Dokumentvorlagen und der Ansichts\-Erstellungs\-Prozess Dokument\/](../mfc/document-templates-and-the-document-view-creation-process.md).  
  
## Siehe auch  
 [Erstellen im Framework](../mfc/building-on-the-framework.md)