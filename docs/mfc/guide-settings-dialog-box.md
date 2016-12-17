---
title: "Dialogfeld &quot;F&#252;hrungslinieneinstellungen&quot;"
ms.custom: na
ms.date: "12/14/2016"
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
  - "DLUs (Dialogeinheiten)"
  - "Dialog-Editor, Ausrichten an Führungslinien"
  - "Rasterweite"
  - "Führungslinien, Einstellungen"
  - "Dialogeinheiten (DLUs)"
  - "Layoutraster im Dialog-Editor"
  - "Ausrichten an Führungslinien (Dialog-Editor)"
  - "Steuerelemente [C++], Ausrichten an Führungslinien/Raster"
  - "Führungslinieneinstellungen (Dialogfeld im Dialog-Editor)"
ms.assetid: 55381e1c-146a-4fa7-b1b3-b1492817615f
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Dialogfeld &quot;F&#252;hrungslinieneinstellungen&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Layoutführungslinien  
 Zeigt die Einstellungen für die Layoutführungslinien an.  
  
 **None**  
  
 Blendet die Layouttools aus.  
  
 **Lineale und Führungslinien**  
  
 Ist diese Option aktiviert, werden den Layouttools Lineale hinzugefügt. Auf den Linealen können Führungslinien platziert werden.  Die Standardführungslinien sind die Ränder, die durch Ziehen verschoben werden können.  Klicken Sie auf die Lineale, um eine Führungslinie einzufügen.  Die Steuerelemente werden automatisch an den Führungslinien ausgerichtet, sobald sie in die Nähe oder über die Führungslinien verschoben werden.  Ist ein Steuerelement mit einer Führungslinie verbunden, wird es mit ihr zusammen verschoben.  Wenn beide Seiten eines Steuerelements an einer Führungslinie ausgerichtet sind, wird durch Verschieben einer Führungslinie die Größe des Steuerelements geändert.  
  
 **Raster**  
  
 Erstellt ein Layoutraster.  Neue Steuerelemente werden automatisch am Raster ausgerichtet.  
  
## Rasterweite  
 Zeigt die Einstellungen für die Rasterweite in Dialogeinheiten \(DLUs\) an.  
  
 **Breite: DLUs**  
  
 Legt die Breite des Layoutrasters in Dialogeinheiten \(DLUs\) fest.  Eine horizontale DLU entspricht der durchschnittlichen Breite der Dialogfeld\-Schriftart geteilt durch Vier.  
  
 **Höhe: DLUs**  
  
 Legt die Höhe des Layoutrasters in Dialogeinheiten \(DLUs\) fest.  Eine vertikale DLU entspricht der durchschnittlichen Höhe der Dialogfeld\-Schriftart geteilt durch Acht.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Anforderungen  
 Win32  
  
## Siehe auch  
 [Modifying the Layout Grid](../mfc/modifying-the-layout-grid.md)   
 [Dialog Editor States \(Guides and Grids\)](../mfc/dialog-editor-states-guides-and-grids.md)