---
title: "CMFCColorBar Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCColorBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCColorBar class"
  - "CMFCColorBar::m_bInternal data member"
  - "CMFCColorBar::m_bIsEnabled data member"
  - "CMFCColorBar::m_bIsTearOff data member"
  - "CMFCColorBar::m_BoxSize data member"
  - "CMFCColorBar::m_bShowDocColorsWhenDocked data member"
  - "CMFCColorBar::m_bStdColorDlg data member"
  - "CMFCColorBar::m_ColorAutomatic data member"
  - "CMFCColorBar::m_ColorNames data member"
  - "CMFCColorBar::m_colors data member"
  - "CMFCColorBar::m_ColorSelected data member"
  - "CMFCColorBar::m_lstDocColors data member"
  - "CMFCColorBar::m_nCommandID data member"
  - "CMFCColorBar::m_nHorzMargin data member"
  - "CMFCColorBar::m_nHorzOffset data member"
  - "CMFCColorBar::m_nNumColumns data member"
  - "CMFCColorBar::m_nNumColumnsVert data member"
  - "CMFCColorBar::m_nNumRowsHorz data member"
  - "CMFCColorBar::m_nRowHeight data member"
  - "CMFCColorBar::m_nVertMargin data member"
  - "CMFCColorBar::m_nVertOffset data member"
  - "CMFCColorBar::m_Palette data member"
  - "CMFCColorBar::m_pParentBtn data member"
  - "CMFCColorBar::m_pParentRibbonBtn data member"
  - "CMFCColorBar::m_pWndPropList data member"
  - "CMFCColorBar::m_strAutoColor data member"
  - "CMFCColorBar::m_strDocColors data member"
  - "CMFCColorBar::m_strOtherColor data member"
ms.assetid: 4756ee40-25a5-4cee-af7f-acab7993d1c7
caps.latest.revision: 35
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 37
---
# CMFCColorBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Klasse stellt eine `CMFCColorBar` andockbare Symbolleisten dar, die Farben in einem Dokument oder einer Anwendung auswählen kann.  
  
## Syntax  
  
```  
class CMFCColorBar : public CMFCPopupMenuBar  
```  
  
## Mitglieder  
  
### Geschützte Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCColorBar::CMFCColorBar](../Topic/CMFCColorBar::CMFCColorBar.md)|Erstellt ein `CMFCColorBar`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCColorBar::ContextToSize](../Topic/CMFCColorBar::ContextToSize.md)|Berechnet die vertikale und horizontale Ränder, die erforderlich sind, um die Schaltflächen auf dem Farbleistensteuerelement zu enthalten und passt dann den Speicherort dieser Schaltflächen.|  
|[CMFCColorBar::CreateControl](../Topic/CMFCColorBar::CreateControl.md)|Stellt ein Farbleistensteuerfenster erstellt, fügt es an den `CMFCColorBar`\-Objekt an und ändert die Größe des Steuerelements, um die angegebene Farbpalette zu enthalten.|  
|[CMFCColorBar::Create](../Topic/CMFCColorBar::Create.md)|Stellt ein Farbleistensteuerfenster erstellt und fügt es an den `CMFCColorBar`\-Objekt.|  
|[CMFCColorBar::EnableAutomaticButton](../Topic/CMFCColorBar::EnableAutomaticButton.md)|In oder aus die automatische Schaltfläche.|  
|[CMFCColorBar::EnableOtherButton](../Topic/CMFCColorBar::EnableOtherButton.md)|Aktiviert oder deaktiviert die Anzeige eines Dialogfelds, das den Benutzer mehr Farben auswählen können.|  
|[CMFCColorBar::GetColor](../Topic/CMFCColorBar::GetColor.md)|Ruft die aktuell ausgewählte Farbe ab.|  
|[CMFCColorBar::GetCommandID](../Topic/CMFCColorBar::GetCommandID.md)|Ruft die Befehls\-ID des aktuellen Farbleistensteuerelements ab.|  
|[CMFCColorBar::GetHighlightedColor](../Topic/CMFCColorBar::GetHighlightedColor.md)|Ruft die Farbe ab, die angibt, dass eine Farbenschaltfläche den Fokus besitzt; Das bedeutet, dass die Schaltfläche *heiß*.|  
|[CMFCColorBar::GetHorzMargin](../Topic/CMFCColorBar::GetHorzMargin.md)|Ruft die horizontale Rand ab, der das Leerzeichen zwischen der linken oder rechten Farbenzelle und der Clientbereichsgrenze ist.|  
|[CMFCColorBar::GetVertMargin](../Topic/CMFCColorBar::GetVertMargin.md)|Ruft den vertikalen Rand ab, der das Leerzeichen zwischen der oberen oder die Unterseitenfarbenzelle und die Clientbereichsgrenze ist.|  
|[CMFCColorBar::IsTearOff](../Topic/CMFCColorBar::IsTearOff.md)|Gibt an, ob die aktuelle Farbbalken von ist.|  
|[CMFCColorBar::SetColor](../Topic/CMFCColorBar::SetColor.md)|Legt die Farbe fest, die derzeit ausgewählt ist.|  
|[CMFCColorBar::SetColorName](../Topic/CMFCColorBar::SetColorName.md)|Legt einen neuen Namen für eine angegebene Farbe fest.|  
|[CMFCColorBar::SetCommandID](../Topic/CMFCColorBar::SetCommandID.md)|Legt eine neue Befehls\-ID für ein Farbleistensteuerelement fest.|  
|[CMFCColorBar::SetDocumentColors](../Topic/CMFCColorBar::SetDocumentColors.md)|Legt die Liste von Farben fest, die im aktuellen Dokument verwendet werden.|  
|[CMFCColorBar::SetHorzMargin](../Topic/CMFCColorBar::SetHorzMargin.md)|Legt den horizontalen Rand fest, der das Leerzeichen zwischen der linken oder rechten Farbenzelle und der Clientbereichsgrenze ist.|  
|[CMFCColorBar::SetVertMargin](../Topic/CMFCColorBar::SetVertMargin.md)|Legt den vertikalen Rand fest, der das Leerzeichen zwischen der oberen oder die Unterseitenfarbenzelle und die Clientbereichsgrenze ist.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCColorBar::AdjustLocations](../Topic/CMFCColorBar::AdjustLocations.md)|Passt die Positionen der Farbenschaltflächen auf dem Farbleistensteuerelement.|  
|[CMFCColorBar::AllowChangeTextLabels](../Topic/CMFCColorBar::AllowChangeTextLabels.md)|Gibt an, ob die Beschriftung von Farbenschaltflächen ändern kann.|  
|[CMFCColorBar::AllowShowOnList](../Topic/CMFCColorBar::AllowShowOnList.md)|Gibt an, ob das Farbleistensteuerobjekt in einer Symbolleistenliste während des Anpassungsprozesses angezeigt werden kann.|  
|[CMFCColorBar::CalcSize](../Topic/CMFCColorBar::CalcSize.md)|Aufgerufen vom Framework als Teil des Layoutrechenvorgangs.|  
|[CMFCColorBar::CreatePalette](../Topic/CMFCColorBar::CreatePalette.md)|Initalizes eine Palette mit den Farben in einem angegebenen Array Farben.|  
|[CMFCColorBar::GetColorGridSize](../Topic/CMFCColorBar::GetColorGridSize.md)|Berechnet die Anzahl der Zeilen und Spalten im Raster eines Farbleistensteuerelements.|  
|[CMFCColorBar::GetExtraHeight](../Topic/CMFCColorBar::GetExtraHeight.md)|Berechnet die zusätzliche Höhe, die die aktuelle Farbleiste benötigt, um andere Benutzeroberflächenelemente wie die Schaltfläche **Andere** anzuzeigen, dokumentieren Farben, u. a.|  
|[CMFCColorBar::InitColors](../Topic/CMFCColorBar::InitColors.md)|Initialisiert ein Array Farben mit den Farben in einer angegebenen Palette oder in der Systemstandardpalette.|  
|[CMFCColorBar::OnKey](../Topic/CMFCColorBar::OnKey.md)|Aufgerufen vom Framework, wenn ein Benutzer eine Taste drückt.|  
|[CMFCColorBar::OnSendCommand](../Topic/CMFCColorBar::OnSendCommand.md)|Aufgerufen durch das Framework, um eine Hierarchie von Popup\- Steuerelemente zu schließen.|  
|[CMFCColorBar::OnUpdateCmdUI](../Topic/CMFCColorBar::OnUpdateCmdUI.md)|Aufgerufen durch das Framework, um ein Benutzeroberflächen\-Element eines Farbleistensteuerelements vor dem Element wird zu aktivieren oder zu deaktivieren angezeigt.|  
|[CMFCColorBar::OpenColorDialog](../Topic/CMFCColorBar::OpenColorDialog.md)|Öffnet ein Dialogfeld.|  
|[CMFCColorBar::Rebuild](../Topic/CMFCColorBar::Rebuild.md)|Aktualisiert vollständig das Farbleistensteuerelement neu.|  
|[CMFCColorBar::SelectPalette](../Topic/CMFCColorBar::SelectPalette.md)|Legt die Logische Palette des angegebenen Gerätekontexts zur Palette der übergeordneten Schaltfläche des aktuellen Farbleistensteuerelements fest.|  
|[CMFCColorBar::SetPropList](../Topic/CMFCColorBar::SetPropList.md)|Legt den `m_pWndPropList` geschützten Datenmember zum angegebenen Zeiger auf ein Eigenschaftenraster fest.|  
|[CMFCColorBar::ShowCommandMessageString](../Topic/CMFCColorBar::ShowCommandMessageString.md)|Zeigt das Rahmenfenster an, das das Farbleistensteuerelement besitzt, um die Meldungszeile in der Statusleiste zu aktualisieren.|  
  
### Geschützte Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|`m_bInternal`|Ein boolesches Feld, das bestimmt, ob Mausereignisse verarbeitet werden.  In der Regel werden Mausereignisse verarbeitet, wenn dieses Feld `TRUE` ist und Anpassungsmodus `FALSE` ist.|  
|`m_bIsEnabled`|Ein boolescher Wert, der angibt, ob ein Steuerelement aktiviert ist.|  
|`m_bIsTearOff`|Ein boolescher Wert, der angibt, ob das Farbleistensteuerelement Andocken unterstützt.|  
|`m_BoxSize`|Ein [CSize](../../atl-mfc-shared/reference/csize-class.md)\-Objekt, das die Größe einer Zelle in einem Farbleistenraster angibt.|  
|`m_bShowDocColorsWhenDocked`|Ein boolescher Wert, der angibt, ob Dokumentenfarben anzeigt, wenn die Farbleiste angedockt ist.  Weitere Informationen finden Sie unter [CMFCColorBar::SetDocumentColors](../Topic/CMFCColorBar::SetDocumentColors.md).|  
|`m_bStdColorDlg`|Ein boolescher Wert, der angibt, ob das Standardsystem Farbe Dialogfeld oder das Dialogfeld [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) anzeigt.  Weitere Informationen finden Sie unter [CMFCColorBar::EnableOtherButton](../Topic/CMFCColorBar::EnableOtherButton.md).|  
|`m_ColorAutomatic`|[COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449), das die aktuelle Farbe automatische speichert.  Weitere Informationen finden Sie unter [CMFCColorBar::EnableOtherButton](../Topic/CMFCColorBar::EnableOtherButton.md).|  
|`m_ColorNames`|Ein [CMap](../../mfc/reference/cmap-class.md)\-Objekt, das einen Satz RGB zuordnet, Farbe mit ihren Namen.|  
|`m_colors`|[CArray](../../mfc/reference/carray-class.md) von [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)\-Werten, das die Farben enthält, die im Farbleistensteuerelement angezeigt werden.|  
|`m_ColorSelected`|Ein [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)\-Wert, der die Farbe ist, die der Benutzer gerade vom Farbleistensteuerelement ausgewählt hat.|  
|`m_lstDocColors`|[CList](../../mfc/reference/clist-class.md) von [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)\-Werten, das die Farben enthält, die derzeit in einem Dokument verwendet werden.|  
|`m_nCommandID`|Eine ganze Zahl, die die Befehls\-ID einer Farbenschaltfläche ist.|  
|`m_nHorzMargin`|Eine ganze Zahl, die der horizontale Rand zwischen der Farbe ist, Schaltflächen in einem Raster von Farben.|  
|`m_nHorzOffset`|Eine ganze Zahl, die der horizontale Offset zum Mittelpunkt der Farbenschaltfläche ist.  Dieser Wert ist von Bedeutung, wenn die auf ein Bild oder zusätzlich zu einer Farbe Text.|  
|`m_nNumColumns`|Eine ganze Zahl, die die Anzahl der Spalten in einem Farbleistensteuergitter von Farben ist.|  
|`m_nNumColumnsVert`|Eine ganze Zahl, die die Anzahl der Spalten in einem vertikal orientierten Raster von Farben ist.|  
|`m_nNumRowsHorz`|Eine ganze Zahl, die die Anzahl der Spalten in einem horizontal ausgerichteten Raster von Farben ist.|  
|`m_nRowHeight`|Eine ganze Zahl, die auf die Höhe einer Zeile der Farbe ist, Schaltflächen in einem Raster von Farben.|  
|`m_nVertMargin`|Eine ganze Zahl, die der vertikalen Rand zwischen der Farbe ist, Schaltflächen in einem Raster von Farben.|  
|`m_nVertOffset`|Eine ganze Zahl, die der vertikalen Offset zum Mittelpunkt der Farbenschaltfläche ist.  Dieser Wert ist von Bedeutung, wenn die auf ein Bild oder zusätzlich zu einer Farbe Text.|  
|`m_Palette`|[CPalette](../../mfc/reference/cpalette-class.md) der Farben, die im Farbleistensteuerelement verwendet werden.|  
|`m_pParentBtn`|Ein Zeiger auf einen [CMFCColorButton](../../mfc/reference/cmfccolorbutton-class.md)\-Objekt, das das übergeordnete Element der aktuellen Schaltfläche ist.  Dieser Wert ist von Bedeutung, wenn die Farbenschaltfläche in einer Hierarchie von Symbolleisten\-Steuerelementen ist oder in einem Farbeigenschaftenraster\-steuerelement ist.|  
|`m_pParentRibbonBtn`|Ein Zeiger auf einen [CMFCRibbonColorButton](../../mfc/reference/cmfcribboncolorbutton-class.md)\-Objekt, das auf dem Menüband ist und die Elemente Schaltfläche der aktuellen Schaltfläche ist.  Dieser Wert ist von Bedeutung, wenn die Farbenschaltfläche in einer Hierarchie von Symbolleisten\-Steuerelementen ist oder in einem Farbeigenschaftenraster\-steuerelement ist.|  
|`m_pWndPropList`|Ein Zeiger auf ein Objekt [CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md).|  
|`m_strAutoColor`|[CString](../../atl-mfc-shared/reference/cstringt-class.md), das der Text ist, der auf der Schaltfläche **Automatisch** angezeigt wird.  Weitere Informationen finden Sie unter [CMFCColorBar::EnableAutomaticButton](../Topic/CMFCColorBar::EnableAutomaticButton.md).|  
|`m_strDocColors`|[CString](../../atl-mfc-shared/reference/cstringt-class.md), das der Text ist, der auf der Dokumentenfarbenschaltfläche angezeigt wird.  Weitere Informationen finden Sie unter [CMFCColorBar::SetDocumentColors](../Topic/CMFCColorBar::SetDocumentColors.md).|  
|`m_strOtherColor`|[CString](../../atl-mfc-shared/reference/cstringt-class.md), das der Text ist, der auf der *anderen* Schaltfläche angezeigt wird.  Weitere Informationen finden Sie unter [CMFCColorBar::EnableOtherButton](../Topic/CMFCColorBar::EnableOtherButton.md).|  
  
## Hinweise  
 Normalerweise erstellen Sie kein `CMFCColorBar`\-Objekt direkt.  Stattdessen erstellt [CMFCColorMenuButton Class](../../mfc/reference/cmfccolormenubutton-class.md) \(wird in Menüs und in den Symbolleisten\) oder [CMFCColorButton Class](../../mfc/reference/cmfccolorbutton-class.md) das `CMFCColorBar`\-Objekt.  
  
 Die `CMFCColorBar`\-Klasse stellt die folgende Funktionalität:  
  
-   Passt automatisch die Liste der Dokumentenfarben.  
  
-   Rettet und stellt diesen Zustand, zusammen mit dem Dokumentenzustand wieder her.  
  
-   Verwaltet die "auto" Schaltfläche.  
  
-   Verwendet das [CMFCColorPickerCtrl Class](../../mfc/reference/cmfccolorpickerctrl-class.md)\-Steuerelement, um eine benutzerdefinierte Farbe auswählen.  
  
-   Unterstützt einen "Tearoffen" Zustand \(wenn sie erstellt wird, indem [CMFCColorMenuButton Class](../../mfc/reference/cmfccolormenubutton-class.md) verwendet\).  
  
 Um die `CMFCColorBar`\-Funktionalität in die Anwendung enthalten:  
  
1.  Erstellen Sie eine reguläre Menütaste und weisen Sie eine ID, beispielsweise ID\_CHAR\_COLOR zu.  
  
2.  In der Rahmenfensterklasse überschreiben Sie die Methode [CFrameWndEx::OnShowPopupMenu](../Topic/CFrameWndEx::OnShowPopupMenu.md) und ersetzen Sie die reguläre Menüschaltfläche durch ein Objekt [CMFCColorMenuButton Class](../../mfc/reference/cmfccolormenubutton-class.md) \(durch Aufrufen von [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md)\).  
  
3.  Legen Sie alle Stile fest und aktivieren oder deaktivieren Sie die Funktionen des `CMFCColorBar`\-Objekts während [CMFCColorMenuButton Class](../../mfc/reference/cmfccolormenubutton-class.md) Erstellung.  Das `CMFCColorMenuButton`\-Objekt dynamisch erstellt das `CMFCColorBar`\-Objekt, nachdem das Framework die `CreatePopupMenu`\-Methode aufruft.  
  
 Wenn der Benutzer auf eine Farbleistensteuerschaltfläche klickt, verwendet das Framework `ON_COMMAND`\-Makro, um das übergeordnete Element des Farbleistensteuerelements zu benachrichtigen.  Im Makro ist der Befehls\-ID\-Parameter der Wert, den Sie der Farbleistensteuerschaltfläche in Schritt 1 zugewiesen haben ID\_CHAR\_COLOR \(in diesem Beispiel\).  Weitere Informationen finden Sie in [CMFCColorMenuButton Class](../../mfc/reference/cmfccolormenubutton-class.md), [CMFCColorButton Class](../../mfc/reference/cmfccolorbutton-class.md), [CMFCColorPickerCtrl Class](../../mfc/reference/cmfccolorpickerctrl-class.md), [CFrameWndEx Class](../../mfc/reference/cframewndex-class.md) und [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)\-Klassen.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie eine Farbleiste konfiguriert, indem verschiedene Methoden in der `CMFCColorBar`\-Klasse angewendet wird.  Die Methoden legen das horizontale und vertikale Ränder fest, aktivieren die andere Schaltfläche, erstellen ein Farbleistensteuerfenster und legt die aktuell ausgewählte Farbe.  Dieses Beispiel ist Teil [Neue Kontrollprobe](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_NewControls#1](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#1)]  
[!CODE [NVC_MFC_NewControls#2](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#2)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md)  
  
 [CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md)  
  
## Anforderungen  
 **Header:** afxcolorbar.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)