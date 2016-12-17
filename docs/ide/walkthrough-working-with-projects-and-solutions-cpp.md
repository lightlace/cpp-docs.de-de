---
title: "Exemplarische Vorgehensweise: Arbeiten mit Projekten und L&#246;sungen (C++)"
ms.custom: na
ms.date: "12/15/2016"
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
  - "Projekte [C++]"
  - "Projekte [C++], Informationen über Projekte"
  - "Projektmappen [C++]"
  - "Projektmappen [C++], Informationen über Projektmappen"
ms.assetid: 93a3f290-e294-46e3-876e-e3084d9ae833
caps.latest.revision: 25
caps.handback.revision: "23"
ms.author: "corob"
manager: "ghogen"
---
# Exemplarische Vorgehensweise: Arbeiten mit Projekten und L&#246;sungen (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Abschnitt lesen Sie, wie Sie ein C\+\+\-Projekt in Visual Studio erstellen, Code hinzufügen und dann das Projekt erstellen und ausführen.  Bei dem Projekt in dieser exemplarischen Vorgehensweise handelt es sich um ein Programm, das nachverfolgt, wie viele Spieler verschiedene Kartenspiele spielen.  
  
 In [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] wird die Arbeit in Projekten und Projektmappen organisiert.  Eine Projektmappe kann mehr als ein Projekt enthalten, z. B. eine DLL und eine ausführbare Datei, die auf diese DLL verweist.  Weitere Informationen finden Sie unter [Projektmappen und Projekte](../Topic/Solutions%20and%20Projects%20in%20Visual%20Studio.md).  
  
## Vorbereitungsmaßnahmen  
  
-   Zur Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Grundkenntnisse in C\+\+.  
  
## Erstellen eines Projekts  
 Um ein Projekt zu erstellen, wählen Sie zunächst eine Projekttypvorlage.  Für jeden Projekttyp legt [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] Compilereinstellungen fest und generiert abhängig vom Typ Startcode, den Sie später ändern können.  
  
#### So erstellen Sie ein Projekt  
  
1.  Wählen Sie in der Menüleiste **Datei**, **Neu**, **Projekt** aus.  
  
2.  Erweitern Sie im linken Bereich des Dialogfelds **Neues Projekt** den Knoten für **installierte Vorlagen**, erweitern Sie dann den Knoten **Visual C\+\+**, und wählen Sie **Win32** aus.  
  
3.  Wählen Sie aus der Liste der installierten Vorlagen im mittleren Bereich **Win32\-Konsolenanwendung** aus.  
  
4.  Geben Sie in das Feld **Name** einen Namen für das Projekt ein.  Geben Sie für dieses Beispiel "Game" ein.  
  
     Sie können den Standardspeicherort in der Dropdownliste **Speicherort** akzeptieren, einen anderen Speicherort eingeben oder über die Schaltfläche **Durchsuchen** das Verzeichnis auswählen, in dem Sie das Projekt speichern möchten.  
  
     Beim Erstellen eines Projekts wird das Projekt von [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] in eine Lösung eingefügt.  Standardmäßig weist die Lösung den gleichen Namen wie das Projekt auf.  Sie können den Namen im Feld **Projektmappenname** ändern. Für dieses Beispiel behalten Sie jedoch bitte den Standardnamen bei.  
  
     Klicken Sie auf die Schaltfläche **OK**, um den **Win32\-Anwendungs\-Assistenten** zu starten.  
  
5.  Klicken Sie auf der Seite **Übersicht** des Dialogfelds **Win32\-Anwendungs\-Assistent** auf die Schaltfläche **Weiter**.  
  
6.  Wählen Sie auf der Seite **Anwendungseinstellungen** unter **Anwendungstyp** die Option **Konsolenanwendung** aus.  Deaktivieren Sie unter **Zusätzliche Optionen** die Einstellung **Vorkompilierter Header**, und wählen Sie die Einstellung **Leeres Projekt** aus.  Wählen Sie die Schaltfläche **Fertig stellen**, um das Projekt zu erstellen.  
  
     Sie verfügen nun über ein Projekt, das jedoch noch keine Quellcodedateien besitzt.  
  
## Organisieren von Projekten und Dateien in einer Projektmappe  
 Sie können den **Projektmappen\-Explorer** verwenden, um Projekte, Dateien und andere Ressourcen in der Projektmappe zu organisieren und zu verwalten.  
  
 In diesem Teil der exemplarischen Vorgehensweise wird gezeigt, wie dem Projekt eine Klasse hinzugefügt wird.  Wenn Sie die Klasse hinzufügen, fügt [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] die entsprechenden H\- und CPP\-Dateien hinzu.  Als Nächstes fügen Sie eine neue Quellcodedatei für das Hauptprogramm hinzu, das zum Testen der Klasse dient.  
  
#### So fügen Sie einem Projekt eine Klasse hinzu  
  
1.  Wenn der **Projektmappen\-Explorer** nicht angezeigt wird, klicken Sie in der Menüleiste auf **Ansicht** und dann auf **Projektmappen\-Explorer**.  
  
2.  Öffnen Sie im **Projektmappen\-Explorer** das Kontextmenü für den Ordner **Headerdateien**, und klicken Sie auf **Hinzufügen** und dann auf **Klasse**.  
  
     Erweitern Sie im linken Bereich des Dialogfelds **Klasse hinzufügen** den Knoten **Visual C\+\+**, und wählen Sie **C\+\+** aus. Wählen Sie anschließend aus der Liste der installierten Vorlagen im mittleren Bereich **C\+\+\-Klasse** aus.  Wählen Sie die Schaltfläche **Hinzufügen** aus.  
  
3.  Geben Sie im Dialogfeld **Generischer C\+\+\-Klassen\-Assistent** in das Feld **Klassenname** "Cardgame" ein.  Ändern Sie die Standarddateinamen und \- einstellungen nicht.  Wählen Sie die Schaltfläche **Fertig stellen** aus.  
  
4.  Die Cardgame.h\-Datei wird im Editor geöffnet.  Nehmen Sie folgende Änderungen vor:  
  
    -   Fügen Sie hinter der öffnenden geschweiften Klammer der Klassendefinition zwei private Datenmember hinzu.  
  
         [!CODE [NVC_Walkthrough_Working_With_Projects#100](../CodeSnippet/VS_Snippets_Cpp/nvc_walkthrough_working_with_projects#100)]  
  
    -   Ändern Sie den Standardkonstruktor, der von Visual Studio generiert wurde.  Suchen Sie nach dem `public:`\-Zugriffsspezifizierer die Zeile, die wie folgt aussieht:  
  
         `Cardgame(void);`  
  
         Ändern Sie die Zeile so, dass ein Parameter des Typs `int` namens "players" vorhanden ist.  
  
         [!CODE [NVC_Walkthrough_Working_With_Projects#101](../CodeSnippet/VS_Snippets_Cpp/nvc_walkthrough_working_with_projects#101)]  
  
    -   Fügen Sie nach dem Standarddestruktor eine inline\-Deklaration für eine statische int\-Memberfunktion namens GetParticipants hinzu, die keine Parameter übernimmt und den totalParticipants\-Wert zurückgibt.  
  
         [!CODE [NVC_Walkthrough_Working_With_Projects#102](../CodeSnippet/VS_Snippets_Cpp/nvc_walkthrough_working_with_projects#102)]  
  
5.  Die Datei "Cardgame.h" sieht nach der Änderung ungefähr folgendermaßen aus:  
  
     [!CODE [NVC_Walkthrough_Working_With_Projects#103](../CodeSnippet/VS_Snippets_Cpp/nvc_walkthrough_working_with_projects#103)]  
  
     Die Zeile `#pragma once` teilt dem Compiler mit, die Datei nur einmal aufzunehmen.  Weitere Informationen finden Sie unter [once](../preprocessor/once.md).  
  
     Informationen über weitere C\+\+\-Schlüsselwörter in dieser Headerdatei finden Sie unter [class](../cpp/class-cpp.md), [int](../cpp/fundamental-types-cpp.md), [static](../misc/static-cpp.md) und [public](../cpp/public-cpp.md).  
  
6.  Wählen Sie im Bearbeitungsbereich die Registerkarte **Cardgame.cpp** aus, um sie zum Bearbeiten zu öffnen.  
  
7.  Löschen Sie den gesamten Inhalt der Datei, und ersetzen Sie ihn durch den folgenden Code:  
  
     [!CODE [NVC_Walkthrough_Working_With_Projects#111](../CodeSnippet/VS_Snippets_Cpp/nvc_walkthrough_working_with_projects#111)]  
  
    > [!NOTE]
    >  Sie können bei der Codeeingabe die automatische Vervollständigung verwenden.  Bei der Eingabe dieses Codes können Sie beispielsweise "pl" oder "tot" eingeben und dann STRG\+LEERTASTE drücken, damit die automatische Vervollständigung `players` bzw. `totalParticipants` für Sie ergänzt.  
  
     Informationen zu `#include` finden Sie unter [\#include\-Direktive](../preprocessor/hash-include-directive-c-cpp.md).  
  
## Hinzufügen einer Quelldatei  
 Fügen Sie nun eine Quellcodedatei für das Hauptprogramm hinzu, das zum Testen der Klasse dient.  
  
#### So fügen Sie eine neue Quelldatei hinzu  
  
1.  Öffnen Sie im **Projektmappen\-Explorer** das Kontextmenü für den Ordner **Quelldateien**, und klicken Sie dann auf **Hinzufügen** und dann auf **Neues Element**.  
  
     Erweitern Sie im Dialogfeld **Neues Element hinzufügen** im linken Bereich den Knoten **Installiert**, erweitern Sie den Knoten **Visual C\+\+**, und wählen Sie dann **Code** aus.  Wählen Sie im mittleren Bereich die Option **C\+\+\-Datei \(.cpp\)**.  
  
2.  Geben Sie in das Feld **Name** "TestGames.cpp" ein, und klicken Sie dann auf die Schaltfläche **Hinzufügen**.  
  
3.  Geben Sie im Bearbeitungsfenster "TestGames.cpp" den folgenden Code ein:  
  
     [!CODE [NVC_Walkthrough_Working_With_Projects#120](../CodeSnippet/VS_Snippets_Cpp/nvc_walkthrough_working_with_projects#120)]  
  
## Erstellen und Ausführen eines Projekts  
 Erstellen Sie nun das Projekt, und führen Sie die Anwendung aus.  
  
#### So erstellen Sie das Projekt und führen es aus  
  
1.  Wählen Sie in der Menüleiste **Erstellen**, **Projektmappe erstellen**.  
  
    > [!NOTE]
    >  Wenn Sie eine Express Edition verwenden, bei der kein Menü **Erstellen** angezeigt wird, wählen Sie auf der Menüleiste **Extras**, **Einstellungen** und **Erweiterte Einstellungen** aus, um das Menü zu aktivieren.  
  
     Die Ausgabe eines Builds wird im **Ausgabefenster** angezeigt.  Wenn der Build erfolgreich erstellt wurde, sollte die Ausgabe in etwa wie folgt aussehen:  
  
  **1\>\-\-\-\-\-\- Erstellen gestartet: Projekt: Game, Konfiguration: Debug Win32 \-\-\-\-\-\-**  
**1\>  TestGames.cpp**  
**1\> Cardgame.cpp**  
**1\> Code wird generiert...**  
**1\> Game.vcxproj \-\> C:\\Users\\username\\Dokumente\\Visual Studio\\Projects\\Game\\Debug\\Game.exe**  
**\=\=\=\=\=\=\=\=\=\= Build: 1 erfolgreich, 0 fehlerhaft, 0 aktuell, 0 übersprungen \=\=\=\=\=\=\=\=\=\=**     Abhängig von der Edition und der Buildkonfiguration können im **Ausgabefenster** verschiedene Schritte angezeigt werden, wenn das Projekt jedoch erfolgreich erstellt wird, sollte die letzte Zeile der angezeigten Ausgabe ähneln.  
  
     Wenn die Erstellung nicht erfolgreich war, vergleichen Sie Ihren Code mit dem Code, der in den Schritten weiter oben angegeben wurde.  
  
2.  Wählen Sie zum Ausführen des Projekts auf der Menüleiste **Debuggen**, **Starten ohne Debugging** aus.  Die Ausgabe sollte dieser Ausgabe ähneln:  
  
  **4 Spieler haben ein neues Spiel begonnen.  Es gibt jetzt insgesamt 4 Spieler.**  
**8 Spieler haben ein neues Spiel begonnen.  Es gibt jetzt insgesamt 12 Spieler.**  
**1 Spieler hat ein neues Spiel begonnen.  Es gibt jetzt insgesamt 13 Spieler.**  
**5 Spieler haben ein neues Spiel begonnen.  Es gibt jetzt insgesamt 18 Spieler.**  
  
## Nächste Schritte  
 **Vorheriges Thema:** [Verwenden der Visual Studio\-IDE für C\+\+\-Desktopentwicklung](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).  **Nächstes Thema:** [Exemplarische Vorgehensweise: Erstellen eines Projekts \(C\+\+\)](../ide/walkthrough-building-a-project-cpp.md).  
  
## Siehe auch  
 [Visual C\+\+ Guided Tour](assetId:///499cb66f-7df1-45d6-8b6b-33d94fd1f17c)