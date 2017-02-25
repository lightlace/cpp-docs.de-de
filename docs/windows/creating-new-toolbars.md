---
title: "Creating New Toolbars | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.toolbar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "toolbars [C++], creating"
  - "Toolbar editor, creating new toolbars"
  - "Insert Resource"
ms.assetid: 1b28264b-0718-4df8-9f65-979805d2efef
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Creating New Toolbars
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### So erstellen Sie eine neue Symbolleiste  
  
1.  Klicken Sie in der Ressourcenansicht mit der rechten Maustaste auf die RC\-Datei, und wählen Sie dann **Ressource hinzufügen** aus dem Kontextmenü.  \(Wenn in der RC\-Datei bereits eine Symbolleiste vorhanden ist, klicken Sie einfach mit der rechten Maustaste auf den Ordner **Toolbar** und wählen **Toolbar einfügen** aus dem Kontextmenü aus.\)  
  
     **Hinweis** Wenn das Projekt noch keine RC\-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Wählen Sie im Dialogfeld **Ressource hinzufügen** aus der Liste **Ressourcentyp** die Option **Symbolleiste**, und klicken Sie auf **Neu**.  
  
     Wenn neben dem Ressourcentyp **Symbolleiste** ein Pluszeichen \(\+\) angezeigt wird, bedeutet dies, dass Symbolleistenvorlagen verfügbar sind.  Klicken Sie auf das Pluszeichen, um die Vorlagenliste zu erweitern, markieren Sie eine Vorlage, und klicken Sie auf **Neu**.  
  
     \- oder \-  
  
3.  [Konvertieren einer vorhandenen Bitmap in eine Symbolleiste](../mfc/converting-bitmaps-to-toolbars.md).  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Anforderungen  
  
 MFC oder ATL  
  
## Siehe auch  
 [Toolbar Editor](../mfc/toolbar-editor.md)