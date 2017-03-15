---
title: "Sizing Individual Controls | Microsoft Docs"
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
  - "Size to Content command"
  - "size, controls"
  - "text, autosizing controls to fit text"
  - "controls [C++], sizing"
ms.assetid: 14ccba02-7171-463a-a121-7018cf1e2e5a
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Sizing Individual Controls
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mithilfe der Ziehpunkte können Sie die Größe eines Steuerelements ändern.  Wenn der Mauszeiger auf einem Ziehpunkt positioniert ist, ändert er seine Form und zeigt die Richtungen an, in die die Steuerelementgröße geändert werden kann.  Aktive Ziehpunkte sind gefüllt. Bei leeren Ziehpunkten kann die Größe des Steuerelements nicht entlang dieser Achse geändert werden.  
  
 Sie können außerdem die Größe eines Steuerelements ändern, indem Sie das Steuerelement entweder an Führungslinien oder Rändern ausrichten oder ein an einer Führungslinie ausgerichtetes Steuerelement verschieben.  
  
### So legen Sie die Größe eines Steuerelements fest  
  
1.  Markieren Sie das Steuerelement.  
  
2.  Ziehen Sie die Ziehpunkte, um die Größe des Steuerelements zu ändern:  
  
    -   Mit Ziehpunkten an der Oberseite und den Seiten wird die horizontale oder vertikale Größe geändert.  
  
    -   Mit Ziehpunkten an den Ecken wird sowohl die horizontale als auch die vertikale Größe geändert.  
  
    > [!TIP]
    >  Sie können die Größe des Steuerelements jeweils um eine Dialogeinheit \(DLU, Dialog Unit\) ändern, indem Sie die UMSCHALTTASTE gedrückt halten und die NACH\-RECHTS\- und NACH\-UNTEN\-TASTEN verwenden.  
  
### So passen Sie die Größe eines Steuerelements automatisch an den darin enthaltenen Text an  
  
1.  Wählen Sie im Menü **Format** die Option **Größe an den Inhalt anpassen**.  
  
 \- oder \-  
  
-   Klicken Sie mit der rechten Maustaste auf das Steuerelement, und wählen Sie im Kontextmenü die Option **Größe an den Inhalt anpassen**.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Anforderungen  
  
 Win32  
  
## Siehe auch  
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)   
 [Steuerelemente](../mfc/controls-mfc.md)