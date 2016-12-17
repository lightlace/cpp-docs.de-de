---
title: "Grundleisten-Steuerelemente und B&#228;nder"
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
  - "Bänder, in rebar-Steuerelemente"
  - "rebar-Steuerelemente, Arbeiten mit Bereichen in"
ms.assetid: b647e7a5-9ea7-48b1-8e5f-096d104748f0
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Grundleisten-Steuerelemente und B&#228;nder
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Hauptzweck eines Infoleiste\-Steuerelements ist, als Container für untergeordnete Fenster, allgemeine Dialogfeldkontrollen, Menüs, Symbolleisten auftreten, u. a.  Diese Kapselung wird unterstützt durch das Konzept eines Bands "." Jedes Infoleistenband kann jede Kombination einer Ziehpunktleiste, der Bitmaps, der Beschriftung und des untergeordneten Fensters enthalten.  
  
 `CReBarCtrl`\-Klasse verfügt über zahlreiche Memberfunktionen, die Sie verwenden können, um das Abrufen und Bearbeiten, Informationen für ein bestimmtes Infoleistenband:  
  
-   [GetBandCount](../Topic/CReBarCtrl::GetBandCount.md) ruft die Anzahl von im aktuellen Bändern Grundleistensteuerelement ab.  
  
-   [GetBandInfo](../Topic/CReBarCtrl::GetBandInfo.md) initialisiert eine **REBARBANDINFO**\-Struktur mit Informationen aus dem angegebenen Band.  Es gibt eine entsprechende Memberfunktion [SetBandInfo](../Topic/CReBarCtrl::SetBandInfo.md).  
  
-   [GetRect](../Topic/CReBarCtrl::GetRect.md) ruft das umgebende Rechteck eines angegebenen Bands ab.  
  
-   [GetRowCount](../Topic/CReBarCtrl::GetRowCount.md) ruft die Anzahl von Bandzeilen in ein Infoleistensteuerelement ab.  
  
-   [IDToIndex](../Topic/CReBarCtrl::IDToIndex.md) ruft den Index eines gegebenen Bands ab.  
  
-   [GetBandBorders](../Topic/CReBarCtrl::GetBandBorders.md) ruft die Rahmen eines Bands ab.  
  
 Zusätzlich zur Manipulation sind einige Memberfunktionen, vorausgesetzt, mit denen Sie, um bestimmte Infoleistenbänder angezeigt werden.  
  
 [InsertBand](../Topic/CReBarCtrl::InsertBand.md) und [DeleteBand](../Topic/CReBarCtrl::DeleteBand.md) hinzufügen und entfernen Infoleistenbänder.  [MinimizeBand](../Topic/CReBarCtrl::MinimizeBand.md) und [MaximizeBand](../Topic/CReBarCtrl::MaximizeBand.md) beeinflussen die aktuelle Größe eines bestimmten Infoleistenbandes.  [MoveBand](../Topic/CReBarCtrl::MoveBand.md) ändert den Index eines bestimmten Infoleistenbandes.  [ShowBand](../Topic/CReBarCtrl::ShowBand.md) zeigt oder blendet ein Infoleistenband vom Benutzer aus.  
  
 Im folgenden Beispiel wird das Hinzufügen eines Symbolleistenbandes \(`m_wndToolBar`\) zu einem vorhandenen Grundleistensteuerelement \(`m_wndReBar`\).  Das Band wird beschrieben, indem die `rbi`\-Struktur initialisiert und dann die `InsertBand`\-Memberfunktion aufruft:  
  
 [!CODE [NVC_MFCControlLadenDialog#27](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#27)]  
  
## Siehe auch  
 [Verwenden von CReBarCtrl](../mfc/using-crebarctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)