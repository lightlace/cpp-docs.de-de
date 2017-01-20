---
title: "String Editor"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.editors.string.F1"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "String editor"
  - "string tables"
  - "string tables, String editor"
  - "string editing"
  - "string editing, string tables"
  - "resource editors, String editor"
  - "strings [C++], editing"
ms.assetid: f71ab8de-3068-4e29-8e28-5a33d18dd416
caps.latest.revision: 15
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# String Editor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Zeichenfolgentabelle in einer Windows\-Ressource, die eine Liste mit IDs, Werten und Beschriftungen für alle Zeichenfolgen Ihrer Anwendung enthält. Beispielsweise befinden sich die Statusleistenmeldungen in der Zeichenfolgentabelle.  
  
 Beim Entwickeln einer Anwendung können Sie mehrere Zeichenfolgentabellen verwenden – eine für jede Sprache oder Bedingung. Ein ausführbares Moduls weist jedoch nur eine Zeichenfolgentabelle auf. Eine ausgeführte Anwendung kann auf verschiedene Zeichenfolgentabellen verweisen, wenn Sie die Tabellen in verschiedenen DLLs platzieren.  
  
 Mithilfe von Zeichenfolgentabellen können Sie Ihre Anwendung bequem in verschiedene Sprachen lokalisieren. Wenn sich alle Zeichenfolgen in einer Zeichenfolgentabelle befinden, können Sie die Anwendung lokalisieren, indem Sie die Zeichenfolgen \(und andere Ressourcen\) übersetzen, ohne den Quellcode zu ändern. Dies ist normalerweise sinnvoller, als manuell verschiedene Zeichenfolgen in Quelldateien zu suchen und zu ersetzen.  
  
 Mithilfe des Zeichenfolgen\-Editors können Sie diese Aktionen ausführen:  
  
-   [Suche nach einer oder mehreren Zeichenfolge\(n\)](../mfc/finding-a-string.md).  
  
-   Schnell [neue Einträge](../mfc/adding-or-deleting-a-string.md) in die Zeichenfolgentabelle einfügen.  
  
-   [Eine Zeichenfolge aus einer Ressourcendatei in eine andere verschieben](../mfc/moving-a-string-from-one-resource-file-to-another.md)  
  
-   [Direkte Bearbeitung für die Eigenschaften „ID“, „Value“ und „Caption“ verwenden](../mfc/changing-the-properties-of-a-string.md) und Änderungen sofort anzeigen.  
  
-   [Die „caption“\-Eigenschaft mehrerer Zeichenfolgen ändern](../mfc/changing-the-caption-property-of-multiple-strings.md)  
  
-   [Einer Zeichenfolge Formatierungs\- oder Sonderzeichen hinzufügen](../mfc/adding-formatting-or-special-characters-to-a-string.md)  
  
    > [!NOTE]
    >  Windows erlaubt die Erstellung leerer Zeichenfolgentabellen nicht. Wenn Sie eine Zeichenfolgentabelle ohne Einträge erstellen, wird sie beim Speichern der Ressourcendatei automatisch gelöscht.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten \(Projekten mit der Common Language Runtime als Zielplattform\) finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Anforderungen  
 Win32  
  
## Siehe auch  
 [Resource Editors](../mfc/resource-editors.md)   
 [Zeichenfolgen](http://msdn.microsoft.com/library/windows/desktop/ms646979.aspx)   
 [Informationen über Zeichenfolgen](http://msdn.microsoft.com/library/windows/desktop/ms647465.aspx)