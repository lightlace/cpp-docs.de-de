---
title: 'Exemplarische Vorgehensweise: Debuggen eines Projekts (C++) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 09/14/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- projects [C++], debugging
- project debugging [C++]
- debugging projects
ms.assetid: a5cade77-ba51-4b03-a7a0-6897e3cd6a59
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bd8d0cebc34b8f0d59f54e720d6a37a52ab2d9e9
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50069320"
---
# <a name="walkthrough-debugging-a-project-c"></a>Exemplarische Vorgehensweise: Debuggen eines Projekts (C++)

In dieser exemplarischen Vorgehensweise bearbeiten Sie das Programm, um das beim Testen des Projekts gefundene Problem zu beheben.

## <a name="prerequisites"></a>Erforderliche Komponenten

- In dieser exemplarischen Vorgehensweise wird davon ausgegangen, dass Sie die Grundlagen der Programmiersprache C++ beherrschen.

- Es wird ebenfalls davon ausgegangen, dass Sie die früheren exemplarischen Vorgehensweisen abgeschlossen haben, die unter [Verwenden der Visual Studio-IDE für die C++-Desktopentwicklung](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md) aufgeführt sind.

### <a name="to-fix-a-program-that-has-a-bug"></a>So korrigieren Sie ein fehlerhaftes Programm

1. Um zu sehen, was beim Zerstören eines `Cardgame`-Objekts geschieht, zeigen Sie den Destruktor der `Cardgame`-Klasse an.

   Klicken Sie in der Menüleiste auf **Ansicht** > **Klassenansicht**.

   Erweitern Sie im Fenster **Klassenansicht** die Projektstruktur **Spiel**, und wählen Sie zum Anzeigen der Klassenmembers und -methoden die Klasse **Cardgame** aus.

   Öffnen Sie das Kontextmenü für den Destruktor **~Cardgame (void)**, und klicken Sie dann auf **Gehe zu Definition**.

1. Um den Wert von `totalParticipants` beim Beenden eines Kartenspiels zu verringern, fügen Sie zwischen der öffnenden und der schließenden Klammer des `Cardgame::~Cardgame`-Destruktors folgenden Code hinzu.

   [!code-cpp[NVC_Walkthrough_Debugging_A_Project#110](../ide/codesnippet/CPP/walkthrough-debugging-a-project-cpp_1.cpp)]

1. Die Datei „Cardgame.cpp“ sieht nach der Änderung ungefähr wie der folgende Code aus:

   [!code-cpp[NVC_Walkthrough_Debugging_A_Project#111](../ide/codesnippet/CPP/walkthrough-debugging-a-project-cpp_2.cpp)]

1. Wählen Sie auf der Menüleiste **Erstellen** > **Projektmappe erstellen** aus.

1. Führen Sie sie nach Abschluss des Buildvorgangs im Debugmodus aus, indem Sie in der Menüleiste auf **Debuggen** > **Debuggen starten** klicken oder **F5** drücken. Die Programmausführung wird beim ersten Haltepunkt unterbrochen.

1. Klicken Sie in der Menüleiste auf **Debuggen** > **Prozedurschritt**, oder drücken Sie **F10**, um das Programm schrittweise zu durchlaufen.

   Beachten Sie, dass der Wert von `totalParticipants` nach der Ausführung jedes `Cardgame`-Konstruktors zunimmt. Wenn die `PlayGames`-Funktion zurückkehrt, sobald jede `Cardgame`-Instanz den Gültigkeitsbereich verlässt und gelöscht wird (und der Destruktor aufgerufen wird), nimmt der Wert von `totalParticipants` ab. Direkt vor der Ausführung der `return`-Anweisung ist `totalParticipants` gleich 0.

1. Setzen Sie das schrittweise Durchlaufen des Programms fort, bis es beendet wird, oder führen Sie das Programm aus, indem Sie in der Menüleiste auf **Debuggen** > **Ausführen** klicken oder **F5** drücken.

## <a name="next-steps"></a>Nächste Schritte

**Zurück:** [Exemplarische Vorgehensweise: Testen eines Projekts (C++)](../ide/walkthrough-testing-a-project-cpp.md)<br/>
**Weiter:** [Exemplarische Vorgehensweise: Bereitstellen des Programms (C++)](../ide/walkthrough-deploying-your-program-cpp.md)<br/>

## <a name="see-also"></a>Siehe auch

[C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)<br/>
[Erstellen von C/C++-Programmen](../build/building-c-cpp-programs.md)<br/>
