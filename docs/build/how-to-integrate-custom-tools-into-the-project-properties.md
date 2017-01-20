---
title: "Gewusst wie: Integrieren von benutzerdefinierte Tools in die Projekteigenschaften"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "msbuild.cpp.howto.integratecustomtools"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MSBuild (C++), Gewusst wie: Integrieren von benutzerdefinierten Tools"
ms.assetid: f32d91a4-44e9-4de3-aa9a-1c7f709ad2ee
caps.latest.revision: 14
caps.handback.revision: "14"
ms.author: "corob"
manager: "ghogen"
---
# Gewusst wie: Integrieren von benutzerdefinierte Tools in die Projekteigenschaften
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können dem Visual Studio\-Fenster **Eigenschaftenseiten** Optionen für benutzerdefinierte Tools hinzufügen, indem Sie eine zugrunde liegende XML\-Schemadatei erstellen.  
  
 Im Abschnitt **Konfigurationseigenschaften** des Fensters **Eigenschaftenseiten** werden Einstellungsgruppen angezeigt, die als *Regeln* bezeichnet werden.  Jede Regel enthält die Einstellungen für ein Tool oder eine Gruppe von Funktionen.  Die Regel **Linker** enthält z. B. die Einstellungen für das Linkertool.  Die Einstellungen in einer Regel können in *Kategorien* unterteilt werden.  
  
 In diesem Dokument wird beschrieben, wie in einem festgelegten Verzeichnis eine Datei erstellt wird, die Eigenschaften für das benutzerdefinierte Tool enthält, sodass die Eigenschaften beim Start von Visual Studio geladen werden.  Weitere Informationen darüber, wie die Datei, finden Sie unter [Plattform Extensibilty\-Teil 2](http://go.microsoft.com/fwlink/?LinkID=191489) im Visual Studio\-Projektteamblog ändert.  
  
### So fügen Sie Projekteigenschaften hinzu oder ändern Sie Projekteigenschaften  
  
1.  Erstellen Sie im XML\-Editor eine XML\-Datei.  
  
2.  Speichern Sie die Datei im Ordner "%Programme%\\MSBuild\\Microsoft.Cpp\\v4.0\\".  Jede Regel im Fenster **Eigenschaftenseiten** wird durch eine XML\-Datei in diesem Ordner dargestellt.  Stellen Sie sicher, dass die Datei im Ordner eindeutig benannt ist.  
  
3.  Kopieren Sie den Inhalt von "%Programme%\\MSBuild\\Microsoft.Cpp\\v4.0\\cl.xml", schließen Sie die Datei, ohne die Änderungen zu speichern, und fügen Sie den Inhalt dann in der neuen XML\-Datei ein.  Sie können eine beliebige XML\-Schemadatei verwenden. Dies ist nur eine Datei, die als Vorlage verwendet werden kann.  
  
4.  Ändern Sie in der neuen XML\-Datei den Inhalt entsprechend Ihren Anforderungen.  Denken Sie daran, den **Regelnamen** und **Rule.DisplayName** am Anfang der Datei zu ändern.  
  
5.  Speichern Sie die Änderungen, und schließen Sie die Datei.  
  
6.  Die XML\-Dateien in "%Programme%\\MSBuild\\Microsoft.Cpp\\v4.0\\" werden beim Start von Visual Studio geladen.  Starten Sie zum Testen der neuen Datei daher Visual Studio neu.  
  
7.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf ein Projekt, und klicken Sie dann auf **Eigenschaften**.  Überprüfen Sie im linken Bereich des Fensters **Eigenschaftenseiten**, ob ein neuer Knoten mit dem Namen der Regel vorhanden ist.  
  
## Siehe auch  
 [MSBuild \(Visual C\+\+\)](../build/msbuild-visual-cpp.md)