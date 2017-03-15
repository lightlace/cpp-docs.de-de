---
title: "Selecting Controls | Microsoft Docs"
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
  - "Dialog editor, selecting controls"
  - "dominant controls"
  - "dialog box controls, selecting in editor"
  - "controls [C++], selecting"
  - "size, controls"
  - "controls [C++], dominant"
ms.assetid: 27f05450-4550-4229-9f4c-2c9e06365596
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Selecting Controls
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie ein Steuerelement ausrichten, verschieben, kopieren, löschen oder seine Größe ändern möchten, müssen Sie es markieren und anschließend die gewünschte Operation ausführen.  In den meisten Fällen müssen Sie bei Verwendung der Größenanpassungs\- und Ausrichtungstools auf der [Symbolleiste des Dialog\-Editors](../mfc/showing-or-hiding-the-dialog-editor-toolbar.md) mehrere Steuerelemente markieren.  
  
 Ein markiertes Steuerelement verfügt über einen schattierten Rahmen und gefüllte \(aktivierte\) oder leere \(deaktivierte\) "Ziehpunkte", d. h. kleine Quadrate, die im Markierungsrahmen angezeigt werden.  Wenn mehrere Steuerelemente markiert sind, hat das bestimmende Steuerelement gefüllte Ziehpunkte; alle anderen markierten Steuerelemente haben leere Ziehpunkte.  
  
 Werden mehrere Steuerelemente vergrößert, verkleinert oder ausgerichtet, verwendet der Dialog\-Editor das "bestimmende Steuerelement", um festzulegen, wie die Größe der übrigen Steuerelemente angepasst wird oder wie diese ausgerichtet werden.  Das bestimmende Steuerelement ist standardmäßig das zuerst markierte Steuerelement.  
  
-   [Markieren mehrerer Steuerelemente](../mfc/selecting-multiple-controls.md)  
  
-   [Festlegen des bestimmenden Steuerelements](../mfc/specifying-the-dominant-control.md)  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Anforderungen  
 Win32  
  
## Siehe auch  
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)   
 [Steuerelemente](../mfc/controls-mfc.md)