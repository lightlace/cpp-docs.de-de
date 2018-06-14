---
title: 'Exemplarische Vorgehensweise: Debuggen eines Projekts (C++) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: ecfda5e2549b3aa9be1f0471e301cc2a21c6fd5a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33340033"
---
# <a name="walkthrough-debugging-a-project-c"></a>Exemplarische Vorgehensweise: Debuggen eines Projekts (C++)
In dieser exemplarischen Vorgehensweise bearbeiten Sie das Programm, um das beim Testen des Projekts gefundene Problem zu beheben.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
  
-   In dieser exemplarischen Vorgehensweise wird davon ausgegangen, dass Sie die Grundlagen der Programmiersprache C++ beherrschen.  
  
-   Es wird ebenfalls davon ausgegangen, dass Sie die früheren exemplarischen Vorgehensweisen abgeschlossen haben, die unter [Using the Visual Studio IDE for C++ Desktop Development (Verwenden der Visual Studio-IDE für die C++-Desktopentwicklung)](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md) aufgeführt sind.  
  
### <a name="to-fix-a-program-that-has-a-bug"></a>So korrigieren Sie ein fehlerhaftes Programm  
  
1.  Um zu sehen, was beim Zerstören eines `Cardgame`-Objekts geschieht, zeigen Sie den Destruktor der `Cardgame`-Klasse an.  
  
     Klicken Sie in der Menüleiste auf **Ansicht** und dann auf **Klassenansicht**.  
  
     Erweitern Sie im Fenster **Klassenansicht** die Projektstruktur **Spiel**, und wählen Sie zum Anzeigen der Klassenmembers und -methoden die Klasse **Cardgame** aus.  
  
     Öffnen Sie das Kontextmenü für den Destruktor **~Cardgame (void)**, und klicken Sie dann auf **Gehe zu Definition**.  
  
2.  Um den Wert von `totalParticipants` beim Beenden eines Kartenspiels zu verringern, fügen Sie zwischen der öffnenden und der schließenden Klammer des `Cardgame::~Cardgame`-Destruktors folgenden Code hinzu:  
  
     [!code-cpp[NVC_Walkthrough_Debugging_A_Project#110](../ide/codesnippet/CPP/walkthrough-debugging-a-project-cpp_1.cpp)]  
  
3.  Die Datei "Cardgame.cpp" sieht nach der Änderung ungefähr folgendermaßen aus:  
  
     [!code-cpp[NVC_Walkthrough_Debugging_A_Project#111](../ide/codesnippet/CPP/walkthrough-debugging-a-project-cpp_2.cpp)]  
  
4.  Wählen Sie in der Menüleiste **Erstellen**, **Projektmappe erstellen**.  
  
5.  Führen Sie sie nach Abschluss des Buildvorgangs im Debugmodus aus, indem Sie in der Menüleiste auf **Debuggen** und **Debugging starten** klicken oder F5 drücken. Die Programmausführung wird beim ersten Haltepunkt unterbrochen.  
  
6.  Klicken Sie in der Menüleiste auf **Debuggen** und **Prozedurschritt**, oder drücken Sie F10, um das Programm schrittweise durchzugehen.  
  
     Beachten Sie, dass der Wert von `totalParticipants` nach der Ausführung jedes Cardgame-Konstruktors zunimmt. Wird die `PlayGames`-Funktion zurückgegeben, sobald jede Cardgame-Instanz den Gültigkeitsbereichs verlässt und gelöscht wird (und der Destruktor aufgerufen wird), nimmt `totalParticipants` ab. Direkt vor der Ausführung der `return`-Anweisung ist `totalParticipants` gleich 0.  
  
7.  Setzen Sie das schrittweise Durchgehen des Programms fort, bis es beendet wird, oder lassen Sie es ausführen, indem Sie in der Menüleiste auf **Debuggen** und **Ausführen** klicken oder F5 drücken.  
  
## <a name="next-steps"></a>Nächste Schritte  
 **Zurück:** [Walkthrough: Testing a Project (C++) (Exemplarische Vorgehensweise: Testen eines Projekts (C++))](../ide/walkthrough-testing-a-project-cpp.md) &#124; **Weiter:** [Walkthrough: Deploying Your Program (C++) (Exemplarische Vorgehensweise: Bereitstellen des Programms (C++))](../ide/walkthrough-deploying-your-program-cpp.md)  
  
## <a name="see-also"></a>Siehe auch  
 [C++ Language Reference (C++-Programmiersprachenreferenz)](../cpp/cpp-language-reference.md)   
 [Erstellen von C/C++-Programmen](../build/building-c-cpp-programs.md)