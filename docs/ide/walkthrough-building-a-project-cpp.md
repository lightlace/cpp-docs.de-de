---
title: "Exemplarische Vorgehensweise: Erstellen eines Projekts (C++)"
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
  - "Erstellen von Projekten [C++]"
  - "Projekte [C++], Erstellen"
  - "Erstellen eines Projekts [C++]"
ms.assetid: d459bc03-88ef-48d0-9f9a-82d17f0b6a4d
caps.latest.revision: 14
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# Exemplarische Vorgehensweise: Erstellen eines Projekts (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In dieser exemplarischen Vorgehensweise fügen Sie absichtlich einen Visual C\+\+\-Syntaxfehler in den Code ein, um zu lernen, wie ein Kompilierungsfehler aussieht und wie Sie diesen beheben.  Beim Kompilieren des Projekts wird eine Fehlermeldung angezeigt. Diese gibt an, worin das Problem besteht und wo es aufgetreten ist.  
  
## Vorbereitungsmaßnahmen  
  
-   In dieser exemplarischen Vorgehensweise wird davon ausgegangen, dass Sie die Grundlagen der Programmiersprache C\+\+ beherrschen.  
  
-   Es wird ebenfalls davon ausgegangen, dass Sie die früheren exemplarischen Vorgehensweisen dazu abgeschlossen haben, die in [Verwenden der Visual Studio\-IDE für C\+\+\-Desktopentwicklung](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md) aufgeführt sind.  
  
### So beheben Sie Kompilierungsfehler  
  
1.  Löschen Sie das Semikolon in der letzten Zeile von TestGames.cpp, sodass diese Zeile ungefähr wie folgt aussieht:  
  
     `return 0`  
  
2.  Wählen Sie in der Menüleiste **Erstellen**, **Projektmappe erstellen**.  
  
3.  Eine Meldung im Fenster **Fehlerliste** gibt an, dass bei der Erstellung des Projekts ein Fehler aufgetreten ist.  Die Beschreibung sieht ungefähr so aus:  
  
     `error C2143: syntax error : missing ';' before '}'`  
  
     Um Hilfeinformationen zu diesem Fehler anzuzeigen, markieren Sie ihn im Fenster **Fehlerliste**, und wählen Sie dann F1 aus.  
  
4.  Fügen Sie das Semikolon wieder am Ende der Zeile mit dem Syntaxfehler ein:  
  
     `return 0;`  
  
5.  Wählen Sie in der Menüleiste **Erstellen**, **Projektmappe erstellen**.  
  
     Die im **Ausgabe**\-Fenster angezeigte Meldung gibt an, dass das Projekt ordnungsgemäß kompiliert wurde.  
  
  **1\>\-\-\-\-\-\- Erstellen gestartet: Projekt: Game, Konfiguration: Debug Win32 \-\-\-\-\-\-**  
**1\>  TestGames.cpp**  
**1\>  Game.vcxproj \-\> C:\\Benutzer\\\<username\>\\Dokumente\\Visual Studio 2012 *\<version\>*Projects\\Game\\Debug\\Game.exe**  
**\=\=\=\=\=\=\=\=\=\= Build: 1 erfolgreich, 0 fehlerhaft, 0 aktuell, 0 übersprungen \=\=\=\=\=\=\=\=\=\=**  
  
## Nächste Schritte  
 **Zurück:** [Exemplarische Vorgehensweise: Arbeiten mit Projekten und Lösungen \(C\+\+\)](../ide/walkthrough-working-with-projects-and-solutions-cpp.md) &#124; **Weiter:** [Exemplarische Vorgehensweise: Testen eines Projekts \(C\+\+\)](../ide/walkthrough-testing-a-project-cpp.md)  
  
## Siehe auch  
 [Visual C\+\+ Guided Tour](assetId:///499cb66f-7df1-45d6-8b6b-33d94fd1f17c)   
 [DELETE\_PENDING\_Building and Debugging](assetId:///9f6ba537-5ea0-46fb-b6ba-b63d657d84f1)