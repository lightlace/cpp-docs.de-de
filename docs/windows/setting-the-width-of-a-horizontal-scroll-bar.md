---
title: "Setting the Width of a Horizontal Scroll Bar"
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
  - "list controls, scroll bar width"
  - "CListBox::SetHorizontalExtent"
  - "controls [C++], scroll bar"
  - "scroll bars, displaying in controls"
  - "horizontal scroll bar width"
  - "CListBox class, scroll bar width"
  - "scroll bars, width"
ms.assetid: 51dad141-aa0b-46a3-a82c-46b80d603d94
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Setting the Width of a Horizontal Scroll Bar
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie einem Dialogfeld unter Verwendung der MFC\-Klassen ein Listenfeld mit einer horizontalen Schiebeleiste hinzufügen, wird die Schiebeleiste nicht automatisch in der Anwendung angezeigt.  
  
### So wird die Schiebeleiste sichtbar  
  
1.  Legen Sie für das breiteste Element eine maximale Breite fest, indem Sie [CListBox::SetHorizontalExtent](../Topic/CListBox::SetHorizontalExtent.md) im Code aufrufen.  
  
     Ohne diesen Wert wird die Schiebeleiste selbst dann nicht angezeigt, wenn die Elemente im Listenfeld breiter als das Feld sind.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Anforderungen  
  
 MFC  
  
## Siehe auch  
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)   
 [Steuerelemente](../mfc/controls-mfc.md)