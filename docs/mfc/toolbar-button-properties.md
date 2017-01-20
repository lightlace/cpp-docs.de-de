---
title: "Toolbar Button Properties"
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
  - "C++"
helpviewer_keywords: 
  - "size, toolbar buttons"
  - "toolbar buttons (in Toolbar editor), setting properties"
  - "Toolbar editor, toolbar button properties"
  - "status bars, active toolbar button text"
  - "command IDs, toolbar buttons"
  - "width, toolbar buttons"
ms.assetid: b2705814-7c5d-4f24-8f77-07559b0cdda2
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Toolbar Button Properties
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Im Folgenden sehen Sie die Eigenschaften einer Symbolleisten\-Schaltfläche:  
  
|Property|Beschreibung|  
|--------------|------------------|  
|**ID**|Definiert die ID der Schaltfläche.  Die Dropdownliste enthält geläufige **ID**\-Namen.|  
|**Breite**|Legt die Breite der Schaltfläche fest.  16 Pixel werden empfohlen.|  
|**Höhe**|Legt die Höhe der Schaltfläche fest.  Beachten Sie, dass die Höhe aller Schaltflächen auf der Symbolleiste geändert wird, sobald Sie die Höhe einer Schaltfläche ändern.  15 Pixel werden empfohlen.|  
|**Eingabeaufforderung**|Definiert die Meldung, die in der Statusleiste angezeigt wird.  Indem Sie \\n und einen Namen hinzufügen, erhält die jeweilige Symbolleisten\-Schaltfläche eine QuickInfo.  Weitere Informationen finden Sie unter [Erstellen einer QuickInfo für eine Symbolleisten\-Schaltfläche](../mfc/creating-a-tool-tip-for-a-toolbar-button.md).|  
  
 Die Einstellungen für **Breite** und **Höhe** wirken sich auf alle Schaltflächen aus.  Eine zum Erstellen einer Symbolleiste verwendete Bitmap hat eine Mindestbreite von 2048 Pixeln.  Wenn Sie die Schaltflächenbreite auf 512 Pixel festlegen, ist maximal Platz für vier Schaltflächen. Legen Sie die Breite mit 513 Pixeln fest, finden lediglich drei Schaltflächen Platz.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Anforderungen  
 MFC oder ATL  
  
## Siehe auch  
 [Changing the Properties of a Toolbar Button](../mfc/changing-the-properties-of-a-toolbar-button.md)   
 [Toolbar Editor](../mfc/toolbar-editor.md)