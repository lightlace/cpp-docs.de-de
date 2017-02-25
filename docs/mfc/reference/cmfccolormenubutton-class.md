---
title: "CMFCColorMenuButton Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCColorMenuButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCColorMenuButton class"
ms.assetid: 42685704-e994-4f7b-9553-62283c27b754
caps.latest.revision: 29
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 31
---
# CMFCColorMenuButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CMFCColorMenuButton`\-Klasse unterstützt einen Menübefehl oder eine Symbolleisten\-Schaltfläche, die ein Farben\-Auswahldialogfeld startet.  
  
## Syntax  
  
```  
class CMFCColorMenuButton : public CMFCToolBarMenuButton  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCColorMenuButton::CMFCColorMenuButton](../Topic/CMFCColorMenuButton::CMFCColorMenuButton.md)|Erstellt ein `CMFCColorMenuButton`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCColorMenuButton::EnableAutomaticButton](../Topic/CMFCColorMenuButton::EnableAutomaticButton.md)|Aktiviert und deaktiviert eine "auto" Schaltfläche, die über den regulären Farbenschaltflächen positioniert wird.  \(Die automatische Schaltfläche des Standardsystems wird **Automatisch** bezeichnet\).|  
|[CMFCColorMenuButton::EnableDocumentColors](../Topic/CMFCColorMenuButton::EnableDocumentColors.md)|Aktiviert die Anzeige von Dokumentbesondere Farben anstelle der Systemfarben.|  
|[CMFCColorMenuButton::EnableOtherButton](../Topic/CMFCColorMenuButton::EnableOtherButton.md)|Aktiviert und deaktiviert eine "eine andere" Schaltfläche, die den regulären Farbenschaltflächen positioniert wird.  \(Das Standardsystem "andere" Schaltfläche wird **Weitere Farben...** bezeichnet\).|  
|[CMFCColorMenuButton::EnableTearOff](../Topic/CMFCColorMenuButton::EnableTearOff.md)|Aktiviert die Möglichkeit, einen Farbenbereich auseinanderzureißen.|  
|[CMFCColorMenuButton::GetAutomaticColor](../Topic/CMFCColorMenuButton::GetAutomaticColor.md)|Ruft die aktuelle automatische Farbe ab.|  
|[CMFCColorMenuButton::GetColor](../Topic/CMFCColorMenuButton::GetColor.md)|Ruft die aktuelle Farbe der Schaltfläche ab.|  
|[CMFCColorMenuButton::GetColorByCmdID](../Topic/CMFCColorMenuButton::GetColorByCmdID.md)|Ruft die Farbe ab, die einer angegebenen Befehl ID entspricht|  
|[CMFCColorMenuButton::OnChangeParentWnd](../Topic/CMFCColorMenuButton::OnChangeParentWnd.md)|Aufgerufen vom Framework, wenn das übergeordnete Fenster ändert.|  
|[CMFCColorMenuButton::OpenColorDialog](../Topic/CMFCColorMenuButton::OpenColorDialog.md)|Öffnet ein Farben\-Auswahldialogfeld.|  
|[CMFCColorMenuButton::SetColor](../Topic/CMFCColorMenuButton::SetColor.md)|Legt die Farbe der aktuellen Farbenschaltfläche fest.|  
|[CMFCColorMenuButton::SetColorByCmdID](../Topic/CMFCColorMenuButton::SetColorByCmdID.md)|Legt die Farbe der angegebenen Farbenmenüschaltfläche fest.|  
|[CMFCColorMenuButton::SetColorName](../Topic/CMFCColorMenuButton::SetColorName.md)|Legt einen neuen Namen für die angegebene Farbe fest.|  
|[CMFCColorMenuButton::SetColumnsNumber](../Topic/CMFCColorMenuButton::SetColumnsNumber.md)|Legt die Anzahl von Spalten fest, die von einem `CMFCColorBar`\-Objekt angezeigt werden.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCColorMenuButton::CopyFrom](../Topic/CMFCColorMenuButton::CopyFrom.md)|Kopiert eine andere Symbolleisten\-Schaltfläche zur aktuellen Schaltfläche.|  
|[CMFCColorMenuButton::CreatePopupMenu](../Topic/CMFCColorMenuButton::CreatePopupMenu.md)|Stellt ein Farben\-Auswahldialogfeld erstellt.|  
|[CMFCColorMenuButton::IsEmptyMenuAllowed](../Topic/CMFCColorMenuButton::IsEmptyMenuAllowed.md)|Gibt an, ob leere Menüs unterstützt werden.|  
|[CMFCColorMenuButton::OnDraw](../Topic/CMFCColorMenuButton::OnDraw.md)|Aufgerufen vom Framework, um ein Bild auf einer Schaltfläche anzuzeigen.|  
|[CMFCColorMenuButton::OnDrawOnCustomizeList](../Topic/CMFCColorMenuButton::OnDrawOnCustomizeList.md)|Aufgerufen vom Framework, bevor ein `CMFCColorMenuButton`\-Objekt in der Liste eines Symbolleistenanpassungsdialogfelds angezeigt wird.|  
  
## Hinweise  
 Um den ursprünglichen Menübefehl oder die Symbolleistenschaltfläche durch ein `CMFCColorMenuButton`\-Objekt zu ersetzen, erstellen Sie das `CMFCColorMenuButton`\-Objekt, legen Sie alle entsprechenden [CMFCColorBar Class](../../mfc/reference/cmfccolorbar-class.md) Stile fest, und rufen Sie dann die Methode der Klasse `ReplaceButton`[CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md) auf.  Wenn Sie eine Symbolleiste anpassen, rufen Sie die [CMFCToolBarsCustomizeDialog::ReplaceButton](../Topic/CMFCToolBarsCustomizeDialog::ReplaceButton.md)\-Methode auf.  
  
 Das Farben\-Auswahldialogfeld wird während der Verarbeitung des [CMFCColorMenuButton::CreatePopupMenu](../Topic/CMFCColorMenuButton::CreatePopupMenu.md)\-Ereignishandler erstellt.  Der Ereignishandler wird der übergeordneten Frames mit einer `WM_COMMAND` Meldung.  Das `CMFCColorMenuButton`\-Objekt sendet die Steuerelement\-ID, die dem ursprünglichen Menübefehl oder die Symbolleistenschaltfläche zugewiesen wird.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie eine Farbenmenüschaltfläche erstellt und konfiguriert, indem verschiedene Methoden in der `CMFCColorMenuButton`\-Klasse angewendet wird.  Im Beispiel wird ein `CPalette`\-Objekt zuerst und anschließend erstellt, um ein Objekt der `CMFCColorMenuButton`\-Klasse zu erstellen.  Das `CMFCColorMenuButton`\-Objekt wird dann konfiguriert, indem die automatischen und anderen Schaltflächen aktiviert, und die Farbe und die Anzahl der Spalten festgelegt wird.  Dieser Code ist Teil [Word\-Auflagenbeispiel](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_WordPad#5](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_WordPad#5)]  
[!CODE [NVC_MFC_WordPad#6](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_WordPad#6)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md)  
  
 [CMFCColorMenuButton](../../mfc/reference/cmfccolormenubutton-class.md)  
  
## Anforderungen  
 **Header:** afxcolormenubutton.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCColorBar Class](../../mfc/reference/cmfccolorbar-class.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarsCustomizeDialog Class](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)   
 [CMFCColorButton Class](../../mfc/reference/cmfccolorbutton-class.md)