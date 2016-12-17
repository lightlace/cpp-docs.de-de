---
title: "Assigning Access Keys to Menu Commands"
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
  - "access keys [C++], checking"
  - "menus, shortcut keys"
  - "keyboard shortcuts [C++], command assignments"
  - "access keys [C++], assigning"
  - "mnemonics, adding to menus"
  - "keyboard shortcuts [C++], uniqueness checking"
  - "mnemonics, uniqueness checking"
  - "Check Mnemonics command"
ms.assetid: fbcf1a00-af6a-4171-805a-0ac01d4e8b0d
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Assigning Access Keys to Menu Commands
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können Ihren Menüs und Menübefehlen eine Zugriffstaste \(ein mnemonisches Zeichen, das dem Benutzer die Auswahl des Menüs mit der Tastatur ermöglicht\) zuweisen.  
  
### So weisen Sie einem Menübefehl eine Zugriffstaste \(Tastenkombination\) zu  
  
1.  Geben Sie vor einem Buchstaben im Namen des Menüs oder Befehls ein kaufmännisches Und\-Zeichen \(**&**\) ein, um diesen Buchstaben als die entsprechende Zugriffstaste festzulegen. Beispielsweise legt „&Datei“ ALT\+D als Tastenkombination für das Dateimenü in Anwendungen fest, die für Microsoft Windows erstellt wurden.  
  
     Das Menüelement gibt einen sichtbaren Hinweis darauf, dass einem der Buchstaben eine Zugriffstaste zugeordnet ist. Der Buchstabe, der auf das kaufmännische Und\-Zeichen folgt, wird unterstrichen dargestellt \(abhängig vom Betriebssystem\).  
  
    > [!NOTE]
    >  Achten Sie darauf, dass alle Zugriffstasten in einem Menü eindeutig sind, indem Sie mit der rechten Maustaste auf das Menü klicken und im Kontextmenü **Mnemonik überprüfen** auswählen.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Anforderungen  
  
 Win32  
  
## Siehe auch  
 [Menu Editor](../mfc/menu-editor.md)