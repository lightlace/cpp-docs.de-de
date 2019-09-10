---
title: 'Exemplarische Vorgehensweise: Testen eines Projekts (C++)'
ms.date: 04/25/2019
helpviewer_keywords:
- project testing [C++]
- testing projects
- projects [C++], testing
ms.assetid: 88cdd377-c5c8-4201-889d-32f5653ebead
ms.openlocfilehash: e0422b4f862b5438a313e25dac421d591bbbb9a5
ms.sourcegitcommit: fd0f8839da5c6a3663798a47c6b0bb6e63b518bd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70273700"
---
# <a name="walkthrough-testing-a-project-c"></a>Exemplarische Vorgehensweise: Testen eines Projekts (C++)

Bei der Ausführung eines Programms im Debugmodus können Sie mithilfe von Haltepunkten die Programmausführung unterbrechen, um den Zustand von Variablen und Objekten zu untersuchen.

In dieser exemplarischen Vorgehensweise überwachen Sie während der Programmausführung den Wert einer Variablen und ziehen Schlussfolgerungen, warum der Wert möglicherweise nicht Ihren Erwartungen entspricht.

## <a name="prerequisites"></a>Erforderliche Komponenten

- In dieser exemplarischen Vorgehensweise wird davon ausgegangen, dass Sie die Grundlagen der Programmiersprache C++ beherrschen.

- Es wird ebenfalls davon ausgegangen, dass Sie die früheren exemplarischen Vorgehensweisen abgeschlossen haben, die unter [Verwenden der Visual Studio-IDE für die C++-Desktopentwicklung](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md) aufgeführt sind.

### <a name="to-run-a-program-in-debug-mode"></a>So führen Sie ein Programm im Debugmodus aus

1. Öffnen Sie „Games.cpp“, um die Datei zu bearbeiten.

1. Wählen Sie diese Codezeile aus:

   `Cardgame solitaire(1);`

1. Klicken Sie zum Festlegen eines Haltepunkts für diese Zeile in der Menüleiste auf **Debuggen** > **Haltepunkt ein/aus**, oder drücken Sie **F9**. Ein roter Kreis wird auf der linken Seite der Zeile angezeigt. Er gibt an, dass ein Haltepunkt festgelegt wurde. Zum Entfernen eines Haltepunkts können Sie den Menübefehl oder die **F9**-TASTE erneut auswählen.

   Bei Verwendung einer Maus können Sie einen Haltepunkt festlegen oder entfernen, indem Sie auf den linken Rand klicken.

1. Klicken Sie in der Menüleiste auf **Debuggen** > **Debuggen starten**, oder drücken Sie **F5**.

   Wenn bei der Programmausführung die Zeile mit dem Haltepunkt erreicht wird, wird die Ausführung vorübergehend unterbrochen (da sich das Programm im Unterbrechungsmodus befindet). Ein gelber Pfeil links neben einer Codezeile gibt an, dass diese Zeile als Nächstes ausgeführt wird.

1. Um den Wert der `Cardgame::totalParticipants`-Variable zu überprüfen, bewegen Sie den Zeiger über `Cardgame` und bewegen Sie ihn über das Erweiterungssteuerelement links vom QuickInfo-Fenster. Der Variablenname `totalParticipants` und der Wert **12** werden angezeigt.

   Öffnen Sie das Kontextmenü der `Cardgame::totalParticipants`-Variable, und klicken Sie dann auf **Überwachung hinzufügen**, um die Variable im Fenster **Überwachen 1** anzuzeigen. Sie können auch eine Variable markieren und in das Fenster **Überwachen 1** ziehen.

1. Klicken Sie in der Menüleiste auf **Debuggen** > **Prozedurschritt**, oder drücken Sie **F10**, um mit der nächsten Codezeile fortzufahren.

   Der Wert von `Cardgame::totalParticipants` im Fenster **Überwachen 1** wird nun als **13** angezeigt.

1. Öffnen Sie das Kontextmenü der Anweisung `return 0;`, und klicken Sie dann auf **Ausführen bis Cursor**. Der gelbe Pfeil links vom Code zeigt auf die Anweisung, die als Nächstes ausgeführt wird.

1. Die Anzahl von `Cardgame::totalParticipants` sollte abnehmen, wenn ein `Cardgame` beendet wird. An diesem Punkt sollte `Cardgame::totalParticipants` gleich „0“ sein, da alle `Cardgame`-Instanzen gelöscht wurden. Im Fenster **Überwachen 1** wird jedoch angegeben, dass `Cardgame::totalparticipants` gleich **18** ist. Durch diese Differenz wird ein Fehler im Code deutlich, den Sie erkennen und beheben können, indem Sie die folgende exemplarische Vorgehensweise durchführen: [Exemplarische Vorgehensweise: Debuggen eines Projekts (C++)](../ide/walkthrough-debugging-a-project-cpp.md)

1. Klicken Sie zum Beenden des Programms in der Menüleiste auf **Debuggen** > **Debuggen beenden**, oder drücken Sie die Tastenkombination **UMSCHALT**+**F5**.

## <a name="next-steps"></a>Nächste Schritte

**Zurück:** [Exemplarische Vorgehensweise: Erstellen eines Projekts (C++)](../ide/walkthrough-building-a-project-cpp.md)<br/>
**Weiter:** [Exemplarische Vorgehensweise: Debuggen eines Projekts (C++)](../ide/walkthrough-debugging-a-project-cpp.md)

## <a name="see-also"></a>Siehe auch

[C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)<br/>
[Projekte und Buildsysteme](../build/projects-and-build-systems-cpp.md)<br/>
