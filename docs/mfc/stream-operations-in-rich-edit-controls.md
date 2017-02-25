---
title: "Streamoperationen in RichEdit-Steuerelementen | Microsoft Docs"
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
  - "CRichEditCtrl-Klasse, Streamoperationen"
  - "CRichEditCtrl-Klasse, Streamspeicher"
  - "Rich-Edit-Steuerelemente, Streamoperationen"
  - "Speicher, Stream in CRichEditCtrl"
  - "Streamvorgänge in CRichEditCtrl"
  - "Streamspeicher und CRichEditCtrl"
ms.assetid: 110b4684-1e76-4ca6-9ef0-5bc8b2d93c78
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Streamoperationen in RichEdit-Steuerelementen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können Streams für Datenübertragung in oder aus einem Rich\-Edit\-Steuerelement \([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)\) verwenden.  Ein Stream wird durch eine [EDITSTREAM](http://msdn.microsoft.com/library/windows/desktop/bb787891)\-Struktur definiert, die einen Puffer und eine anwendungsdefinierte Rückruffunktion angibt.  
  
 Um Daten in ein Rich\-Edit\-Steuerelement zu lesen \(Objekts bedeutet, dass Sie die Daten in\), verwenden Sie die [StreamIn](../Topic/CRichEditCtrl::StreamIn.md)\-Memberfunktion.  Das Steuerelement ruft wiederholt die anwendungsdefinierte Rückruffunktion auf, die einen Teil der Daten in den Puffer jedes Mal überträgt.  
  
 Um Inhalte eines Rich\-Edit\-Steuerelements zu speichern \(Objekts bedeutet, dass Sie die Daten aus\), können Sie die Memberfunktion [StreamOut](../Topic/CRichEditCtrl::StreamOut.md) verwenden.  Das Steuerelement schreibt wiederholt des Puffers und ruft dann die anwendungsdefinierte Rückruffunktion auf.  Für jeden Aufruf speichert die Rückruffunktion den Inhalt des Puffers.  
  
## Siehe auch  
 [Verwenden von CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)