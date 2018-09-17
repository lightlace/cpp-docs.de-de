---
title: CMFCColorBar-Klasse | Microsoft-Dokumentation
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
ms.openlocfilehash: 5610cd7f5c861fb8f82364e8f1d4d6975a18d7b7
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45717976"
---
# <a name="cmfccolorbar-class"></a>CMFCColorBar-Klasse
Die `CMFCColorBar` -Klasse stellt eine andockbare Steuerleiste, die Farben in einem Dokument oder die Anwendung auswählen können.  
  
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
|[CMFCColorBar::ContextToSize](#contexttosize)|Berechnet die vertikale und horizontale Ränder, die sind erforderlich, um die Schaltflächen auf der Farbleiste-Steuerelement enthalten, und klicken Sie dann die Position dieser Schaltflächen angepasst.|  
|[CMFCColorBar::CreateControl](#createcontrol)|Erstellt ein Fenster der Farbleiste-Steuerelement, fügt es der `CMFCColorBar` Objekt aus, und ändert die Größe des Steuerelements, um der Palette angegebenen Farben enthalten.|  
|[CMFCColorBar::Create](#create)|Erstellt ein Fenster der Farbleiste-Steuerelement, und fügt es der `CMFCColorBar` Objekt.|  
|[CMFCColorBar::EnableAutomaticButton](#enableautomaticbutton)|Anzeigen oder ausblenden die automatische Schaltfläche.|  
|[CMFCColorBar::EnableOtherButton](#enableotherbutton)|Aktiviert oder deaktiviert die Anzeige eines Dialogfelds, in dem den Benutzer weitere Farben auswählen können.|  
|[CMFCColorBar::GetColor](#getcolor)|Ruft ab, die zurzeit ausgewählte Farbe.|  
|[CMFCColorBar::GetCommandID](#getcommandid)|Ruft die Befehls-ID des aktuellen Farbleiste-Steuerelements ab.|  
|[CMFCColorBar::GetHighlightedColor](#gethighlightedcolor)|Ruft die Farbe, die gibt an, dass eine Schaltfläche "Farbe" den Fokus besitzt; die Schaltfläche wird *"Hot"*.|  
|[CMFCColorBar::GetHorzMargin](#gethorzmargin)|Ruft den horizontalen Rand, der den Abstand zwischen der linken Seite oder rechte Farbe Zelle und die Client-Bereich-Grenze ist ab.|  
|[CMFCColorBar::GetVertMargin](#getvertmargin)|Ruft den vertikalen Rand wird der Abstand zwischen dem oberen oder unteren Rand der Zelle "Color" und die Client-Bereich-Grenze ab.|  
|[CMFCColorBar::IsTearOff](#istearoff)|Gibt an, ob der aktuelle Farbleiste angedockt werden kann.|  
|[CMFCColorBar::SetColor](#setcolor)|Legt die Farbe, die derzeit ausgewählt ist.|  
|[CMFCColorBar::SetColorName](#setcolorname)|Legt einen neuen Namen für eine angegebene Farbe fest.|  
|[CMFCColorBar::SetCommandID](#setcommandid)|Legt eine neue Befehls-ID für ein Steuerelement der Farbleiste an.|  
|[CMFCColorBar::SetDocumentColors](#setdocumentcolors)|Legt die Liste der Farben, die verwendet werden, in das aktuelle Dokument fest.|  
|[CMFCColorBar::SetHorzMargin](#sethorzmargin)|Legt den horizontalen Rand, der den Abstand zwischen der linken Seite oder rechte Farbe Zelle und die Client-Bereich-Grenze ist fest.|  
|[CMFCColorBar::SetVertMargin](#setvertmargin)|Legt den vertikalen Rand, der den Abstand zwischen der obersten oder untersten Zelle Farbe und die Client-Bereich-Grenze ist fest.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCColorBar::AdjustLocations](#adjustlocations)|Passt die Positionen der Farbe Schaltflächen auf der Farbleiste-Steuerelement.|  
|[CMFCColorBar::AllowChangeTextLabels](#allowchangetextlabels)|Gibt an, ob die textbezeichnung des Color-Schaltflächen geändert werden kann.|  
|[CMFCColorBar::AllowShowOnList](#allowshowonlist)|Gibt an, ob das Steuerelementobjekt Farbleiste während des Anpassungsvorgangs in der Liste eine Symbolleiste angezeigt werden kann.|  
|[CMFCColorBar::CalcSize](#calcsize)|Wird aufgerufen, durch das Framework als Teil der Berechnungsprozess Layout.|  
|[CMFCColorBar::CreatePalette](#createpalette)|Initialisiert eine Palette mit den Farben in einem angegebenen Array von Farben.|  
|[CMFCColorBar::GetColorGridSize](#getcolorgridsize)|Berechnet die Anzahl von Zeilen und Spalten im Raster eine Farbleiste-Steuerelements.|  
|[CMFCColorBar::GetExtraHeight](#getextraheight)|Berechnet die zusätzliche Höhe, die der aktuellen Farbleiste erfordert verschiedene Elemente der Benutzeroberfläche angezeigt, wie z. B. die **andere** Schaltfläche Dokumentfarben und So weiter.|  
|[CMFCColorBar::InitColors](#initcolors)|Initialisiert ein Array von Farben mit den Farben in einer angegebenen Palette oder der System-Standardpalette an.|  
|[CMFCColorBar::OnKey](#onkey)|Wird von Framework aufgerufen, wenn ein Benutzer eine Taste drückt.|  
|[CMFCColorBar::OnSendCommand](#onsendcommand)|Wird aufgerufen, durch das Framework, um eine Hierarchie von Popup-Steuerelementen zu schließen.|  
|[CMFCColorBar::OnUpdateCmdUI](#onupdatecmdui)|Wird aufgerufen, durch das Framework zu aktivieren oder deaktivieren ein Element der Benutzeroberfläche eines Steuerelements Farbleiste aus, bevor das Element angezeigt wird.|  
|[CMFCColorBar::OpenColorDialog](#opencolordialog)|Öffnet das Dialogfeld Farbe an.|  
|[CMFCColorBar::Rebuild](#rebuild)|Vollständig zeichnet das Steuerelement der Farbleiste.|  
|[CMFCColorBar::SelectPalette](#selectpalette)|Legt die logische Palette von den angegebenen Gerätekontext auf der Palette der Schaltfläche übergeordnete Element des aktuellen Farbleiste-Steuerelements fest.|  
|[CMFCColorBar::SetPropList](#setproplist)|Legt die `m_pWndPropList` geschützte Datenmember, des angegebenen Zeigers auf ein Eigenschaftenraster-Steuerelement.|  
|[CMFCColorBar::ShowCommandMessageString](#showcommandmessagestring)|Fordert das Rahmenfenster, das Besitzer das Farbleiste-Steuerelement ist, um die Nachricht-Zeile in der Statusleiste zu aktualisieren.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|`m_bInternal`|Ein boolesches Feld, das bestimmt, ob die Mausereignisse verarbeitet werden. Mausereignisse werden in der Regel verarbeitet, wenn dieses Feld "true ist" und Anpassungsmodus "false ist".|  
|`m_bIsEnabled`|Ein boolescher Wert, der angibt, ob ein Steuerelement aktiviert ist.|  
|`m_bIsTearOff`|Ein boolescher Wert, der angibt, ob das Steuerelement für die Farbleiste Andocken unterstützt.|  
|`m_BoxSize`|Ein [CSize](../../atl-mfc-shared/reference/csize-class.md) -Objekt, das die Größe einer Zelle in einem Raster Farbleiste angibt.|  
|`m_bShowDocColorsWhenDocked`|Ein boolescher Wert, der angibt, ob Dokumentfarben angezeigt, wenn der Farbleiste angedockt wird. Weitere Informationen finden Sie unter [CMFCColorBar::SetDocumentColors](#setdocumentcolors).|  
|`m_bStdColorDlg`|Ein boolescher Wert, der angibt, ob das Dialogfeld Farbe standardsystembenachrichtigung angezeigt oder [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) Dialogfeld. Weitere Informationen finden Sie unter [CMFCColorBar::EnableOtherButton](#enableotherbutton).|  
|`m_ColorAutomatic`|Ein [COLORREF](/windows/desktop/gdi/colorref) , speichert die aktuelle Farbe. Weitere Informationen finden Sie unter [CMFCColorBar::EnableOtherButton](#enableotherbutton).|  
|`m_ColorNames`|Ein [CMap](../../mfc/reference/cmap-class.md) -Objekt, das ordnet einen Satz von RGB-Farben, mit ihren Namen.|  
|`m_colors`|Ein [CArray](../../mfc/reference/carray-class.md) von [COLORREF](/windows/desktop/gdi/colorref) Werte, die die Farben enthält, die im Steuerelement Farbleiste angezeigt werden.|  
|`m_ColorSelected`|Ein [COLORREF](/windows/desktop/gdi/colorref) Wert, der die Farbe, die der Benutzer gerade aus dem Steuerelement Farbleiste ausgewählt hat.|  
|`m_lstDocColors`|Ein [CList](../../mfc/reference/clist-class.md) von [COLORREF](/windows/desktop/gdi/colorref) Werte, die die Farben enthält, die derzeit in einem Dokument verwendet werden.|  
|`m_nCommandID`|Eine ganze Zahl ohne Vorzeichen, die die Befehls-ID, der eine Schaltfläche "Farbe" ist.|  
|`m_nHorzMargin`|Eine ganze Zahl, die der horizontalen Rand zwischen den Schaltflächen Farbe in einem Raster von Farben ist.|  
|`m_nHorzOffset`|Eine ganze Zahl, die den horizontalen Offset in die Mitte der Schaltfläche für die Farbe ist. Dieser Wert ist wichtig, wenn die Schaltfläche Text oder ein Bild zusätzlich zu einer Farbe angezeigt.|  
|`m_nNumColumns`|Eine ganze Zahl, der die Anzahl der Spalten in einem Raster: Steuerelement Farbleiste Farben.|  
|`m_nNumColumnsVert`|Eine ganze Zahl, die die Anzahl der Spalten in einem vertikal ausgerichteten Raster von Farben ist.|  
|`m_nNumRowsHorz`|Eine ganze Zahl, die die Anzahl der Spalten in einem horizontal ausgerichteten Raster von Farben ist.|  
|`m_nRowHeight`|Eine ganze Zahl, die die Höhe einer Zeile der Farbe von Schaltflächen in einem Raster von Farben ist.|  
|`m_nVertMargin`|Eine ganze Zahl, die den vertikalen Rand zwischen den Schaltflächen Farbe in einem Raster von Farben ist.|  
|`m_nVertOffset`|Eine ganze Zahl, die den vertikalen Offset in die Mitte der Schaltfläche für die Farbe ist. Dieser Wert ist wichtig, wenn die Schaltfläche Text oder ein Bild zusätzlich zu einer Farbe angezeigt.|  
|`m_Palette`|Ein [CPalette](../../mfc/reference/cpalette-class.md) der Farben, die in der Farbleiste-Steuerelement verwendet werden.|  
|`m_pParentBtn`|Ein Zeiger auf eine [CMFCColorButton](../../mfc/reference/cmfccolorbutton-class.md) -Objekt, das das übergeordnete Element der aktuellen Schaltfläche ist. Dieser Wert ist erheblich, wenn die Schaltfläche "Farbe" in einer Hierarchie der Steuerelemente auf der Symbolleiste ist oder im Eigenschaftenraster-Steuerelement eine Farbe.|  
|`m_pParentRibbonBtn`|Ein Zeiger auf eine [CMFCRibbonColorButton](../../mfc/reference/cmfcribboncolorbutton-class.md) -Objekt, das auf dem Menüband und die Schaltfläche "übergeordneten" der aktuellen Schaltfläche. Dieser Wert ist erheblich, wenn die Schaltfläche "Farbe" in einer Hierarchie der Steuerelemente auf der Symbolleiste ist oder im Eigenschaftenraster-Steuerelement eine Farbe.|  
|`m_pWndPropList`|Ein Zeiger auf eine [CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md) Objekt.|  
|`m_strAutoColor`|Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) , der Text, der angezeigt wird der **automatische** Schaltfläche. Weitere Informationen finden Sie unter [CMFCColorBar::EnableAutomaticButton](#enableautomaticbutton).|  
|`m_strDocColors`|Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) , der Text, der auf die Schaltfläche Dokument Farben angezeigt wird. Weitere Informationen finden Sie unter [CMFCColorBar::SetDocumentColors](#setdocumentcolors).|  
|`m_strOtherColor`|Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) , der Text, der angezeigt wird der *andere* Schaltfläche. Weitere Informationen finden Sie unter [CMFCColorBar::EnableOtherButton](#enableotherbutton).|  
  
## <a name="remarks"></a>Hinweise  
 In der Regel erstellen Sie keine `CMFCColorBar` direkt. Stattdessen die [CMFCColorMenuButton-Klasse](../../mfc/reference/cmfccolormenubutton-class.md) (verwendet in den Menüs und Symbolleisten) oder die [CMFCColorButton-Klasse](../../mfc/reference/cmfccolorbutton-class.md) erstellt die `CMFCColorBar` Objekt.  
  
 Die `CMFCColorBar` Klasse bietet folgende Funktionen:  
  
-   Passt automatisch die Liste der Dokumentfarben an.  
  
-   Speichert und stellt den Zustand, zusammen mit den Zustand des Dokuments.  
  
-   Verwaltet die Schaltfläche "Automatische".  
  
-   Verwendet die [CMFCColorPickerCtrl-Klasse](../../mfc/reference/cmfccolorpickerctrl-class.md) Steuerelement, um eine benutzerdefinierte Farbe auszuwählen.  
  
-   Unterstützt einen Status "abtrennbare" (wenn es erstellt wird die [CMFCColorMenuButton-Klasse](../../mfc/reference/cmfccolormenubutton-class.md)).  
  
 Integrieren der `CMFCColorBar` -Funktionen in Ihrer Anwendung:  
  
1.  Erstellen Sie eine normale Menüschaltfläche, und weisen sie eine ID, z. B. ID_CHAR_COLOR.  
  
2.  Überschreiben Sie in Ihr Rahmenfenster (Klasse), die [CFrameWndEx::OnShowPopupMenu](../../mfc/reference/cframewndex-class.md#onshowpopupmenu) -Methode, und ersetzen das reguläre Menü-Schaltfläche mit einer [CMFCColorMenuButton-Klasse](../../mfc/reference/cmfccolormenubutton-class.md) Objekt (durch Aufrufen von [CMFCToolBar: : ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)).  
  
3.  Legen Sie alle Stile an und aktivieren oder deaktivieren Sie die Funktionen von der `CMFCColorBar` -Objekt während [CMFCColorMenuButton-Klasse](../../mfc/reference/cmfccolormenubutton-class.md) erstellen. Die `CMFCColorMenuButton` Objekt dynamisch erstellt die `CMFCColorBar` Objekt nach dem Aufrufen der Framework die `CreatePopupMenu` Methode.  
  
 Klickt der Benutzer eine Schaltfläche der Farbleiste-Steuerelement, das Framework verwendet die `ON_COMMAND` Makro, um das übergeordnete Element des Steuerelements Farbleiste zu benachrichtigen. In das Makro ist der Befehls-ID-Parameter der Wert, den Sie die Schaltfläche der Farbleiste Steuerung in Schritt 1 (in diesem Beispiel ID_CHAR_COLOR) zugewiesen. Weitere Informationen finden Sie unter den [CMFCColorMenuButton-Klasse](../../mfc/reference/cmfccolormenubutton-class.md), [CMFCColorButton-Klasse](../../mfc/reference/cmfccolorbutton-class.md), [CMFCColorPickerCtrl-Klasse](../../mfc/reference/cmfccolorpickerctrl-class.md), [CFrameWndEx-Klasse](../../mfc/reference/cframewndex-class.md), und [CMFCToolBar-Klasse](../../mfc/reference/cmfctoolbar-class.md) Klassen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt eine Farbleiste konfigurieren mithilfe verschiedener Methoden in der `CMFCColorBar` Klasse. Die Methoden legen Sie die horizontale und vertikale Ränder, die andere Schaltfläche "aktivieren", erstellen Sie ein Fenster der Farbleiste-Steuerelement und legt die zurzeit ausgewählte Farbe. In diesem Beispiel ist Teil der [Beispiel neue Steuerelemente](../../visual-cpp-samples.md).  
  
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
 Diese Methode wird vom Framework aufgerufen, während der Verarbeitung der WM_SIZE-Meldung.  
  
##  <a name="allowchangetextlabels"></a>  CMFCColorBar::AllowChangeTextLabels  
 Gibt an, ob die textbezeichnung des Color-Schaltflächen geändert werden kann.  
  
```  
virtual BOOL AllowChangeTextLabels() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Immer "false".  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig gibt diese Methode immer "false", was bedeutet, dass die Beschriftungen nicht geändert werden können. Überschreiben Sie diese Methode zum Ändern von Beschriftungen zu aktivieren.  
  
##  <a name="allowshowonlist"></a>  CMFCColorBar::AllowShowOnList  
 Gibt an, ob das Steuerelementobjekt Farbleiste während des Anpassungsvorgangs in der Liste eine Symbolleiste angezeigt werden kann.  
  
```  
virtual BOOL AllowShowOnList() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Immer "true".  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig gibt diese Methode immer "true", was bedeutet, dass das Framework das Steuerelement für die Farbleiste während des Anpassungsvorgangs angezeigt werden kann. Überschreiben Sie diese Methode, um ein anderes Verhalten zu implementieren.  
  
##  <a name="calcsize"></a>  CMFCColorBar::CalcSize  
 Wird aufgerufen, durch das Framework als Teil der Berechnungsprozess Layout.  
  
```  
virtual CSize CalcSize(BOOL bVertDock);
```  
  
### <a name="parameters"></a>Parameter  
*bVertDock*<br/>
[in] True, um anzugeben, dass das Steuerelement für die Farbleiste vertikal angedockt ist. "False", um anzugeben, dass das Steuerelement für die Farbleiste horizontal angedockt ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Größe des Arrays der Farbe von Schaltflächen in einem Steuerelement der Farbleiste.  
  
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
*Farben*<br/>
[in] Ein Array von Farben, die das Framework für das Steuerelement der Farbleiste angezeigt werden soll.  
  
*Farbe*<br/>
[in] Die anfänglich ausgewählte Farbe.  
  
*lpszAutoColor*<br/>
[in] Die textbezeichnung des der *automatische* farbenschaltfläche (Standard), oder NULL.  
  
 Die standardmäßige Bezeichnung für die automatische Schaltfläche ist **automatische**.  
  
*lpszOtherColor*<br/>
[in] Die textbezeichnung des der *andere* Schaltfläche, welche zeigt weitere Farben, oder NULL.  
  
 Die standardmäßige Bezeichnung für die andere Schaltfläche ist **Weitere Farben...** .  
  
*lpszDocColors*<br/>
[in] Die Beschriftung der Schaltfläche Dokument Farben. Die Farben (Palette) Dokument Listet alle Farben, die das Dokument derzeit verwendet.  
  
*lstDocColors*<br/>
[in] Eine Liste von Farben, die das Dokument derzeit verwendet werden soll.  
  
*nColumns*<br/>
[in] Die Anzahl der Spalten, die das Array von Farben aufweist.  
  
*nRowsDockHorz*<br/>
[in] Die Anzahl der Zeilen, die über der Farbleiste verfügt, wenn er horizontal angedockt ist.  
  
*nColDockVert*<br/>
[in] Die Anzahl der Spalten, die der Farbleiste hat, wenn sie vertikal angedockt wird.  
  
*colorAutomatic*<br/>
[in] Die Standardfarbe, die das Framework gilt, wenn Sie die automatische Schaltfläche klicken.  
  
*nCommandID*<br/>
[in] Der Befehl der Farbleiste-Control-ID.  
  
*pParentBtn*<br/>
[in] Ein Zeiger auf eine Schaltfläche "übergeordneten".  
  
*src*<br/>
[in] Eine vorhandene `CMFCColorBar` Objekt, das in die neue kopiert werden `CMFCColorBar` Objekt.  
  
*uiCommandID*<br/>
[in] Die Befehls-ID.  
  
##  <a name="contexttosize"></a>  CMFCColorBar::ContextToSize  
 Berechnet die horizontale und vertikale Ränder, die sind erforderlich, um die Schaltflächen auf der Farbleiste-Steuerelement enthalten, und passt die Position dieser Schaltflächen an.  
  
```  
void ContextToSize(
    BOOL bSquareButtons = TRUE,   
    BOOL bCenterButtons = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|*bSquareButtons*|[in] True, um anzugeben, dass die Form der Schaltflächen auf einem Steuerelement Farbleiste quadratischen sind. andernfalls "false". Der Standardwert ist "true".|  
|*bCenterButtons*|[in] True, um anzugeben, dass der Inhalt der Rückgabe eine Farbleiste Steuerelement zentriert ist. andernfalls "false". Der Standardwert ist "true".|  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="create"></a>  CMFCColorBar::Create  
 Erstellt ein Fenster der Farbleiste-Steuerelement, und fügt es der `CMFCColorBar` Objekt.  
  
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
*pParentWnd*<br/>
[in] Zeiger auf das übergeordnete Fenster.  
  
*dwStyle*<br/>
[in] Eine bitweise Kombination (OR) von [Window-Stile](../../mfc/reference/styles-used-by-mfc.md#window-styles).  
  
*nID*<br/>
[in] Die Befehls-ID.  
  
*pPalette*<br/>
[in] Zeiger auf eine Palette von Farben. Der Standardwert ist NULL.  
  
*nColumns*<br/>
[in] Die Anzahl der Spalten im Steuerelement Farbleiste. Der Standard ist 0.  
  
*nRowsDockHorz*<br/>
[in] Die Anzahl der Zeilen in der Farbleiste-Steuerelement, wenn er horizontal angedockt ist. Der Standard ist 0.  
  
*nColDockVert*<br/>
[in] Die Anzahl der Spalten in der Farbleiste steuern, wann sie vertikal angedockt wird. Der Standard ist 0.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn diese Methode erfolgreich ist. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Zum Erstellen einer `CMFCColorBar` Objekt, rufen Sie den Klassenkonstruktor wird diese Methode. Die `Create` Methode wird das Windows-Steuerelement erstellt und initialisiert Sie eine Liste mit Farben.  
  
##  <a name="createcontrol"></a>  CMFCColorBar::CreateControl  
 Erstellt ein Fenster der Farbleiste-Steuerelement, fügt es der `CMFCColorBar` Objekt aus, und ändert das Steuerelementfenster, um der Palette angegebenen Farben enthalten.  
  
```  
virtual BOOL CreateControl(
    CWnd* pParentWnd,  
    const CRect& rect,  
    UINT nID,  
    int nColumns=-1,  
    CPalette* pPalette=NULL);
```  
  
### <a name="parameters"></a>Parameter  
*pParentWnd*<br/>
[in] Zeiger auf das übergeordnete Fenster. Darf nicht NULL sein.  
  
*Rect*<br/>
[in] Ein umgebendes Rechteck, das angibt, wo Sie die Farbleiste-Steuerelement zu zeichnen.  
  
*nID*<br/>
[in] Die Steuerelement-ID.  
  
*nColumns*<br/>
[in] Die ideale Anzahl von Spalten im Steuerelement Farbleiste. Diese Methode wird die Anzahl die Palette angegebene Farben entsprechend geändert. Der Standardwert ist-1 und bedeutet, dass dieser Parameter nicht angegeben ist.  
  
*pPalette*<br/>
[in] Zeiger auf eine Palette mit Farben, oder NULL. Wenn dieser Parameter NULL ist, berechnet dieser Methode die Größe des Steuerelements Farbleiste an, wie bei 20 Farben angegeben wurden. Der Standardwert ist NULL.  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn diese Methode erfolgreich ist. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode verwendet die *Rect*, *nColumns*, und *pPalette* Parameter zum Berechnen die entsprechende Anzahl oder Zeilen und Spalten in der Farbleiste-Steuerelement, und ruft dann die [CMFCColorBar::Create](#create) Methode.  
  
##  <a name="createpalette"></a>  CMFCColorBar::CreatePalette  
 Initialisiert eine Palette mit den Farben in einem angegebenen Array von Farben an.  
  
```  
static BOOL CreatePalette(
    const CArray<COLORREF, COLORREF>& arColors,   
    CPalette& palette);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|*arColors*|[in] Ein Array von Farben.|  
|*Palette*|[in] Eine Palette von Farben.|  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn diese Methode erfolgreich ist. andernfalls "false".  
  
##  <a name="enableautomaticbutton"></a>  CMFCColorBar::EnableAutomaticButton  
 Anzeigen oder ausblenden die automatische Schaltfläche.  
  
```  
void EnableAutomaticButton(
    LPCTSTR lpszLabel,  
    COLORREF colorAutomatic,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
*lpszLabel*<br/>
[in] Die textbezeichnung des der *automatische* farbenschaltfläche (Standard), oder NULL.  
  
 Die standardmäßige Bezeichnung für die automatische Schaltfläche ist **automatische**.  
  
*colorAutomatic*<br/>
[in] Die Standardfarbe, die das Framework gilt, wenn Sie die automatische Schaltfläche klicken.  
  
*bAktivieren*<br/>
[in] True, um die automatische Schaltfläche zu aktivieren. "False", um die automatische Schaltfläche zu deaktivieren. Der Standardwert ist "true".  
  
### <a name="remarks"></a>Hinweise  
 Die textbezeichnung des "automatisch" wird gelöscht, wenn die *LpszLabel* Parameter NULL ist oder die *bAktivieren* Parameter ist "false".  
  
##  <a name="enableotherbutton"></a>  CMFCColorBar::EnableOtherButton  
 Aktiviert oder deaktiviert die Anzeige eines Dialogfelds, in dem den Benutzer weitere Farben auswählen können.  
  
```  
void EnableOtherButton(
    LPCTSTR lpszLabel,  
    BOOL bAltColorDlg=TRUE,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
*lpszLabel*<br/>
[in] Die textbezeichnung des der *andere* Schaltfläche, welche zeigt weitere Farben, oder NULL.  
  
 Die standardmäßige Bezeichnung für diese Schaltfläche ist **Weitere Farben...** .  
  
*bAltColorDlg*<br/>
[in] "True" Anzeige der [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) Dialogfeld "False" zum Anzeigen des Standards [CColorDialog](../../mfc/reference/ccolordialog-class.md) Dialogfeld. Der Standardwert ist "true".  
  
*bAktivieren*<br/>
[in] True, um die Schaltfläche zu aktivieren. FALSE, wenn die Schaltfläche zu deaktivieren. Der Standardwert ist "true".  
  
##  <a name="getcolor"></a>  CMFCColorBar::GetColor  
 Ruft ab, die zurzeit ausgewählte Farbe.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die zurzeit ausgewählte Farbe.  
  
##  <a name="getcolorgridsize"></a>  CMFCColorBar::GetColorGridSize  
 Berechnet die Anzahl von Zeilen und Spalten im Raster eine Farbleiste-Steuerelements.  
  
```  
CSize GetColorGridSize(BOOL bVertDock) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|*bVertDock*|[in] "True" zum Durchführen der Berechnung für ein Steuerelement vertikal angedockten Farbleiste; Andernfalls führen Sie die Berechnung für ein Steuerelement horizontal angedockt.|  
  
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
 Wenn der Benutzer eine neue Farbe auswählt, sendet das Framework die Befehls-ID in einer WM_COMMAND-Meldung benachrichtigt das übergeordnete Element der `CMFCColorBar` Objekt.  
  
##  <a name="getextraheight"></a>  CMFCColorBar::GetExtraHeight  
 Berechnet die zusätzliche Höhe, die der aktuellen Farbleiste angezeigt verschiedene Elemente der Benutzeroberfläche, wie z. B. erfordert die **andere** Schaltfläche oder ein Dokument Farben.  
  
```  
int GetExtraHeight(int nNumColumns) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|*nNumColumns*|[in] Wenn das Steuerelement für die Farbleiste Dokumentfarben, die Anzahl der Spalten im Raster des Dokumentfarben angezeigt werden sollen enthält. Andernfalls wird dieser Wert nicht verwendet werden.|  
  
### <a name="return-value"></a>Rückgabewert  
 Die berechnete Höhe zusätzliche, die erforderlich ist.  
  
##  <a name="gethighlightedcolor"></a>  CMFCColorBar::GetHighlightedColor  
 Ruft die Farbe, die gibt an, dass eine Schaltfläche "Farbe" den Fokus besitzt; die Schaltfläche wird *"Hot"*.  
  
```  
COLORREF GetHighlightedColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein RGB-Wert.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="gethorzmargin"></a>  CMFCColorBar::GetHorzMargin  
 Ruft den horizontalen Rand, der den Abstand zwischen der linken Seite oder rechte Farbe Zelle und die Client-Bereich-Grenze ist ab.  
  
```  
int GetHorzMargin();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der horizontalen Rand.  
  
##  <a name="getvertmargin"></a>  CMFCColorBar::GetVertMargin  
 Ruft den vertikalen Rand wird der Abstand zwischen dem oberen oder unteren Rand der Zelle "Color" und die Client-Bereich-Grenze ab.  
  
```  
int GetVertMargin() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der vertikale Rand.  
  
##  <a name="initcolors"></a>  CMFCColorBar::InitColors  
 Initialisiert ein Array von Farben, die die Farben in einer angegebenen Palette oder mit der Standardpalette System an.  
  
```  
static int InitColors(
    CPalette* pPalette,   
    CArray<COLORREF, COLORREF>& arColors);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|*pPalette*|[in] Ein Zeiger auf ein Palettenobjekt, oder NULL. Wenn dieser Parameter NULL ist, verwendet diese Methode die Standardpalette des Betriebssystems.|  
|*arColors*|[in] Ein Array von Farben.|  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente im Array von Farben.  
  
##  <a name="istearoff"></a>  CMFCColorBar::IsTearOff  
 Gibt an, ob der aktuelle Farbleiste angedockt werden kann.  
  
```  
BOOL IsTearOff() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn das aktuelle Farbleiste Steuerelement angedockt werden kann. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Steuerelement für die Farbleiste angedockt werden kann, können Sie vor zerrissenen Seiten, aus einer Steuerleiste und an einem anderen Speicherort angedockt werden.  
  
##  <a name="onkey"></a>  CMFCColorBar::OnKey  
 Wird von Framework aufgerufen, wenn ein Benutzer eine Taste drückt.  
  
```  
virtual BOOL OnKey(UINT nChar);
```  
  
### <a name="parameters"></a>Parameter  
*NChar*<br/>
[in] Der virtuelle Taste Code für den Schlüssel, den ein Benutzer gedrückt.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn diese Methode mit den angegebenen Schlüssel verarbeitet. andernfalls "false".  
  
##  <a name="onsendcommand"></a>  CMFCColorBar::OnSendCommand  
 Wird aufgerufen, durch das Framework, um eine Hierarchie von Popup-Steuerelemente zu schließen.  
  
```  
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|*pButton*|[in] Zeiger auf ein Steuerelement, das auf einer Symbolleiste befindet.|  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn diese Methode erfolgreich ist. andernfalls "false".  
  
##  <a name="onupdatecmdui"></a>  CMFCColorBar::OnUpdateCmdUI  
 Wird aufgerufen, durch das Framework zu aktivieren oder deaktivieren ein Element der Benutzeroberfläche eines Steuerelements Farbleiste aus, bevor das Element angezeigt wird.  
  
```  
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,  
    BOOL bDisableIfNoHndler);
```  
  
### <a name="parameters"></a>Parameter  
*pTarget*<br/>
[in] Zeiger auf ein Fenster, das eine Benutzeroberfläche, zu aktualisierenden Elements enthält.  
  
*bDisableIfNoHndler*<br/>
[in] True, um das Element der Benutzeroberfläche zu deaktivieren, wenn kein Handler in einer meldungszuordnung definiert ist. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Klickt ein Benutzer Ihrer Anwendung ein UI-Element, muss das Element wissen, ob es als aktiviert angezeigt werden soll oder deaktiviert. Das Ziel der Nachricht enthält diese Informationen durch die Implementierung einer ON_UPDATE_COMMAND_UI-Befehlshandler. Verwenden Sie diese Methode, um die Verarbeitung des Befehls. Weitere Informationen finden Sie unter [CCmdUI-Klasse](../../mfc/reference/ccmdui-class.md).  
  
##  <a name="opencolordialog"></a>  CMFCColorBar::OpenColorDialog  
 Öffnet das Dialogfeld Farbe an.  
  
```  
virtual BOOL OpenColorDialog(
    const COLORREF colorDefault,  
    COLORREF& colorRes);
```  
  
### <a name="parameters"></a>Parameter  
*colorDefault*<br/>
[in] Die Farbe, die standardmäßig ausgewählt ist, wenn das Dialogfeld "Farbe" geöffnet wird.  
  
*colorRes*<br/>
[out] Die Farbe, die ein Benutzer ausgewählt.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn der Benutzer eine Farbe ausgewählt. "False", wenn der Benutzer das Dialogfeld "Farbe" abgebrochen.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="rebuild"></a>  CMFCColorBar::Rebuild  
 Vollständig zeichnet das Steuerelement der Farbleiste.  
  
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
|*pDC*|[in] Zeiger auf den Gerätekontext, der Schaltfläche übergeordnete Element des aktuellen Farbleiste-Steuerelements.|  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf der Palette, die durch die Palette der Schaltfläche übergeordnete Element des aktuellen Farbleiste-Steuerelements ersetzt wird.  
  
##  <a name="setcolor"></a>  CMFCColorBar::SetColor  
 Legt die Farbe, die derzeit ausgewählt ist.  
  
```  
void SetColor(COLORREF color);
```  
  
### <a name="parameters"></a>Parameter  
*Farbe*<br/>
[in] Ein RGB-Farbwert.  
  
##  <a name="setcolorname"></a>  CMFCColorBar::SetColorName  
 Legt einen neuen Namen für eine angegebene Farbe fest.  
  
```  
static void SetColorName(
    COLORREF color,  
    const CString& strName);
```  
  
### <a name="parameters"></a>Parameter  
*Farbe*<br/>
[in] Eine Farbe der RGB-Wert.  
  
*strName*<br/>
[in] Der neue Name für die angegebene Farbe.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ändert den Namen der angegebenen Farbe in allen `CMFCColorBar` Objekte in der Anwendung.  
  
##  <a name="setcommandid"></a>  CMFCColorBar::SetCommandID  
 Legt eine neue Befehls-ID für ein Steuerelement der Farbleiste an.  
  
```  
void SetCommandID(UINT nCommandID);
```  
  
### <a name="parameters"></a>Parameter  
*nCommandID*<br/>
[in] Eine Befehls-ID.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode aus, um die Befehls-ID eines Steuerelements Farbleiste ändern und das übergeordnete Fenster des Steuerelements zu benachrichtigen, dass die ID geändert wurde.  
  
##  <a name="setdocumentcolors"></a>  CMFCColorBar::SetDocumentColors  
 Legt die Liste der Farben, die verwendet werden, in das aktuelle Dokument fest.  
  
```  
void SetDocumentColors(
    LPCTSTR lpszCaption,  
    CList<COLORREF,COLORREF>& lstDocColors,  
    BOOL bShowWhenDocked=FALSE);
```  
  
### <a name="parameters"></a>Parameter  
*lpszCaption*<br/>
[in] Eine Beschriftung, die angezeigt wird, wenn das Steuerelement für die Farbleiste nicht angedockt ist.  
  
*lstDocColors*<br/>
[in] Eine Liste von Farben, die die Farben des aktuellen Dokuments ersetzt.  
  
*bShowWhenDocked*<br/>
[in] True, um Dokumentfarben angezeigt werden soll, wenn die Farbleiste Steuerelement angedockt ist. andernfalls "false". Der Standardwert ist "false".  
  
### <a name="remarks"></a>Hinweise  
 *Dokumentieren Sie Farben* sind die Farben, die derzeit in einem Dokument verwendet werden. Das Framework verwaltet automatisch eine Liste der Dokumentfarben, aber Sie können diese Methode verwenden, um die Liste zu ändern.  
  
##  <a name="sethorzmargin"></a>  CMFCColorBar::SetHorzMargin  
 Legt den horizontalen Rand, wird der Abstand zwischen der linken Seite oder rechte Farbe Zelle und die Begrenzung des Clientbereichs fest.  
  
```  
void SetHorzMargin(int nHorzMargin);
```  
  
### <a name="parameters"></a>Parameter  
*nHorzMargin*<br/>
[in] Der horizontalen Rand in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 In der Standardeinstellung die [CMFCColorBar::CMFCColorBar](#cmfccolorbar) Konstruktor legt den horizontalen Rand auf 4 Pixel.  
  
##  <a name="setproplist"></a>  CMFCColorBar::SetPropList  
 Legt die `m_pWndPropList` geschützte Datenmember, des angegebenen Zeigers auf ein Eigenschaftenraster-Steuerelement.  
  
```  
void SetPropList(CMFCPropertyGridCtrl* pWndList);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|*pWndList*|[in] Zeiger auf die Eigenschaft DataGrid-Steuerelement-Objekt.|  
  
##  <a name="setvertmargin"></a>  CMFCColorBar::SetVertMargin  
 Legt den vertikalen Rand, der den Abstand zwischen der obersten oder untersten Zelle Farbe und die Client-Bereich-Grenze ist fest.  
  
```  
void SetVertMargin(int nVertMargin);
```  
  
### <a name="parameters"></a>Parameter  
*nVertMargin*<br/>
[in] Der vertikale Rand in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 In der Standardeinstellung die [CMFCColorBar::CMFCColorBar](#cmfccolorbar) Konstruktor legt den vertikalen Rand auf 4 Pixel.  
  
##  <a name="showcommandmessagestring"></a>  CMFCColorBar::ShowCommandMessageString  
 Fordert das Rahmenfenster, das Besitzer das Farbleiste-Steuerelement ist, um die Nachricht-Zeile in der Statusleiste zu aktualisieren.  
  
```  
virtual void ShowCommandMessageString(UINT uiCmdId);
```  
  
### <a name="parameters"></a>Parameter  
*uiCmdId*<br/>
[in] Eine Befehls-ID. (Dieser Parameter wird ignoriert.)  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die WM_SETMESSAGESTRING-Nachricht an den Besitzer des Steuerelements Farbleiste an.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)
