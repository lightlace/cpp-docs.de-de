---
title: "Associating Menu Commands with Status Bar Text in MFC Applications"
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
  - "status bars, associating menu items"
  - "menus, status bar text"
ms.assetid: 757c0e02-bc97-493f-bccd-6cc6887ebc64
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# Associating Menu Commands with Status Bar Text in MFC Applications
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Anwendung kann für die vom Benutzer auszuwählenden Menübefehle beschreibenden Text anzeigen. Dazu müssen Sie im Eigenschaftenfenster jedem Menübefehl mit der **Eingabeaufforderung** \-Eigenschaft eine Textzeichenfolge zuweisen. Wenn eine Zeichenfolge in der [Zeichenfolgentabelle](../mfc/string-editor.md) die gleiche ID wie der Befehl aufweist, zeigt eine MFC\-Anwendung automatisch diese Zeichenfolgenressource in der Statusleiste der ausgeführten Anwendung an, wenn ein Benutzer auf ein Menüelement zeigt.  
  
### So ordnen Sie einer Statusleisten\-Zeichenfolge ein Menübefehl zu  
  
1.  Wählen Sie im **Menü**\-Editor den Menübefehl aus.  
  
2.  Geben Sie im [Eigenschaftenfenster](../Topic/Properties%20Window.md) den zugeordneten Statusleistentext im Feld **Eingabeaufforderung**ein.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Anforderungen**  
  
 MFC  
  
## Siehe auch  
 [Zeichenfolgen](../atl-mfc-shared/strings-atl-mfc.md)   
 [Adding Commands to a Menu](../windows/adding-commands-to-a-menu.md)   
 [Menu Editor](../mfc/menu-editor.md)