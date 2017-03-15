---
title: "Exemplarische Vorgehensweise: Debuggen eines Projekts (C++)"
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
  - "Debuggen von Projekten"
  - "Debuggen eines Projekts [C++]"
  - "Projekte [C++], Debuggen"
ms.assetid: a5cade77-ba51-4b03-a7a0-6897e3cd6a59
caps.latest.revision: 16
caps.handback.revision: "16"
ms.author: "corob"
manager: "ghogen"
---
# Exemplarische Vorgehensweise: Debuggen eines Projekts (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In dieser exemplarischen Vorgehensweise bearbeiten Sie das Programm, um das beim Testen des Projekts gefundene Problem zu beheben.  
  
## Vorbereitungsmaßnahmen  
  
-   In dieser exemplarischen Vorgehensweise wird davon ausgegangen, dass Sie die Grundlagen der Programmiersprache C\+\+ beherrschen.  
  
-   Es wird ebenfalls davon ausgegangen, dass Sie die früheren exemplarischen Vorgehensweisen dazu abgeschlossen haben, die in [Verwenden der Visual Studio\-IDE für C\+\+\-Desktopentwicklung](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md) aufgeführt sind.  
  
### So korrigieren Sie ein fehlerhaftes Programm  
  
1.  Um zu sehen, was beim Zerstören eines `Cardgame`\-Objekts geschieht, zeigen Sie den Destruktor der `Cardgame`\-Klasse an.  
  
     Wählen Sie in der Menüleiste **Ansicht**, **Klassenansicht** aus.  
  
     Erweitern Sie im Fenster **Klassenansicht** die Projektstruktur **Spiel**, und wählen Sie zum Anzeigen der Member und Methoden die Klasse **Cardgame** aus.  
  
     Öffnen Sie das Kontextmenü für den **~Cardgame \(void\)**\-Destruktor und wählen Sie dann **Gehe zu Definition** aus.  
  
2.  Um den Wert von `totalParticipants` beim Beenden eines Kartenspiels zu verringern, fügen Sie zwischen der öffnenden und der schließenden Klammer des `Cardgame::~Cardgame`\-Destruktors folgenden Code hinzu:  
  
     [!CODE [NVC_Walkthrough_Debugging_A_Project#110](../CodeSnippet/VS_Snippets_Cpp/nvc_walkthrough_debugging_a_project#110)]  
  
3.  Die Datei "Cardgame.cpp" sieht nach der Änderung ungefähr folgendermaßen aus:  
  
     [!CODE [NVC_Walkthrough_Debugging_A_Project#111](../CodeSnippet/VS_Snippets_Cpp/nvc_walkthrough_debugging_a_project#111)]  
  
4.  Wählen Sie in der Menüleiste **Erstellen**, **Projektmappe erstellen**.  
  
5.  Führen Sie es nach Abschluss des Buildvorgangs im Debugmodus aus, indem Sie auf der Menüleiste **Debuggen**, **Debugging starten** oder die F5\-TASTE auswählen.  Die Programmausführung wird beim ersten Haltepunkt unterbrochen.  
  
6.  Wählen Sie auf der Menüleiste **Debuggen** und dann **Prozedurschritt** aus, oder drücken Sie F10, um das Programm Schritt für Schritt durchzugehen.  
  
     Beachten Sie, dass der Wert von `totalParticipants` nach der Ausführung jedes Cardgame\-Konstruktors zunimmt.  Wird die `PlayGames`\-Funktion zurückgegeben, sobald jede Cardgame\-Instanz den Gültigkeitsbereichs verlässt und gelöscht wird \(und der Destruktor aufgerufen wird\), nimmt `totalParticipants` ab.  Direkt vor der Ausführung der `return`\-Anweisung ist `totalParticipants` gleich 0.  
  
7.  Setzen Sie das schrittweise Durchgehen des Programms fort, bis es beendet wird, oder lassen Sie es ausführen, indem Sie auf der Menüleiste **Debuggen**, **Ausführen** oder die F5\-TASTE auswählen.  
  
## Nächste Schritte  
 **Zurück:** [Exemplarische Vorgehensweise: Testen eines Projekts \(C\+\+\)](../ide/walkthrough-testing-a-project-cpp.md) &#124; **Weiter:** [Exemplarische Vorgehensweise: Bereitstellen des Programms \(C\+\+\)](../ide/walkthrough-deploying-your-program-cpp.md)  
  
## Siehe auch  
 [Visual C\+\+ Guided Tour](assetId:///499cb66f-7df1-45d6-8b6b-33d94fd1f17c)   
 [DELETE\_PENDING\_Building and Debugging](assetId:///9f6ba537-5ea0-46fb-b6ba-b63d657d84f1)