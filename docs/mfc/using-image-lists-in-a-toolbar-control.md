---
title: "Verwenden von Bildlisten in einem Symbolleisten-Steuerelement"
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
  - "CToolBarCtrl-Klasse, Bilderlisten"
  - "Bilderlisten [C++], Symbolleisten-Steuerelemente"
  - "Symbolleisten-Steuerelemente [MFC], Bild"
ms.assetid: ccbe8df4-4ed9-4b54-bb93-9a1dcb3b97eb
caps.latest.revision: 12
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Verwenden von Bildlisten in einem Symbolleisten-Steuerelement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Standardmäßig werden die Bilder, die von der Schaltflächen in einem ToolBar\-Steuerelement verwendet werden, als einzelne Bitmap gespeichert.  Sie können jedoch Schaltflächenbilder in einem Satz Bildlisten auch speichern.  Das Symbolleisten\-Steuerelement\-Objekt kann bis drei verschiedene Bildlisten verwenden:  
  
-   Aktivierte Bildliste Bilder enthält für die Symbolleisten\-Schaltflächen, derzeit aktiviert werden.  
  
-   Deaktivierte Bildliste Bilder enthält für die Symbolleisten\-Schaltflächen, gerade deaktiviert sind.  
  
-   Die markierten Bildliste Bilder enthält für Symbolleistenschaltflächen, die derzeit die hervorgehoben werden.  Diese Bildliste wird nur verwendet, wenn die Symbolleiste das **TBSTYLE\_FLAT** Format verwendet.  
  
 Grafiklisten Diese werden vom ToolBar\-Steuerelement verwendet, wenn Sie sie mit `CToolBarCtrl`\-Objekt zuordnen.  Diese Zuordnung wird vorgenommen, indem Aufrufe von [CToolBarCtrl::SetImageList](../Topic/CToolBarCtrl::SetImageList.md), zu [SetDisabledImageList](../Topic/CToolBarCtrl::SetDisabledImageList.md) und zu [SetHotImageList](../Topic/CToolBarCtrl::SetHotImageList.md).  
  
 Standardmäßig verwendet MFC die `CToolBar`\-Klasse, um MFC\-Anwendungssymbolleisten zu implementieren.  kann jedoch `GetToolBarCtrl`\-Memberfunktion verwendet werden, um das `CToolBarCtrl` eingebettete Objekt abzurufen.  Sie können Aufrufe `CToolBarCtrl`\-Memberfunktionen mit dem zurückgegebenen Objekts ausführen.  
  
 Im folgenden Beispiel wird diese Technik veranschaulicht, indem mit aktivierten \(`m_ToolBarImages`\) und `m_ToolBarDisabledImages`\(deaktivierte\) Bildliste zu einem `CToolBarCtrl`\-Objekt \(`m_ToolBarCtrl`\) zugewiesen wird.  
  
 [!CODE [NVC_MFCControlLadenDialog#35](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#35)]  
  
> [!NOTE]
>  Die Bildlisten, die vom Symbolleistenobjekt verwendet werden, müssen permanente Objekte sein.  Aus diesem Grund sind sie häufig Datenmember eine MFC\-Klasse; in diesem Beispiel die Hauptrahmenfensterklasse.  
  
 Sobald die Bildlisten mit `CToolBarCtrl`\-Objekt verknüpft sind, zeigt das Framework automatisch das richtige Schaltflächensymbol an.  
  
## Siehe auch  
 [Verwenden von CToolBarCtrl](../mfc/using-ctoolbarctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)