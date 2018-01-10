---
title: "Exemplarische Vorgehensweise: Arbeiten mit Projekten und Lösungen (C++) | Microsoft Docs"
ms.custom: 
ms.date: 12/13/2017
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
ms.workload: cplusplus
ms.openlocfilehash: a20c0ee933d49465a841b638a8260181d7175ac5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-working-with-projects-and-solutions-c"></a>Exemplarische Vorgehensweise: Arbeiten mit Projekten und Lösungen (C++)

In diesem Abschnitt lesen Sie, wie Sie ein C++-Projekt in Visual Studio erstellen, Code hinzufügen und dann das Projekt erstellen und ausführen. Bei dem Projekt in dieser exemplarischen Vorgehensweise handelt es sich um ein Programm, das nachverfolgt, wie viele Spieler verschiedene Kartenspiele spielen.

In Visual Studio wird die Arbeit in Projekten und Projektmappen organisiert. Eine Projektmappe kann mehr als ein Projekt enthalten, z. B. eine DLL und eine ausführbare Datei, die auf diese DLL verweist. Weitere Informationen finden Sie unter [Projektmappen und Projekte](/visualstudio/ide/solutions-and-projects-in-visual-studio).

## <a name="before-you-start"></a>Vor der Installation

Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie Visual Studio 2017 Version 15,3 oder höher. Wenn Sie eine Kopie benötigen, wird hier eine kurze Anleitung: [Installieren von C++-Unterstützung in Visual Studio](../build/vscpp-step-0-installation.md). Wenn Sie es noch nicht gespeichert haben, führen Sie die nächsten Schritte nach der Installation über das im Lernprogramm "Hello, World" Stellen Sie sicher, dass Visual C++ ordnungsgemäß installiert ist und es alles funktioniert.

Es ist hilfreich, wenn Sie die Grundlagen der Programmiersprache C++ verstehen und wissen, was für einen Compiler, Linker und Debugger verwendet werden. Im Lernprogramm wird davon ausgegangen, dass Sie mit Windows sowie zum Verwenden von Menüs, Dialogfeldern vertraut sind,

## <a name="create-a-project"></a>Erstellen eines Projekts

Um ein Projekt zu erstellen, wählen Sie zunächst eine Projekttypvorlage. Für jeden Projekttyp legt Visual Studio compilereinstellungen und – je nach Typ – generiert Startcode, den Sie später ändern können.

### <a name="to-create-a-project"></a>So erstellen Sie ein Projekt

1. Wählen Sie in der Menüleiste **Datei > Neu > Projekt**.

1. Im linken Bereich des der **neues Projekt** Dialogfeld erweitern Sie **installiert** , und wählen Sie **Visual C++**, wenn er bereits geöffnet ist.

1. Wählen Sie in der Liste der installierten Vorlagen im mittleren Bereich **Windows-Konsolenanwendung**.

1. Geben Sie einen Namen für das Projekt in der **Namen** Feld. In diesem Beispiel geben Sie **Spiel**.

   Sie können den Standardspeicherort in übernehmen die **Speicherort** Dropdown-Liste, geben Sie einen anderen Speicherort, oder wählen Sie die **Durchsuchen** Schaltfläche, um ein Verzeichnis zu suchen, in dem das Projekt gespeichert werden soll.

   Wenn Sie ein Projekt erstellen, fügt Visual Studio das Projekt in einer Projektmappe. Standardmäßig weist die Lösung den gleichen Namen wie das Projekt auf. Sie ändern können Sie den Namen in der **Projektmappenname** Feld, aber in diesem Beispiel behalten Sie den Standardnamen.

1. Wählen Sie die Schaltfläche **OK** aus, um das Projekt zu erstellen.

   Visual Studio erstellt die neue Projektmappe und Projektdateien und öffnet den-Editor für Game.cpp Quellcodedatei an, die sie generiert.

## <a name="organize-projects-and-files"></a>Organisieren von Projekten und Dateien

Sie können **Projektmappen-Explorer** organisieren und verwalten die Projekte, Dateien und andere Ressourcen in der Projektmappe.

In diesem Teil der exemplarischen Vorgehensweise wird gezeigt, wie dem Projekt eine Klasse hinzugefügt wird. Wenn Sie die Klasse hinzufügen, fügt Visual Studio die entsprechenden h- und CPP-Dateien. Sehen Sie die Ergebnisse in **Projektmappen-Explorer**.

### <a name="to-add-a-class-to-a-project"></a>So fügen Sie einem Projekt eine Klasse hinzu

1. Wenn die **Projektmappen-Explorer** Fenster ist nicht in Visual Studio in der Menüleiste angezeigt wird, wählen Sie **Ansicht > Projektmappen-Explorer**.

1. In **Projektmappen-Explorer**, wählen die **Spiel** Projekt. Wählen Sie in der Menüleiste **Projekt > Klasse hinzufügen**.

1. In der **Klasse hinzufügen** Dialogfeld, geben Sie *Cardgame* in der **Klassenname** Feld. Ändern Sie die Standarddateinamen und - einstellungen nicht. Klicken Sie auf die Schaltfläche **OK** .

   Visual Studio neue Dateien erstellt und dem Projekt hinzugefügt. Sehen Sie in der **Projektmappen-Explorer** Fenster. Die Cardgame.h und Cardgame.cpp-Dateien sind im Editor geöffnet.

1. Bearbeiten Sie die Cardgame.h-Datei, und nehmen Sie diese Änderungen vor:

   - Fügen Sie hinter der öffnenden geschweiften Klammer der Klassendefinition zwei private Datenmember hinzu.
      <!--      [!code-cpp[NVC_Walkthrough_Working_With_Projects#100](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_1.h)] -->

      ```cpp
      int players;
      static int totalParticipants;
      ```

   - Ändern Sie den Standardkonstruktor, der von Visual Studio generiert wurde. Suchen Sie nach dem `public:`-Zugriffsspezifizierer die Zeile, die wie folgt aussieht:

      `Cardgame();`

      Ändern Sie diesen Konstruktor, um einen Parameter des Typs annehmen `int`mit dem Namen *Player*.

      <!--[!code-cpp[NVC_Walkthrough_Working_With_Projects#101](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_2.h)]-->
      `Cardgame(int players);`

   - Fügen Sie nach dem Standarddestruktor eine Inline-Deklaration für eine `static int` -Memberfunktion namens *getParticipants hinzu* , die keine Parameter und gibt die `totalParticipants` Wert.

      <!--[!code-cpp[NVC_Walkthrough_Working_With_Projects#102](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_3.h)]-->
      `static int GetParticipants() { return totalParticipants; }`

   Die Datei "Cardgame.h" sieht nach der Änderung ungefähr folgendermaßen aus:

   <!--[!code-cpp[NVC_Walkthrough_Working_With_Projects#103](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_4.h)]-->
   ```cpp
   #pragma once
   class Cardgame
   {
       int players;
       static int totalParticipants;
   public:
       Cardgame(int players);
       ~Cardgame(void);
       static int GetParticipants() { return totalParticipants; }
   };
   ```

   Die Zeile `#pragma once` weist den Compiler an, die Header-Datei nur einmal aufzunehmen. Weitere Informationen finden Sie unter [nach](../preprocessor/once.md). Informationen über weitere C++-Schlüsselwörter in dieser Headerdatei finden Sie unter [Klasse](../cpp/class-cpp.md), [Int](../cpp/fundamental-types-cpp.md), [statische](../cpp/storage-classes-cpp.md), und [öffentlichen](../cpp/public-cpp.md).

1. Wählen Sie die **Cardgame.cpp** Registerkarte am oberen Rand der Bearbeitungsbereichs, um ihn zur Bearbeitung zu öffnen.

1. Löschen Sie den gesamten Inhalt der Datei, und ersetzen Sie ihn durch den folgenden Code:

   <!--[!code-cpp[NVC_Walkthrough_Working_With_Projects#111](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_5.cpp)]-->
   ```cpp
   #include "stdafx.h"
   #include "Cardgame.h"
   #include <iostream>

   using namespace std;

   int Cardgame::totalParticipants = 0;

   Cardgame::Cardgame(int players)
       : players(players)
   {
       totalParticipants += players;
       cout << players << " players have started a new game.  There are now "
            << totalParticipants << " players in total." << endl;
   }

   Cardgame::~Cardgame()
   {
   }
   ```

   > [!NOTE]
   > Sie können bei der Codeeingabe die automatische Vervollständigung verwenden. Beispielsweise, wenn Sie diesen Code über die Tastatur eingeben, können Sie eingeben *pl* oder *in Warteschlangen gesamt* und drücken Sie STRG + LEERTASTE. Automatische Vervollständigung eingibt `players` oder `totalParticipants` für Sie.

## <a name="add-test-code-to-your-main-function"></a>Hinzufügen von Testcode an Ihre main-Funktion

Fügen Sie Code hinzu, um Ihre app, die die neuen Funktionen testet.

### <a name="to-add-test-code-to-the-project"></a>So fügen Sie Testcode zum Projekt hinzu

1. Ersetzen Sie den vorhandenen Code im Editorfenster Game.cpp mit diesem:

   <!--[!code-cpp[NVC_Walkthrough_Working_With_Projects#120](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_6.cpp)]-->
   ```cpp
   // Game.cpp : Defines the entry point for the console application.
   //

   #include "stdafx.h"
   #include "Cardgame.h"
   #include <iostream>

   using namespace std;

   void PlayGames()
   {
       Cardgame bridge(4);
       Cardgame blackjack(8);
       Cardgame solitaire(1);
       Cardgame poker(5);
   }

   int main()
   {
       PlayGames();
       return 0;
   }
   ```
Dieser Code Fügt eine Testfunktion `PlayGames`, um den Quellcode, und ruft in `main`. 

## <a name="build-and-run-your-app-project"></a>Erstellen und Ausführen von app-Projekts

Als Nächstes erstellen Sie das Projekt, und führen Sie die app.

### <a name="to-build-and-run-the-project"></a>So erstellen Sie das Projekt und führen es aus

1. Klicken Sie in der Menüleiste auf **Erstellen > Projektmappe erstellen**.

   Ausgabe eines Builds wird angezeigt, der **Ausgabe** Fenster. Wenn der Build erfolgreich erstellt wurde, sollte die Ausgabe in etwa wie folgt aussehen:

   ```Output
   1>------ Build started: Project: Game, Configuration: Debug Win32 ------
   1>  stdafx.cpp
   1>  Game.cpp
   1>  Cardgame.cpp
   1>  Generating Code...
   1>  Game.vcxproj -> C:\Users\username\Source\Repos\Game\Debug\Game.exe
   ========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
   ```

   Die **Ausgabe** Fenster kann verschiedene Schritte, abhängig von der Buildkonfiguration angezeigt, aber wenn die Projektbuilds erfolgreich ist, sollte die letzte Zeile der angezeigten Ausgabe ähneln.

   Wenn Ihr Build nicht erfolgreich war, vergleichen Sie Ihren Code auf den Code, der in den vorherigen Schritten angezeigt wird.

1. Wählen Sie zum Ausführen des Projekts auf der Menüleiste **Debuggen > Starten ohne Debugging**. Eine Konsolenfenster sollte angezeigt werden, und die Ausgabe sollte diesem ähneln:

   ```Output
   4 players have started a new game.  There are now 4 players in total.
   8 players have started a new game.  There are now 12 players in total.
   1 players have started a new game.  There are now 13 players in total.
   5 players have started a new game.  There are now 18 players in total.
   ```
Drücken Sie im Konsolenfenster zu schließen.

Herzlichen Glückwunsch, Sie haben erfolgreich ein app-Projekt und Projektmappe erstellt. Weitere Informationen zum Erstellen von C++-Codeprojekte in Visual Studio weiterhin der exemplarischen Vorgehensweise.

## <a name="next-steps"></a>Nächste Schritte

**Vorherige:** [mithilfe von Visual Studio-IDE für C++-Desktopentwicklung](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).  
**Weiter:** [Exemplarische Vorgehensweise: Erstellen eines Projekts (C++)](../ide/walkthrough-building-a-project-cpp.md).

## <a name="see-also"></a>Siehe auch

[C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)  
[Erstellen von C/C++-Programmen](../build/building-c-cpp-programs.md)