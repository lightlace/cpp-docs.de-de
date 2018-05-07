---
title: 'Exemplarische Vorgehensweise: Debuggen eines Projekts (C++) | Microsoft Docs'
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
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-debugging-a-project-c"></a>Exemplarische Vorgehensweise: Debuggen eines Projekts (C++)
In dieser exemplarischen Vorgehensweise bearbeiten Sie das Programm, um das beim Testen des Projekts gefundene Problem zu beheben.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
  
-   In dieser exemplarischen Vorgehensweise wird davon ausgegangen, dass Sie die Grundlagen der Programmiersprache C++ beherrschen.  
  
-   Außerdem wird angenommen, dass Sie zuvor verwandten exemplarischen Vorgehensweisen abgeschlossen haben, die aufgelisteten [über die Visual Studio-IDE für C++-Desktopentwicklung](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).  
  
### <a name="to-fix-a-program-that-has-a-bug"></a>So korrigieren Sie ein fehlerhaftes Programm  
  
1.  Um zu sehen, was beim Zerstören eines `Cardgame`-Objekts geschieht, zeigen Sie den Destruktor der `Cardgame`-Klasse an.  
  
     Wählen Sie in der Menüleiste **Ansicht**, **Klassenansicht**.  
  
     In der **Klassenansicht** Fenster, erweitern Sie die **Spiel** Projektstruktur und wählen Sie die **Cardgame** zum Anzeigen der-Klasse, Member und Methoden.  
  
     Öffnen Sie das Kontextmenü für die **~Cardgame(void)** Destruktor und wählen Sie dann **Gehe zu Definition**.  
  
2.  Um den Wert von `totalParticipants` beim Beenden eines Kartenspiels zu verringern, fügen Sie zwischen der öffnenden und der schließenden Klammer des `Cardgame::~Cardgame`-Destruktors folgenden Code hinzu:  
  
     [!code-cpp[NVC_Walkthrough_Debugging_A_Project#110](../ide/codesnippet/CPP/walkthrough-debugging-a-project-cpp_1.cpp)]  
  
3.  Die Datei "Cardgame.cpp" sieht nach der Änderung ungefähr folgendermaßen aus:  
  
     [!code-cpp[NVC_Walkthrough_Debugging_A_Project#111](../ide/codesnippet/CPP/walkthrough-debugging-a-project-cpp_2.cpp)]  
  
4.  Wählen Sie in der Menüleiste **Erstellen**, **Projektmappe erstellen**.  
  
5.  Wenn der Build abgeschlossen ist, führen Sie ihn im Debugmodus mit auswählen **Debuggen**, **Debuggen** in der Menüleiste oder durch Auswählen der F5-Taste. Die Programmausführung wird beim ersten Haltepunkt unterbrochen.  
  
6.  Schrittweise Durchlaufen des Programms in der Menüleiste wählen **Debuggen**, **Prozedurschritt**, oder drücken Sie F10.  
  
     Beachten Sie, dass der Wert von `totalParticipants` nach der Ausführung jedes Cardgame-Konstruktors zunimmt. Wird die `PlayGames`-Funktion zurückgegeben, sobald jede Cardgame-Instanz den Gültigkeitsbereichs verlässt und gelöscht wird (und der Destruktor aufgerufen wird), nimmt `totalParticipants` ab. Direkt vor der Ausführung der `return`-Anweisung ist `totalParticipants` gleich 0.  
  
7.  Fahren Sie fort, beim Durchlaufen des Programms, bis er beendet wird, oder lassen Sie ihn durch Auswahl ausführen **Debuggen**, **ausführen** in der Menüleiste oder durch Auswählen der F5-Taste.  
  
## <a name="next-steps"></a>Nächste Schritte  
 **Vorherige:** [Exemplarische Vorgehensweise: Testen eines Projekts (C++)](../ide/walkthrough-testing-a-project-cpp.md) &#124; **weiter:**[Exemplarische Vorgehensweise: Bereitstellen des Programms (C++)](../ide/walkthrough-deploying-your-program-cpp.md)  
  
## <a name="see-also"></a>Siehe auch  
 [C++-Sprachreferenz](../cpp/cpp-language-reference.md)   
 [Erstellen von C/C++-Programmen](../build/building-c-cpp-programs.md)