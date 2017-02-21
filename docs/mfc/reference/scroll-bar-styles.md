---
title: "Stile des Schiebeleisten-Steuerelements | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SBS_VERT"
  - "SBS_SIZEBOXBOTTOMRIGHTALIGN"
  - "SBS_LEFTALIGN"
  - "SBS_RIGHTALIGN"
  - "SBS_TOPALIGN"
  - "SBS_SIZEBOXTOPLEFTALIGN"
  - "SBS_BOTTOMALIGN"
  - "SBS_SIZEBOX"
  - "SBS_HORZ"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SBS_BOTTOMALIGN-Konstante"
  - "SBS_HORZ-Konstante"
  - "SBS_LEFTALIGN-Konstante"
  - "SBS_RIGHTALIGN-Konstante"
  - "SBS_SIZEBOX-Konstante"
  - "SBS_SIZEBOXBOTTOMRIGHTALIGN-Konstante"
  - "SBS_SIZEBOXTOPLEFTALIGN-Konstante"
  - "SBS_TOPALIGN-Konstante"
  - "SBS_VERT-Konstante"
  - "Bildlaufleisten, Stile"
ms.assetid: 8bcde35b-387d-49ae-bdd6-7cda9f5dae26
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# Stile des Schiebeleisten-Steuerelements
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

-   **SBS\_BOTTOMALIGN** mit dem **SBS\_HORZ** verwendete Format.  Der untere Rand der Bildlaufleiste wird am unteren Rand des Rechtecks ausgerichtet, das in der **Erstellen**\-Memberfunktion angegeben wird.  Die Bildlaufleiste vorhanden die Standardhöhe für Systembildlaufleisten.  
  
-   **SBS\_HORZ** legt eine horizontale Bildlaufleiste fest.  Wenn weder das **SBS\_BOTTOMALIGN** noch **SBS\_TOPALIGN** Format angegeben ist, verfügt die Bildlaufleiste die Höhe, Breite und Position, die in der **Erstellen**\-Memberfunktion angegeben wird.  
  
-   **SBS\_LEFTALIGN** mit dem **SBS\_VERT** verwendete Format.  Der linke Rand der Bildlaufleiste ist dem linken Rand des Rechtecks ausgerichtet, das in der **Erstellen**\-Memberfunktion angegeben wird.  Die Bildlaufleiste vorhanden die Standardbreite für Systembildlaufleisten.  
  
-   **SBS\_RIGHTALIGN** mit dem **SBS\_VERT** verwendete Format.  Der rechte Rand der Bildlaufleiste ist dem rechten Rand des Rechtecks ausgerichtet, das in der **Erstellen**\-Memberfunktion angegeben wird.  Die Bildlaufleiste vorhanden die Standardbreite für Systembildlaufleisten.  
  
-   **SBS\_SIZEBOX** legt ein Größenfeld fest.  Wenn weder das **SBS\_SIZEBOXBOTTOMRIGHTALIGN** noch **SBS\_SIZEBOXTOPLEFTALIGN** Format angegeben ist, verfügt das Größenfeld die Höhe, Breite und Position, die in der **Erstellen**\-Memberfunktion angegeben wird.  
  
-   **SBS\_SIZEBOXBOTTOMRIGHTALIGN** mit dem **SBS\_SIZEBOX** verwendete Format.  Die rechte untere Ecke des Größenfelds wird mit der rechten unteren Ecke des Rechtecks ausgerichtet, das in der **Erstellen**\-Memberfunktion angegeben wird.  Das Größenfeld hat die Standardgröße für Systemgrößenfelder.  
  
-   **SBS\_SIZEBOXTOPLEFTALIGN** mit dem **SBS\_SIZEBOX** verwendete Format.  Die linke obere Ecke des Größenfelds wird mit der oberen linken Ecke des Rechtecks ausgerichtet, das in der **Erstellen**\-Memberfunktion angegeben wird.  Das Größenfeld hat die Standardgröße für Systemgrößenfelder.  
  
-   **SBS\_SIZEGRIP** entspricht der **SBS\_SIZEBOX** ausgelösten, aber mit einem Rand.  
  
-   **SBS\_TOPALIGN** mit dem **SBS\_HORZ** verwendete Format.  Der obere Rand der Bildlaufleiste wird mit dem oberen Rand des Rechtecks ausgerichtet, das in der **Erstellen**\-Memberfunktion angegeben wird.  Die Bildlaufleiste vorhanden die Standardhöhe für Systembildlaufleisten.  
  
-   **SBS\_VERT** legt eine vertikale Bildlaufleiste fest.  Wenn weder das **SBS\_RIGHTALIGN** noch **SBS\_LEFTALIGN** Format angegeben ist, verfügt die Bildlaufleiste die Höhe, Breite und Position, die in der **Erstellen**\-Memberfunktion angegeben wird.  
  
## Siehe auch  
 [Von MFC verwendete Stile](../../mfc/reference/styles-used-by-mfc.md)   
 [CScrollBar::Create](../Topic/CScrollBar::Create.md)   
 [Scroll Bar Control Styles](http://msdn.microsoft.com/library/windows/desktop/bb787533)