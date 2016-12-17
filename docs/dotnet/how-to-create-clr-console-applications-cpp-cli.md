---
title: "Gewusst wie: Erstellen von CLR-Konsolenanwendungen (C++/CLI)"
ms.custom: na
ms.date: "12/14/2016"
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
  - "Konsolenanwendungen, Vorlagen"
  - "CLR-Konsolenanwendungen, Projektvorlage"
ms.assetid: e89bce3c-706f-4ae0-8a90-cb1a0f674e70
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Erstellen von CLR-Konsolenanwendungen (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können die Vorlage für Konsolenanwendungen zum Erstellen eines Konsolen\-App\-Projekts verwenden, das bereits wesentliche Projektverweise und Dateien enthält.  
  
 Normalerweise wird eine Konsolen\-App in eine eigenständige ausführbare Datei kompiliert, sie hat jedoch keine grafische Benutzeroberfläche. Ein Benutzer führt die Konsolen\-App mit einer Eingabeaufforderung aus und verwendet die Eingabeaufforderung, um Anweisungen an die ausgeführte App auszugeben. Außerdem stellt die App an der Eingabeaufforderung Ausgabeinformationen bereit. Aufgrund ihrer Unmittelbarkeit eignet sich die Konsolen\-App hervorragend, um Programmiertechniken zu erlernen, ohne sich über die Implementierung einer Benutzeroberfläche Gedanken zu machen.  
  
 Wenn Sie die Vorlage für Konsolenanwendungen zum Erstellen eines Projekts verwenden, werden automatisch diese Verweise und Dateien hinzugefügt:  
  
-   Verweise auf diese .NET Framework\-Namespaces:  
  
    -   [System](https://msdn.microsoft.com/en-us/library/system.appdomainmanager.appdomainmanager.aspx) – Enthält grundlegende Klassen und Basisklassen zur Definition allgemein verwendeter Werte und Verweisdatentypen, Ereignisse und Ereignishandler, Schnittstellen, Attribute und Verarbeitungsausnahmen.  
  
    -   mscorlib – Assembly\-DLL, die die .NET Framework\-Entwicklung unterstützt.  
  
-   Quelldateien:  
  
    -   Konsole \(CPP\-Datei\) – Hauptquelldatei und Einstiegspunkt in die App, die Sie soeben erstellt haben. Diese Datei identifiziert die DLL\-Datei und den Namespace des Projekts. Fügen Sie eigenen Code in diese Datei ein.  
  
    -   AssemblyInfo.cpp – Diese Datei enthält Attribute, Dateien, Ressourcen, Typen, Versionsinformationen, Signaturinformationen usw., die Sie zum Ändern der Assemblymetadaten des Projekts verwenden können. Weitere Informationen finden Sie unter [Assemblyinhalte](../Topic/Assembly%20Contents.md).  
  
    -   Stdafx.cpp – Diese Datei wird zum Erstellen der vorkompilierten Headerdatei "Win32.pc" und der vorkompilierten Typendatei "StdAfx.obj" verwendet.  
  
-   Headerdateien:  
  
    -   Stdafx.h – Diese Datei wird zum Erstellen der vorkompilierten Headerdatei "Win32.pc" und der vorkompilierten Typendatei "StdAfx.obj" verwendet.  
  
    -   resource.h – Eine generierte Includedatei für "app.rc".  
  
-   Ressourcendateien:  
  
    -   app.rc – Die Ressourcenskriptdatei eines Programms.  
  
    -   app.ico – Die Symboldatei eines Programms.  
  
-   ReadMe.txt – Diese Datei beschreibt die Dateien im Projekt.  
  
## Zum Erstellen eines Common Language Runtime \(CLR\)\-Konsolen\-App\-Projekts  
  
1.  Wählen Sie in der Menüleiste **Datei**, **Neu**, **Projekt** aus.  
  
2.  Wählen Sie im Dialogfeld **Neues Projekt** im Bereich **Installierte Vorlagen** den Knoten **Visual C\+\+** aus. Wählen Sie den Knoten **CLR** und dann die Vorlage für Konsolenanwendungen aus.  
  
3.  Geben Sie im Feld **Name** einen eindeutigen Namen für die Anwendung ein.  
  
     Sie können andere Projekt\- und Lösungseinstellungen angeben, sie sind jedoch nicht erforderlich.  
  
4.  Klicken Sie auf die Schaltfläche **OK**.  
  
## Siehe auch  
 [NOTINBUILD Gewusst wie: Erstellen von CLR\-Konsolenanwendungen](assetId:///b8af4197-e65f-4b17-b18e-b9e92965d026)   
 [CLR\-Projekte](../ide/files-created-for-clr-projects.md)   
 [NIB: Elementverwaltung in Projekten](assetId:///762e606b-7f44-4b66-97a1-e30a703654a0)