---
title: "Specifying the Location and Size of a Dialog Box"
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
  - "dialog boxes, size"
  - "dialog boxes, positioning"
ms.assetid: 2b7c495e-6595-4cfb-9664-80b2826d0851
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Specifying the Location and Size of a Dialog Box
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Position und Größe eines Dialogfelds sowie der darin enthaltenen Steuerelemente werden in Dialogeinheiten \(DLUs\) gemessen.  Die Werte für einzelne Steuerelemente und für das Dialogfeld werden unten rechts in der Visual Studio\-Statusleiste angezeigt, sobald Sie eines der Elemente markieren.  
  
 Das [Eigenschaftenfenster](../Topic/Properties%20Window.md) enthält drei Eigenschaften, über die Sie festlegen können, an welcher Stelle ein Dialogfeld auf dem Bildschirm angezeigt wird.  Die Eigenschaft **Zentriert** ist vom Typ `Boolean`. Wenn Sie diese Eigenschaft auf **True** festlegen, wird das Dialogfeld immer in der Bildschirmmitte angezeigt.  Wenn Sie die Eigenschaft auf **False** festlegen, können Sie die **XPos**\-Eigenschaft und die **YPos**\-Eigenschaft festlegen, um explizit anzugeben, an welcher Stelle das Dialogfeld auf dem Bildschirm angezeigt werden soll.  Die Positionseigenschaften sind Offsetwerte, deren Ursprung in der oberen linken Ecke des als {X\=0, Y\=0} definierten Anzeigebereichs liegt.  Zusätzlich basiert die Position auf der Eigenschaft **Absolute Ausrichtung**: Falls **True**, verhalten sich die Koordinaten relativ zum Bildschirm; falls **False**, verhalten sie sich relativ zum Fenster des Dialogfeldbesitzers.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Anforderungen  
 Win32  
  
## Siehe auch  
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)   
 [Steuerelemente](../mfc/controls-mfc.md)