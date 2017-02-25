---
title: "CMFCColorButton Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCColorButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCColorButton class"
  - "CMFCColorButton::m_bAltColorDlg data member"
  - "CMFCColorButton::m_bAutoSetFocus data member"
  - "CMFCColorButton::m_Color data member"
  - "CMFCColorButton::m_ColorAutomatic data member"
  - "CMFCColorButton::m_lstDocColors data member"
  - "CMFCColorButton::m_nColumns data member"
  - "CMFCColorButton::m_pPalette data member"
  - "CMFCColorButton::m_pPopup data member"
  - "CMFCColorButton::m_strAutoColorText data member"
  - "CMFCColorButton::m_strDocColorsText data member"
  - "CMFCColorButton::m_strOtherText data member"
ms.assetid: 9fdf34ae-4cc5-4c5e-9d89-1c50e8a73699
caps.latest.revision: 34
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 36
---
# CMFCColorButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCColorButton` und die [CMFCColorBar Class](../../mfc/reference/cmfccolorbar-class.md)\-Klassen werden zusammen verwendet, um ein Farben\-Auswahlsteuerelement zu implementieren.  
  
## Syntax  
  
```  
class CMFCColorButton : public CMFCButton  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCColorButton::CMFCColorButton](../Topic/CMFCColorButton::CMFCColorButton.md)|Erstellt ein neues `CMFCColorButton`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCColorButton::EnableAutomaticButton](../Topic/CMFCColorButton::EnableAutomaticButton.md)|Aktiviert und deaktiviert eine "auto" Schaltfläche, die über den regulären Farbenschaltflächen positioniert wird.  \(Die automatische Schaltfläche des Standardsystems wird **Automatisch** bezeichnet\).|  
|[CMFCColorButton::EnableOtherButton](../Topic/CMFCColorButton::EnableOtherButton.md)|Aktiviert und deaktiviert eine "eine andere" Schaltfläche, die den regulären Farbenschaltflächen positioniert wird.  \(Das Standardsystem "andere" Schaltfläche wird **Weitere Farben...** bezeichnet\).|  
|[CMFCColorButton::GetAutomaticColor](../Topic/CMFCColorButton::GetAutomaticColor.md)|Ruft die aktuelle automatische Farbe ab.|  
|[CMFCColorButton::GetColor](../Topic/CMFCColorButton::GetColor.md)|Ruft die Farbe einer Schaltfläche ab.|  
|[CMFCColorButton::SetColor](../Topic/CMFCColorButton::SetColor.md)|Legt die Farbe einer Schaltfläche fest.|  
|[CMFCColorButton::SetColorName](../Topic/CMFCColorButton::SetColorName.md)|Legt einen Farbnamen fest.|  
|[CMFCColorButton::SetColumnsNumber](../Topic/CMFCColorButton::SetColumnsNumber.md)|Legt die Anzahl der Spalten im Farben\-Auswahldialogfeld fest.|  
|[CMFCColorButton::SetDocumentColors](../Topic/CMFCColorButton::SetDocumentColors.md)|Gibt eine Liste von Dokumentbesondere Farben, die auf dem Farben\-Auswahldialogfeld angezeigt werden.|  
|[CMFCColorButton::SetPalette](../Topic/CMFCColorButton::SetPalette.md)|Gibt eine Palette von Standardanzeigenfarben an.|  
|[CMFCColorButton::SizeToContent](../Topic/CMFCColorButton::SizeToContent.md)|Ändert die Größe des Button\-Steuerelements, je nach Text und Imagegröße.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCColorButton::IsDrawXPTheme](../Topic/CMFCColorButton::IsDrawXPTheme.md)|Gibt an, ob die aktuelle Farbenschaltfläche im Stil von Windows XP angezeigt wird.|  
|[CMFCColorButton::OnDraw](../Topic/CMFCColorButton::OnDraw.md)|Aufgerufen vom Framework, um ein Bild der Schaltfläche anzuzeigen.|  
|[CMFCColorButton::OnDrawBorder](../Topic/CMFCColorButton::OnDrawBorder.md)|Aufgerufen vom Framework, um den Rahmen der Schaltfläche anzuzeigen.|  
|[CMFCColorButton::OnDrawFocusRect](../Topic/CMFCColorButton::OnDrawFocusRect.md)|Aufgerufen vom Framework, um ein Fokusrechteck anzuzeigen, wenn die Schaltfläche ein den Fokus besitzt.|  
|[CMFCColorButton::OnShowColorPopup](../Topic/CMFCColorButton::OnShowColorPopup.md)|Aufgerufen vom Framework, wenn das Farben\-Auswahldialogfeld im Begriff ist angezeigt werden.|  
|[CMFCColorButton::RebuildPalette](../Topic/CMFCColorButton::RebuildPalette.md)|Initialisiert den `m_pPalette` geschützten Datenmember der angegebenen Palette oder auf die Systempalette.|  
|[CMFCColorButton::UpdateColor](../Topic/CMFCColorButton::UpdateColor.md)|Aufgerufen vom Framework, wenn der Benutzer eine Farbe aus der Palette des Farben\-Auswahldialogfelds auswählt.|  
  
### Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|`m_bAltColorDlg`|Ein boolescher Wert.  Wenn `TRUE`, das Framework [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) Dialogfeld anzeigt, wenn *andere* auf die Schaltfläche geklickt wird, oder wenn `FALSE`, das Systemfarbendialogfeld.  Der Standardwert ist `TRUE`.  Weitere Informationen finden Sie unter [CMFCColorButton::EnableOtherButton](../Topic/CMFCColorButton::EnableOtherButton.md).|  
|`m_bAutoSetFocus`|Ein boolescher Wert.  Wenn `TRUE`, das Framework den Fokus auf das Farbenmenü festlegt, wenn das Menü angezeigt wird, oder wenn `FALSE`, ändert nicht den Fokus.  Der Standardwert ist `TRUE`.|  
|[CMFCColorButton::m\_bEnabledInCustomizeMode](../Topic/CMFCColorButton::m_bEnabledInCustomizeMode.md)|Gibt an, ob Anpassungsmodus für die Farbenschaltfläche aktiviert ist.|  
|`m_Color`|Ein [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)\-Wert.  Enthält die aktuell ausgewählte Farbe.|  
|`m_ColorAutomatic`|Ein [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)\-Wert.  Enthält die aktuell ausgewählte Standardfarbe.|  
|`m_Colors`|[CArray](../../mfc/reference/carray-class.md) von [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)\-Werten.  Enthält die zur Zeit verfügbaren Farben.|  
|`m_lstDocColors`|[CList](../../mfc/reference/clist-class.md) von [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)\-Werten.  Enthält die Farben des aktuellen Dokuments.|  
|`m_nColumns`|Eine ganze Zahl.  Enthält die Anzahl der Spalten, um im Raster von Farben in einem Farben\-Auswahlmenü anzuzeigen.|  
|`m_pPalette`|Ein Zeiger auf [CPalette](../../mfc/reference/cpalette-class.md).  Enthält die Farben, die im aktuellen Farben\-Auswahlmenü verfügbar sind.|  
|`m_pPopup`|Ein Zeiger auf ein Objekt [CMFCColorPopupMenu Class](../../mfc/reference/cmfccolorpopupmenu-class.md).  Das Farben\-Auswahlmenü, das angezeigt wird, wenn Sie auf die Farbenschaltfläche klicken.|  
|`m_strAutoColorText`|Eine Zeichenfolge.  Die Bezeichnung "der automatischen" Schaltfläche in einem Farben\-Auswahlmenü.|  
|`m_strDocColorsText`|Eine Zeichenfolge.  Die Bezeichnung der Schaltfläche in einem Farben\-Auswahlmenü, das das Dokument anzeigt, Farbe.|  
|`m_strOtherText`|Eine Zeichenfolge.  Die Bezeichnung "von der anderen" Schaltfläche in einem Farben\-Auswahlmenü.|  
  
## Hinweise  
 Standardmäßig verhält sich die `CMFCColorButton`\-Klasse als Schaltfläche, die ein Farben\-Auswahldialogfeld öffnet.  Das Farben\-Auswahldialogfeld enthält ein Array von kleinen Farbenschaltflächen und von "einer anderen" Schaltfläche, die eine benutzerdefinierte Farbauswahl anzeigt.  \(Das Standardsystem "andere" Schaltfläche wird **Weitere Farben...** bezeichnet\). Wenn ein Benutzer eine neue Farbe auswählen, gibt das `CMFCColorButton`\-Objekt die Änderung und zeigt die ausgewählte Farbe an.  
  
 Erstellen Sie ein Farbenschaltflächen\-steuerelement entweder direkt im Code oder das Tool **ClassWizard** und eine Dialogfeldvorlage verwenden.  Wenn Sie ein Farbenschaltflächen\-steuerelement direkt erstellen, fügen Sie eine `CMFCColorButton`\-Variable der Anwendung hinzu, und rufen Sie dann den Konstruktor auf und `Create`\-Methoden `CMFCColorButton` ein Objekt.  Wenn Sie **ClassWizard** verwenden, fügen Sie eine `CButton`\-Variable der Anwendung hinzu, und ändern Sie dann den Typ der Variablen von `CButton` zu `CMFCColorButton`.  
  
 Das Farben\-Auswahldialogfeld \([CMFCColorBar Class](../../mfc/reference/cmfccolorbar-class.md)\) wird durch die [CMFCColorButton::OnShowColorPopup](../Topic/CMFCColorButton::OnShowColorPopup.md)\-Methode angezeigt, wenn das Framework den `OnLButtonDown`\-Ereignishandler aufruft.  Die [CMFCColorButton::OnShowColorPopup](../Topic/CMFCColorButton::OnShowColorPopup.md)\-Methode kann überschrieben werden, um benutzerdefinierte Farbauswahl zu unterstützen.  
  
 Das Objekt `CMFCColorButton` benachrichtigt das übergeordnete Element, dass eine Farbe ändert, indem es eine `WM_COMMAND | BN_CLICKED` Benachrichtigung sendet.  Das übergeordnete Element verwendet die [CMFCColorButton::GetColor](../Topic/CMFCColorButton::GetColor.md)\-Methode, um die aktuelle Farbe abzurufen.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie eine Farbenschaltfläche konfiguriert, indem verschiedene Methoden in der `CMFCColorButton`\-Klasse angewendet wird.  Die Methoden legen die Farbe der Farbenschaltfläche und der Anzahl von Spalten fest und aktivieren die automatischen und anderen Schaltflächen.  Dieses Beispiel ist Teil [Statusleisten\-Demobeispiel](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_StatusBarDemo#10](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_StatusBarDemo#10)]  
[!CODE [NVC_MFC_StatusBarDemo#11](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_StatusBarDemo#11)]  
  
## Anforderungen  
 **Header:** afxcolorbutton.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCButton Class](../../mfc/reference/cmfcbutton-class.md)   
 [CMFCColorBar Class](../../mfc/reference/cmfccolorbar-class.md)   
 [CMFCColorButton::OnShowColorPopup](../Topic/CMFCColorButton::OnShowColorPopup.md)   
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)   
 [CPalette Class](../../mfc/reference/cpalette-class.md)   
 [CArray Class](../../mfc/reference/carray-class.md)   
 [CList Class](../../mfc/reference/clist-class.md)   
 [CString](../../atl-mfc-shared/reference/cstringt-class.md)