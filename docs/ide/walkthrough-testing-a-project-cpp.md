---
title: 'Exemplarische Vorgehensweise: Testen eines Projekts (C++) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- project testing [C++]
- testing projects
- projects [C++], testing
ms.assetid: 88cdd377-c5c8-4201-889d-32f5653ebead
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3a9455fa9bf3c9f903f5018a1263978913aa35b2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33333563"
---
# <a name="walkthrough-testing-a-project-c"></a>Exemplarische Vorgehensweise: Testen eines Projekts (C++)
Bei der Ausführung eines Programms im Debugmodus können Sie mithilfe von Haltepunkten die Programmausführung unterbrechen, um den Zustand von Variablen und Objekten zu untersuchen.  
  
 In dieser exemplarischen Vorgehensweise überwachen Sie während der Programmausführung den Wert einer Variablen und ziehen Schlussfolgerungen, warum der Wert möglicherweise nicht Ihren Erwartungen entspricht.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
  
-   In dieser exemplarischen Vorgehensweise wird davon ausgegangen, dass Sie die Grundlagen der Programmiersprache C++ beherrschen.  
  
-   Es wird ebenfalls davon ausgegangen, dass Sie die früheren exemplarischen Vorgehensweisen abgeschlossen haben, die unter [Using the Visual Studio IDE for C++ Desktop Development (Verwenden der Visual Studio-IDE für die C++-Desktopentwicklung)](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md) aufgeführt sind.  
  
### <a name="to-run-a-program-in-debug-mode"></a>So führen Sie ein Programm im Debugmodus aus  
  
1.  Öffnen Sie "TestGames.cpp" zum Bearbeiten.  
  
2.  Wählen Sie diese Codezeile aus:  
  
     `Cardgame.solitaire(1);`  
  
3.  Klicken Sie zum Festlegen eines Haltepunkts auf der Zeile in der Menüleiste auf **Debuggen** > **Haltepunkt ein/aus**, oder drücken Sie F9. Ein roter Kreis wird auf der linken Seite der Zeile angezeigt. Er gibt an, dass ein Haltepunkt festgelegt wurde. Zum Entfernen eines Haltepunkts können Sie den Menübefehl oder die F9-TASTE erneut auswählen.  
  
     Bei Verwendung einer Maus können Sie einen Haltepunkt festlegen oder entfernen, indem Sie auf den linken Rand klicken.  
  
4.  Klicken Sie in der Menüleiste auf **Debuggen** > **Debuggen starten**, oder drücken Sie F5.  
  
     Wenn bei der Programmausführung die Zeile mit dem Haltepunkt erreicht wird, wird die Ausführung vorübergehend unterbrochen (da sich das Programm im Unterbrechungsmodus befindet). Ein gelber Pfeil links neben einer Codezeile gibt an, dass diese Zeile als Nächstes ausgeführt wird.  
  
5.  Um den Wert der `Cardgame::totalParticipants`-Variable zu überprüfen, bewegen Sie den Zeiger über `Cardgame` und bewegen Sie ihn über das Erweiterungssteuerelement links vom QuickInfo-Fenster. Der Variablenname `totalParticipants` und der Wert "12" werden angezeigt.  
  
     Öffnen Sie das Kontextmenü der `Cardgame::totalParticipants`-Variable, und klicken Sie dann auf **Überwachung hinzufügen**, um die Variable im Fenster **Überwachen 1** anzuzeigen. Sie können auch eine Variable auswählen und in das Fenster **Überwachen 1** ziehen.  
  
6.  Klicken Sie in der Menüleiste auf **Debuggen** und dann auf **Prozedurschritt**, oder drücken Sie F10, um mit der nächsten Codezeile fortzufahren.  
  
     Der Wert von `Cardgame::totalParticipants` im Fenster **Überwachen 1** wird nun als „13“ angezeigt.  
  
7.  Öffnen Sie das Kontextmenü der Anweisung `return 0;`, und klicken Sie dann auf **Ausführen bis Cursor**. Der gelbe Pfeil links vom Code zeigt auf die Anweisung, die als Nächstes ausgeführt wird.  
  
8.  Die `Cardgame::totalParticipants`-Anzahl sollte abnehmen, wenn "Cardgame" beendet wird. An diesem Punkt sollte `Cardgame::totalParticipants` gleich „0“ sein, da alle Cardgame-Instanzen gelöscht wurden. Im Fenster **Überwachen 1** wird jedoch angegeben, dass `Cardgame::totalparticipants` gleich „18“ ist. Damit wird ein Fehler im Code deutlich, den Sie erkennen und beheben können, indem Sie die folgende exemplarische Vorgehensweise durchführen: [Walkthrough: Debugging a Project (C++) (Exemplarische Vorgehensweise: Debuggen eines Projekts (C++))](../ide/walkthrough-debugging-a-project-cpp.md).  
  
9. Klicken Sie zum Beenden des Programms in der Menüleiste auf **Debuggen** und **Debuggen beenden**, oder drücken Sie die Tastenkombination UMSCHALT+F5.  
  
## <a name="next-steps"></a>Nächste Schritte  
 **Zurück:** [Walkthrough: Building a Project (C++) (Exemplarische Vorgehensweise: Erstellen eines Projekts (C++))](../ide/walkthrough-building-a-project-cpp.md) &#124; **Weiter:** [Walkthrough: Debugging a Project (C++) (Exemplarische Vorgehensweise: Debuggen eines Projekts (C++))](../ide/walkthrough-debugging-a-project-cpp.md)  
  
## <a name="see-also"></a>Siehe auch  
 [C++ Language Reference (C++-Programmiersprachenreferenz)](../cpp/cpp-language-reference.md)   
 [Erstellen von C/C++-Programmen](../build/building-c-cpp-programs.md)