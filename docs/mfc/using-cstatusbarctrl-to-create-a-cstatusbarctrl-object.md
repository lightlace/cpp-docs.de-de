---
title: "Verwenden von CStatusBarCtrl zum Erstellen eines CStatusBarCtrl-Objekts | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CStatusBarCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStatusBarCtrl-Klasse, Erstellen"
  - "Statusleiste-Steuerelement, Erstellen"
ms.assetid: 365c2b65-12de-49e6-9a2e-416c6ee10d60
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Verwenden von CStatusBarCtrl zum Erstellen eines CStatusBarCtrl-Objekts
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Im Folgenden ein Beispiel für eine typische Verwendung einer [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md):  
  
### So ein StatusBar\-Steuerelement mit Teilen verwenden  
  
1.  Erstellen Sie das `CStatusBarCtrl`\-Objekt.  
  
2.  Rufen Sie [SetMinHeight](../Topic/CStatusBarCtrl::SetMinHeight.md) auf, wenn Sie die Mindesthöhe des Zeichnungsbereichs des Statusleistensteuer festlegen möchten.  
  
3.  Rufen Sie [SetBkColor](../Topic/CStatusBarCtrl::SetBkColor.md) auf, um die Hintergrundfarbe des StatusBar\-Steuerelements festzulegen.  
  
4.  Rufen Sie [SetParts](../Topic/CStatusBarCtrl::SetParts.md) auf, um die Anzahl von Teilen in einem StatusBar\-Steuerelement und die Koordinate des rechten Rands jedes Teils festzulegen.  
  
5.  Rufen Sie [SetText](../Topic/CStatusBarCtrl::SetText.md) auf, um Text in einem angegebenen Teil des StatusBar\-Steuerelements festzulegen.  Die Meldung macht den Teil des Steuerelements, das geändert hat ungültig und führt es, den neuen Text angezeigt, wenn das Steuerelement als Nächstes `WM_PAINT` die Meldung empfängt.  
  
 In einigen Fällen die Anforderungen der Statusleiste, nur eine Textzeile anzuzeigen.  In diesem Fall ändern Sie [SetSimple](../Topic/CStatusBarCtrl::SetSimple.md) einen Aufruf.  Dadurch wird das in StatusBar\-Steuerelement "einfachen" Modus, der eine einzelne Textzeile anzeigt.  
  
## Siehe auch  
 [Verwenden von CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)