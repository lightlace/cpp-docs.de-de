---
title: "CMFCColorDialog Class"
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
  - "CMFCColorDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCColorDialog class"
  - "CMFCColorDialog::m_bIsMyPalette data member"
  - "CMFCColorDialog::m_bPickerMode data member"
  - "CMFCColorDialog::m_btnColorSelect data member"
  - "CMFCColorDialog::m_CurrentColor data member"
  - "CMFCColorDialog::m_hcurPicker data member"
  - "CMFCColorDialog::m_NewColor data member"
  - "CMFCColorDialog::m_pColourSheetOne data member"
  - "CMFCColorDialog::m_pColourSheetTwo data member"
  - "CMFCColorDialog::m_pPalette data member"
  - "CMFCColorDialog::m_pPropSheet data member"
  - "CMFCColorDialog::m_wndColors data member"
  - "CMFCColorDialog::m_wndStaticPlaceHolder data member"
  - "CMFCColorDialog::PreTranslateMessage method"
ms.assetid: 235bbbbc-a3b1-46e0-801b-fb55093ec579
caps.latest.revision: 30
caps.handback.revision: "18"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCColorDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Klasse stellt ein `CMFCColorDialog` Farben\-Auswahldialogfeld dar.  
  
## Syntax  
  
```  
class CMFCColorDialog : public CDialogEx  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCColorDialog::CMFCColorDialog](../Topic/CMFCColorDialog::CMFCColorDialog.md)|Erstellt ein `CMFCColorDialog`\-Objekt.|  
|`CMFCColorDialog::~CMFCColorDialog`|Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCColorDialog::GetColor](../Topic/CMFCColorDialog::GetColor.md)|Gibt die momentan ausgewählte Farbe zurück.|  
|[CMFCColorDialog::GetPalette](../Topic/CMFCColorDialog::GetPalette.md)|Gibt die Palette der Farbe zurück.|  
|`CMFCColorDialog::PreTranslateMessage`|Übersetzt Fenstermeldungen, bevor sie an den [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows\-Funktionen weitergeleitet werden.  So Syntax und weitere Informationen finden Sie unter [CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md).  \(Überschreibungen `CDialogEx::PreTranslateMessage`.\)|  
|[CMFCColorDialog::RebuildPalette](../Topic/CMFCColorDialog::RebuildPalette.md)|Berechnet eine Palette von der Systempalette.|  
|[CMFCColorDialog::SetCurrentColor](../Topic/CMFCColorDialog::SetCurrentColor.md)|Legt die momentan ausgewählte Farbe fest.|  
|[CMFCColorDialog::SetNewColor](../Topic/CMFCColorDialog::SetNewColor.md)|Legt die Farbe die meisten Äquivalent zu einem angegebenen RGB\-Wert fest.|  
|[CMFCColorDialog::SetPageOne](../Topic/CMFCColorDialog::SetPageOne.md)|Wählt einen RGB\-Wert für die erste Eigenschaftenseite aus.|  
|[CMFCColorDialog::SetPageTwo](../Topic/CMFCColorDialog::SetPageTwo.md)|Wählt einen RGB\-Wert für die zweite Eigenschaftenseite aus.|  
  
### Geschützte Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|`m_bIsMyPalette`|`TRUE`, wenn das Farben\-Auswahldialogfeld seine eigene Farbpalette verwendet oder `FALSE`, wenn das Dialogfeld eine Palette verwendet, die im `CMFCColorDialog`\-Konstruktor angegeben wird.|  
|`m_bPickerMode`|`TRUE`, während der Benutzer eine Farbe im Auswahldialogfeld auswählt; andernfalls `FALSE`.|  
|`m_btnColorSelect`|Die Farbenschaltfläche, die der Benutzer ausgewählt hat.|  
|`m_CurrentColor`|Das derzeit ausgewählte Farbe.|  
|`m_hcurPicker`|Der Cursor, der verwendet wird, um eine Farbe auszuwählen.|  
|`m_NewColor`|Die potenzielle ausgewählte Farbe, die die ursprüngliche Farbe dauerhaft ausgewählt werden oder wiederhergestellt werden kann.|  
|`m_pColourSheetOne`|Ein Zeiger auf die erste Seite des Farben\-Auswahleigenschaftenblatts.|  
|`m_pColourSheetTwo`|Ein Zeiger auf die zweite Seite des Farben\-Auswahleigenschaftenblatts.|  
|`m_pPalette`|Die aktuelle Logische Palette.|  
|`m_pPropSheet`|Ein Zeiger auf das Eigenschaftenblatt für das Farben\-Auswahldialogfeld.|  
|`m_wndColors`|Ein Farben\-Auswahlsteuerobjekt.|  
|`m_wndStaticPlaceHolder`|Ein statisches Steuerelement, das ein Platzhalter für das Farben\-Auswahleigenschaftenblatt ist.|  
  
## Hinweise  
 Das Farben\-Auswahldialogfeld wird als Eigenschaftenblatt mit zwei Seiten angezeigt.  Auf der ersten Seite eine Standardfarbe von der Systempalette aus; auf der zweiten Seite eine benutzerdefinierte Farbe aus.  
  
 Sie können ein `CMFCColorDialog`\-Objekt auf dem Stapel erstellen und `DoModal` dann aufrufen und die ursprüngliche Farbe als Parameter an das `CMFCColorDialog`\-Konstruktor.  Das Farben\-Auswahldialogfeld erstellt dann mehrere [CMFCColorPickerCtrl Class](../../mfc/reference/cmfccolorpickerctrl-class.md)\-Objekte, um jede Farbpalette zu behandeln.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog\-Klasse](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
 [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein Dialogfeld konfiguriert, indem verschiedene Methoden in der `CMFCColorDialog`\-Klasse angewendet wird.  Das Beispiel zeigt, wie die aktuellen und neuen Farben des Dialogfelds festgelegt wird und wie das festlegt Rot\-, Grün\- und Blauanteil einer ausgewählten Farbe auf den beiden Eigenschaftenseiten des Farbdialogfelds.  Dieses Beispiel ist Teil [Neue Kontrollprobe](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_NewControls#3](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#3)]  
  
## Anforderungen  
 **Header:** afxcolordialog.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCColorPickerCtrl Class](../../mfc/reference/cmfccolorpickerctrl-class.md)