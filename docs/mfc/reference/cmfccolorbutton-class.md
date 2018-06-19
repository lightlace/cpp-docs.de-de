---
title: CMFCColorButton Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCColorButton
- AFXCOLORBUTTON/CMFCColorButton
- AFXCOLORBUTTON/CMFCColorButton::CMFCColorButton
- AFXCOLORBUTTON/CMFCColorButton::EnableAutomaticButton
- AFXCOLORBUTTON/CMFCColorButton::EnableOtherButton
- AFXCOLORBUTTON/CMFCColorButton::GetAutomaticColor
- AFXCOLORBUTTON/CMFCColorButton::GetColor
- AFXCOLORBUTTON/CMFCColorButton::SetColor
- AFXCOLORBUTTON/CMFCColorButton::SetColorName
- AFXCOLORBUTTON/CMFCColorButton::SetColumnsNumber
- AFXCOLORBUTTON/CMFCColorButton::SetDocumentColors
- AFXCOLORBUTTON/CMFCColorButton::SetPalette
- AFXCOLORBUTTON/CMFCColorButton::SizeToContent
- AFXCOLORBUTTON/CMFCColorButton::IsDrawXPTheme
- AFXCOLORBUTTON/CMFCColorButton::OnDraw
- AFXCOLORBUTTON/CMFCColorButton::OnDrawBorder
- AFXCOLORBUTTON/CMFCColorButton::OnDrawFocusRect
- AFXCOLORBUTTON/CMFCColorButton::OnShowColorPopup
- AFXCOLORBUTTON/CMFCColorButton::RebuildPalette
- AFXCOLORBUTTON/CMFCColorButton::UpdateColor
- AFXCOLORBUTTON/CMFCColorButton::m_bEnabledInCustomizeMode
dev_langs:
- C++
helpviewer_keywords:
- CMFCColorButton [MFC], CMFCColorButton
- CMFCColorButton [MFC], EnableAutomaticButton
- CMFCColorButton [MFC], EnableOtherButton
- CMFCColorButton [MFC], GetAutomaticColor
- CMFCColorButton [MFC], GetColor
- CMFCColorButton [MFC], SetColor
- CMFCColorButton [MFC], SetColorName
- CMFCColorButton [MFC], SetColumnsNumber
- CMFCColorButton [MFC], SetDocumentColors
- CMFCColorButton [MFC], SetPalette
- CMFCColorButton [MFC], SizeToContent
- CMFCColorButton [MFC], IsDrawXPTheme
- CMFCColorButton [MFC], OnDraw
- CMFCColorButton [MFC], OnDrawBorder
- CMFCColorButton [MFC], OnDrawFocusRect
- CMFCColorButton [MFC], OnShowColorPopup
- CMFCColorButton [MFC], RebuildPalette
- CMFCColorButton [MFC], UpdateColor
- CMFCColorButton [MFC], m_bEnabledInCustomizeMode
ms.assetid: 9fdf34ae-4cc5-4c5e-9d89-1c50e8a73699
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cea6fc2a543a528a0838479b2c47bea99f21cf96
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33371112"
---
# <a name="cmfccolorbutton-class"></a>CMFCColorButton-Klasse
Die `CMFCColorButton` und [CMFCColorBar Klasse](../../mfc/reference/cmfccolorbar-class.md) Klassen werden zusammen verwendet, um ein Farben-Auswahlsteuerelement zu implementieren.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCColorButton : public CMFCButton  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCColorButton::CMFCColorButton](#cmfccolorbutton)|Erstellt ein neues `CMFCColorButton`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCColorButton::EnableAutomaticButton](#enableautomaticbutton)|Aktiviert und deaktiviert eine "Automatische"-Schaltfläche, die über die normale Schaltflächen positioniert ist. (Die Schaltfläche "automatisch Standardbetriebssystem" ist mit der Bezeichnung **automatische**.)|  
|[CMFCColorButton::EnableOtherButton](#enableotherbutton)|Aktiviert und deaktiviert eine "other" Schaltfläche, die unter den regulären Farbe Schaltflächen positioniert ist. (Das Standardbetriebssystem "other" Schaltfläche ist mit der Bezeichnung **Weitere Farben**.)|  
|[CMFCColorButton::GetAutomaticColor](#getautomaticcolor)|Ruft die aktuelle Farbe ab.|  
|[CMFCColorButton::GetColor](#getcolor)|Ruft die Farbe einer Schaltfläche ab.|  
|[CMFCColorButton::SetColor](#setcolor)|Legt die Farbe einer Schaltfläche fest.|  
|[CMFCColorButton::SetColorName](#setcolorname)|Legt einen Namen für die Farbe fest.|  
|[CMFCColorButton::SetColumnsNumber](#setcolumnsnumber)|Legt die Anzahl der Spalten im Dialogfeld die Farbe fest.|  
|[CMFCColorButton::SetDocumentColors](#setdocumentcolors)|Gibt eine Liste der dokumentspezifische Farben, die auf das Dialogfeld Auswahl einer Farbe angezeigt werden.|  
|[CMFCColorButton::SetPalette](#setpalette)|Gibt eine Palette von Standardanzeige Farben an.|  
|[CMFCColorButton::SizeToContent](#sizetocontent)|Ändert die Größe des Schaltflächen-Steuerelements, abhängig von der Größe von Text- und Bilddateien.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCColorButton::IsDrawXPTheme](#isdrawxptheme)|Gibt an, ob die Schaltfläche für die aktuelle Farbe in den visuellen Stil von Windows XP angezeigt wird.|  
|[CMFCColorButton::OnDraw](#ondraw)|Wird aufgerufen, durch das Framework um ein Bild der Schaltfläche anzuzeigen.|  
|[CMFCColorButton::OnDrawBorder](#ondrawborder)|Wird aufgerufen, durch das Framework die Schaltfläche Rahmen angezeigt.|  
|[CMFCColorButton::OnDrawFocusRect](#ondrawfocusrect)|Wird aufgerufen, durch das Framework ein Fokusrechteck an, wenn die Schaltfläche einen den Fokus besitzt.|  
|[CMFCColorButton::OnShowColorPopup](#onshowcolorpopup)|Vom Framework aufgerufen, wird die Farbe-Auswahldialogfeld angezeigt wird.|  
|[CMFCColorButton::RebuildPalette](#rebuildpalette)|Initialisiert die `m_pPalette` Datenmember der angegebenen Palette oder das System Standardpalette geschützt.|  
|[CMFCColorButton::UpdateColor](#updatecolor)|Wird vom Framework aufgerufen, wenn der Benutzer eine Farbe aus der Palette der Farben-Auswahldialogfeld auswählt.|  
  
### <a name="data-members"></a>Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|`m_bAltColorDlg`|Ein boolescher Wert. Wenn `TRUE`, zeigt das Framework der [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) Farbe Dialogfeld bei der *andere* Schaltfläche geklickt wird, oder, wenn `FALSE`, das System Farbe (Dialogfeld). Der Standardwert ist `TRUE`. Weitere Informationen finden Sie unter [CMFCColorButton::EnableOtherButton](#enableotherbutton).|  
|`m_bAutoSetFocus`|Ein boolescher Wert. Wenn `TRUE`, das Framework legt den Fokus auf das Menü Farbe fest, wenn das Menü angezeigt wird, oder wenn `FALSE`, ändert sich nicht auf den Fokus. Der Standardwert ist `TRUE`.|  
|[CMFCColorButton::m_bEnabledInCustomizeMode](#m_benabledincustomizemode)|Gibt an, ob für die Farbschaltfläche Anpassungsmodus aktiviert ist.|  
|`m_Color`|Ein [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Wert. Enthält die zurzeit ausgewählte Farbe an.|  
|`m_ColorAutomatic`|Ein [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Wert. Enthält die aktuell ausgewählte Standardfarbe.|  
|`m_Colors`|Ein [CArray](../../mfc/reference/carray-class.md) von [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Werte. Enthält die derzeit verfügbaren Farben an.|  
|`m_lstDocColors`|Ein [CList](../../mfc/reference/clist-class.md) von [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Werte. Enthält die Farben des aktuellen Dokuments.|  
|`m_nColumns`|Eine ganze Zahl. Enthält die Anzahl der Spalten im Raster der Farben in der Menübefehl für die Auswahl einer Farbe angezeigt.|  
|`m_pPalette`|Ein Zeiger auf eine [CPalette](../../mfc/reference/cpalette-class.md). Enthält die Farben, die in der aktuellen Farbe Auswahlmenü verfügbar sind.|  
|`m_pPopup`|Ein Zeiger auf eine [CMFCColorPopupMenu Klasse](../../mfc/reference/cmfccolorpopupmenu-class.md) Objekt. Die Farbe Auswahlmenü, das angezeigt wird, wenn Sie auf die Farbschaltfläche klicken.|  
|`m_strAutoColorText`|Eine Zeichenfolge. Die Bezeichnung der Schaltfläche "automatisch" in der Menübefehl für die Auswahl einer Farbe.|  
|`m_strDocColorsText`|Eine Zeichenfolge. Die Bezeichnung der Schaltfläche in einer Farbe Auswahlmenü, in dem die Farben angezeigt.|  
|`m_strOtherText`|Eine Zeichenfolge. Die Bezeichnung der "other"-Schaltfläche in der Menübefehl für die Auswahl einer Farbe.|  
  
## <a name="remarks"></a>Hinweise  
 Wird standardmäßig die `CMFCColorButton` Klasse verhält sich wie eine Schaltfläche, die ein Farben-Auswahldialogfeld wird geöffnet. Farben-Auswahldialogfeld enthält ein Array von kleine Schaltflächen und ein "other" Schaltfläche, die eine benutzerdefinierte Farbauswahl angezeigt. (Das Standardbetriebssystem "other" Schaltfläche ist mit der Bezeichnung **Weitere Farben**.) Wenn ein Benutzer eine neue Farbe wählt die `CMFCColorButton` Objekt die Änderung wiedergibt, und zeigt die ausgewählte Farbe.  
  
 Erstellen Sie eine Farbe Button-Steuerelement aus, entweder direkt im Code oder mithilfe der **ClassWizard** Tool und einer Dialogfeldvorlage. Wenn Sie direkt zu einer Farbe Button-Steuerelement erstellen, fügen Sie eine `CMFCColorButton` Variablen auf Ihre Anwendung, und rufen Sie dann den Konstruktor und `Create` Methoden die `CMFCColorButton` Objekt. Bei Verwendung der **ClassWizard**, Hinzufügen einer `CButton` -Variablen an die Anwendung, und ändern Sie den Typ der Variablen aus `CButton` auf `CMFCColorButton`.  
  
 Farben-Auswahldialogfeld ( [CMFCColorBar Klasse](../../mfc/reference/cmfccolorbar-class.md)) wird angezeigt, die [CMFCColorButton::OnShowColorPopup](#onshowcolorpopup) Methode, wenn das Framework Ruft die `OnLButtonDown` -Ereignishandler. Die [CMFCColorButton::OnShowColorPopup](#onshowcolorpopup) Methode kann überschrieben werden, um benutzerdefinierte Farbauswahl zu unterstützen.  
  
 Die `CMFCColorButton` Objekt benachrichtigt, die das übergeordnete Element, die eine Farbe geändert wird, indem er sendet eine `WM_COMMAND | BN_CLICKED` Benachrichtigung. Das übergeordnete Element verwendet die [CMFCColorButton::GetColor](#getcolor) Methode, um die aktuelle Farbe abzurufen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie eine farbenschaltfläche konfigurieren mithilfe verschiedener Methoden in der `CMFCColorButton` Klasse. Die Methoden legen Sie die Farbe der Schaltfläche für die Farbe und die Anzahl der Spalten, und aktivieren Sie die automatische und die anderen Schaltflächen. In diesem Beispiel ist Teil der [Status Leiste Demobeispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StatusBarDemo#10](../../mfc/reference/codesnippet/cpp/cmfccolorbutton-class_1.h)]  
[!code-cpp[NVC_MFC_StatusBarDemo#11](../../mfc/reference/codesnippet/cpp/cmfccolorbutton-class_2.cpp)]  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcolorbutton.h  
  
##  <a name="cmfccolorbutton"></a>  CMFCColorButton::CMFCColorButton  
 Erstellt ein neues `CMFCColorButton`-Objekt.  
  
```  
CMFCColorButton();
```  
  
##  <a name="enableautomaticbutton"></a>  CMFCColorButton::EnableAutomaticButton  
 Aktivieren Sie oder deaktivieren Sie die Schaltfläche "Automatische", der ein Farben-Auswahlsteuerelement, und legen Sie die automatisch (Standard)-Farbe.  
  
```  
void EnableAutomaticButton(
    LPCTSTR lpszLabel,  
    COLORREF colorAutomatic,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszLabel`  
 Gibt die automatische Schaltflächentext an.  
  
 [in] `colorAutomatic`  
 Ein RGB-Wert, der Schaltfläche "automatisch" die Standardfarbe angibt.  
  
 [in] `bEnable`  
 Gibt an, ob die Schaltfläche "Automatische" aktiviert oder deaktiviert ist.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="enableotherbutton"></a>  CMFCColorButton::EnableOtherButton  
 Aktivieren Sie oder deaktivieren Sie die Schaltfläche "other", die unterhalb der regulären Farbe Schaltflächen angezeigt wird.  
  
```  
void EnableOtherButton(
    LPCTSTR lpszLabel,  
    BOOL bAltColorDlg=TRUE,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszLabel`  
 Gibt an, der Text der Schaltfläche.  
  
 [in] `bAltColorDlg`  
 Gibt an, ob die [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) Dialogfeld oder im Dialogfeld Farbe System wird geöffnet, wenn der Benutzer auf die Schaltfläche klickt.  
  
 [in] `bEnable`  
 Gibt an, ob die Schaltfläche "Sonstige" aktiviert oder deaktiviert ist.  
  
### <a name="remarks"></a>Hinweise  
 Klicken Sie auf die "other" Schaltfläche, um ein Dialogfeld anzuzeigen. Wenn die *bAltColorDlg* Parameter ist `TRUE`, die [CMFCColorDialog Klasse](../../mfc/reference/cmfccolordialog-class.md) wird angezeigt; andernfalls wird das Dialogfeld Farbe angezeigt.  
  
##  <a name="getautomaticcolor"></a>  CMFCColorButton::GetAutomaticColor  
 Ruft die aktuelle automatisch (Standard)-Farbe ab.  
  
```  
COLORREF GetAutomaticColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 RGB-Wert, der die aktuelle Farbe darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Die aktuelle Farbe wird festgelegt, indem die [CMFCColorButton::EnableAutomaticButton](#enableautomaticbutton) Methode.  
  
##  <a name="getcolor"></a>  CMFCColorButton::GetColor  
 Ruft die zurzeit ausgewählte Farbe ab.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 RGB-Wert.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isdrawxptheme"></a>  CMFCColorButton::IsDrawXPTheme  
 Gibt an, ob die Schaltfläche für die aktuelle Farbe in den visuellen Stil von Windows XP angezeigt wird.  
  
```  
BOOL IsDrawXPTheme() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn visuelle Stile werden unterstützt, und die Schaltfläche für die aktuelle Farbe, in den visuellen Stil von Windows XP angezeigt wird; andernfalls `FALSE`.  
  
##  <a name="m_benabledincustomizemode"></a>  CMFCColorButton::m_bEnabledInCustomizeMode  
 Legt eine farbenschaltfläche auf Anpassungsmodus fest.  
  
```  
BOOL m_bEnabledInCustomizeMode;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie eine Anpassung Dialogseite eine farbenschaltfläche hinzu (oder ermöglicht dem Benutzer eine andere Farbe Auswahl während der Anpassung) möchten, aktivieren Sie die Schaltfläche mit den durch Festlegen der `m_bEnabledInCustomizeMode` Element `TRUE`. Standardmäßig wird bei diesem Member festgelegt `FALSE`.  
  
##  <a name="ondraw"></a>  CMFCColorButton::OnDraw  
 Wird aufgerufen, durch das Framework um ein Bild der Schaltfläche zu rendern.  
  
```  
virtual void OnDraw(
    CDC* pDC,  
    const CRect& rect,  
    UINT uiState);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Verweist auf den Gerätekontext, der verwendet wird, um das Bild der Schaltfläche zu rendern.  
  
 [in] `rect`  
 Ein Rechteck, das die Schaltfläche "" umschließt.  
  
 [in] `uiState`  
 Gibt den visuellen Status der Schaltfläche.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, um das Rendern zu passen.  
  
##  <a name="ondrawborder"></a>  CMFCColorButton::OnDrawBorder  
 Wird aufgerufen, durch das Framework den Rahmen der Schaltfläche angezeigt.  
  
```  
virtual void OnDrawBorder(
    CDC* pDC,  
    CRect& rectClient,  
    UINT uiState);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Verweist auf den Gerätekontext, der zum Zeichnen des Rahmens.  
  
 [in] `rectClient`  
 Ein Rechteck in den Gerätekontext, der durch angegeben ist das der `pDC` Parameter, der die Begrenzungen der Schaltfläche gezeichnet werden definiert.  
  
 [in] `uiState`  
 Gibt den visuellen Status der Schaltfläche.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, um die Farbschaltfläche Rahmen Darstellung anpassen.  
  
##  <a name="ondrawfocusrect"></a>  CMFCColorButton::OnDrawFocusRect  
 Wird aufgerufen, durch das Framework ein Fokusrechteck an, wenn die Schaltfläche "" den Fokus besitzt.  
  
```  
virtual void OnDrawFocusRect(
    CDC* pDC,  
    const CRect& rectClient);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Verweist auf den Gerätekontext, der zum Zeichnen des Fokusrechtecks verwendet.  
  
 [in] `rectClient`  
 Ein Rechteck in den Gerätekontext, der gemäß der `pDC` Parameter, der die Begrenzungen der Schaltfläche definiert.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, um die Darstellung des Systemfokusrechtecks anpassen.  
  
##  <a name="onshowcolorpopup"></a>  CMFCColorButton::OnShowColorPopup  
 Wird aufgerufen, bevor der Farbleiste Popupfenster angezeigt wird.  
  
```  
virtual void OnShowColorPopup();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="rebuildpalette"></a>  CMFCColorButton::RebuildPalette  
 Initialisiert die `m_pPalette` Datenmember der angegebenen Palette oder das System Standardpalette geschützt.  
  
```  
void RebuildPalette(CPalette* pPal);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `pPal`|Ein Zeiger auf eine logische Palette oder `NULL`. Wenn `NULL`, die Standardpalette-System verwendet wird.|  
  
##  <a name="setcolor"></a>  CMFCColorButton::SetColor  
 Gibt die Farbe der Schaltfläche.  
  
```  
void SetColor(COLORREF color);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `color`  
 RGB-Wert.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setcolorname"></a>  CMFCColorButton::SetColorName  
 Gibt den Namen einer Farbe.  
  
```  
static void SetColorName(
    COLORREF color,  
    const CString& strName);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `color`  
 Die Farbe RGB-Wert.  
  
 [in] `strName`  
 Der Name der Farbe.  
  
### <a name="remarks"></a>Hinweise  
 Die Liste der Farbnamen ist global pro Anwendung. Diese Methode überträgt folglich die Parameter an [CMFCColorBar::SetColorName](../../mfc/reference/cmfccolorbar-class.md#setcolorname).  
  
##  <a name="setcolumnsnumber"></a>  CMFCColorButton::SetColumnsNumber  
 Definiert die Anzahl der Spalten, die in der Tabelle der Farben angezeigt werden, die dem Benutzer, während der Benutzer Farbe Auswahlprozesses verwendet werden angezeigt werden.  
  
```  
void SetColumnsNumber(int nColumns);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nColumns`  
 Gibt die Anzahl der Spalten an.  
  
### <a name="remarks"></a>Hinweise  
 Der Benutzer kann eine Farbe aus einer Popup-Farbleiste auszuwählen, in dem eine Tabelle mit vordefinierter Farben angezeigt. Verwenden Sie diese Methode, um die Anzahl der Spalten in der Tabelle zu definieren.  
  
##  <a name="setdocumentcolors"></a>  CMFCColorButton::SetDocumentColors  
 Gibt einen Satz von Farben und den Namen des Satzes an. Der Satz von Farben wird angezeigt, mit einem [CMFCColorBar Klasse](../../mfc/reference/cmfccolorbar-class.md) Objekt.  
  
```  
void SetDocumentColors(
    LPCTSTR lpszLabel,  
    CList<COLORREF,COLORREF>& lstColors);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszLabel`  
 Gibt die Bezeichnung, die mit dem Satz von Dokumentfarben angezeigt werden.  
  
 [in] `lstColors`  
 Ein Verweis auf eine Liste mit RGB-Werten.  
  
### <a name="remarks"></a>Hinweise  
 Ein `CMFCColorButton` Objekt verwaltet eine Liste mit RGB-Werten, die zum Übertragen einer [CMFCColorBar Klasse](../../mfc/reference/cmfccolorbar-class.md) Objekt. Wenn der Farbleiste angezeigt wird, werden diese Farben angezeigt, in einem speziellen Abschnitt, dessen Bezeichnung, indem angegeben wird, die `lpszLabel` Parameter.  
  
##  <a name="setpalette"></a>  CMFCColorButton::SetPalette  
 Gibt die standardmäßigen Farben auf die Farbleiste Popupfenster angezeigt werden sollen.  
  
```  
void SetPalette(CPalette* pPalette);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pPalette`  
 Ein Zeiger auf eine Farbpalette.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="sizetocontent"></a>  CMFCColorButton::SizeToContent  
 Das Schaltflächen-Steuerelement, um Text und Bild passt die Größe ändert.  
  
```  
virtual CSize SizeToContent(BOOL bCalcOnly=FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bCalcOnly`  
 Wert ungleich NULL ist, wird die neue Größe des Schaltflächensteuerelements jedoch die tatsächliche Größe wird nicht geändert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CSize` Objekt, das eine neue Größe für Schaltfläche Steuerelement angibt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="updatecolor"></a>  CMFCColorButton::UpdateColor  
 Vom Framework aufgerufen, wenn der Benutzer eine Farbe aus der Farbleiste, die angezeigt wird auswählt, wenn der Benutzer eine Farbe klickt.  
  
```  
virtual void UpdateColor(COLORREF color);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `color`  
 Ein vom Benutzer ausgewählten Farbe.  
  
### <a name="remarks"></a>Hinweise  
 Die `UpdateColor` Funktion ändert den aktuell ausgewählten Schaltflächenfarbe und benachrichtigt von seinem übergeordneten Element durch Senden einer `WM_COMMAND` -Nachricht mit einer `BN_CLICKED` standard Notification. Verwenden der [CMFCColorButton::GetColor](#getcolor) Methode, um die ausgewählte Farbe abzurufen.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCButton-Klasse](../../mfc/reference/cmfcbutton-class.md)   
 [CMFCColorBar-Klasse](../../mfc/reference/cmfccolorbar-class.md)   
 [CMFCColorButton::OnShowColorPopup](#onshowcolorpopup)   
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)   
 [CPalette-Klasse](../../mfc/reference/cpalette-class.md)   
 [CArray-Klasse](../../mfc/reference/carray-class.md)   
 [CList-Klasse](../../mfc/reference/clist-class.md)   
 [CString](../../atl-mfc-shared/reference/cstringt-class.md)
