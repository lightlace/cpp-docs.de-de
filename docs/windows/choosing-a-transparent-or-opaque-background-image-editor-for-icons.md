---
title: "Choosing a Transparent or Opaque Background (Image Editor for Icons) | Microsoft Docs"
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
  - "opaque backgrounds"
  - "background colors, images"
  - "colors [C++], image"
  - "Image editor [C++], transparent or opague backgrounds"
  - "background images"
  - "images [C++], transparency"
  - "images [C++], opaque background"
  - "transparent backgrounds"
  - "transparency, background"
  - "transparent backgrounds, images"
ms.assetid: 61b743d9-c86b-405d-9a81-0806431b4363
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Choosing a Transparent or Opaque Background (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie eine Markierung aus einem Bild verschieben oder kopieren, sind die Pixel in der Markierung, die mit der aktuellen Hintergrundfarbe übereinstimmen, standardmäßig transparent; sie verdecken also keine Pixel an der Zielposition.  
  
 Sie können von einem transparenten Hintergrund \(Standard\) zu einem deckenden Hintergrund wechseln und umgekehrt.  Wenn Sie ein Markierungstool verwenden, werden die Optionen **Transparenter Hintergrund** und **Nicht transparenter Hintergrund** auf der Symbolleiste des Grafik\-Editors in der Optionsauswahl angezeigt \(siehe unten\).  
  
 ![Hintergrundoptionen – "Deckend" oder "Transparent"](../windows/media/vcimageeditoropaqtranspback.png "vcImageEditorOpaqTranspBack")  
Optionen für transparentes und deckendes Zeichnen auf der Symbolleiste des Grafik\-Editors  
  
### So wechseln Sie zwischen einem transparenten und einem nicht transparenten Hintergrund  
  
1.  Klicken Sie auf der Symbolleiste des **Grafik\-Editors** auf die **Optionsauswahl** und dann auf den entsprechenden Hintergrund:  
  
    -   **Nicht transparenter Hintergrund \(O\)**: Das vorhandene Bild wird von allen Bereichen der Markierung verdeckt.  
  
    -   **Transparenter Hintergrund \(T\)**: Das vorhandene Bild scheint durch die Bereiche der Markierung durch, die mit der aktuellen Hintergrundfarbe übereinstimmen.  
  
 \- oder \-  
  
-   Aktivieren oder deaktivieren Sie im Menü **Bild** die Option **Nicht transparent zeichnen**.  
  
 Sie können die Hintergrundfarbe ändern, während eine Markierung bereits aktiv ist, um neu festzulegen, welche Teile des Bildes transparent sind.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Anforderungen  
  
 None  
  
## Siehe auch  
 [Accelerator Keys](../mfc/accelerator-keys-image-editor-for-icons.md)   
 [Working with Color](../mfc/working-with-color-image-editor-for-icons.md)