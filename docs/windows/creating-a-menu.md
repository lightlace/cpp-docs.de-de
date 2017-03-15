---
title: "Creating a Menu | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.menu"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "mnemonics, associating menu items"
  - "menus, associating commands with mnemonic keys"
  - "menus, creating"
ms.assetid: 66f94448-9b97-4b73-bf97-10d4bf87cc65
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Creating a Menu
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Das Ressourcen\-Fenster ist in Express\-Editionen nicht verfügbar.  
  
### So erstellen Sie ein Standardmenü  
  
1.  Klicken Sie im Menü **Ansicht** auf **Ressourcenansicht** und klicken Sie mit der rechten Maustaste auf die Überschrift **Menü**, und wählen Sie **Ressource hinzufügen** aus. Wählen Sie **Menü** aus.  
  
2.  Wählen Sie auf der Menüleiste das Feld **Neues Element** \(das Rechteck mit dem Text "Hier eingeben"\) aus.  
  
     ![Feld "Neues Element" im Menü&#45;Editor](../windows/media/vcmenueditornewitembox.png "vcMenuEditorNewItemBox")  
Feld "Neues Element"  
  
3.  Geben Sie einen Namen für das neue Menü ein, z. B. "Datei".  
  
     Der eingegebene Text wird sowohl im **Menü**\-Editor als auch im Feld **Beschriftung** im [Eigenschaftenfenster](../Topic/Properties%20Window.md) angezeigt. Die Eigenschaften des neuen Menüs können an einer der beiden Stellen bearbeitet werden.  
  
     Nachdem Sie das neue Menü in der Menüleiste benannt haben, rückt das Feld für das neue Menüelement nach rechts \(damit ein weiteres Menü eingefügt werden kann\). Unter dem ersten Menü wird ein weiteres Feld geöffnet, dem Sie Menübefehle hinzufügen können.  
  
     ![Erweitertes Feld "Neues Element"](../windows/media/vcmenueditornewitemboxexpanded.png "vcMenuEditorNewItemBoxExpanded")  
Feld "Neues Element", dessen Fokus nach der Eingabe des Menünamens versetzt wurde  
  
    > [!NOTE]
    >  Um ein Menü mit einem einzigen Element in der Menüleiste zu erstellen, legen Sie die Eigenschaft Popup auf False fest.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Anforderungen**  
  
 Win32  
  
## Siehe auch  
 [Menu Editor](../mfc/menu-editor.md)