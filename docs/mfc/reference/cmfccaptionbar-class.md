---
title: "CMFCCaptionBar-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCCaptionBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCCaptionBar-Klasse"
ms.assetid: acb54d5f-14ff-4c96-aeb3-7717cf566d9a
caps.latest.revision: 28
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 30
---
# CMFCCaptionBar-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein \- Objekt `CMFCCaptionBar` ist eine Steuerleiste, die drei Elemente angezeigt werden: eine Schaltfläche, eine Beschriftung und eine Bitmap.  Es kann ein Element jedes Typs nur gleichzeitig anzeigen.  Sie können jedes Element zum linken oder rechten Rand des Steuerelements oder den Mittelpunkt ausrichten.  Sie können eine Ebene oder ein 3D\-Format an der oberen und der unteren Rändern der Titelleiste auch anwenden.  
  
## Syntax  
  
```  
class CMFCCaptionBar : public CPane  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CMFCCaptionBar::Create](../Topic/CMFCCaptionBar::Create.md)|Erstellt das Beschriftungsleistesteuerelement und fügt es dem `CMFCCaptionBar`\-Objekt.|  
|[CMFCCaptionBar::DoesAllowDynInsertBefore](../Topic/CMFCCaptionBar::DoesAllowDynInsertBefore.md)|Gibt an, ob ein anderer Bereich zwischen die Titelleiste und seine übergeordneten Frames dynamisch eingefügt werden kann.  \(Überschreibungen [CBasePane::DoesAllowDynInsertBefore](../Topic/CBasePane::DoesAllowDynInsertBefore.md).\)|  
|[CMFCCaptionBar::EnableButton](../Topic/CMFCCaptionBar::EnableButton.md)|Aktiviert oder deaktiviert die Schaltfläche in der Titelleiste.|  
|[CMFCCaptionBar::GetAlignment](../Topic/CMFCCaptionBar::GetAlignment.md)|Gibt die Ausrichtung des angegebenen Elements zurück.|  
|[CMFCCaptionBar::GetBorderSize](../Topic/CMFCCaptionBar::GetBorderSize.md)|Gibt die Rahmengröße der Titelleiste zurück.|  
|[CMFCCaptionBar::GetButtonRect](../Topic/CMFCCaptionBar::GetButtonRect.md)|Ruft das umschließende Rechteck der Schaltfläche in der Titelleiste ab.|  
|[CMFCCaptionBar::GetMargin](../Topic/CMFCCaptionBar::GetMargin.md)|Gibt den Abstand zwischen dem Rand der Beschriftungsleisteelemente und dem Rand des Beschriftungsleistesteuerelements zurück.|  
|[CMFCCaptionBar::IsMessageBarMode](../Topic/CMFCCaptionBar::IsMessageBarMode.md)|Gibt an, ob die Titelleiste im Statusleistenmodus ist.|  
|[CMFCCaptionBar::RemoveBitmap](../Topic/CMFCCaptionBar::RemoveBitmap.md)|Entfernt das Bitmapbild von der Titelleiste.|  
|[CMFCCaptionBar::RemoveButton](../Topic/CMFCCaptionBar::RemoveButton.md)|Entfernt die Schaltfläche von der Titelleiste.|  
|[CMFCCaptionBar::RemoveIcon](../Topic/CMFCCaptionBar::RemoveIcon.md)|Entfernt das Symbol aus der Titelleiste.|  
|[CMFCCaptionBar::RemoveText](../Topic/CMFCCaptionBar::RemoveText.md)|Entfernt die Beschriftung von der Titelleiste.|  
|[CMFCCaptionBar::SetBitmap](../Topic/CMFCCaptionBar::SetBitmap.md)|Legt das Bitmapbild für die Titelleiste fest.|  
|[CMFCCaptionBar::SetBorderSize](../Topic/CMFCCaptionBar::SetBorderSize.md)|Legt die Rahmengröße der Titelleiste fest.|  
|[CMFCCaptionBar::SetButton](../Topic/CMFCCaptionBar::SetButton.md)|Legt die Schaltfläche für die Titelleiste fest.|  
|[CMFCCaptionBar::SetButtonPressed](../Topic/CMFCCaptionBar::SetButtonPressed.md)|Gibt an, ob die Schaltflächenaufenthalte drücken.|  
|[CMFCCaptionBar::SetButtonToolTip](../Topic/CMFCCaptionBar::SetButtonToolTip.md)|Legt die QuickInfo für die Schaltfläche fest.|  
|[CMFCCaptionBar::SetFlatBorder](../Topic/CMFCCaptionBar::SetFlatBorder.md)|Legt die Rahmenart der Titelleiste fest.|  
|[CMFCCaptionBar::SetIcon](../Topic/CMFCCaptionBar::SetIcon.md)|Legt das Symbol für eine Titelleiste fest.|  
|[CMFCCaptionBar::SetImageToolTip](../Topic/CMFCCaptionBar::SetImageToolTip.md)|Legt die QuickInfo für das Bild für die Titelleiste fest.|  
|[CMFCCaptionBar::SetMargin](../Topic/CMFCCaptionBar::SetMargin.md)|Legt den Abstand zwischen dem Rand des Beschriftungsleisteelements und dem Rand des Beschriftungsleistesteuerelements fest.|  
|[CMFCCaptionBar::SetText](../Topic/CMFCCaptionBar::SetText.md)|Legt die Beschriftung für die Titelleiste fest.|  
  
### Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CMFCCaptionBar::OnDrawBackground](../Topic/CMFCCaptionBar::OnDrawBackground.md)|Aufgerufen vom Framework, um den Hintergrund der Titelleiste auszufüllen.|  
|[CMFCCaptionBar::OnDrawBorder](../Topic/CMFCCaptionBar::OnDrawBorder.md)|Aufgerufen vom Framework, um den Rahmen der Titelleiste zu zeichnen.|  
|[CMFCCaptionBar::OnDrawButton](../Topic/CMFCCaptionBar::OnDrawButton.md)|Aufgerufen vom Framework, um die Beschriftungsleisteschaltfläche zu zeichnen.|  
|[CMFCCaptionBar::OnDrawImage](../Topic/CMFCCaptionBar::OnDrawImage.md)|Aufgerufen vom Framework, um das Beschriftungsleisteimage zu zeichnen.|  
|[CMFCCaptionBar::OnDrawText](../Topic/CMFCCaptionBar::OnDrawText.md)|Aufgerufen vom Framework, um den Beschriftungsleistetext zu zeichnen.|  
  
### Datenmember  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CMFCCaptionBar::m\_clrBarBackground](../Topic/CMFCCaptionBar::m_clrBarBackground.md)|Die Hintergrundfarbe der Titelleiste.|  
|[CMFCCaptionBar::m\_clrBarBorder](../Topic/CMFCCaptionBar::m_clrBarBorder.md)|Die Farbe des Rahmens der Titelleiste.|  
|[CMFCCaptionBar::m\_clrBarText](../Topic/CMFCCaptionBar::m_clrBarText.md)|Die Farbe des Beschriftungsleistetexts.|  
  
## Hinweise  
 Um eine Titelleiste zu erstellen, führen Sie folgende Schritte aus:  
  
1.  Erstellen Sie das `CMFCCaptionBar`\-Objekt.  In der Regel ist die Titelleiste einer Rahmenfensterklasse hinzufügen.  
  
2.  Rufen Sie die [CMFCCaptionBar::Create](../Topic/CMFCCaptionBar::Create.md)\-Methode auf, um das Beschriftungsleistesteuerelement zu erstellen und auf `CMFCCaptionBar`\-Objekt anzufügen.  
  
3.  Rufen Sie [CMFCCaptionBar::SetButton](../Topic/CMFCCaptionBar::SetButton.md), [CMFCCaptionBar::SetText](../Topic/CMFCCaptionBar::SetText.md), [CMFCCaptionBar::SetIcon](../Topic/CMFCCaptionBar::SetIcon.md) und [CMFCCaptionBar::SetBitmap](../Topic/CMFCCaptionBar::SetBitmap.md) auf, um die Beschriftungsleisteelemente festzulegen.  
  
 Wenn Sie das Schaltflächenelement, Ihnen eine Befehls\-ID zur Schaltfläche zuweisen müssen.  Wenn der Benutzer auf die Schaltfläche klickt, leitet die Titelleiste die `WM_COMMAND` Meldungen angezeigt, die diese ID auf das übergeordnete Rahmenfenster haben.  
  
 Die Titelleiste kann im Statusleistenmodus auch arbeiten, der die Statusleiste emuliert, die in Microsoft Office 2007\-Anwendungen angezeigt wird.  Im Statusleistenmodus zeigt die Titelleiste eine Bitmap, eine Meldung und eine Schaltfläche an \(in der Regel ein Dialogfeld geöffnet\). Sie können eine QuickInfo zur Bitmap zuweisen.  
  
 Um Statusleistenmodus zu aktivieren, rufen Sie [CMFCCaptionBar::Create](../Topic/CMFCCaptionBar::Create.md) auf und legen Sie den vierten Parameter \(bIsMessageBarMode\) zu `TRUE` fest.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie verschiedene Methoden in der Klasse `CMFCCaptionBar` verwendet.  Im Beispiel wird gezeigt, wie das Beschriftungsleistesteuerelement, legen Sie einen 3D\-Rahmen der Titelleiste, legen Sie den Abstand, in Pixel, zwischen dem Rand der Beschriftungsleisteelemente und dem Rand des Beschriftungsleistesteuerelements, legen Sie die Schaltfläche für die Titelleiste, legen Sie die QuickInfo für die Schaltfläche, legen Sie die Beschriftung für die Titelleiste, legen Sie das Bitmapbild für die Titelleiste und legen Sie die QuickInfo für das Bild in der Titelleiste erstellt.  Dieser Codeausschnitt ist Teil [MS Office\-Demobeispiel 2007](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_MSOffice2007Demo#1](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_MSOffice2007Demo#1)]  
[!CODE [NVC_MFC_MSOffice2007Demo#2](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_MSOffice2007Demo#2)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCCaptionBar](../../mfc/reference/cmfccaptionbar-class.md)  
  
## Anforderungen  
 **Header:** afxcaptionbar.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)