---
title: "Exemplarische Vorgehensweise: Arbeiten mit Projekten und Lösungen (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- solutions [C++]
- projects [C++], about projects
- projects [C++]
- solutions [C++], about solutions
ms.assetid: 93a3f290-e294-46e3-876e-e3084d9ae833
caps.latest.revision: "25"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6b30cd4885d5fdd65831c8044a088fcb87b52ae3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="walkthrough-working-with-projects-and-solutions-c"></a>Exemplarische Vorgehensweise: Arbeiten mit Projekten und Lösungen (C++)
In diesem Abschnitt lesen Sie, wie Sie ein C++-Projekt in Visual Studio erstellen, Code hinzufügen und dann das Projekt erstellen und ausführen. Bei dem Projekt in dieser exemplarischen Vorgehensweise handelt es sich um ein Programm, das nachverfolgt, wie viele Spieler verschiedene Kartenspiele spielen.  
  
 In Visual Studio wird die Arbeit in Projekten und Projektmappen organisiert. Eine Projektmappe kann mehr als ein Projekt enthalten, z. B. eine DLL und eine ausführbare Datei, die auf diese DLL verweist. Weitere Informationen finden Sie unter [Projektmappen und Projekte](/visualstudio/ide/solutions-and-projects-in-visual-studio).  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
  
-   Zur Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Grundkenntnisse in C++.  
  
## <a name="creating-a-project"></a>Erstellen eines Projekts  
 Um ein Projekt zu erstellen, wählen Sie zunächst eine Projekttypvorlage. Für jeden Projekttyp legt Visual Studio compilereinstellungen und – je nach Typ – generiert Startcode, den Sie später ändern können.  
  
#### <a name="to-create-a-project"></a>So erstellen Sie ein Projekt  
  
1.  Wählen Sie in der Menüleiste **Datei**, **Neu**, **Projekt**aus.  
  
2.  Im linken Bereich des der **neues Projekt** Dialogfeld erweitern Sie die **installierte Vorlagen** Knoten, erweitern Sie die **Visual C++** Knoten, und wählen Sie dann **Win32**.  
  
3.  Wählen Sie in der Liste der installierten Vorlagen im mittleren Bereich **Win32-Konsolenanwendung**.  
  
4.  Geben Sie einen Namen für das Projekt in der **Namen** Feld. In diesem Beispiel geben Sie **Spiel**.  
  
     Sie können den Standardspeicherort in übernehmen die **Speicherort** Dropdown-Liste, geben Sie einen anderen Speicherort, oder wählen Sie die **Durchsuchen** Schaltfläche, um ein Verzeichnis zu suchen, in dem das Projekt gespeichert werden soll.  
  
     Wenn Sie ein Projekt erstellen, fügt Visual Studio das Projekt in einer Projektmappe. Standardmäßig weist die Lösung den gleichen Namen wie das Projekt auf. Sie ändern können Sie den Namen in der **Projektmappenname** Feld, aber in diesem Beispiel behalten Sie den Standardnamen.  
  
     Wählen Sie die **OK** Schaltfläche zum Starten der **Win32-Anwendungsassistenten**.  
  
5.  Auf der **Übersicht** auf der Seite der **Win32-Anwendung-Assistent**, wählen Sie die **Weiter** Schaltfläche.  
  
6.  Auf der **Anwendungseinstellungen** Seite **Anwendungstyp**Option **Konsolenanwendung**. Klicken Sie unter **Zusatzoptionen**Deaktivieren der **vorkompilierter Header** festlegen, und wählen Sie dann die **leeres Projekt** Einstellung. Wählen Sie die Schaltfläche **Fertig stellen** , um das Projekt zu erstellen.  
  
     Sie verfügen nun über ein Projekt, das jedoch noch keine Quellcodedateien besitzt.  
  
## <a name="organizing-projects-and-files-in-a-solution"></a>Organisieren von Projekten und Dateien in einer Projektmappe  
 Sie können **Projektmappen-Explorer** organisieren und verwalten die Projekte, Dateien und andere Ressourcen in der Projektmappe.  
  
 In diesem Teil der exemplarischen Vorgehensweise wird gezeigt, wie dem Projekt eine Klasse hinzugefügt wird. Wenn Sie die Klasse hinzufügen, fügt Visual Studio die entsprechenden h- und CPP-Dateien. Als Nächstes fügen Sie eine neue Quellcodedatei für das Hauptprogramm hinzu, das zum Testen der Klasse dient.  
  
#### <a name="to-add-a-class-to-a-project"></a>So fügen Sie einem Projekt eine Klasse hinzu  
  
1.  Wenn **Projektmappen-Explorer** wird nicht angezeigt, in der Menüleiste wählen **Ansicht**, **Projektmappen-Explorer**.  
  
2.  In **Projektmappen-Explorer**, öffnen Sie das Kontextmenü für die **Headerdateien** Ordner, und wählen Sie dann **hinzufügen**, **Klasse**.  
  
     Im linken Bereich des der **Klasse hinzufügen** Dialogfeld erweitern Sie die **Visual C++** Knoten, und wählen **C++**, und wählen Sie dann in der Liste der installierten Vorlagen im mittleren Bereich  **C++-Klasse**. Wählen Sie die Schaltfläche **Hinzufügen** aus.  
  
3.  In der **generische C++-Klassen-Assistent**, geben Sie **Cardgame** in der **Klassenname** Feld. Ändern Sie die Standarddateinamen und - einstellungen nicht. Wählen Sie die **Fertig stellen** Schaltfläche.  
  
4.  Die Cardgame.h-Datei wird im Editor geöffnet. Nehmen Sie folgende Änderungen vor:  
  
    -   Fügen Sie hinter der öffnenden geschweiften Klammer der Klassendefinition zwei private Datenmember hinzu.  
  
         [!code-cpp[NVC_Walkthrough_Working_With_Projects#100](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_1.h)]  
  
    -   Ändern Sie den Standardkonstruktor, der von Visual Studio generiert wurde. Suchen Sie nach dem `public:`-Zugriffsspezifizierer die Zeile, die wie folgt aussieht:  
  
         `Cardgame(void);`  
  
         Ändern, um einen Parameter des Typs annehmen `int`mit dem Namen **Player**.  
  
         [!code-cpp[NVC_Walkthrough_Working_With_Projects#101](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_2.h)]  
  
    -   Fügen Sie nach dem Standarddestruktor eine Inline-Deklaration für eine statische Int-Memberfunktion, die mit dem Namen **getParticipants hinzu** , die keine Parameter und gibt die **TotalParticipants** Wert.  
  
         [!code-cpp[NVC_Walkthrough_Working_With_Projects#102](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_3.h)]  
  
5.  Die Datei "Cardgame.h" sieht nach der Änderung ungefähr folgendermaßen aus:  
  
     [!code-cpp[NVC_Walkthrough_Working_With_Projects#103](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_4.h)]  
  
     Die Zeile `#pragma once` teilt dem Compiler mit, die Datei nur einmal aufzunehmen. Weitere Informationen finden Sie unter [nach](../preprocessor/once.md).  
  
     Informationen über weitere C++-Schlüsselwörter in dieser Headerdatei finden Sie unter [Klasse](../cpp/class-cpp.md), [Int](../cpp/fundamental-types-cpp.md), [statische](../cpp/storage-classes-cpp.md), und [öffentlichen](../cpp/public-cpp.md).  
  
6.  Wählen Sie die **Cardgame.cpp** Registerkarte im Bearbeitungsbereich um ihn zur Bearbeitung zu öffnen.  
  
7.  Löschen Sie den gesamten Inhalt der Datei, und ersetzen Sie ihn durch den folgenden Code:  
  
     [!code-cpp[NVC_Walkthrough_Working_With_Projects#111](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_5.cpp)]  
  
    > [!NOTE]
    >  Sie können bei der Codeeingabe die automatische Vervollständigung verwenden. Z. B. Wenn Sie diesen Code eingegeben wurden, konnten eingegebene **pl** oder **in Warteschlangen gesamt** und drücken Sie dann STRG + LEERTASTE, sodass automatische Vervollständigung eingeben `players` oder `totalParticipants` für Sie.  
  
     Informationen zu `#include`, finden Sie unter [#include-Direktive (C/C++)](../preprocessor/hash-include-directive-c-cpp.md).  
  
## <a name="adding-a-source-file"></a>Hinzufügen einer Quelldatei  
 Fügen Sie nun eine Quellcodedatei für das Hauptprogramm hinzu, das zum Testen der Klasse dient.  
  
#### <a name="to-add-a-new-source-file"></a>So fügen Sie eine neue Quelldatei hinzu  
  
1.  In **Projektmappen-Explorer**, öffnen Sie das Kontextmenü für die **Quelldateien** Ordner, und wählen Sie dann **hinzufügen**, **neues Element**.  
  
     In der **neues Element hinzufügen** (Dialogfeld), im linken Bereich, erweitern Sie die **installiert** Knoten, erweitern Sie die **Visual C++** Knoten, und wählen Sie dann **Code**. Wählen Sie im mittleren Bereich die Option **C++-Datei (.cpp)**.  
  
2.  Geben Sie **"testgames.cpp"** in der **Namen** ein, und wählen Sie dann die **hinzufügen** Schaltfläche.  
  
3.  Geben Sie im Bearbeitungsfenster "TestGames.cpp" den folgenden Code ein:  
  
     [!code-cpp[NVC_Walkthrough_Working_With_Projects#120](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_6.cpp)]  
  
## <a name="building-and-running-a-project"></a>Erstellen und Ausführen eines Projekts  
 Erstellen Sie nun das Projekt, und führen Sie die Anwendung aus.  
  
#### <a name="to-build-and-run-the-project"></a>So erstellen Sie das Projekt und führen es aus  
  
1.  Wählen Sie in der Menüleiste **Erstellen**, **Projektmappe erstellen**.  
  
    > [!NOTE]
    >  Wenn Sie eine Express Edition verwenden, die nicht angezeigt wird eine **erstellen** , in der Menüleiste im Menü **Tools**, **Einstellungen**, **Erweiterte Einstellungen**zu aktivieren.  
  
     Ausgabe eines Builds wird angezeigt, der **Ausgabe** Fenster. Wenn der Build erfolgreich erstellt wurde, sollte die Ausgabe in etwa wie folgt aussehen:  
  
    ```Output  
    1>------ Build started: Project: Game, Configuration: Debug Win32 ------  
    1>  TestGames.cpp  
    1>  Cardgame.cpp  
    1>  Generating Code...  
    1>  Game.vcxproj -> c:\users\username\documents\visual studio\Projects\Game\Debug\Game.exe  
    ========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========  
  
    ```  
  
     Die **Ausgabe** Fenster kann verschiedene Schritte je nach der Edition und die Buildkonfiguration angezeigt, aber wenn die Projektbuilds erfolgreich ist, sollte die letzte Zeile der angezeigten Ausgabe ähneln.  
  
     Wenn die Erstellung nicht erfolgreich war, vergleichen Sie Ihren Code mit dem Code, der in den Schritten weiter oben angegeben wurde.  
  
2.  Wählen Sie zum Ausführen des Projekts auf der Menüleiste **Debuggen**, **Starten ohne Debugging**aus. Die Ausgabe sollte dieser Ausgabe ähneln:  
  
    ```Output  
    4 players have started a new game.  There are now 4 players in total.  
    8 players have started a new game.  There are now 12 players in total.  
    1 players have started a new game.  There are now 13 players in total.  
    5 players have started a new game.  There are now 18 players in total.  
    ```  
  
## <a name="next-steps"></a>Nächste Schritte  
 **Vorherige:** [mithilfe von Visual Studio-IDE für C++-Desktopentwicklung](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md). **Weiter:**[Exemplarische Vorgehensweise: Erstellen eines Projekts (C++)](../ide/walkthrough-building-a-project-cpp.md).  
  
## <a name="see-also"></a>Siehe auch  
 [C++-Sprachreferenz](../cpp/cpp-language-reference.md)   
 [Erstellen von C/C++-Programmen](../build/building-c-cpp-programs.md)