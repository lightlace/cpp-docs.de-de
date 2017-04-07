---
title: Klasse CMFCColorBar | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- CMFCColorBar class
- CMFCColorBar::m_ColorAutomatic data member
- CMFCColorBar::m_bInternal data member
- CMFCColorBar::m_bIsEnabled data member
- CMFCColorBar::m_nNumColumnsVert data member
- CMFCColorBar::m_nVertMargin data member
- CMFCColorBar::m_strDocColors data member
- CMFCColorBar::m_BoxSize data member
- CMFCColorBar::m_pParentBtn data member
- CMFCColorBar::m_bIsTearOff data member
- CMFCColorBar::m_nHorzOffset data member
- CMFCColorBar::m_pParentRibbonBtn data member
- CMFCColorBar::m_nNumRowsHorz data member
- CMFCColorBar::m_bStdColorDlg data member
- CMFCColorBar::m_strAutoColor data member
- CMFCColorBar::m_ColorNames data member
- CMFCColorBar::m_strOtherColor data member
- CMFCColorBar::m_lstDocColors data member
- CMFCColorBar::m_pWndPropList data member
- CMFCColorBar::m_ColorSelected data member
- CMFCColorBar::m_nCommandID data member
- CMFCColorBar::m_nHorzMargin data member
- CMFCColorBar::m_nRowHeight data member
- CMFCColorBar::m_Palette data member
- CMFCColorBar::m_colors data member
- CMFCColorBar::m_nVertOffset data member
- CMFCColorBar::m_nNumColumns data member
- CMFCColorBar::m_bShowDocColorsWhenDocked data member
ms.assetid: 4756ee40-25a5-4cee-af7f-acab7993d1c7
caps.latest.revision: 35
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: bf4d431a3f3237587dc9f86be91f11b9b5016fe2
ms.lasthandoff: 02/24/2017

---
# <a name="cmfccolorbar-class"></a>CMFCColorBar-Klasse
Die `CMFCColorBar` -Klasse stellt eine andockbare Symbolleiste, die Farben in einem Dokument oder die Anwendung auswählen können.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCColorBar : public CMFCPopupMenuBar  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="protected-constructors"></a>Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCColorBar::CMFCColorBar](#cmfccolorbar)|Erstellt ein `CMFCColorBar`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCColorBar::ContextToSize](#contexttosize)|Berechnet die vertikalen und horizontalen Ränder, die dann passt die Position dieser Schaltflächen sind erforderlich, um die Schaltflächen auf dem Steuerelement Farbe enthalten.|  
|[CMFCColorBar::CreateControl](#createcontrol)|Erstellt ein Fenster der Farbleiste-Steuerelement, fügt es die `CMFCColorBar` Objekt, und ändert die Größe des Steuerelements, um die angegebenen Farbpalette enthalten.|  
|[CMFCColorBar::Create](#create)|Erstellt ein Fenster der Farbleiste-Steuerelement und fügt es der `CMFCColorBar` Objekt.|  
|[CMFCColorBar::EnableAutomaticButton](#enableautomaticbutton)|Anzeigen oder ausblenden "Automatische".|  
|[CMFCColorBar::EnableOtherButton](#enableotherbutton)|Aktiviert oder deaktiviert die Anzeige eines Dialogfelds, in dem den Benutzer weitere Farben auswählen können.|  
|[CMFCColorBar::GetColor](#getcolor)|Ruft die derzeit ausgewählte Farbe ab.|  
|[CMFCColorBar::GetCommandID](#getcommandid)|Ruft die Befehls-ID des aktuellen Steuerelements Farbleiste ab.|  
|[CMFCColorBar::GetHighlightedColor](#gethighlightedcolor)|Ruft die Farbe, die gibt an, dass eine Farbe den Fokus besitzt; die Schaltfläche ist *hot*.|  
|[CMFCColorBar::GetHorzMargin](#gethorzmargin)|Ruft den horizontalen Rand, der den Abstand zwischen der linken Seite oder Zelle richtige Farbe und die Client-Bereich-Grenze ist.|  
|[CMFCColorBar::GetVertMargin](#getvertmargin)|Ruft den vertikalen Rand, der den Abstand zwischen dem oberen oder unteren Zelle "Color" und die Client-Bereich-Grenze ist.|  
|[CMFCColorBar::IsTearOff](#istearoff)|Gibt an, ob der aktuelle Farbleiste angedockt werden kann.|  
|[CMFCColorBar::SetColor](#setcolor)|Legt die Farbe, die derzeit ausgewählt ist.|  
|[CMFCColorBar::SetColorName](#setcolorname)|Legt einen neuen Namen für eine angegebene Farbe fest.|  
|[CMFCColorBar::SetCommandID](#setcommandid)|Legt eine neue Befehls-ID für ein Steuerelement Farbe fest.|  
|[CMFCColorBar::SetDocumentColors](#setdocumentcolors)|Legt die Liste der Farben, mit denen im aktuellen Dokument fest.|  
|[CMFCColorBar::SetHorzMargin](#sethorzmargin)|Legt den horizontalen Rand, der den Abstand zwischen der linken Seite oder Zelle richtige Farbe und die Client-Bereich-Grenze ist.|  
|[CMFCColorBar::SetVertMargin](#setvertmargin)|Legt den vertikalen Rand, der den Abstand zwischen den obersten oder untersten Zelle Farbe und die Client-Bereich-Grenze ist.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCColorBar::AdjustLocations](#adjustlocations)|Passt die Positionen der Farbe Schaltflächen-Steuerelement die Farbe.|  
|[CMFCColorBar::AllowChangeTextLabels](#allowchangetextlabels)|Gibt an, ob die Beschriftung der Schaltflächen ändern kann.|  
|[CMFCColorBar::AllowShowOnList](#allowshowonlist)|Gibt an, ob die Farbleiste Control-Objekt in der Liste eine Symbolleiste während des Anpassungsvorgangs angezeigt werden kann.|  
|[CMFCColorBar::CalcSize](#calcsize)|Vom Framework als Teil der Berechnungsprozess Layout aufgerufen.|  
|[CMFCColorBar::CreatePalette](#createpalette)|Initialisiert eine Palette mit Farben in einem angegebenen Array von Farben.|  
|[CMFCColorBar::GetColorGridSize](#getcolorgridsize)|Berechnet die Anzahl von Zeilen und Spalten im Raster eines Steuerelements Farbleiste.|  
|[CMFCColorBar::GetExtraHeight](#getextraheight)|Berechnet die zusätzliche Höhe, die der aktuellen Farbleiste erfordert verschiedene Elemente der Benutzeroberfläche angezeigt, wie z. B. die **andere** Schaltfläche Dokumentfarben und So weiter.|  
|[CMFCColorBar::InitColors](#initcolors)|Ein Array von Farben mit der Farben in einer angegebenen Palette oder die System-Standardpalette initialisiert.|  
|[CMFCColorBar::OnKey](#onkey)|Vom Framework aufgerufen, wenn ein Benutzer eine Taste drückt.|  
|[CMFCColorBar::OnSendCommand](#onsendcommand)|Aufgerufen, um eine Hierarchie von Popup-Steuerelementen zu schließen.|  
|[CMFCColorBar::OnUpdateCmdUI](#onupdatecmdui)|Vom Framework aufgerufen wird, aktivieren oder deaktivieren ein Element der Benutzeroberfläche eines Steuerelements Farbleiste, bevor das Element angezeigt wird.|  
|[CMFCColorBar::OpenColorDialog](#opencolordialog)|Öffnet das Dialogfeld Farbe an.|  
|[CMFCColorBar::Rebuild](#rebuild)|Zeichnet die Farbleiste-Steuerelement vollständig neu.|  
|[CMFCColorBar::SelectPalette](#selectpalette)|Die logische Palette von den angegebenen Gerätekontext festgelegt auf der Palette der Schaltfläche übergeordneten des aktuellen Steuerelements Farbleiste.|  
|[CMFCColorBar::SetPropList](#setproplist)|Legt die `m_pWndPropList` geschützte Datenmember des angegebenen Zeigers auf ein Eigenschaftenraster-Steuerelement.|  
|[CMFCColorBar::ShowCommandMessageString](#showcommandmessagestring)|Fordert das Rahmenfenster, das die Farbleiste Steuerelement zum Aktualisieren der Position der Meldung in der Statusleiste besitzt.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`m_bInternal`|Ein boolesches Feld, das bestimmt, ob Mausereignisse verarbeitet werden. Mausereignisse werden in der Regel verarbeitet, wenn dieses Feld ist `TRUE` und Anpassungsmodus `FALSE`.|  
|`m_bIsEnabled`|Ein boolescher Wert, der angibt, ob ein Steuerelement aktiviert ist.|  
|`m_bIsTearOff`|Ein boolescher Wert, der angibt, ob die Farbleiste Andocken unterstützt.|  
|`m_BoxSize`|Ein [CSize](../../atl-mfc-shared/reference/csize-class.md) -Objekt, das die Größe einer Zelle in einem Raster Farbleiste angibt.|  
|`m_bShowDocColorsWhenDocked`|Ein boolescher Wert, der angibt, ob Dokumentfarben angezeigt, wenn der Farbleiste angedockt wird. Weitere Informationen finden Sie unter [CMFCColorBar::SetDocumentColors](#setdocumentcolors).|  
|`m_bStdColorDlg`|Ein boolescher Wert, der angibt, ob das Dialogfeld Farbe Standardbetriebssystem anzeigen oder die [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) das Dialogfeld. Weitere Informationen finden Sie unter [CMFCColorBar::EnableOtherButton](#enableotherbutton).|  
|`m_ColorAutomatic`|Ein [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) , speichert die aktuelle Farbe. Weitere Informationen finden Sie unter [CMFCColorBar::EnableOtherButton](#enableotherbutton).|  
|`m_ColorNames`|Ein [CMap](../../mfc/reference/cmap-class.md) Objekt, einen Satz von RGB-Farben mit ihren Namen.|  
|`m_colors`|Ein [CArray](../../mfc/reference/carray-class.md) von [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Werte, die die Farben enthält, die im Steuerelement Farbleiste angezeigt werden.|  
|`m_ColorSelected`|Ein [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Wert, der die Farbe, die der Benutzer aus dem Steuerelement Farbleiste derzeit ausgewählt hat.|  
|`m_lstDocColors`|Ein [CList](../../mfc/reference/clist-class.md) von [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Werte, die die Farben enthält, die derzeit in einem Dokument verwendet werden.|  
|`m_nCommandID`|Eine Ganzzahl ohne Vorzeichen, die die Befehls-ID einer Schaltfläche Farbe ist.|  
|`m_nHorzMargin`|Eine ganze Zahl, die den horizontalen Abstand zwischen die Schaltflächen in einem Raster mit Farben.|  
|`m_nHorzOffset`|Eine ganze Zahl, die den horizontalen Offset in die Mitte der Schaltfläche für die Farbe. Dieser Wert ist wichtig, wenn die Schaltfläche Text oder ein Bild neben einer Farbe angezeigt.|  
|`m_nNumColumns`|Eine ganze Zahl, die Anzahl der Spalten in einem Raster Farbleiste Steuerelement Farben.|  
|`m_nNumColumnsVert`|Eine ganze Zahl, die Anzahl der Spalten in einem vertikal ausgerichteten Raster von Farben.|  
|`m_nNumRowsHorz`|Eine ganze Zahl, die Anzahl der Spalten in einem horizontal ausgerichteten Raster von Farben.|  
|`m_nRowHeight`|Eine ganze Zahl, die die Höhe einer Zeile der Color-Schaltflächen in einem Raster mit Farben.|  
|`m_nVertMargin`|Eine ganze Zahl, die den vertikalen Abstand zwischen die Schaltflächen in einem Raster mit Farben.|  
|`m_nVertOffset`|Eine ganze Zahl, die den vertikalen Offset in die Mitte der Schaltfläche für die Farbe. Dieser Wert ist wichtig, wenn die Schaltfläche Text oder ein Bild neben einer Farbe angezeigt.|  
|`m_Palette`|Ein [CPalette](../../mfc/reference/cpalette-class.md) der Farben, die in der Farbleiste-Steuerelement verwendet werden.|  
|`m_pParentBtn`|Ein Zeiger auf eine [CMFCColorButton](../../mfc/reference/cmfccolorbutton-class.md) -Objekt, das das übergeordnete Element der aktuellen Schaltfläche ist. Dieser Wert ist erheblichen, wenn die farbenschaltfläche in einer Hierarchie der Steuerelemente der Symbolleiste oder im Eigenschaftenraster-Steuerelement eine Farbe.|  
|`m_pParentRibbonBtn`|Ein Zeiger auf eine [CMFCRibbonColorButton](../../mfc/reference/cmfcribboncolorbutton-class.md) -Objekt, das auf dem Menüband und die Schaltfläche "übergeordnete" der aktuellen Schaltfläche. Dieser Wert ist erheblichen, wenn die farbenschaltfläche in einer Hierarchie der Steuerelemente der Symbolleiste oder im Eigenschaftenraster-Steuerelement eine Farbe.|  
|`m_pWndPropList`|Ein Zeiger auf eine [CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md) Objekt.|  
|`m_strAutoColor`|Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) , der Text, der angezeigt wird die **automatische** Schaltfläche. Weitere Informationen finden Sie unter [CMFCColorBar::EnableAutomaticButton](#enableautomaticbutton).|  
|`m_strDocColors`|Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) , den Text, der auf die Schaltfläche Dokument Farben angezeigt wird. Weitere Informationen finden Sie unter [CMFCColorBar::SetDocumentColors](#setdocumentcolors).|  
|`m_strOtherColor`|Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) , der Text, der angezeigt wird die *andere* Schaltfläche. Weitere Informationen finden Sie unter [CMFCColorBar::EnableOtherButton](#enableotherbutton).|  
  
## <a name="remarks"></a>Hinweise  
 In der Regel erstellen Sie keine `CMFCColorBar` direkt. Stattdessen die [CMFCColorMenuButton Klasse](../../mfc/reference/cmfccolormenubutton-class.md) (in Menüs und Symbolleisten verwendet) oder die [CMFCColorButton Klasse](../../mfc/reference/cmfccolorbutton-class.md) erstellt die `CMFCColorBar` Objekt.  
  
 Die `CMFCColorBar` -Klasse stellt die folgenden Funktionen:  
  
-   Passt automatisch die Liste der Dokumentfarben an.  
  
-   Speichert und seinen Status, der zusammen mit dem Dokument Zustand wiederhergestellt.  
  
-   Verwaltet die Schaltfläche 'Automatische'.  
  
-   Verwendet die [CMFCColorPickerCtrl Klasse](../../mfc/reference/cmfccolorpickerctrl-class.md) Steuerelement, um eine benutzerdefinierte Farbe auszuwählen.  
  
-   Unterstützt einen Status "abtrennbare" (Wenn sie mithilfe von erstellt wird die [CMFCColorMenuButton Klasse](../../mfc/reference/cmfccolormenubutton-class.md)).  
  
 Integrieren der `CMFCColorBar` -Funktionen in Ihrer Anwendung:  
  
1.  Erstellen einer regulären Menüschaltfläche, und weisen Sie diese ID, z. B. ID_CHAR_COLOR.  
  
2.  In der Frame-Fensters-Klasse überschreiben die [CFrameWndEx::OnShowPopupMenu](../../mfc/reference/cframewndex-class.md#onshowpopupmenu) -Methode und Ersetzen Sie das reguläre Menü Schaltfläche mit einer [CMFCColorMenuButton-Klasse](../../mfc/reference/cmfccolormenubutton-class.md) Objekt (durch Aufrufen von [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)).  
  
3.  Legen Sie alle Stile zum Aktivieren oder deaktivieren Sie die Funktionen von der `CMFCColorBar` -Objekt während [CMFCColorMenuButton Klasse](../../mfc/reference/cmfccolormenubutton-class.md) erstellen. Die `CMFCColorMenuButton` Objekt dynamisch erstellt der `CMFCColorBar` Objekts nach das Framework Ruft die `CreatePopupMenu` Methode.  
  
 Klickt der Benutzer auf eine Schaltfläche der Farbleiste-Steuerelement, verwendet das Framework die `ON_COMMAND` Makro, um das übergeordnete Element des Steuerelements Farbe zu benachrichtigen. In der Makro ist die Befehls-ID-Parameter der Wert, den Sie auf die Farbleiste Steuerelement Schaltfläche in Schritt 1 (in diesem Beispiel ID_CHAR_COLOR) zugewiesen. Weitere Informationen finden Sie unter der [CMFCColorMenuButton Klasse](../../mfc/reference/cmfccolormenubutton-class.md), [CMFCColorButton Klasse](../../mfc/reference/cmfccolorbutton-class.md), [CMFCColorPickerCtrl-Klasse](../../mfc/reference/cmfccolorpickerctrl-class.md), [CFrameWndEx Klasse](../../mfc/reference/cframewndex-class.md), und [CMFCToolBar Klasse](../../mfc/reference/cmfctoolbar-class.md) Klassen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie eine Farbleiste konfigurieren mithilfe verschiedener Methoden in der `CMFCColorBar` Klasse. Die Methoden legen Sie die horizontale und vertikale Ränder, aktivieren die andere Schaltfläche, ein Farbleiste Steuerelement-Fenster erstellt und werden die ausgewählte Farbe. Dieses Beispiel ist Teil der [Beispiel neue Steuerelemente](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls&#1;](../../mfc/reference/codesnippet/cpp/cmfccolorbar-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls&#2;](../../mfc/reference/codesnippet/cpp/cmfccolorbar-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
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
  
##  <a name="adjustlocations"></a>CMFCColorBar::AdjustLocations  
 Passt die Positionen der Farbe Schaltflächen-Steuerelement die Farbe.  
  
```  
virtual void AdjustLocations();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Framework während aufgerufen `WM_SIZE` Verarbeitung von Nachrichten.  
  
##  <a name="allowchangetextlabels"></a>CMFCColorBar::AllowChangeTextLabels  
 Gibt an, ob die Beschriftung der Schaltflächen ändern kann.  
  
```  
virtual BOOL AllowChangeTextLabels() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Immer `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig gibt diese Methode immer `FALSE`, was bedeutet, dass die Beschriftungen kann nicht geändert werden. Überschreiben Sie diese Methode zum Ändern von Beschriftungen zu aktivieren.  
  
##  <a name="allowshowonlist"></a>CMFCColorBar::AllowShowOnList  
 Gibt an, ob die Farbleiste Control-Objekt in der Liste eine Symbolleiste während des Anpassungsvorgangs angezeigt werden kann.  
  
```  
virtual BOOL AllowShowOnList() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Immer `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig gibt diese Methode immer `TRUE`, was bedeutet, dass das Framework während des Anpassungsvorgangs-Steuerelement die Farbe anzeigen kann. Überschreiben Sie diese Methode, um ein anderes Verhalten zu implementieren.  
  
##  <a name="calcsize"></a>CMFCColorBar::CalcSize  
 Vom Framework als Teil der Berechnungsprozess Layout aufgerufen.  
  
```  
virtual CSize CalcSize(BOOL bVertDock);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bVertDock`  
 `TRUE`um anzugeben, dass das Steuerelement Farbleiste vertikal angedockt wird; `FALSE` angeben, dass das Steuerelement Farbleiste horizontal angedockt ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Größe des Arrays der Color-Schaltflächen in einem Steuerelement Farbleiste.  
  
##  <a name="cmfccolorbar"></a>CMFCColorBar::CMFCColorBar  
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
 Ein Array von Farben, die vom Framework auf dem Steuerelement Farbe angezeigt.  
  
 [in] `color`  
 Die ursprünglich ausgewählte Farbe.  
  
 [in] `lpszAutoColor`  
 Die Beschriftung für die *automatische* Farbschaltfläche (Standard), oder `NULL`.  
  
 Ist die Bezeichnung für "automatisch" **automatische**.  
  
 [in] `lpszOtherColor`  
 Die Beschriftung für die *andere* Schaltfläche Weitere Farben angezeigt werden, oder `NULL`.  
  
 Die Bezeichnung für die andere Schaltfläche wird **Weitere Farben... **.  
  
 [in] `lpszDocColors`  
 Die Beschriftung der Schaltfläche Farben Dokument. Die Dokument-Farben-Palette Listet alle Farben, die das Dokument zurzeit verwendet.  
  
 [in] `lstDocColors`  
 Eine Liste der Farben, die das Dokument zurzeit verwendet.  
  
 [in] `nColumns`  
 Die Anzahl der Spalten, die das Array von Farben aufweist.  
  
 [in] `nRowsDockHorz`  
 Die Anzahl der Zeilen, die die Farbleiste hat, wenn es horizontal angedockt ist.  
  
 [in] `nColDockVert`  
 Die Anzahl der Spalten, die auf die Farbleiste hat, wenn es vertikal angedockt ist.  
  
 [in] `colorAutomatic`  
 Die Standardfarbe, die das Framework gilt, wenn Sie auf "Automatische" klicken.  
  
 [in] `nCommandID`  
 Der Befehl der Farbleiste Control-ID.  
  
 [in] `pParentBtn`  
 Ein Zeiger auf eine übergeordnete-Schaltfläche.  
  
 [in] `src`  
 Eine vorhandene `CMFCColorBar` -Objekt, in das neue kopiert werden `CMFCColorBar` Objekt.  
  
 [in] `uiCommandID`  
 Die Befehls-ID.  
  
##  <a name="contexttosize"></a>CMFCColorBar::ContextToSize  
 Berechnet die vertikalen und horizontalen Ränder, die sind erforderlich, um die Schaltflächen auf dem Steuerelement Farbe enthalten, und passt die Position dieser Schaltflächen.  
  
```  
void ContextToSize(
    BOOL bSquareButtons = TRUE,   
    BOOL bCenterButtons = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `bSquareButtons`|`TRUE`angeben, dass die Form der Schaltflächen auf einem Steuerelement Farbe quadratische; andernfalls `FALSE`. Der Standardwert ist `TRUE`.|  
|[in] `bCenterButtons`|`TRUE`um anzugeben, dass der Inhalt in einer Farbleiste Steuerelement Schaltfläche zentriert wird; andernfalls `FALSE`. Der Standardwert ist `TRUE`.|  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="create"></a>CMFCColorBar::Create  
 Erstellt ein Fenster der Farbleiste-Steuerelement und fügt es der `CMFCColorBar` Objekt.  
  
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
 Eine bitweise Kombination (OR) [Fensterstile](../../mfc/reference/window-styles.md).  
  
 [in] `nID`  
 Die Befehls-ID.  
  
 [in] `pPalette`  
 Ein Zeiger auf eine Palette mit Farben. Die Standardeinstellung ist `NULL`.  
  
 [in] `nColumns`  
 Die Anzahl der Spalten im Steuerelement Farbleiste. Der Standard ist 0.  
  
 [in] `nRowsDockHorz`  
 Die Anzahl der Zeilen in der Farbleiste steuern, wenn sie horizontal angedockt wird. Der Standard ist 0.  
  
 [in] `nColDockVert`  
 Die Anzahl der Spalten in der Farbleiste steuern, wenn sie vertikal angedockt wird. Der Standard ist 0.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn diese Methode erfolgreich ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Erstellt ein `CMFCColorBar` Objekt, das den Klassenkonstruktor diese Methode aufrufen. Die `Create` Methode des Steuerelements in Windows erstellt und initialisiert eine Liste von Farben.  
  
##  <a name="createcontrol"></a>CMFCColorBar::CreateControl  
 Erstellt ein Fenster der Farbleiste-Steuerelement, fügt es die `CMFCColorBar` Objekt, und ändert das Steuerelementfenster, um die angegebenen Farbpalette enthalten.  
  
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
 Ein Zeiger auf das übergeordnete Fenster. Nicht `NULL`.  
  
 [in] `rect`  
 Ein umgebendes Rechteck, das angibt, wo das Steuerelement Farbe gezeichnet.  
  
 [in] `nID`  
 Die Steuerelement-ID.  
  
 [in] `nColumns`  
 Die ideale Anzahl von Spalten im Steuerelement Farbleiste. Diese Methode ändert diese Zahl entsprechend der angegebene Farbpalette. Der Standardwert ist-1 und bedeutet, dass dieser Parameter nicht angegeben wird.  
  
 [in] `pPalette`  
 Zeiger auf eine Palette mit Farben oder `NULL`. Wenn dieser Parameter ist `NULL`, diese Methode berechnet die Größe des Steuerelements Farbleiste, als wenn 20 Farben angegeben wurden. Die Standardeinstellung ist `NULL`.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn diese Methode erfolgreich ist. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode verwendet die `rect`, `nColumns`, und `pPalette` Parameter berechnet die geeignete Anzahl oder Zeilen und Spalten in die Farbleiste-Steuerelement, und ruft dann die [CMFCColorBar::Create](#create) Methode.  
  
##  <a name="createpalette"></a>CMFCColorBar::CreatePalette  
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
|[in] `palette`|Eine Palette mit Farben.|  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn diese Methode erfolgreich ist; andernfalls `FALSE`.  
  
##  <a name="enableautomaticbutton"></a>CMFCColorBar::EnableAutomaticButton  
 Anzeigen oder ausblenden "Automatische".  
  
```  
void EnableAutomaticButton(
    LPCTSTR lpszLabel,  
    COLORREF colorAutomatic,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszLabel`  
 Die Beschriftung für die *automatische* Farbschaltfläche (Standard), oder `NULL`.  
  
 Ist die Bezeichnung für "automatisch" **automatische**.  
  
 [in] `colorAutomatic`  
 Die Standardfarbe, die das Framework gilt, wenn Sie auf "Automatische" klicken.  
  
 [in] `bEnable`  
 `TRUE`So aktivieren Sie "Automatische"; `FALSE` "Automatische" deaktivieren. Der Standardwert ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
 Die Beschriftung für "automatisch" wird gelöscht, wenn die `lpszLabel` Parameter ist `NULL` oder `bEnable` Parameter ist `FALSE`.  
  
##  <a name="enableotherbutton"></a>CMFCColorBar::EnableOtherButton  
 Aktiviert oder deaktiviert die Anzeige eines Dialogfelds, in dem den Benutzer weitere Farben auswählen können.  
  
```  
void EnableOtherButton(
    LPCTSTR lpszLabel,  
    BOOL bAltColorDlg=TRUE,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszLabel`  
 Die Beschriftung für die *andere* Schaltfläche Weitere Farben angezeigt werden, oder `NULL`.  
  
 Ist diese Schaltfläche die Bezeichnung **Weitere Farben... **.  
  
 [in] `bAltColorDlg`  
 `TRUE`zum Anzeigen der [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) Dialogfeld; `FALSE` zum Anzeigen des Standards [CColorDialog](../../mfc/reference/ccolordialog-class.md) Dialogfeld. Der Standardwert ist `TRUE`.  
  
 [in] `bEnable`  
 `TRUE`um die Schaltfläche zu aktivieren; `FALSE` auf die Schaltfläche deaktiviert. Der Standardwert ist `TRUE`.  
  
##  <a name="getcolor"></a>CMFCColorBar::GetColor  
 Ruft die derzeit ausgewählte Farbe ab.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die ausgewählte Farbe.  
  
##  <a name="getcolorgridsize"></a>CMFCColorBar::GetColorGridSize  
 Berechnet die Anzahl von Zeilen und Spalten im Raster eines Steuerelements Farbleiste.  
  
```  
CSize GetColorGridSize(BOOL bVertDock) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `bVertDock`|`TRUE`zum Durchführen der Berechnung für ein Steuerelement vertikal verankerter Farbleiste; Andernfalls führen Sie die Berechnung für ein horizontal angedockten Steuerelement.|  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CSize](../../atl-mfc-shared/reference/csize-class.md) -Objekt, dessen `cx` Komponente enthält die Anzahl der Spalten und deren `cy` Komponente enthält die Anzahl der Zeilen.  
  
##  <a name="getcommandid"></a>CMFCColorBar::GetCommandID  
 Ruft die Befehls-ID des aktuellen Steuerelements Farbleiste ab.  
  
```  
UINT GetCommandID() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Befehls-ID.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Benutzer eine neue Farbe auswählt, sendet das Framework die Befehls-ID in einer `WM_COMMAND` Nachricht, um das übergeordnete Element des informieren die `CMFCColorBar` Objekt.  
  
##  <a name="getextraheight"></a>CMFCColorBar::GetExtraHeight  
 Berechnet die zusätzliche Höhe, die der aktuellen Farbleiste angezeigt verschiedene Elemente der Benutzeroberfläche, wie z. B. erfordert der **andere** Schaltfläche oder ein Dokument Farben.  
  
```  
int GetExtraHeight(int nNumColumns) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `nNumColumns`|Enthält die Farbleiste-Steuerelement Dokumentfarben, die Anzahl der Spalten im Raster des Dokumentfarben angezeigt werden sollen. Andernfalls wird dieser Wert nicht verwendet.|  
  
### <a name="return-value"></a>Rückgabewert  
 Die berechnete zusätzliche Höhe, die erforderlich ist.  
  
##  <a name="gethighlightedcolor"></a>CMFCColorBar::GetHighlightedColor  
 Ruft die Farbe, die gibt an, dass eine Farbe den Fokus besitzt; die Schaltfläche ist *hot*.  
  
```  
COLORREF GetHighlightedColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 RGB-Wert.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="gethorzmargin"></a>CMFCColorBar::GetHorzMargin  
 Ruft den horizontalen Rand, der den Abstand zwischen der linken Seite oder Zelle richtige Farbe und die Client-Bereich-Grenze ist.  
  
```  
int GetHorzMargin();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der horizontale Rand.  
  
##  <a name="getvertmargin"></a>CMFCColorBar::GetVertMargin  
 Ruft den vertikalen Rand, der den Abstand zwischen dem oberen oder unteren Zelle "Color" und die Client-Bereich-Grenze ist.  
  
```  
int GetVertMargin() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der vertikalen Rand.  
  
##  <a name="initcolors"></a>CMFCColorBar::InitColors  
 Initialisiert ein Array von Farben in einer Palette angegebenen Farben oder mit der Standardpalette System.  
  
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
  
##  <a name="istearoff"></a>CMFCColorBar::IsTearOff  
 Gibt an, ob der aktuelle Farbleiste angedockt werden kann.  
  
```  
BOOL IsTearOff() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das aktuelle Farbleiste Steuerelement angedockt werden kann; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Farbleiste Steuerelement angedockt werden kann, können Sie aus einer Steuerleiste abgebrochen und an einer anderen Position angedockt werden.  
  
##  <a name="onkey"></a>CMFCColorBar::OnKey  
 Vom Framework aufgerufen, wenn ein Benutzer eine Taste drückt.  
  
```  
virtual BOOL OnKey(UINT nChar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nChar`  
 Der virtuelle Taste Code, die ein Benutzer gedrückten Taste.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn diese Methode mit den angegebenen Schlüssel verarbeitet andernfalls `FALSE`.  
  
##  <a name="onsendcommand"></a>CMFCColorBar::OnSendCommand  
 Aufgerufen, um eine Hierarchie von Popup-Steuerelemente zu schließen.  
  
```  
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `pButton`|Ein Zeiger auf ein Steuerelement, das auf einer Symbolleiste befindet.|  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn diese Methode erfolgreich ist; andernfalls `FALSE`.  
  
##  <a name="onupdatecmdui"></a>CMFCColorBar::OnUpdateCmdUI  
 Vom Framework aufgerufen wird, aktivieren oder deaktivieren ein Element der Benutzeroberfläche eines Steuerelements Farbleiste, bevor das Element angezeigt wird.  
  
```  
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,  
    BOOL bDisableIfNoHndler);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pTarget`  
 Ein Zeiger auf ein Fenster, das eine Benutzeroberfläche zu aktualisierenden Elements enthält.  
  
 [in] `bDisableIfNoHndler`  
 `TRUE`zum Deaktivieren der Benutzeroberflächen-Element, wenn kein Handler ist eine Nachricht Zuordnung definiert. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Klickt ein Benutzer der Anwendung ein Element der Benutzeroberfläche, muss das Element wissen, ob es als aktiviert angezeigt werden soll oder deaktiviert. Das Ziel der Befehlsnachricht bietet diese Informationen durch die Implementierung einer `ON_UPDATE_COMMAND_UI` Befehlshandler. Verwenden Sie diese Methode, um die Verarbeitung des Befehls. Weitere Informationen finden Sie unter [CCmdUI-Klasse](../../mfc/reference/ccmdui-class.md).  
  
##  <a name="opencolordialog"></a>CMFCColorBar::OpenColorDialog  
 Öffnet das Dialogfeld Farbe an.  
  
```  
virtual BOOL OpenColorDialog(
    const COLORREF colorDefault,  
    COLORREF& colorRes);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `colorDefault`  
 Die Farbe, die standardmäßig aktiviert ist, wenn das Dialogfeld "Farbe" wird geöffnet.  
  
 [out] `colorRes`  
 Die Farbe, die ein Benutzer ausgewählt.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Benutzer eine Farbe ausgewählt `FALSE` , wenn der Benutzer das Dialogfeld Farbe abgebrochen.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="rebuild"></a>CMFCColorBar::Rebuild  
 Zeichnet die Farbleiste-Steuerelement vollständig neu.  
  
```  
virtual void Rebuild();
```  
  
##  <a name="selectpalette"></a>CMFCColorBar::SelectPalette  
 Die logische Palette von den angegebenen Gerätekontext festgelegt auf der Palette der Schaltfläche übergeordneten des aktuellen Steuerelements Farbleiste.  
  
```  
CPalette* SelectPalette(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `pDC`|Ein Zeiger auf den Gerätekontext, der übergeordneten Schaltfläche des aktuellen Steuerelements Farbleiste.|  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Palette, die von der Palette der Schaltfläche übergeordneten des aktuellen Steuerelements Farbleiste ersetzt wird.  
  
##  <a name="setcolor"></a>CMFCColorBar::SetColor  
 Legt die Farbe, die derzeit ausgewählt ist.  
  
```  
void SetColor(COLORREF color);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `color`  
 Ein Wert für den RGB-Farbe.  
  
##  <a name="setcolorname"></a>CMFCColorBar::SetColorName  
 Legt einen neuen Namen für eine angegebene Farbe fest.  
  
```  
static void SetColorName(
    COLORREF color,  
    const CString& strName);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `color`  
 Der RGB-Wert einer Farbe.  
  
 [in] `strName`  
 Der neue Name für die angegebene Farbe.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ändert den Namen der angegebenen Farbe in allen `CMFCColorBar` Objekte in der Anwendung.  
  
##  <a name="setcommandid"></a>CMFCColorBar::SetCommandID  
 Legt eine neue Befehls-ID für ein Steuerelement Farbe fest.  
  
```  
void SetCommandID(UINT nCommandID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nCommandID`  
 Eine Befehls-ID.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die Befehls-ID eines Steuerelements Farbe zu ändern und das übergeordnete Fenster des Steuerelements zu benachrichtigen, dass die ID geändert hat.  
  
##  <a name="setdocumentcolors"></a>CMFCColorBar::SetDocumentColors  
 Legt die Liste der Farben, mit denen im aktuellen Dokument fest.  
  
```  
void SetDocumentColors(
    LPCTSTR lpszCaption,  
    CList<COLORREF,COLORREF>& lstDocColors,  
    BOOL bShowWhenDocked=FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszCaption`  
 Eine Beschriftung, die angezeigt wird, wenn das Steuerelement Farbe nicht verankert ist.  
  
 [in] `lstDocColors`  
 Eine Liste der Farben, die die Farben des aktuellen Dokuments ersetzt.  
  
 [in] `bShowWhenDocked`  
 `TRUE`Dokumentfarben bei zum Anzeigen der Farbleiste Steuerelement angedockt ist; andernfalls `FALSE`. Der Standardwert ist `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 *Dokumentieren Sie Farben* sind die Farben, die derzeit in einem Dokument verwendet werden. Das Framework verwaltet automatisch eine Liste der Dokumentfarben, aber Sie können diese Methode verwenden, um die Liste zu ändern.  
  
##  <a name="sethorzmargin"></a>CMFCColorBar::SetHorzMargin  
 Legt den horizontalen Rand, der den Abstand zwischen der linken Seite oder richtige Farbe Zelle und dem Rand des Clientbereichs ist.  
  
```  
void SetHorzMargin(int nHorzMargin);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nHorzMargin`  
 Der horizontale Rand in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 In der Standardeinstellung die [CMFCColorBar::CMFCColorBar](#cmfccolorbar) Konstruktor legt den horizontalen Rand auf 4 Pixel.  
  
##  <a name="setproplist"></a>CMFCColorBar::SetPropList  
 Legt die `m_pWndPropList` geschützte Datenmember des angegebenen Zeigers auf ein Eigenschaftenraster-Steuerelement.  
  
```  
void SetPropList(CMFCPropertyGridCtrl* pWndList);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `pWndList`|Ein Zeiger auf die Eigenschaft Grid Control-Objekt.|  
  
##  <a name="setvertmargin"></a>CMFCColorBar::SetVertMargin  
 Legt den vertikalen Rand, der den Abstand zwischen den obersten oder untersten Zelle Farbe und die Client-Bereich-Grenze ist.  
  
```  
void SetVertMargin(int nVertMargin);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nVertMargin`  
 Der vertikalen Rand in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 In der Standardeinstellung die [CMFCColorBar::CMFCColorBar](#cmfccolorbar) Konstruktor legt den vertikalen Rand auf 4 Pixel.  
  
##  <a name="showcommandmessagestring"></a>CMFCColorBar::ShowCommandMessageString  
 Fordert das Rahmenfenster, das die Farbleiste Steuerelement zum Aktualisieren der Position der Meldung in der Statusleiste besitzt.  
  
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

