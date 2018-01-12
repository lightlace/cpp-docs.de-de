---
title: 'Exemplarische Vorgehensweise: Testen eines Projekts (C++) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- project testing [C++]
- testing projects
- projects [C++], testing
ms.assetid: 88cdd377-c5c8-4201-889d-32f5653ebead
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2ba928d4a81252b76856273160af63ed8707e7e5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-testing-a-project-c"></a>Exemplarische Vorgehensweise: Testen eines Projekts (C++)
Bei der Ausführung eines Programms im Debugmodus können Sie mithilfe von Haltepunkten die Programmausführung unterbrechen, um den Zustand von Variablen und Objekten zu untersuchen.  
  
 In dieser exemplarischen Vorgehensweise überwachen Sie während der Programmausführung den Wert einer Variablen und ziehen Schlussfolgerungen, warum der Wert möglicherweise nicht Ihren Erwartungen entspricht.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
  
-   In dieser exemplarischen Vorgehensweise wird davon ausgegangen, dass Sie die Grundlagen der Programmiersprache C++ beherrschen.  
  
-   Außerdem wird angenommen, dass Sie zuvor verwandten exemplarischen Vorgehensweisen abgeschlossen haben, die aufgelisteten [über die Visual Studio-IDE für C++-Desktopentwicklung](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).  
  
### <a name="to-run-a-program-in-debug-mode"></a>So führen Sie ein Programm im Debugmodus aus  
  
1.  Öffnen Sie "TestGames.cpp" zum Bearbeiten.  
  
2.  Wählen Sie diese Codezeile aus:  
  
     `Cardgame.solitaire(1);`  
  
3.  Wählen Sie zum Festlegen eines Haltepunkts in dieser Zeile, in der Menüleiste **Debuggen**, **Haltepunkt ein/aus**, oder drücken Sie F9. Ein roter Kreis wird auf der linken Seite der Zeile angezeigt. Er gibt an, dass ein Haltepunkt festgelegt wurde. Zum Entfernen eines Haltepunkts können Sie den Menübefehl oder die F9-TASTE erneut auswählen.  
  
     Bei Verwendung einer Maus können Sie einen Haltepunkt festlegen oder entfernen, indem Sie auf den linken Rand klicken.  
  
4.  Wählen Sie in der Menüleiste **Debuggen**, **Debuggen**, oder drücken Sie die F5-Taste.  
  
     Wenn bei der Programmausführung die Zeile mit dem Haltepunkt erreicht wird, wird die Ausführung vorübergehend unterbrochen (da sich das Programm im Unterbrechungsmodus befindet). Ein gelber Pfeil links neben einer Codezeile gibt an, dass diese Zeile als Nächstes ausgeführt wird.  
  
5.  Um den Wert der `Cardgame::totalParticipants`-Variable zu überprüfen, bewegen Sie den Zeiger über `Cardgame` und bewegen Sie ihn über das Erweiterungssteuerelement links vom QuickInfo-Fenster. Der Variablenname `totalParticipants` und der Wert "12" werden angezeigt.  
  
     Öffnen Sie das Kontextmenü für die `Cardgame::totalParticipants` Variable und wählen Sie dann **Überwachung hinzufügen** zum Anzeigen dieser Variablen in der **Überwachen 1** Fenster. Sie können auch eine Variable auswählen und ziehen Sie es auf die **Überwachen 1** Fenster.  
  
6.  Wählen Sie auf die nächste Zeile des Codes, auf der Menüleiste Schritt **Debuggen**, **Prozedurschritt**, oder drücken Sie F10.  
  
     Der Wert der `Cardgame::totalParticipants` in der **Überwachen 1** Fenster wird jetzt als 13 angezeigt.  
  
7.  Öffnen Sie das Kontextmenü für die `return 0;` Anweisung, und wählen Sie dann **Ausführen bis Cursor**. Der gelbe Pfeil links vom Code zeigt auf die Anweisung, die als Nächstes ausgeführt wird.  
  
8.  Die `Cardgame::totalParticipants`-Anzahl sollte abnehmen, wenn "Cardgame" beendet wird. An diesem Punkt `Cardgame::totalParticipants` sollte gleich 0, da alle Cardgame-Instanzen gelöscht wurden, aber die **Überwachen 1** Fenster gibt an, dass `Cardgame::totalparticipants` gleich 18. Dies gibt an, dass ein Fehler im Code können Sie erkennen und beheben, indem Sie die nächste exemplarische Vorgehensweise durcharbeiten, [Exemplarische Vorgehensweise: Debuggen von einem Projekt (C++)](../ide/walkthrough-debugging-a-project-cpp.md).  
  
9. Um das Programm in der Menüleiste zu beenden, wählen Sie **Debuggen**, **Beenden des Debuggens**, oder wählen Sie die Tastenkombination UMSCHALT + F5.  
  
## <a name="next-steps"></a>Nächste Schritte  
 **Vorherige:** [Exemplarische Vorgehensweise: Erstellen eines Projekts (C++)](../ide/walkthrough-building-a-project-cpp.md) &#124; **Weiter:**[Exemplarische Vorgehensweise: Debuggen eines Projekts (C++)](../ide/walkthrough-debugging-a-project-cpp.md)  
  
## <a name="see-also"></a>Siehe auch  
 [C++-Sprachreferenz](../cpp/cpp-language-reference.md)   
 [Erstellen von C/C++-Programmen](../build/building-c-cpp-programs.md)