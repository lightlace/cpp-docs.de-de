---
title: CMFCColorBar Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCColorBar
- AFXCOLORBAR/CMFCColorBar
- AFXCOLORBAR/CMFCColorBar::CMFCColorBar
- AFXCOLORBAR/CMFCColorBar::ContextToSize
- AFXCOLORBAR/CMFCColorBar::CreateControl
- AFXCOLORBAR/CMFCColorBar::Create
- AFXCOLORBAR/CMFCColorBar::EnableAutomaticButton
- AFXCOLORBAR/CMFCColorBar::EnableOtherButton
- AFXCOLORBAR/CMFCColorBar::GetColor
- AFXCOLORBAR/CMFCColorBar::GetCommandID
- AFXCOLORBAR/CMFCColorBar::GetHighlightedColor
- AFXCOLORBAR/CMFCColorBar::GetHorzMargin
- AFXCOLORBAR/CMFCColorBar::GetVertMargin
- AFXCOLORBAR/CMFCColorBar::IsTearOff
- AFXCOLORBAR/CMFCColorBar::SetColor
- AFXCOLORBAR/CMFCColorBar::SetColorName
- AFXCOLORBAR/CMFCColorBar::SetCommandID
- AFXCOLORBAR/CMFCColorBar::SetDocumentColors
- AFXCOLORBAR/CMFCColorBar::SetHorzMargin
- AFXCOLORBAR/CMFCColorBar::SetVertMargin
- AFXCOLORBAR/CMFCColorBar::AdjustLocations
- AFXCOLORBAR/CMFCColorBar::AllowChangeTextLabels
- AFXCOLORBAR/CMFCColorBar::AllowShowOnList
- AFXCOLORBAR/CMFCColorBar::CalcSize
- AFXCOLORBAR/CMFCColorBar::CreatePalette
- AFXCOLORBAR/CMFCColorBar::GetColorGridSize
- AFXCOLORBAR/CMFCColorBar::GetExtraHeight
- AFXCOLORBAR/CMFCColorBar::InitColors
- AFXCOLORBAR/CMFCColorBar::OnKey
- AFXCOLORBAR/CMFCColorBar::OnSendCommand
- AFXCOLORBAR/CMFCColorBar::OnUpdateCmdUI
- AFXCOLORBAR/CMFCColorBar::OpenColorDialog
- AFXCOLORBAR/CMFCColorBar::Rebuild
- AFXCOLORBAR/CMFCColorBar::SelectPalette
- AFXCOLORBAR/CMFCColorBar::SetPropList
- AFXCOLORBAR/CMFCColorBar::ShowCommandMessageString
dev_langs:
- C++
helpviewer_keywords:
- CMFCColorBar [MFC], CMFCColorBar
- CMFCColorBar [MFC], ContextToSize
- CMFCColorBar [MFC], CreateControl
- CMFCColorBar [MFC], Create
- CMFCColorBar [MFC], EnableAutomaticButton
- CMFCColorBar [MFC], EnableOtherButton
- CMFCColorBar [MFC], GetColor
- CMFCColorBar [MFC], GetCommandID
- CMFCColorBar [MFC], GetHighlightedColor
- CMFCColorBar [MFC], GetHorzMargin
- CMFCColorBar [MFC], GetVertMargin
- CMFCColorBar [MFC], IsTearOff
- CMFCColorBar [MFC], SetColor
- CMFCColorBar [MFC], SetColorName
- CMFCColorBar [MFC], SetCommandID
- CMFCColorBar [MFC], SetDocumentColors
- CMFCColorBar [MFC], SetHorzMargin
- CMFCColorBar [MFC], SetVertMargin
- CMFCColorBar [MFC], AdjustLocations
- CMFCColorBar [MFC], AllowChangeTextLabels
- CMFCColorBar [MFC], AllowShowOnList
- CMFCColorBar [MFC], CalcSize
- CMFCColorBar [MFC], CreatePalette
- CMFCColorBar [MFC], GetColorGridSize
- CMFCColorBar [MFC], GetExtraHeight
- CMFCColorBar [MFC], InitColors
- CMFCColorBar [MFC], OnKey
- CMFCColorBar [MFC], OnSendCommand
- CMFCColorBar [MFC], OnUpdateCmdUI
- CMFCColorBar [MFC], OpenColorDialog
- CMFCColorBar [MFC], Rebuild
- CMFCColorBar [MFC], SelectPalette
- CMFCColorBar [MFC], SetPropList
- CMFCColorBar [MFC], ShowCommandMessageString
ms.assetid: 4756ee40-25a5-4cee-af7f-acab7993d1c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2083c26943768afff4b3b20a2ba95c709648dd50
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33376137"
---
# <a name="cmfccolorbar-class"></a>CMFCColorBar-Klasse
Die `CMFCColorBar` -Klasse stellt eine andockbare Symbolleiste, die Farben in einem Dokument oder die Anwendung auswählen können.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCColorBar : public CMFCPopupMenuBar  
```  
  
## <a name="members"></a>Member  
  
### <a name="protected-constructors"></a>Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCColorBar::CMFCColorBar](#cmfccolorbar)|Erstellt ein `CMFCColorBar`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCColorBar::ContextToSize](#contexttosize)|Berechnet die horizontale und vertikale Ränder, die auf die Schaltflächen auf der Farbleiste Steuerelement enthalten erforderlich sind, und klicken Sie dann passt die Position über diese Schaltflächen an.|  
|[CMFCColorBar::CreateControl](#createcontrol)|Erstellt eine Farbleiste Steuerelementfensters, fügt es der `CMFCColorBar` Objekt, und ändert die Größe des Steuerelements, um der Palette angegebenen Farben enthalten.|  
|[CMFCColorBar::Create](#create)|Erstellt eine Farbleiste Steuerelementfensters und fügt es der `CMFCColorBar` Objekt.|  
|[CMFCColorBar::EnableAutomaticButton](#enableautomaticbutton)|Anzeigen oder Ausblenden der Schaltfläche "Automatische".|  
|[CMFCColorBar::EnableOtherButton](#enableotherbutton)|Aktiviert oder deaktiviert die Anzeige eines Dialogfelds, in dem den Benutzer weitere Farben auswählen können.|  
|[CMFCColorBar::GetColor](#getcolor)|Ruft die zurzeit ausgewählte Farbe ab.|  
|[CMFCColorBar::GetCommandID](#getcommandid)|Ruft die Befehls-ID des aktuellen Farbleiste-Steuerelements ab.|  
|[CMFCColorBar::GetHighlightedColor](#gethighlightedcolor)|Ruft die Farbe, der anzeigt, dass eine farbenschaltfläche im Fokus ist, ab. die Schaltfläche ist *hot*.|  
|[CMFCColorBar::GetHorzMargin](#gethorzmargin)|Ruft den horizontalen Rand die Fläche zwischen links oder rechts Farbe Zelle und die Grenze der Client-Bereich ist ab.|  
|[CMFCColorBar::GetVertMargin](#getvertmargin)|Ruft den vertikalen Rand der Abstand zwischen dem oberen oder unteren Farbe Zelle und die Grenze der Client-Bereich wird ab.|  
|[CMFCColorBar::IsTearOff](#istearoff)|Gibt an, ob der aktuelle Farbleiste angedockt werden kann.|  
|[CMFCColorBar::SetColor](#setcolor)|Legt die Farbe, die derzeit ausgewählt ist.|  
|[CMFCColorBar::SetColorName](#setcolorname)|Legt einen neuen Namen für eine angegebene Farbe fest.|  
|[CMFCColorBar::SetCommandID](#setcommandid)|Legt eine neue Befehls-ID für ein Steuerelement Farbleiste an.|  
|[CMFCColorBar::SetDocumentColors](#setdocumentcolors)|Legt die Liste der Farben, mit denen im aktuellen Dokument fest.|  
|[CMFCColorBar::SetHorzMargin](#sethorzmargin)|Legt den horizontalen Rand, der den Abstand zwischen der linken Seite oder Zelle rechts Farbe und die Client-Bereich-Grenze ist.|  
|[CMFCColorBar::SetVertMargin](#setvertmargin)|Legt den vertikalen Rand, der den Abstand zwischen der obersten oder untersten Zelle Farbe und die Client-Bereich-Grenze ist.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCColorBar::AdjustLocations](#adjustlocations)|Passt die Positionen der Farbe Schaltflächen auf der Farbleiste-Steuerelement.|  
|[CMFCColorBar::AllowChangeTextLabels](#allowchangetextlabels)|Gibt an, ob die Beschriftung der Color-Schaltflächen geändert werden kann.|  
|[CMFCColorBar::AllowShowOnList](#allowshowonlist)|Gibt an, ob das Steuerelementobjekt Farbleiste während Anpassungsvorgangs in eine Symbolleistenliste angezeigt werden kann.|  
|[CMFCColorBar::CalcSize](#calcsize)|Vom Framework als Teil der Berechnungsprozess Layout aufgerufen.|  
|[CMFCColorBar::CreatePalette](#createpalette)|Initialisiert eine Palette mit Farben in einem angegebenen Array von Farben.|  
|[CMFCColorBar::GetColorGridSize](#getcolorgridsize)|Berechnet die Anzahl der Zeilen und Spalten des Rasters eines Steuerelements Farbleiste an.|  
|[CMFCColorBar::GetExtraHeight](#getextraheight)|Berechnet die zusätzliche Höhe, die der aktuellen Farbleiste erfordert verschiedene Elemente der Benutzeroberfläche angezeigt, wie z. B. die **andere** Schaltfläche Dokumentfarben und So weiter.|  
|[CMFCColorBar::InitColors](#initcolors)|Initialisiert ein Array von Farben mit der Farben in einer angegebenen Palette oder der Standardpalette System an.|  
|[CMFCColorBar::OnKey](#onkey)|Wird vom Framework aufgerufen, wenn ein Benutzer eine Taste drückt.|  
|[CMFCColorBar::OnSendCommand](#onsendcommand)|Vom Framework aufgerufen wird, schließen Sie eine Hierarchie von Popup-Steuerelementen.|  
|[CMFCColorBar::OnUpdateCmdUI](#onupdatecmdui)|Wird aufgerufen, durch das Framework zu aktivieren oder deaktivieren ein Element der Benutzeroberfläche eines Steuerelements Farbleiste aus, bevor das Element angezeigt wird.|  
|[CMFCColorBar::OpenColorDialog](#opencolordialog)|Öffnet das Dialogfeld Farbe an.|  
|[CMFCColorBar::Rebuild](#rebuild)|Vollständig zeichnet die Farbleiste-Steuerelement.|  
|[CMFCColorBar::SelectPalette](#selectpalette)|Legt die logische Palette von den angegebenen Gerätekontext auf der Palette der Schaltfläche übergeordnete Element des aktuellen Farbleiste-Steuerelements fest.|  
|[CMFCColorBar::SetPropList](#setproplist)|Legt die `m_pWndPropList` geschützt Datenmember des angegebenen Zeigers auf ein Eigenschaftenraster-Steuerelement.|  
|[CMFCColorBar::ShowCommandMessageString](#showcommandmessagestring)|Fordert das Rahmenfenster, das die Farbleiste Steuerelement zum Aktualisieren der Nachricht Position in der Statusleiste besitzt.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|`m_bInternal`|Ein boolesches Feld, das bestimmt, ob Mausereignisse verarbeitet werden. Mausereignisse werden in der Regel wird verarbeitet, wenn dieses Feld ist `TRUE` und Anpassungsmodus `FALSE`.|  
|`m_bIsEnabled`|Ein boolescher Wert, der angibt, ob ein Steuerelement aktiviert ist.|  
|`m_bIsTearOff`|Ein boolescher Wert, der angibt, ob das Steuerelement Farbleiste Andocken unterstützt.|  
|`m_BoxSize`|Ein [CSize](../../atl-mfc-shared/reference/csize-class.md) Objekt, das die Größe einer Zelle in einem Raster Farbleiste angibt.|  
|`m_bShowDocColorsWhenDocked`|Ein boolescher Wert, der angibt, ob Dokumentfarben angezeigt, wenn der Farbleiste angedockt wird. Weitere Informationen finden Sie unter [CMFCColorBar::SetDocumentColors](#setdocumentcolors).|  
|`m_bStdColorDlg`|Ein boolescher Wert, der angibt, ob das Dialogfeld Farbe Standardbetriebssystem angezeigt oder [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) (Dialogfeld). Weitere Informationen finden Sie unter [CMFCColorBar::EnableOtherButton](#enableotherbutton).|  
|`m_ColorAutomatic`|Ein [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) , speichert die aktuelle Farbe. Weitere Informationen finden Sie unter [CMFCColorBar::EnableOtherButton](#enableotherbutton).|  
|`m_ColorNames`|Ein [CMap](../../mfc/reference/cmap-class.md) -Objekt, das ordnet eine Reihe von RGB-Farben, mit ihren Namen.|  
|`m_colors`|Ein [CArray](../../mfc/reference/carray-class.md) von [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Werte, die die Farben enthält, die im Steuerelement Farbleiste angezeigt werden.|  
|`m_ColorSelected`|Ein [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Wert, der die Farbe, die der Benutzer derzeit über der Farbleiste-Steuerelement ausgewählt hat.|  
|`m_lstDocColors`|Ein [CList](../../mfc/reference/clist-class.md) von [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Werte, die die Farben enthält, die derzeit in einem Dokument verwendet werden.|  
|`m_nCommandID`|Eine ganze Zahl ohne Vorzeichen, die die Befehls-ID, der eine Schaltfläche "Farbe" ist.|  
|`m_nHorzMargin`|Eine ganze Zahl, die die horizontale Rand zwischen den Schaltflächen Farbe in einem Raster von Farben ist.|  
|`m_nHorzOffset`|Eine ganze Zahl, die den horizontalen Offset in die Mitte der Schaltfläche für die Farbe ist. Dieser Wert ist wichtig, wenn die Schaltfläche Text oder ein Bild zusätzlich zu einer Farbe angezeigt.|  
|`m_nNumColumns`|Eine ganze Zahl, die die Anzahl der Spalten im Raster eine Farbleiste-Steuerelement von Farben ist.|  
|`m_nNumColumnsVert`|Eine ganze Zahl, die die Anzahl der Spalten in ein Raster mit Farben vertikal ausgerichtet ist.|  
|`m_nNumRowsHorz`|Eine ganze Zahl, die die Anzahl der Spalten in einem horizontal ausgerichteten Raster von Farben ist.|  
|`m_nRowHeight`|Eine ganze Zahl, die die Höhe einer Zeile der Color-Schaltflächen in einem Raster von Farben ist.|  
|`m_nVertMargin`|Eine ganze Zahl, die den vertikalen Rand zwischen den Schaltflächen Farbe in einem Raster von Farben ist.|  
|`m_nVertOffset`|Eine ganze Zahl, die den vertikalen Offset in die Mitte der Schaltfläche für die Farbe ist. Dieser Wert ist wichtig, wenn die Schaltfläche Text oder ein Bild zusätzlich zu einer Farbe angezeigt.|  
|`m_Palette`|Ein [CPalette](../../mfc/reference/cpalette-class.md) der Farben, die in der Farbleiste-Steuerelement verwendet werden.|  
|`m_pParentBtn`|Ein Zeiger auf eine [CMFCColorButton](../../mfc/reference/cmfccolorbutton-class.md) -Objekt, das das übergeordnete Element der aktuellen Schaltfläche ist. Dieser Wert ist erhebliche, wenn die Schaltfläche "Farbe" befindet sich in einer Hierarchie von Symbolleisten-Steuerelemente oder befindet sich in einer Farbe Eigenschaftenraster-Steuerelement.|  
|`m_pParentRibbonBtn`|Ein Zeiger auf eine [CMFCRibbonColorButton](../../mfc/reference/cmfcribboncolorbutton-class.md) Objekt, das auf dem Menüband und die Schaltfläche übergeordnete Element der aktuellen Schaltfläche ist. Dieser Wert ist erhebliche, wenn die Schaltfläche "Farbe" befindet sich in einer Hierarchie von Symbolleisten-Steuerelemente oder befindet sich in einer Farbe Eigenschaftenraster-Steuerelement.|  
|`m_pWndPropList`|Ein Zeiger auf eine [CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md) Objekt.|  
|`m_strAutoColor`|Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) also auf angezeigte Text der **automatische** Schaltfläche. Weitere Informationen finden Sie unter [CMFCColorBar::EnableAutomaticButton](#enableautomaticbutton).|  
|`m_strDocColors`|Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) also den Text, der auf die Schaltfläche "Farben" des Dokuments angezeigt wird. Weitere Informationen finden Sie unter [CMFCColorBar::SetDocumentColors](#setdocumentcolors).|  
|`m_strOtherColor`|Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) also auf angezeigte Text der *andere* Schaltfläche. Weitere Informationen finden Sie unter [CMFCColorBar::EnableOtherButton](#enableotherbutton).|  
  
## <a name="remarks"></a>Hinweise  
 In der Regel nicht erstellt eine `CMFCColorBar` -Objekts direkt. Stattdessen die [CMFCColorMenuButton Klasse](../../mfc/reference/cmfccolormenubutton-class.md) (verwendet in den Menüs und Symbolleisten) oder die [CMFCColorButton Klasse](../../mfc/reference/cmfccolorbutton-class.md) erstellt die `CMFCColorBar` Objekt.  
  
 Die `CMFCColorBar` Klasse bietet folgende Funktionen:  
  
-   Passt automatisch die Liste der Dokumentfarben an.  
  
-   Speichert und seinen Status, der zusammen mit dem Dokument Zustand wiederhergestellt.  
  
-   Verwaltet die Schaltfläche "Automatische".  
  
-   Verwendet die [CMFCColorPickerCtrl-Klasse](../../mfc/reference/cmfccolorpickerctrl-class.md) Steuerelement, um eine benutzerdefinierte Farbe auszuwählen.  
  
-   Unterstützt einen Zustand "abtrennbare" (wenn es erstellt wird die [CMFCColorMenuButton Klasse](../../mfc/reference/cmfccolormenubutton-class.md)).  
  
 Integrieren der `CMFCColorBar` Funktionalität in Ihrer Anwendung:  
  
1.  Erstellen einer regulären Menüschaltfläche, und weisen Sie diese in eine ID, z. B. ID_CHAR_COLOR.  
  
2.  In Ihre Rahmenfenster (Klasse), überschreiben die [CFrameWndEx::OnShowPopupMenu](../../mfc/reference/cframewndex-class.md#onshowpopupmenu) Methode, und ersetzen das reguläre Menü mit Schaltfläche eine [CMFCColorMenuButton Klasse](../../mfc/reference/cmfccolormenubutton-class.md) Objekt (durch Aufrufen [CMFCToolBar: : ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)).  
  
3.  Legen Sie alle Formate zum Aktivieren oder deaktivieren Sie die Funktionen von der `CMFCColorBar` -Objekt während [CMFCColorMenuButton Klasse](../../mfc/reference/cmfccolormenubutton-class.md) erstellen. Die `CMFCColorMenuButton` Objekt dynamisch erstellt die `CMFCColorBar` Objekts, nachdem das Framework Ruft die `CreatePopupMenu` Methode.  
  
 Wenn der Benutzer eine Farbleiste Steuerelement Schaltfläche klickt, wird das Framework verwendet die `ON_COMMAND` Makro, das das übergeordnete Element des Steuerelements Farbleiste zu benachrichtigen. In das Makro ist die Befehls-ID-Parameter der Wert, den Sie auf die Farbleiste Steuerelement Schaltfläche in Schritt 1 (in diesem Beispiel ID_CHAR_COLOR) zugewiesen. Weitere Informationen finden Sie unter der [CMFCColorMenuButton Klasse](../../mfc/reference/cmfccolormenubutton-class.md), [CMFCColorButton Klasse](../../mfc/reference/cmfccolorbutton-class.md), [CMFCColorPickerCtrl-Klasse](../../mfc/reference/cmfccolorpickerctrl-class.md), [CFrameWndEx Klasse](../../mfc/reference/cframewndex-class.md), und [CMFCToolBar Klasse](../../mfc/reference/cmfctoolbar-class.md) Klassen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie eine Farbleiste konfigurieren mithilfe verschiedener Methoden in der `CMFCColorBar` Klasse. Die Methoden legen Sie die horizontale und vertikale Ränder, aktivieren die Schaltfläche "Sonstige", erstellen eine Farbleiste Steuerelementfensters und legt die aktuell ausgewählte Farbe fest. In diesem Beispiel ist Teil der [neues Steuerelement-Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#1](../../mfc/reference/codesnippet/cpp/cmfccolorbar-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#2](../../mfc/reference/codesnippet/cpp/cmfccolorbar-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md)  
  
 [CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcolorbar.h  
  
##  <a name="adjustlocations"></a>  CMFCColorBar::AdjustLocations  
 Passt die Positionen der Farbe Schaltflächen auf der Farbleiste-Steuerelement.  
  
```  
virtual void AdjustLocations();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, durch das Framework während `WM_SIZE` Verarbeitung von Nachrichten.  
  
##  <a name="allowchangetextlabels"></a>  CMFCColorBar::AllowChangeTextLabels  
 Gibt an, ob die Beschriftung der Color-Schaltflächen geändert werden kann.  
  
```  
virtual BOOL AllowChangeTextLabels() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Immer `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig gibt diese Methode immer `FALSE`, was bedeutet, dass testbezeichnungen kann nicht geändert werden. Überschreiben Sie diese Methode, um die Änderung von Beschriftungen zu aktivieren.  
  
##  <a name="allowshowonlist"></a>  CMFCColorBar::AllowShowOnList  
 Gibt an, ob das Steuerelementobjekt Farbleiste während Anpassungsvorgangs in eine Symbolleistenliste angezeigt werden kann.  
  
```  
virtual BOOL AllowShowOnList() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Immer `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig gibt diese Methode immer `TRUE`, was bedeutet, dass das Framework, kann die Farbleiste Steuerelement während des Anpassungsvorgangs angezeigt. Überschreiben Sie diese Methode, um ein anderes Verhalten zu implementieren.  
  
##  <a name="calcsize"></a>  CMFCColorBar::CalcSize  
 Vom Framework als Teil der Berechnungsprozess Layout aufgerufen.  
  
```  
virtual CSize CalcSize(BOOL bVertDock);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bVertDock`  
 `TRUE` um anzugeben, dass die Farbleiste Steuerelement vertikal angedockt ist; `FALSE` um anzugeben, dass die Farbleiste Steuerelement horizontal angedockt ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Größe des Arrays mit Farbe Schaltflächen in einem Steuerelement Farbleiste.  
  
##  <a name="cmfccolorbar"></a>  CMFCColorBar::CMFCColorBar  
 Erstellt ein `CMFCColorBar`-Objekt.  
  
```  
CMFCColorBar(
    const CArray<COLORREF,COLORREF>& colors,  
    COLORREF color,  
    LPCTSTR lpszAutoColor,  
    LPCTSTR lpszOtherColor,  
    LPCTSTR lpszDocColors,  
    CList<COLORREF,COLORREF>& lstDocColors,  
    int nColumns,  
    int nRowsDockHorz,  
    int nColDockVert,  
    COLORREF colorAutomatic,  
    UINT nCommandID,  
    CMFCColorButton* pParentBtn);

 
CMFCColorBar(
    const CArray<COLORREF,COLORREF>& colors,  
    COLORREF color,  
    LPCTSTR lpszAutoColor,  
    LPCTSTR lpszOtherColor,  
    LPCTSTR lpszDocColors,  
    CList<COLORREF,COLORREF>& lstDocColors,  
    int nColumns,  
    COLORREF colorAutomatic,  
    UINT nCommandID,  
    CMFCRibbonColorButton* pParentRibbonBtn);

 
CMFCColorBar(
    CMFCColorBar& src,  
    UINT uiCommandID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `colors`  
 Ein Array von Farben aus, denen vom Framework für das Steuerelement der Farbleiste angezeigt wird.  
  
 [in] `color`  
 Die anfänglich ausgewählte Farbe.  
  
 [in] `lpszAutoColor`  
 Die Beschriftung für die *automatische* farbenschaltfläche (Standard), oder `NULL`.  
  
 Die standardmäßige Bezeichnung für die Schaltfläche "automatisch" ist **automatische**.  
  
 [in] `lpszOtherColor`  
 Die Beschriftung für die *andere* Schaltfläche, die weitere Farben angezeigt wird, oder `NULL`.  
  
 Der standard als Bezeichnung für die Schaltfläche "Sonstige" **Weitere Farben...** .  
  
 [in] `lpszDocColors`  
 Die Beschriftung der Schaltfläche Dokument Farben. Die Dokument-Farben-Palette Listet alle Farben, die das Dokument derzeit verwendet.  
  
 [in] `lstDocColors`  
 Eine Liste von Farben, die das Dokument derzeit verwendet.  
  
 [in] `nColumns`  
 Die Anzahl der Spalten, die das Array von Farben aufweist.  
  
 [in] `nRowsDockHorz`  
 Die Anzahl der Zeilen, die die Farbleiste hat, wenn er horizontal angedockt ist.  
  
 [in] `nColDockVert`  
 Die Anzahl der Spalten, die die Farbleiste hat, wenn es vertikal angedockt ist.  
  
 [in] `colorAutomatic`  
 Die Standardfarbe, die das Framework gilt, wenn Sie auf die Schaltfläche "Automatische" klicken.  
  
 [in] `nCommandID`  
 Die Farbleiste steuerungsbefehls-ID.  
  
 [in] `pParentBtn`  
 Ein Zeiger auf eine übergeordnete Schaltfläche.  
  
 [in] `src`  
 Eine vorhandene `CMFCColorBar` -Objekt, in das neue kopiert werden `CMFCColorBar` Objekt.  
  
 [in] `uiCommandID`  
 Die Befehls-ID.  
  
##  <a name="contexttosize"></a>  CMFCColorBar::ContextToSize  
 Berechnet die horizontale und vertikale Ränder, die sind erforderlich, um die Schaltflächen auf der Farbleiste Steuerelement enthalten, und passt die Position über diese Schaltflächen an.  
  
```  
void ContextToSize(
    BOOL bSquareButtons = TRUE,   
    BOOL bCenterButtons = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `bSquareButtons`|`TRUE` um anzugeben, dass die Form der Schaltflächen auf ein Steuerelement Farbleiste sind quadratische; andernfalls `FALSE`. Der Standardwert ist `TRUE`.|  
|[in] `bCenterButtons`|`TRUE` um anzugeben, dass der Inhalt in einer Farbleiste Schaltflächensteuerelement zentriert; andernfalls `FALSE`. Der Standardwert ist `TRUE`.|  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="create"></a>  CMFCColorBar::Create  
 Erstellt eine Farbleiste Steuerelementfensters und fügt es der `CMFCColorBar` Objekt.  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle,  
    UINT nID,  
    CPalette* pPalette=NULL,  
    int nColumns=0,  
    int nRowsDockHorz=0,  
    int nColDockVert=0);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pParentWnd`  
 Ein Zeiger auf das übergeordnete Fenster.  
  
 [in] `dwStyle`  
 Eine bitweise Kombination (OR) [Fensterstile](../../mfc/reference/styles-used-by-mfc.md#window-styles).  
  
 [in] `nID`  
 Die Befehls-ID.  
  
 [in] `pPalette`  
 Ein Zeiger auf eine Palette von Farben. Die Standardeinstellung ist `NULL`.  
  
 [in] `nColumns`  
 Die Anzahl der Spalten im Steuerelement Farbleiste. Der Standard ist 0.  
  
 [in] `nRowsDockHorz`  
 Die Anzahl der Zeilen in der Farbleiste steuern, wann er horizontal angedockt ist. Der Standard ist 0.  
  
 [in] `nColDockVert`  
 Die Anzahl der Spalten in der Farbleiste steuern, wann es vertikal angedockt ist. Der Standard ist 0.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn diese Methode erfolgreich ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 So erstellen Sie eine `CMFCColorBar` Objekt, das dem Klassenkonstruktor Aufrufen dieser Methode. Die `Create` Methode des Steuerelements in Windows erstellt und initialisiert eine Liste von Farben.  
  
##  <a name="createcontrol"></a>  CMFCColorBar::CreateControl  
 Erstellt eine Farbleiste Steuerelementfensters, fügt es der `CMFCColorBar` Objekt, und ändert das Steuerelementfenster, um der Palette angegebenen Farben enthalten.  
  
```  
virtual BOOL CreateControl(
    CWnd* pParentWnd,  
    const CRect& rect,  
    UINT nID,  
    int nColumns=-1,  
    CPalette* pPalette=NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pParentWnd`  
 Ein Zeiger auf das übergeordnete Fenster. Nicht mit `NULL`.  
  
 [in] `rect`  
 Ein umschließendes Rechteck, das angibt, wo die Farbleiste Steuerelement gezeichnet werden soll.  
  
 [in] `nID`  
 Die Steuerelement-ID.  
  
 [in] `nColumns`  
 Die ideale Anzahl von Spalten im Steuerelement Farbleiste. Diese Methode ändert die Anzahl die Palette angegebene Farben anpassen. Der Standardwert ist-1 und bedeutet, dass dieser Parameter nicht angegeben wird.  
  
 [in] `pPalette`  
 Zeiger auf eine Palette von Farben, oder `NULL`. Wenn dieser Parameter ist `NULL`, diese Methode berechnet die Größe des Steuerelements Farbleiste an, wie wenn 20 Farben angegeben wurden. Die Standardeinstellung ist `NULL`.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn diese Methode erfolgreich ist. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode verwendet die `rect`, `nColumns`, und `pPalette` Parameter zum Berechnen der erforderlichen Anzahl oder Zeilen und Spalten in der Farbleiste-Steuerelement, und ruft dann die [CMFCColorBar::Create](#create) Methode.  
  
##  <a name="createpalette"></a>  CMFCColorBar::CreatePalette  
 Initialisiert eine Palette mit Farben in einem angegebenen Array von Farben an.  
  
```  
static BOOL CreatePalette(
    const CArray<COLORREF, COLORREF>& arColors,   
    CPalette& palette);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `arColors`|Ein Array von Farben.|  
|[in] `palette`|Eine Palette von Farben.|  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn diese Methode erfolgreich ist; andernfalls `FALSE`.  
  
##  <a name="enableautomaticbutton"></a>  CMFCColorBar::EnableAutomaticButton  
 Anzeigen oder Ausblenden der Schaltfläche "Automatische".  
  
```  
void EnableAutomaticButton(
    LPCTSTR lpszLabel,  
    COLORREF colorAutomatic,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszLabel`  
 Die Beschriftung für die *automatische* farbenschaltfläche (Standard), oder `NULL`.  
  
 Die standardmäßige Bezeichnung für die Schaltfläche "automatisch" ist **automatische**.  
  
 [in] `colorAutomatic`  
 Die Standardfarbe, die das Framework gilt, wenn Sie auf die Schaltfläche "Automatische" klicken.  
  
 [in] `bEnable`  
 `TRUE` So aktivieren Sie die Schaltfläche "Automatische"; `FALSE` auf die Schaltfläche "Automatische" zu deaktivieren. Der Standardwert ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
 Die Beschriftung für die Schaltfläche "automatisch" wird gelöscht, wenn die `lpszLabel` Parameter ist `NULL` oder `bEnable` Parameter ist `FALSE`.  
  
##  <a name="enableotherbutton"></a>  CMFCColorBar::EnableOtherButton  
 Aktiviert oder deaktiviert die Anzeige eines Dialogfelds, in dem den Benutzer weitere Farben auswählen können.  
  
```  
void EnableOtherButton(
    LPCTSTR lpszLabel,  
    BOOL bAltColorDlg=TRUE,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszLabel`  
 Die Beschriftung für die *andere* Schaltfläche, die weitere Farben angezeigt wird, oder `NULL`.  
  
 Die standardmäßige Bezeichnung für diese Schaltfläche ist **Weitere Farben...** .  
  
 [in] `bAltColorDlg`  
 `TRUE` zum Anzeigen der [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) Dialogfeld; `FALSE` zum Anzeigen des Standards [CColorDialog](../../mfc/reference/ccolordialog-class.md) (Dialogfeld). Der Standardwert ist `TRUE`.  
  
 [in] `bEnable`  
 `TRUE` So aktivieren Sie die Schaltfläche ""; `FALSE` auf die Schaltfläche deaktiviert. Der Standardwert ist `TRUE`.  
  
##  <a name="getcolor"></a>  CMFCColorBar::GetColor  
 Ruft die zurzeit ausgewählte Farbe ab.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die zurzeit ausgewählte Farbe.  
  
##  <a name="getcolorgridsize"></a>  CMFCColorBar::GetColorGridSize  
 Berechnet die Anzahl der Zeilen und Spalten des Rasters eines Steuerelements Farbleiste an.  
  
```  
CSize GetColorGridSize(BOOL bVertDock) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `bVertDock`|`TRUE` die Berechnung für ein Steuerelement vertikal angedockten Farbleiste ausführen; Führen Sie andernfalls die Berechnung für ein Steuerelement horizontal angedockt.|  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CSize](../../atl-mfc-shared/reference/csize-class.md) Objekt, dessen `cx` Komponente enthält die Anzahl der Spalten und deren `cy` Komponente enthält die Anzahl der Zeilen.  
  
##  <a name="getcommandid"></a>  CMFCColorBar::GetCommandID  
 Ruft die Befehls-ID des aktuellen Farbleiste-Steuerelements ab.  
  
```  
UINT GetCommandID() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Befehls-ID.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Benutzer eine neue Farbe auswählt, sendet das Framework die Befehls-ID in einem `WM_COMMAND` Nachricht an das übergeordnete Element des benachrichtigen der `CMFCColorBar` Objekt.  
  
##  <a name="getextraheight"></a>  CMFCColorBar::GetExtraHeight  
 Berechnet die zusätzliche Höhe, die der aktuellen Farbleiste erfordert verschiedene Elemente einer Benutzeroberfläche angezeigt, wie z. B. die **andere** Schaltfläche oder das Dokument Farben.  
  
```  
int GetExtraHeight(int nNumColumns) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `nNumColumns`|Wenn das Steuerelement Farbleiste Dokumentfarben, die Anzahl der Spalten im Raster des Dokumentfarben anzeigen enthält. Andernfalls wird dieser Wert nicht verwendet.|  
  
### <a name="return-value"></a>Rückgabewert  
 Die berechnete Höhe zusätzliche, die erforderlich ist.  
  
##  <a name="gethighlightedcolor"></a>  CMFCColorBar::GetHighlightedColor  
 Ruft die Farbe, der anzeigt, dass eine farbenschaltfläche im Fokus ist, ab. die Schaltfläche ist *hot*.  
  
```  
COLORREF GetHighlightedColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 RGB-Wert.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="gethorzmargin"></a>  CMFCColorBar::GetHorzMargin  
 Ruft den horizontalen Rand die Fläche zwischen links oder rechts Farbe Zelle und die Grenze der Client-Bereich ist ab.  
  
```  
int GetHorzMargin();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der horizontale Rand.  
  
##  <a name="getvertmargin"></a>  CMFCColorBar::GetVertMargin  
 Ruft den vertikalen Rand der Abstand zwischen dem oberen oder unteren Farbe Zelle und die Grenze der Client-Bereich wird ab.  
  
```  
int GetVertMargin() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der vertikale Rand.  
  
##  <a name="initcolors"></a>  CMFCColorBar::InitColors  
 Initialisiert ein Array von Farben in einer Palette angegebenen Farben oder mit der Standardpalette System an.  
  
```  
static int InitColors(
    CPalette* pPalette,   
    CArray<COLORREF, COLORREF>& arColors);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `pPalette`|Ein Zeiger auf ein Palettenobjekt oder `NULL`. Wenn dieser Parameter ist `NULL`, diese Methode verwendet die Standardpalette des Betriebssystems.|  
|[in] `arColors`|Ein Array von Farben.|  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente im Array der Farben.  
  
##  <a name="istearoff"></a>  CMFCColorBar::IsTearOff  
 Gibt an, ob der aktuelle Farbleiste angedockt werden kann.  
  
```  
BOOL IsTearOff() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn das aktuelle Farbleiste Steuerelement angedockt werden kann; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Farbleiste Steuerelement angedockt werden kann, können Sie unterbrochener deaktiviert eine Steuerleiste und an eine andere Position angedockt werden.  
  
##  <a name="onkey"></a>  CMFCColorBar::OnKey  
 Wird vom Framework aufgerufen, wenn ein Benutzer eine Taste drückt.  
  
```  
virtual BOOL OnKey(UINT nChar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nChar`  
 Der virtuelle Taste Code für den Schlüssel, den ein Benutzer gedrückt.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn diese Methode mit den angegebenen Schlüssel verarbeitet andernfalls `FALSE`.  
  
##  <a name="onsendcommand"></a>  CMFCColorBar::OnSendCommand  
 Vom Framework aufgerufen wird, schließen Sie eine Hierarchie von Popup-Steuerelemente.  
  
```  
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `pButton`|Ein Zeiger auf ein Steuerelement, das auf einer Symbolleiste befindet.|  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn diese Methode erfolgreich ist; andernfalls `FALSE`.  
  
##  <a name="onupdatecmdui"></a>  CMFCColorBar::OnUpdateCmdUI  
 Wird aufgerufen, durch das Framework zu aktivieren oder deaktivieren ein Element der Benutzeroberfläche eines Steuerelements Farbleiste aus, bevor das Element angezeigt wird.  
  
```  
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,  
    BOOL bDisableIfNoHndler);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pTarget`  
 Ein Zeiger auf ein Fenster, das ein Element der Benutzeroberfläche aktualisiert enthält.  
  
 [in] `bDisableIfNoHndler`  
 `TRUE` in einer meldungszuordnung werden zum Deaktivieren von Benutzeroberflächen-Elements, wenn kein Handler definiert. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Klickt ein Benutzer der Anwendung ein Element der Benutzeroberfläche, muss das Element wissen, ob er als aktiviert angezeigt werden soll oder deaktiviert. Das Ziel der Befehlsnachricht stellt diese Informationen durch die Implementierung einer `ON_UPDATE_COMMAND_UI` Befehlshandler. Verwenden Sie diese Methode, um die Verarbeitung des Befehls. Weitere Informationen finden Sie unter [CCmdUI-Klasse](../../mfc/reference/ccmdui-class.md).  
  
##  <a name="opencolordialog"></a>  CMFCColorBar::OpenColorDialog  
 Öffnet das Dialogfeld Farbe an.  
  
```  
virtual BOOL OpenColorDialog(
    const COLORREF colorDefault,  
    COLORREF& colorRes);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `colorDefault`  
 Die Farbe, die standardmäßig ausgewählt ist, wenn das Dialogfeld "Farbe" geöffnet wird.  
  
 [out] `colorRes`  
 Die Farbe, die ein Benutzer ausgewählt.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Benutzer eine Farbe; ausgewählt. `FALSE` , wenn der Benutzer das Dialogfeld "Farbe" abgebrochen.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="rebuild"></a>  CMFCColorBar::Rebuild  
 Vollständig zeichnet die Farbleiste-Steuerelement.  
  
```  
virtual void Rebuild();
```  
  
##  <a name="selectpalette"></a>  CMFCColorBar::SelectPalette  
 Legt die logische Palette von den angegebenen Gerätekontext auf der Palette der Schaltfläche übergeordnete Element des aktuellen Farbleiste-Steuerelements fest.  
  
```  
CPalette* SelectPalette(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `pDC`|Ein Zeiger auf den Gerätekontext, der übergeordneten Schaltfläche des aktuellen Farbleiste-Steuerelements.|  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf der Palette, die durch die Palette der übergeordneten Schaltfläche des aktuellen Steuerelements Farbleiste ersetzt wird.  
  
##  <a name="setcolor"></a>  CMFCColorBar::SetColor  
 Legt die Farbe, die derzeit ausgewählt ist.  
  
```  
void SetColor(COLORREF color);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `color`  
 Ein Wert für den RGB-Farbe.  
  
##  <a name="setcolorname"></a>  CMFCColorBar::SetColorName  
 Legt einen neuen Namen für eine angegebene Farbe fest.  
  
```  
static void SetColorName(
    COLORREF color,  
    const CString& strName);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `color`  
 Die RGB-Wertes einer Farbe.  
  
 [in] `strName`  
 Der neue Name für die angegebene Farbe.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ändert den Namen der angegebenen Farbe in allen `CMFCColorBar` Objekte in der Anwendung.  
  
##  <a name="setcommandid"></a>  CMFCColorBar::SetCommandID  
 Legt eine neue Befehls-ID für ein Steuerelement Farbleiste an.  
  
```  
void SetCommandID(UINT nCommandID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nCommandID`  
 Eine Befehls-ID.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die Befehls-ID eines Steuerelements Farbleiste zu ändern und das übergeordnete Fenster eines Steuerelements zu benachrichtigen, dass die ID geändert wurde.  
  
##  <a name="setdocumentcolors"></a>  CMFCColorBar::SetDocumentColors  
 Legt die Liste der Farben, mit denen im aktuellen Dokument fest.  
  
```  
void SetDocumentColors(
    LPCTSTR lpszCaption,  
    CList<COLORREF,COLORREF>& lstDocColors,  
    BOOL bShowWhenDocked=FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszCaption`  
 Eine Beschriftung, die angezeigt wird, wenn das Steuerelement Farbleiste nicht angedockt ist.  
  
 [in] `lstDocColors`  
 Eine Liste von Farben, die das aktuelle Dokumentfarben ersetzt.  
  
 [in] `bShowWhenDocked`  
 `TRUE` Dokumentfarben angezeigt, wenn das Steuerelement Farbleiste Dockingstation ist; andernfalls `FALSE`. Der Standardwert ist `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 *Dokumentieren Sie Farben* werden die Farben, die derzeit in einem Dokument verwendet werden. Das Framework automatisch verwaltet eine Liste mit Dokumentfarben, aber Sie können diese Methode verwenden, um die Liste zu ändern.  
  
##  <a name="sethorzmargin"></a>  CMFCColorBar::SetHorzMargin  
 Legt den horizontalen Rand der Abstand zwischen der linken oder rechten Farbe Zelle und die Grenze des Clientbereichs wird fest.  
  
```  
void SetHorzMargin(int nHorzMargin);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nHorzMargin`  
 Der horizontale Rand in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Wird standardmäßig die [CMFCColorBar::CMFCColorBar](#cmfccolorbar) Konstruktor legt den horizontalen Rand auf 4 Pixel.  
  
##  <a name="setproplist"></a>  CMFCColorBar::SetPropList  
 Legt die `m_pWndPropList` geschützt Datenmember des angegebenen Zeigers auf ein Eigenschaftenraster-Steuerelement.  
  
```  
void SetPropList(CMFCPropertyGridCtrl* pWndList);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `pWndList`|Zeiger auf Property Grid-Steuerelement-Objekt.|  
  
##  <a name="setvertmargin"></a>  CMFCColorBar::SetVertMargin  
 Legt den vertikalen Rand, der den Abstand zwischen der obersten oder untersten Zelle Farbe und die Client-Bereich-Grenze ist.  
  
```  
void SetVertMargin(int nVertMargin);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nVertMargin`  
 Der vertikale Rand in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Wird standardmäßig die [CMFCColorBar::CMFCColorBar](#cmfccolorbar) Konstruktor legt den vertikalen Rand auf 4 Pixel.  
  
##  <a name="showcommandmessagestring"></a>  CMFCColorBar::ShowCommandMessageString  
 Fordert das Rahmenfenster, das die Farbleiste Steuerelement zum Aktualisieren der Nachricht Position in der Statusleiste besitzt.  
  
```  
virtual void ShowCommandMessageString(UINT uiCmdId);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmdId`  
 Eine Befehls-ID. (Dieser Parameter wird ignoriert).  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die `WM_SETMESSAGESTRING` Nachricht an den Besitzer des Steuerelements Farbleiste.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)
