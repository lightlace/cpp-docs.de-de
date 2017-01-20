---
title: "Visual C++-Projekttypen"
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
  - "Programme [C++], Projekte"
  - "Projektvorlagen [Visual Studio], C++"
  - "TODO-Kommentare [C++]"
  - "Projekte [C++], Typen"
  - "Vorlagen [C++], Projekte"
  - "Anwendungen [C++], Projekte"
  - "Visual C++-Projekte, Typen"
ms.assetid: 7337987e-1e7b-4120-9a4b-94f0401f15e7
caps.latest.revision: 20
caps.handback.revision: "20"
ms.author: "mblome"
manager: "ghogen"
---
# Visual C++-Projekttypen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können eine Projektvorlage verwenden, um eine grundlegende Programmstruktur, Menüs, Symbolleisten, Symbole, Verweise und `#include`\-Anweisungen zu erstellen, die für das gewünschte Projekt angemessen sind. Visual Studio umfasst verschiedene Arten von Visual C\+\+\-Projektvorlagen und bietet für viele von ihnen Assistenten, sodass Sie Ihre Projekte beim Erstellen anpassen können. Unmittelbar nachdem Sie ein Projekt angelegt haben, können Sie es erstellen und die Anwendung ausführen. Es ist empfehlenswert, die Erstellung immer wieder zwischendurch während der Entwicklung der Anwendung durchzuführen.  
  
 Sie müssen keine Vorlage verwenden, um ein Projekt zu erstellen, doch in den meisten Fällen ist es effizienter dies zu tun, da es einfacher ist, die bereitgestellten Projektdateien und die Struktur zu ändern, anstatt sie von Grund auf neu zu erstellen.  
  
> [!NOTE]
>  Mit C\+\+\-Projektvorlagen können Sie ein C\-Sprachprojekt erstellen. Suchen Sie im generierten Projekt die Dateien mit der Dateinamenerweiterung .cpp, und ändern Sie sie in .c. Erweitern Sie dann auf der Seite **Projekteigenschaften** für das Projekt \(nicht für die Projektmappe\) die Option **Konfigurationseigenschaften**, **C\/C\+\+**, und wählen Sie dann **Erweitert**. Ändern Sie die Einstellung **Kompilierungsart** in **Als C\-Code kompilieren \(\/TC\)**.  
  
## Projektvorlagen  
 Visual Studio bietet die folgenden Visual C\+\+\-Projektvorlagen.  
  
### Store\-Apps  
  
||  
|-|  
|[C\#\-, VB\- und C\+\+\-Projektvorlagen für Store\-Apps](http://go.microsoft.com/fwlink/p/?LinkID=262279)|  
  
### ATL  
  
|Projektvorlage|Erstellen eines Projekts|  
|--------------------|------------------------------|  
|ATL\-Projekt|[Erstellen eines ATL\-Projekts](../atl/reference/creating-an-atl-project.md)|  
  
### CLR  
  
|Projektvorlage|  
|--------------------|  
|[\(NOTINBUILD\) Klassenbibliotheksvorlage \(C\+\+\)](assetId:///0d779bfa-5c5a-4b10-a9d5-a6791764a78f)|  
|[Gewusst wie: Erstellen von CLR\-Konsolenanwendungen](../dotnet/how-to-create-clr-console-applications-cpp-cli.md)|  
|[NOTINBUILD CLR Leere Projektvorlage \(C\+\+\)](assetId:///f57c5572-5581-440f-b684-eec646764f08)|  
  
### Allgemein  
  
|Projektvorlage|Erstellen eines Projekts|  
|--------------------|------------------------------|  
|Leeres Projekt|[Erstellen von Projekten und Projektmappen](../Topic/Creating%20Solutions%20and%20Projects.md)|  
|Benutzerdefinierter Assistent|[Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)|  
|Makefile\-Projekt|[Erstellen eines Makefile\-Projekts](../ide/creating-a-makefile-project.md)|  
  
### MFC  
  
|Projektvorlage|Erstellen eines Projekts|  
|--------------------|------------------------------|  
|MFC\-ActiveX\-Steuerelement|[Erstellen eines MFC\-ActiveX\-Steuerelements](../mfc/reference/creating-an-mfc-activex-control.md)|  
|MFC\-Anwendung|[Erstellen einer MFC\-Anwendung](../mfc/reference/creating-an-mfc-application.md)|  
|MFC\-DLL|[Erstellen eines MFC\-DLL\-Projekts](../mfc/reference/creating-an-mfc-dll-project.md)|  
  
### Test  
  
|Projektvorlage|Erstellen eines Projekts|  
|--------------------|------------------------------|  
|Verwaltetes Testprojekt|[Ein Komponententestprojekt erstellen](../Topic/Create%20a%20unit%20test%20project.md)|  
|Testprojekt für systemeigene Komponente|[Komponententests für systemeigenen Code mit Test\-Explorer](assetId:///8a09d6d8-3613-49d8-9ffe-11375ac4736c)|  
  
### Win32  
  
|Projektvorlage|Erstellen eines Projekts|  
|--------------------|------------------------------|  
|Win32\-Konsolenprojekt|[Erstellen einer Konsolenanwendung](../windows/creating-a-console-application.md)|  
|Win32\-Projekt|[Gewusst wie: Erstellen einer Windows\-Desktopanwendung](../Topic/How%20to:%20Create%20a%20Windows%20Desktop%20Application.md)|  
  
## TODO\-Kommentare  
 Viele der mit einer Projektvorlage generierten Dateien enthalten TODO\-Kommentare, um Ihnen beim Identifizieren von Orten zu helfen, an denen Sie Ihren eigenen Quellcode bereitstellen können. Weitere Informationen zum Hinzufügen von Code finden Sie unter [Hinzufügen neuer Funktionen mit Code\-Assistenten](../ide/adding-functionality-with-code-wizards-cpp.md) und [Working with Resource Files](../mfc/working-with-resource-files.md).  
  
## Siehe auch  
 [Erstellen von Desktopprojekten mit Anwendungs\-Assistenten](../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Verwenden von Projekten zum Erstellen von Anwendungen](assetId:///3339fa90-bac2-4b95-8361-662a2e0e7dfe)   
 [CLR\-Projekte](../ide/files-created-for-clr-projects.md)