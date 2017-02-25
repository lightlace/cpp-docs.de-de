---
title: "CMFCRibbonEdit Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCRibbonEdit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonEdit class"
ms.assetid: 9b85f1f2-446b-454e-9af9-104fdad8a897
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# CMFCRibbonEdit Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert ein Bearbeitungssteuerelement, das auf einer Menübandleiste ist.  
  
## Syntax  
  
```  
class CMFCRibbonEdit : public CMFCRibbonButton  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCRibbonEdit::CMFCRibbonEdit](../Topic/CMFCRibbonEdit::CMFCRibbonEdit.md)|Erstellt ein `CMFCRibbonEdit`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCRibbonEdit::CanBeStretched](../Topic/CMFCRibbonEdit::CanBeStretched.md)|Gibt an, ob die Höhe des Steuerelements `CMFCRibbonEdit` auf die Höhe einer Menübandzeile vertikal zunehmen kann.|  
|[CMFCRibbonEdit::CMFCRibbonEdit](../Topic/CMFCRibbonEdit::CMFCRibbonEdit.md)|Erstellt ein `CMFCRibbonEdit`\-Objekt.|  
|[CMFCRibbonEdit::CopyFrom](../Topic/CMFCRibbonEdit::CopyFrom.md)|Kopiert den Zustand des angegebenen `CMFCRibbonEdit`\-Objekts auf den aktuellen `CMFCRibbonEdit`\-Objekt.|  
|[CMFCRibbonEdit::CreateEdit](../Topic/CMFCRibbonEdit::CreateEdit.md)|Stellt ein neues Textfeld zum `CMFCRibbonEdit`\-Objekt.|  
|[CMFCRibbonEdit::DestroyCtrl](../Topic/CMFCRibbonEdit::DestroyCtrl.md)|Zerstört das `CMFCRibbonEdit`\-Objekt.|  
|[CMFCRibbonEdit::DropDownList](../Topic/CMFCRibbonEdit::DropDownList.md)|Ermöglicht das unten ein Listenfeld ab.|  
|[CMFCRibbonEdit::EnableSpinButtons](../Topic/CMFCRibbonEdit::EnableSpinButtons.md)|Aktiviert und legt den Bereich des Drehfelds für das Textfeld fest.|  
|[CMFCRibbonEdit::GetCompactSize](../Topic/CMFCRibbonEdit::GetCompactSize.md)|Ruft die komprimierte Größe des `CFMCRibbonEdit`\-Objekts ab.|  
|[CMFCRibbonEdit::GetEditText](../Topic/CMFCRibbonEdit::GetEditText.md)|Ruft den Text im Textfeld ab.|  
|[CMFCRibbonEdit::GetIntermediateSize](../Topic/CMFCRibbonEdit::GetIntermediateSize.md)|Ruft die temporären Größe des `CMFCRibbonEdit`\-Objekts ab.|  
|[CMFCRibbonEdit::GetTextAlign](../Topic/CMFCRibbonEdit::GetTextAlign.md)|Ruft die Ausrichtung des Texts im Textfeld ab.|  
|[CMFCRibbonEdit::GetWidth](../Topic/CMFCRibbonEdit::GetWidth.md)|Ruft die Breite, in Pixel, `CMFCRibbonEdit` des Steuerelements ab.|  
|[CMFCRibbonEdit::HasCompactMode](../Topic/CMFCRibbonEdit::HasCompactMode.md)|Gibt an, ob die Anzeigengröße für das Steuerelement `CMFCRibbonEdit` kompakt sein kann.|  
|[CMFCRibbonEdit::HasFocus](../Topic/CMFCRibbonEdit::HasFocus.md)|Gibt an, ob das `CMFCRIbbonEdit`\-Steuerelement den Fokus besitzt.|  
|[CMFCRibbonEdit::HasLargeMode](../Topic/CMFCRibbonEdit::HasLargeMode.md)|Gibt an, ob die Anzeigengröße für das Steuerelement `CMFCRibbonEdit` groß sein kann.|  
|[CMFCRibbonEdit::HasSpinButtons](../Topic/CMFCRibbonEdit::HasSpinButtons.md)|Gibt an, ob das Textfeld ein Drehfeld verfügt.|  
|[CMFCRibbonEdit::IsHighlighted](../Topic/CMFCRibbonEdit::IsHighlighted.md)|Gibt an, ob das `CMFCRibbonEdit`\-Steuerelement hervorgehoben wird.|  
|[CMFCRibbonEdit::OnAfterChangeRect](../Topic/CMFCRibbonEdit::OnAfterChangeRect.md)|Aufgerufen vom Framework wenn die Abmessungen des Anzeigenrechtecks für die `CMFCRibbonEdit`\-Steuerelement ändert.|  
|[CMFCRibbonEdit::OnDraw](../Topic/CMFCRibbonEdit::OnDraw.md)|Aufgerufen vom Framework, um das `CMFCRibbonEdit`\-Steuerelement zu zeichnen.|  
|[CMFCRibbonEdit::OnDrawLabelAndImage](../Topic/CMFCRibbonEdit::OnDrawLabelAndImage.md)|Aufgerufen vom Framework, um die Bezeichnung und das Bild für das `CMFCRibbonEdit`\-Steuerelement zu zeichnen.|  
|[CMFCRibbonEdit::OnDrawOnList](../Topic/CMFCRibbonEdit::OnDrawOnList.md)|Aufgerufen vom Framework, um das `CMFCRibbonEdit`\-Steuerelement in einem Befehlslistenfeld zu zeichnen.|  
|[CMFCRibbonEdit::OnEnable](../Topic/CMFCRibbonEdit::OnEnable.md)|Aufgerufen vom Framework, um das `CMFCRibbonEdit`\-Steuerelement zu aktivieren oder zu deaktivieren.|  
|[CMFCRibbonEdit::OnHighlight](../Topic/CMFCRibbonEdit::OnHighlight.md)|Aufgerufen vom Framework, wenn der Mauszeiger die Grenzen des `CMFCRibbonEdit`\-Steuerelements bewegt wird.|  
|[CMFCRibbonEdit::OnKey](../Topic/CMFCRibbonEdit::OnKey.md)|Aufgerufen vom Framework, wenn der Benutzer drückt, hat ein keytip und das `CMFCRibbonEdit`\-Steuerelement den Fokus.|  
|[CMFCRibbonEdit::OnLButtonDown](../Topic/CMFCRibbonEdit::OnLButtonDown.md)|Aufgerufen vom Framework, um das `CMFCRibbonEdit`\-Steuerelement aktualisiert, wenn der Benutzer die linke Maustaste auf das Steuerelement klickt.|  
|[CMFCRibbonEdit::OnLButtonUp](../Topic/CMFCRibbonEdit::OnLButtonUp.md)|Aufgerufen vom Framework, wenn der Benutzer die linke Maustaste los.|  
|[CMFCRibbonEdit::OnRTLChanged](../Topic/CMFCRibbonEdit::OnRTLChanged.md)|Aufgerufen vom Framework, um das `CMFCRibbonEdit`\-Steuerelement zu aktualisieren, wenn das Layout Richtung ändert.|  
|[CMFCRibbonEdit::OnShow](../Topic/CMFCRibbonEdit::OnShow.md)|Aufgerufen vom Framework, um das `CMFCRibbonEdit`\-Steuerelement anzuzeigen oder auszublenden.|  
|[CMFCRibbonEdit::Redraw](../Topic/CMFCRibbonEdit::Redraw.md)|Aktualisiert die Anzeige des Steuerelements `CMFCRibbonEdit`.|  
|[CMFCRibbonEdit::SetACCData](../Topic/CMFCRibbonEdit::SetACCData.md)|Legt die Barrierefreiheitsdaten für das `CMFCRibbonEdit`\-Objekt fest.|  
|[CMFCRibbonEdit::SetEditText](../Topic/CMFCRibbonEdit::SetEditText.md)|Legt den Text im Textfeld fest.|  
|[CMFCRibbonEdit::SetTextAlign](../Topic/CMFCRibbonEdit::SetTextAlign.md)|Legt die Textausrichtung des Textfelds fest.|  
|[CMFCRibbonEdit::SetWidth](../Topic/CMFCRibbonEdit::SetWidth.md)|Gibt die Breite des Textfelds zum `CMFCRibbonEdit`\-Steuerelement fest.|  
  
## Hinweise  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie ein Objekt erstellt wird, `CMFCRibbonEdit` Drehfelder neben dem Bearbeitungssteuerelement an und für den Text des Bearbeitungssteuerelements fest.  Dieser Codeausschnitt ist Teil [MS Office\-Demobeispiel 2007](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_MSOffice2007Demo#7](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_MSOffice2007Demo#7)]  
  
## Anforderungen  
 **Header:** afxRibbonEdit.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton Class](../../mfc/reference/cmfcribbonbutton-class.md)   
 [CMFCRibbonBar Class](../../mfc/reference/cmfcribbonbar-class.md)