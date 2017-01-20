---
title: "CMFCColorPickerCtrl Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CMFCColorPickerCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCColorPickerCtrl class"
ms.assetid: b9bbd03c-beb0-4b55-9765-9985fd05e5dc
caps.latest.revision: 33
caps.handback.revision: "21"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCColorPickerCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Klasse stellt `CMFCColorPickerCtrl`\-Funktionalität für ein Steuerelement, das verwendet wird, um Farben auszuwählen.  
  
## Syntax  
  
```  
class CMFCColorPickerCtrl : public CButton  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCColorPickerCtrl::CMFCColorPickerCtrl](../Topic/CMFCColorPickerCtrl::CMFCColorPickerCtrl.md)|Erstellt ein `CMFCColorPickerCtrl`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCColorPickerCtrl::GetColor](../Topic/CMFCColorPickerCtrl::GetColor.md)|Ruft die Farbe ab, die der Benutzer auswählt.|  
|[CMFCColorPickerCtrl::GetHLS](../Topic/CMFCColorPickerCtrl::GetHLS.md)|Ruft die Farbton\-, Leuchtdichte\- und Sättigungswerte der Farbe ab, die der Benutzer auswählt.|  
|[CMFCColorPickerCtrl::GetHue](../Topic/CMFCColorPickerCtrl::GetHue.md)|Ruft die Farbtonkomponente der Farbe ab, die der Benutzer auswählt.|  
|[CMFCColorPickerCtrl::GetLuminance](../Topic/CMFCColorPickerCtrl::GetLuminance.md)|Ruft die Leuchtdichtekomponente der Farbe ab, die der Benutzer auswählt.|  
|[CMFCColorPickerCtrl::GetSaturation](../Topic/CMFCColorPickerCtrl::GetSaturation.md)|Ruft die Sättigungskomponente der Farbe ab, die der Benutzer auswählt.|  
|[CMFCColorPickerCtrl::SelectCellHexagon](../Topic/CMFCColorPickerCtrl::SelectCellHexagon.md)|Legt die aktuelle Farbe zur Farbe fest, die von der angegebenen RGB\-Farbanteile oder das angegebene Zellenhexagon definiert ist.|  
|[CMFCColorPickerCtrl::SetColor](../Topic/CMFCColorPickerCtrl::SetColor.md)|Legt die aktuelle Farbe am angegebenen RGB\-Farbwert fest.|  
|[CMFCColorPickerCtrl::SetHLS](../Topic/CMFCColorPickerCtrl::SetHLS.md)|Legt die aktuelle Farbe am angegebenen HLS\-Farbwert fest.|  
|[CMFCColorPickerCtrl::SetHue](../Topic/CMFCColorPickerCtrl::SetHue.md)|Ändert die Farbtonkomponente der ausgewählten Farbe.|  
|[CMFCColorPickerCtrl::SetLuminance](../Topic/CMFCColorPickerCtrl::SetLuminance.md)|Ändert die Leuchtdichtekomponente der ausgewählten Farbe.|  
|[CMFCColorPickerCtrl::SetLuminanceBarWidth](../Topic/CMFCColorPickerCtrl::SetLuminanceBarWidth.md)|Gibt die Breite der Leuchtdichteleiste im Farben\-Auswahlsteuerelement fest.|  
|[CMFCColorPickerCtrl::SetOriginalColor](../Topic/CMFCColorPickerCtrl::SetOriginalColor.md)|Legt die ursprüngliche ausgewählte Farbe fest.|  
|[CMFCColorPickerCtrl::SetPalette](../Topic/CMFCColorPickerCtrl::SetPalette.md)|Legt die aktuelle Farbpalette fest.|  
|[CMFCColorPickerCtrl::SetSaturation](../Topic/CMFCColorPickerCtrl::SetSaturation.md)|Ändert die Sättigungskomponente der ausgewählten Farbe.|  
|[CMFCColorPickerCtrl::SetType](../Topic/CMFCColorPickerCtrl::SetType.md)|Legt den Typ des Farben\-Auswahlsteuerelements fest, um anzuzeigen.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCColorPickerCtrl::DrawCursor](../Topic/CMFCColorPickerCtrl::DrawCursor.md)|Aufgerufen vom Framework vor einem Cursor, der die ausgewählte Farbe zeigt, wird angezeigt.|  
  
## Hinweise  
 Standardfarben werden von einer sechseckigen Farbpalette ausgewählt, und benutzerdefinierte Farben werden von einer Leuchtdichteleiste ausgewählt, in der Farben entweder mit roten\/von Grün\/der blauen Notation oder der Farbton\-\/satuarations\-\/Leuchtdichtenotation angegeben werden.  
  
 Die folgende Abbildung stellt einige `CMFCColorPickerCtrl`\-Objekte dar.  
  
 ![CMFCColorPickerCtrl&#45;Dialogfeld](../../mfc/reference/media/colorpicker.png "ColorPicker")  
  
 `CMFCColorPickerCtrl` unterstützt zwei Paare Stile.  Die HEXADEZIMAL\- und HEX\_GREYSCALE\-Formate sind für Standardfarben\-Auswahl geeignet.  Die AUSWAHL\- und LEUCHTDICHTEformate sind für benutzerdefinierte Farbauswahl geeignet.  
  
 Führen Sie die folgenden Schritte aus, um das `CMFCColorPickerCtrl`\-Steuerelement in ein Dialogfeld zu enthalten:  
  
1.  Wenn Sie **ClassWizard** verwenden, fügen Sie ein neues Schaltflächensteuerelement in die Dialogfeldvorlage ein \(da die `CMFCColorPickerCtrl`\-Klasse von der Klasse geerbt wird `CButton` \).  
  
2.  Fügen Sie eine Membervariable ein, die mit dem neuen Schaltflächensteuerelement in die Dialogfeldklasse zugeordnet ist.  Ändern Sie dann den Variablentyp von `CButton` zu `CMFCColorPickerCtrl`.  
  
3.  Fügen Sie den `WM_INITDIALOG` Meldungshandler für die Dialogfeldklasse ein.  Legen Sie im Handler den Typ, die Palette und die ursprüngliche ausgewählte Farbe `CMFCColorPickerCtrl` des Steuerelements fest.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie ein Objekt `CMFCColorPickerCtrl` konfiguriert, indem verschiedene Methoden in der `CMFCColorPickerCtrl`\-Klasse angewendet wird.  Das Beispiel zeigt, wie der Typ des Auswahlsteuerelements festgelegt wird und wie Farbe, Farbton, Leuchtdichte und Sättigung festgelegt wird.  Das Beispiel ist Teil [Neue Kontrollprobe](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_NewControls#4](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#4)]  
[!CODE [NVC_MFC_NewControls#5](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#5)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCColorPickerCtrl](../../mfc/reference/cmfccolorpickerctrl-class.md)  
  
## Anforderungen  
 **Header:** afxcolorpickerctrl.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCColorDialog Class](../../mfc/reference/cmfccolordialog-class.md)