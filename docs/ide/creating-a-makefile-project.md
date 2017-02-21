---
title: "Erstellen eines Makefile-Projekts | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.makefile.project"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Makefile-Projekte, Erstellen"
  - "Projektdateien [C++], Makefile-Projekte"
ms.assetid: dd077af3-97a8-48fb-baaa-cf7e07ddef61
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Erstellen eines Makefile-Projekts
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie ein Projekt von der Befehlszeile mit einem Makefile erstellen, wird das Projekt in der Visual Studio\-Entwicklungsumgebung nicht erkannt.  Um das Projekt mithilfe von [!INCLUDE[vsUltShort](../ide/includes/vsultshort_md.md)], [!INCLUDE[vsPro](../ide/includes/vspro_md.md)] oder Visual Studio Express für Windows Desktop zu öffnen und zu erstellen, erstellen Sie zuerst ein leeres Projekt, indem Sie die MakeFile\-Projektvorlage auswählen.  Anschließend können Sie Ihr Projekt auf der Grundlage dieses Projekts in der Visual Studio\-Entwicklungsumgebung erstellen.  
  
 Im Projektmappen\-Explorer werden keine Dateien dieses Projekts angezeigt.  Die Buildeinstellungen, die auf der Eigenschaftenseite des Projekts angezeigt werden, werden vom Projekt festgelegt.  
  
 Die Ausgabedatei, die Sie im Projekt festlegen, hat keinen Einfluss auf den vom Buildskript erstellten Namen; sie deklariert lediglich die Bestimmung.  
  
### So erstellen Sie ein Makefile\-Projekt  
  
1.  Folgen Sie den Anweisungen im Hilfethema [Erstellen eines Projekts mit einem Visual C\+\+\-Anwendungs\-Assistenten](../ide/creating-desktop-projects-by-using-application-wizards.md).  
  
2.  Wählen Sie im Dialogfeld **Neues Projekt** im Vorlagenbereich die Option **Makefile\-Projekt** aus, um den Assistenten zu öffnen.  
  
3.  Geben Sie auf der Seite [Anwendungseinstellungen](../ide/application-settings-makefile-project-wizard.md) Befehls\-, Ausgabe\-, Bereinigungs\- und Neuerstellungsinformationen an.  
  
4.  Klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen und das neue Projekt im **Projektmappen\-Explorer** zu öffnen.  
  
 Sie können die Projekteigenschaften auf der Eigenschaftenseite des Projekts anzeigen und bearbeiten.  Weitere Informationen zum Anzeigen der Eigenschaftenseite finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../ide/working-with-project-properties.md).  
  
## Siehe auch  
 [Makefile\-Projekt\-Assistent](../ide/makefile-project-wizard.md)   
 [Sonderzeichen in einem Makefile](../build/special-characters-in-a-makefile.md)   
 [Inhalt eines Makefiles](../build/contents-of-a-makefile.md)