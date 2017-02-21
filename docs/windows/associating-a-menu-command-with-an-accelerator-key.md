---
title: "Associating a Menu Command with an Accelerator Key | Microsoft Docs"
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
  - "keyboard shortcuts, menu association"
  - "commands, associating menu commands with accelerator keys"
  - "menu commands, associating with keyboard shortcuts"
ms.assetid: ad2de43f-b20a-4c9f-bda8-0420179da48c
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Associating a Menu Command with an Accelerator Key
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Häufig ist es wünschenswert, dass ein Menübefehl und eine Tastenkombination den gleichen Programmbefehl ausgeben. Sie erreichen dies, indem Sie im Menü\-Editor dem Menübefehl und einem Eintrag in der Zugriffstastentabelle Ihrer Anwendung den gleichen Ressourcenbezeichner zuordnen. Anschließend bearbeiten Sie die [Beschriftung](../windows/menu-command-properties.md) des Menübefehls so, dass sie den Namen der Zugriffstaste anzeigt.  
  
### So ordnen Sie einen Menübefehl einer Zugriffstaste zu  
  
1.  Wählen Sie im **Menü**\-Editor den gewünschten Menübefehl aus.  
  
2.  Fügen Sie im [Eigenschaftenfenster](../Topic/Properties%20Window.md) der Eigenschaft **Caption** den Namen der Zugriffstaste hinzu:  
  
    -   Geben Sie im Anschluss an die Menübeschriftung die Escapesequenz für einen Tabulator \(\\t\) ein, damit alle Zugriffstasten des Menüs links ausgerichtet sind.  
  
    -   Geben Sie den Namen der Modifizierertaste \(**STRG**, **ALT** oder **UMSCHALT**\) ein, gefolgt von einem Pluszeichen \(**\+**\) und dem Namen, Buchstaben oder Symbol der zusätzlichen Taste.  
  
         Wenn Sie beispielsweise **STRG\+O** zum Befehl **Öffnen** im Menü **Datei** zuordnen möchten, ändern Sie die **Beschriftung** des Menübefehls, sodass sie aussieht wie hier dargestellt:  
  
        ```  
        &Open...\tCtrl+O   
        ```  
  
         Der Menübefehl im Menü\-Editor wird aktualisiert, um die neue Beschriftung so darzustellen, wie Sie sie eingeben.  
  
3.  [Erstellen Sie den Zugriffstastentabellen\-Eintrag](../windows/adding-an-entry-to-an-accelerator-table.md) im **Zugriffstasten**\-Editor, und weisen Sie ihm den gleichen Bezeichner wie dem Menübefehl zu. Verwenden Sie eine Tastenkombination, die Ihrer Ansicht nach leicht zu merken ist.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Anforderungen**  
  
 Win32  
  
## Siehe auch  
 [Adding Commands to a Menu](../windows/adding-commands-to-a-menu.md)   
 [Menu Editor](../mfc/menu-editor.md)