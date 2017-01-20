---
title: "Exemplarische Vorgehensweise: Testen eines Projekts (C++)"
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
  - "Testen des Projekts [C++]"
  - "Projekte [C++], Testen"
  - "Testen des Projekts"
ms.assetid: 88cdd377-c5c8-4201-889d-32f5653ebead
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "corob"
manager: "ghogen"
---
# Exemplarische Vorgehensweise: Testen eines Projekts (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Bei der Ausführung eines Programms im Debugmodus können Sie mithilfe von Haltepunkten die Programmausführung unterbrechen, um den Zustand von Variablen und Objekten zu untersuchen.  
  
 In dieser exemplarischen Vorgehensweise überwachen Sie während der Programmausführung den Wert einer Variablen und ziehen Schlussfolgerungen, warum der Wert möglicherweise nicht Ihren Erwartungen entspricht.  
  
## Vorbereitungsmaßnahmen  
  
-   In dieser exemplarischen Vorgehensweise wird davon ausgegangen, dass Sie die Grundlagen der Programmiersprache C\+\+ beherrschen.  
  
-   Es wird ebenfalls davon ausgegangen, dass Sie die früheren exemplarischen Vorgehensweisen dazu abgeschlossen haben, die in [Verwenden der Visual Studio\-IDE für C\+\+\-Desktopentwicklung](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md) aufgeführt sind.  
  
### So führen Sie ein Programm im Debugmodus aus  
  
1.  Öffnen Sie "TestGames.cpp" zum Bearbeiten.  
  
2.  Wählen Sie diese Codezeile aus:  
  
     `Cardgame.solitaire(1);`  
  
3.  Um einen Haltepunkt in dieser Zeile festzulegen, wählen Sie auf der Menüleiste **Debuggen** und **Haltepunkt umschalten** aus, oder drücken Sie F9.  Ein roter Kreis wird auf der linken Seite der Zeile angezeigt. Er gibt an, dass ein Haltepunkt festgelegt wurde.  Zum Entfernen eines Haltepunkts können Sie den Menübefehl oder die F9\-TASTE erneut auswählen.  
  
     Bei Verwendung einer Maus können Sie einen Haltepunkt festlegen oder entfernen, indem Sie auf den linken Rand klicken.  
  
4.  Wählen Sie auf der Menüleiste **Debuggen** und **Debuggen starten** aus, oder wählen Sie die F5\-TASTE aus.  
  
     Wenn bei der Programmausführung die Zeile mit dem Haltepunkt erreicht wird, wird die Ausführung vorübergehend unterbrochen \(da sich das Programm im Unterbrechungsmodus befindet\).  Ein gelber Pfeil links neben einer Codezeile gibt an, dass diese Zeile als Nächstes ausgeführt wird.  
  
5.  Um den Wert der `Cardgame::totalParticipants`\-Variable zu überprüfen, bewegen Sie den Zeiger über `Cardgame` und bewegen Sie ihn über das Erweiterungssteuerelement links vom QuickInfo\-Fenster.  Der Variablenname `totalParticipants` und der Wert "12" werden angezeigt.  
  
     Öffnen Sie das Kontextmenü für die `Cardgame::totalParticipants`\-Variable und wählen Sie dann **Überwachung hinzufügen** aus, um die Variable im Fenster **Überwachen 1** anzuzeigen.  Sie können auch eine Variable auswählen und in das Fenster **Überwachen 1** ziehen.  
  
6.  Wählen Sie auf der Menüleiste **Debuggen** und dann **Prozedurschritt** aus, oder drücken Sie F10, um mit der nächsten Codezeile fortzufahren.  
  
     Der `Cardgame::totalParticipants`\-Wert im Fenster **Überwachen 1** wird jetzt als "13" angezeigt.  
  
7.  Öffnen Sie das Kontextmenü für die `return 0;`\-Anweisung und wählen Sie dann **Ausführen bis Cursor** aus.  Der gelbe Pfeil links vom Code zeigt auf die Anweisung, die als Nächstes ausgeführt wird.  
  
8.  Die `Cardgame::totalParticipants`\-Anzahl sollte abnehmen, wenn "Cardgame" beendet wird.  An diesem Punkt sollte `Cardgame::totalParticipants` gleich "0" sein, da alle Cardgame\-Instanzen gelöscht wurden. Im Fenster **Überwachen 1** wird aber angegeben, dass `Cardgame::totalparticipants` gleich "18" ist.  Damit wird ein Fehler im Code deutlich, den Sie erkennen und beheben können, indem Sie die folgende exemplarische Vorgehensweise durchführen: [Exemplarische Vorgehensweise: Debuggen eines Projekts \(C\+\+\)](../ide/walkthrough-debugging-a-project-cpp.md).  
  
9. Zum Beenden des Programms wählen Sie auf der Menüleiste **Debuggen** und dann **Debuggen beenden** aus, oder wählen Sie die Tastenkombination UMSCHALT\+F5 aus.  
  
## Nächste Schritte  
 **Zurück:** [Exemplarische Vorgehensweise: Erstellen eines Projekts \(C\+\+\)](../ide/walkthrough-building-a-project-cpp.md) &#124; **Weiter:** [Exemplarische Vorgehensweise: Debuggen eines Projekts \(C\+\+\)](../ide/walkthrough-debugging-a-project-cpp.md)  
  
## Siehe auch  
 [Visual C\+\+ Guided Tour](assetId:///499cb66f-7df1-45d6-8b6b-33d94fd1f17c)   
 [DELETE\_PENDING\_Building and Debugging](assetId:///9f6ba537-5ea0-46fb-b6ba-b63d657d84f1)