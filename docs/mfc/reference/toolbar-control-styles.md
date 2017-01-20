---
title: "Steuerelementtypen f&#252;r die Symbolleiste"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Steuerelementtypen für die Symbolleiste"
ms.assetid: 0f717eb9-fa32-4263-b852-809238863feb
caps.latest.revision: 16
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Steuerelementtypen f&#252;r die Symbolleiste
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[CMFCToolBarButton Class](../../mfc/reference/cmfctoolbarbutton-class.md) enthält einen Satz Formatflags, die die Darstellung und das Verhalten der Schaltfläche bestimmen.  Sie können eine Kombination dieser Flags festlegen, indem Sie [CMFCToolBarButton::SetStyle](../Topic/CMFCToolBarButton::SetStyle.md) aufrufen.  Dieses Thema führt die Formatflagwerte und ihre Bedeutung auf.  
  
## Eigenschaftswerte  
 Die folgenden Werte bestimmt den Typ der Schaltfläche, der das Steuerelement darstellt:  
  
 TBBS\_BUTTON  
 Standardpushbutton \(Standard\).  
  
 TBBS\_CHECKBOX  
 Kontrollkästchen.  
  
 TBBS\_CHECKGROUP  
 Der Beginn einer Gruppe Kontrollkästchen.  
  
 TBBS\_GROUP  
 Der Beginn einer Gruppe Schaltflächen.  
  
 TBBS\_SEPARATOR  
 Trennzeichen.  
  
 Die folgenden Werte stellen den aktuellen Status des Steuerelements dar:  
  
 TBBS\_CHECKED  
 Kontrollkästchen wird überprüft.  
  
 TBBS\_DISABLED  
 Steuerelement ist deaktiviert.  
  
 TBBS\_INDETERMINATE  
 Kontrollkästchen ist in einem unbestimmten Zustand.  
  
 TBBS\_PRESSED  
 Schaltfläche ist aktiviert.  
  
 Die folgenden sich das Layout der Schaltfläche in der Symbolleiste:  
  
 TBBS\_BREAK  
 Setzt das Element auf einer neuen Zeile oder einer neuen Spalte ohne trennende Spalten.  
  
## Hinweise  
 Das aktuelle Format wird in [CMFCToolBarButton::m\_nStyle](../Topic/CMFCToolBarButton::m_nStyle.md) gespeichert.  Legen Sie keinen neuen Wert in `m_nStyle` direkt fest, da auf abgeleitete Klassen zusätzliches ausführen, Verarbeitung, wenn Sie `SetStyles` aufrufen.  
  
 Der visuelle Manager bestimmt die Darstellung der Schaltflächen in jedem Zustand.  Weitere Informationen finden Sie unter [Visualisierungs\-Manager](../../mfc/visualization-manager.md).  
  
## Voraussetzungen  
 **Header:** afxtoolbarbutton.h  
  
## Siehe auch  
 [MFC\-Makros, globale Funktionen und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)   
 [CMFCToolBarButton Class](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [Visualisierungs\-Manager](../../mfc/visualization-manager.md)