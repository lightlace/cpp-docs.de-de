---
title: "Entwerfen eines Assistenten | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Benutzerdefinierte Assistenten [C++], Entwerfen für Projekte"
  - "Projekte [C++], Benutzerdefinierte Assistenten"
  - "Visual C++-Projekte, Benutzerdefinierte Assistenten"
  - "Assistenten [C++], Benutzerdefiniert"
ms.assetid: a7c0be7e-9297-4fed-83e3-5645c896d56b
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Entwerfen eines Assistenten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gegebenenfalls müssen Sie Projekte mit standardisierten Features erstellen, die von den in Visual C\+\+ zur Verfügung gestellten Anwendungs\-Assistenten abweichen.  Zum Ausführen solcher Aufgaben können Sie die Assistentenarchitektur in Visual C\+\+ verwenden, die für eine problemlose Erweiterbarkeit und Anpassung ausgelegt ist.  Mithilfe des [benutzerdefinierten Visual C\+\+\-Assistenten](../ide/creating-a-custom-wizard.md) können Sie einen Assistenten erstellen.  Nachdem der Assistent erstellt wurde, können Sie ihn so konfigurieren, dass er die für Ihre Projekte erforderlichen Startdateien generiert.  
  
 Ein Visual C\+\+\-Assistent ist ein HTML\-Steuerelement.  Er verwendet das Visual C\+\+\-Assistentenmodul <xref:Microsoft.VisualStudio.VsWizard.IVCWizCtlUI>, das häufig verwendete Dienste, z. B. <xref:Microsoft.VisualStudio.VsWizard.IVCWizCtlUI.NavigateToCommandHandler*>, <xref:Microsoft.VisualStudio.VsWizard.IVCWizCtlUI.OkCancelAlert*> usw., bereitstellt.  Außerdem verwendet der Assistent das Skriptmodul, über das mit einem Assistenten sowohl VBScript als auch [JScript .NET](assetId:///c7e636ee-c10f-45b1-85ec-fe2daca30bf5) interpretiert werden kann.  
  
 Die Assistentenarchitektur bietet die Möglichkeit, auf die folgenden Objektmodelle direkt in den Assistenten zuzugreifen und ihre Methoden, Eigenschaften und Ereignisse sowohl aus den JScript\- als auch aus den HTML\-Dateien aufzurufen.  \(Weitere Informationen und Beispiele finden Sie unter [HTML\-Dateien](../ide/html-files.md) und [JScript\-Datei](../ide/jscript-file.md).\)  
  
-   [DTE\-\(Developer Tools Environment\-\)Objektmodell](../Topic/Extending%20the%20Visual%20Studio%20Environment.md)  
  
-   [Visual C\+\+\-Codemodell](assetId:///dd6452c2-1054-44a1-b0eb-639a94a1216b)  
  
-   [Visual C\+\+\-Projektmodell](assetId:///06c1bbd9-4c79-4f97-ad6d-2b1dea8ecd1f)  
  
-   [Visual C\+\+\-Assistentenmodell](assetId:///159395ac-33c7-47bf-ad42-4e1435ddc758)  
  
 Eine Beschreibung der einzelnen Elemente, die Sie zum Entwerfen von Assistenten benötigen, finden Sie unter [Für den Assistenten erstellte Dateien](../ide/files-created-for-your-wizard.md).  
  
## Siehe auch  
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Schritte zum Entwerfen eines Assistenten](../ide/steps-to-designing-a-wizard.md)   
 [Anpassen des Assistenten](../ide/customizing-your-wizard.md)