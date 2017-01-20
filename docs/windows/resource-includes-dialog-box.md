---
title: "Dialogfeld &quot;Ressourcenincludes&quot;"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.editors.resourceincludes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Ressourcenincludes (Dialogfeld)"
  - "RC-Dateien, Ändern des Speichers"
  - "Symbolheaderdateien, ändern"
  - "Kompilieren von Quellcode, Einfügen von Ressourcen"
  - "RC-Dateien, Ändern des Speichers"
  - "Symbolheaderdateien, schreibgeschützte"
  - "Symbole, Symbolheaderdateien"
ms.assetid: 659a54e6-e416-4045-8411-798730ff4ce3
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Dialogfeld &quot;Ressourcenincludes&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können das **Ressourcenincludes** Dialogfeld verwenden, um die normale Arbeitsanordnung der Umgebung zum Speichern aller Ressourcen in der Projektdatei .rc und aller [Symbole](../mfc/symbols-resource-identifiers.md) in Resource.h zu modifizieren.  
  
 Zum Öffnen des **Ressourcenincludes** Dialogfelds, klicken Sie mit der rechten Maustaste auf eine RC\-Datei in [Ressourcenansicht](../windows/resource-view-window.md) und wählen Sie dann **Ressourcenincludes** aus dem Kontextmenü.  
  
 **Symbol header file**  
 Erlaubt es Ihnen, den Namen der Headerdatei dort zu ändern, wo die Symboldefinitionen für Ihre Ressourcendatei gespeichert werden.  Weitere Informationen finden Sie unter [Ändern der Namen von Symbolheaderdateien](../windows/changing-the-names-of-symbol-header-files.md).  
  
 **Direktiven für schreibgeschützte Symbole**  
 Ermöglicht es Ihnen, Headerdateien einzufügen, die Symbole enthalten, die während einer Bearbeitungssitzung nicht geändert werden sollen.  Sie können z. B. eine Symboldatei einfügen, die von mehreren Projekten gemeinsam verwendet wird.  Sie können auch die MFC H\-Dateien einfügen.  Weitere Informationen finden Sie unter [Einfügen gemeinsam genutzter \(schreibgeschützter\) oder berechneter Symbole](../windows/including-shared-read-only-or-calculated-symbols.md).  
  
 **Kompilierzeitdirektiven**  
 Ermöglicht Ihnen das Einfügen von Ressourcendateien, die separat von den Ressourcen in der Hauptressourcendatei erstellt und bearbeitet wurden, Kompilierzeitdirektiven \(z. B. die, die bedingt Ressourcen einfügen\) enthalten oder Ressourcen in einem benutzerdefinierten Format enthalten.  Sie können ebenso das Feld  Kompilierzeitdirektiven verwenden, um Standard\-MFC\-Ressourcendateien einzufügen.  Weitere Informationen finden Sie unter [Einfügen von Ressourcen zur Kompilierungszeit](../windows/how-to-include-resources-at-compile-time.md).  
  
> [!NOTE]
>  Einträge in diesen Textfeldern werden in der RC\-Datei jeweils von `TEXTINCLUDE 1`, `TEXTINCLUDE 2`, und `TEXTINCLUDE 3` markiert.  Weitere Informationen finden Sie unter [TN035: Verwenden mehrerer Ressourcendateien und Headerdateien mit Visual C\+\+](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md).  
  
 Nachdem Sie Änderungen in Ihrer Ressourcendatei mithilfe des **Ressourcenincludes** Dialogfelds vorgenommen haben, müssen Sie die RC\-Datei schließen und erneut öffnen, damit die Änderungen wirksam werden.  Weitere Informationen finden Sie unter [Einfügen von Ressourcen zur Kompilierungszeit](../windows/how-to-include-resources-at-compile-time.md).  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Anforderungen  
 Win32  
  
## Siehe auch  
 [How to: Specify Include Directories for Resources](../windows/how-to-specify-include-directories-for-resources.md)   
 [Symbols: Resource Identifiers](../mfc/symbols-resource-identifiers.md)   
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Resource Editors](../mfc/resource-editors.md)