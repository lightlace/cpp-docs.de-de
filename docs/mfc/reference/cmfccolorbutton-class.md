---
title: Klasse CMFCColorButton | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- CMFCColorButton::m_Color data member
- CMFCColorButton::m_bAutoSetFocus data member
- CMFCColorButton::m_pPopup data member
- CMFCColorButton::m_nColumns data member
- CMFCColorButton class
- CMFCColorButton::m_strAutoColorText data member
- CMFCColorButton::m_bAltColorDlg data member
- CMFCColorButton::m_strDocColorsText data member
- CMFCColorButton::m_strOtherText data member
- CMFCColorButton::m_pPalette data member
- CMFCColorButton::m_lstDocColors data member
- CMFCColorButton::m_ColorAutomatic data member
ms.assetid: 9fdf34ae-4cc5-4c5e-9d89-1c50e8a73699
caps.latest.revision: 34
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
ms.openlocfilehash: 6a9290d396c8ce5ccafa2ae556b21ff89806d830
ms.lasthandoff: 02/24/2017

---
# <a name="cmfccolorbutton-class"></a>CMFCColorButton-Klasse
Die `CMFCColorButton` und [CMFCColorBar Klasse](../../mfc/reference/cmfccolorbar-class.md) Klassen werden zusammen verwendet, um ein Farben-Auswahlsteuerelement zu implementieren.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCColorButton : public CMFCButton  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCColorButton::CMFCColorButton](#cmfccolorbutton)|Erstellt ein neues `CMFCColorButton`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCColorButton::EnableAutomaticButton](#enableautomaticbutton)|Aktiviert und deaktiviert eine 'Automatische' Schaltfläche, die über die normale Schaltflächen positioniert ist. ("Automatisch" Standardsystem ist mit der Bezeichnung **automatische**.)|  
|[CMFCColorButton::EnableOtherButton](#enableotherbutton)|Aktiviert und deaktiviert eine "other"-Schaltfläche, die unter die normale Schaltflächen positioniert ist. (Das Standardbetriebssystem "other" Schaltfläche hat die Bezeichnung **Weitere Farben... **.)|  
|[CMFCColorButton::GetAutomaticColor](#getautomaticcolor)|Ruft die aktuelle Farbe ab.|  
|[CMFCColorButton::GetColor](#getcolor)|Ruft die Farbe einer Schaltfläche.|  
|[CMFCColorButton::SetColor](#setcolor)|Legt die Farbe einer Schaltfläche fest.|  
|[CMFCColorButton::SetColorName](#setcolorname)|Legt den Namen einer Farbe.|  
|[CMFCColorButton::SetColumnsNumber](#setcolumnsnumber)|Legt die Anzahl der Spalten im Dialogfeld die Farbe fest.|  
|[CMFCColorButton::SetDocumentColors](#setdocumentcolors)|Gibt eine Liste der für die spezifischen Farben, die auf das Dialogfeld Auswahl einer Farbe angezeigt werden.|  
|[CMFCColorButton::SetPalette](#setpalette)|Gibt eine Palette mit Farben Standardanzeige an.|  
|[CMFCColorButton::SizeToContent](#sizetocontent)|Ändert die Größe des Steuerelements, abhängig von der Größe von Text- und Bilddaten.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCColorButton::IsDrawXPTheme](#isdrawxptheme)|Gibt an, ob die Schaltfläche für die aktuelle Farbe im Stil von Windows XP angezeigt wird.|  
|[CMFCColorButton::OnDraw](#ondraw)|Aufgerufen, um ein Bild der Schaltfläche anzuzeigen.|  
|[CMFCColorButton::OnDrawBorder](#ondrawborder)|Aufgerufen, um der Schaltfläche Rahmen anzuzeigen.|  
|[CMFCColorButton::OnDrawFocusRect](#ondrawfocusrect)|Vom Framework aufgerufen wird ein Fokusrechteck an, wenn die Schaltfläche einen Fokus hat.|  
|[CMFCColorButton::OnShowColorPopup](#onshowcolorpopup)|Vom Framework aufgerufen, wird das Dialogfeld Auswahl einer Farbe angezeigt werden soll.|  
|[CMFCColorButton::RebuildPalette](#rebuildpalette)|Initialisiert den `m_pPalette` -Datenmember auf die angegebene Palette oder die System-Standardpalette geschützt.|  
|[CMFCColorButton::UpdateColor](#updatecolor)|Vom Framework aufgerufen, wenn der Benutzer eine Farbe aus der Palette der Farben-Auswahldialogfeld auswählt.|  
  
### <a name="data-members"></a>Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`m_bAltColorDlg`|Ein boolescher Wert. Wenn `TRUE`, zeigt das Framework die [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) Farbe Dialogfeld beim der *andere* Schaltfläche geklickt wird, oder wenn `FALSE`, das Dialogfeld Farbe. Der Standardwert ist `TRUE`. Weitere Informationen finden Sie unter [CMFCColorButton::EnableOtherButton](#enableotherbutton).|  
|`m_bAutoSetFocus`|Ein boolescher Wert. Wenn `TRUE`, das Framework setzt den Fokus auf, wenn das Menü angezeigt wird, oder wenn `FALSE`, ändert sich den Fokus nicht. Der Standardwert ist `TRUE`.|  
|[CMFCColorButton::m_bEnabledInCustomizeMode](#m_benabledincustomizemode)|Gibt an, ob die farbenschaltfläche Anpassungsmodus aktiviert ist.|  
|`m_Color`|Ein [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Wert. Enthält die zurzeit ausgewählte Farbe an.|  
|`m_ColorAutomatic`|Ein [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Wert. Enthält die derzeit ausgewählte Farbe an.|  
|`m_Colors`|Ein [CArray](../../mfc/reference/carray-class.md) von [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Werte. Enthält die derzeit verfügbaren Farben.|  
|`m_lstDocColors`|Ein [CList](../../mfc/reference/clist-class.md) von [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Werte. Enthält die aktuellen Farben an.|  
|`m_nColumns`|Eine ganze Zahl. Enthält die Anzahl der Spalten im Raster der Farben in der Menübefehl für die Auswahl einer Farbe angezeigt.|  
|`m_pPalette`|Ein Zeiger auf eine [CPalette](../../mfc/reference/cpalette-class.md). Enthält die Farben, die in der aktuellen Farbe Auswahlmenü verfügbar sind.|  
|`m_pPopup`|Ein Zeiger auf eine [CMFCColorPopupMenu Klasse](../../mfc/reference/cmfccolorpopupmenu-class.md) Objekt. Auswahl im Farbe, die angezeigt wird, wenn Sie auf die Farbschaltfläche klicken.|  
|`m_strAutoColorText`|Eine Zeichenfolge. Die Bezeichnung der Schaltfläche 'automatic' in der Menübefehl für die Auswahl einer Farbe.|  
|`m_strDocColorsText`|Eine Zeichenfolge. Die Bezeichnung der Schaltfläche in einer Farbe Auswahlmenü, in dem die Farben angezeigt.|  
|`m_strOtherText`|Eine Zeichenfolge. Die Bezeichnung der "other"-Schaltfläche in der Menübefehl für die Auswahl einer Farbe.|  
  
## <a name="remarks"></a>Hinweise  
 In der Standardeinstellung die `CMFCColorButton` Klasse verhält sich wie eine Schaltfläche, die ein Farben-Auswahldialogfeld wird geöffnet. Das Dialogfeld Auswahl einer Farbe enthält ein Array von kleine Schaltflächen und ein "other" Schaltfläche, die eine benutzerdefinierte Farbauswahl anzeigt. (Das Standardbetriebssystem "other" Schaltfläche hat die Bezeichnung **Weitere Farben... **.) Wenn ein Benutzer eine neue Farbe, die `CMFCColorButton` -Objekt gibt die Änderung wieder und zeigt die ausgewählte Farbe an.  
  
 Erstellen von Steuerelementen zur Farbauswahl entweder direkt im Code oder mithilfe der **ClassWizard** Tool und einer Dialogfeldvorlage. Wenn Sie ein Button-Steuerelement Farbe direkt erstellen, fügen Sie eine `CMFCColorButton` Variablen auf Ihre Anwendung, und rufen Sie dann den Konstruktor und `Create` Methoden die `CMFCColorButton` Objekt. Bei Verwendung der **ClassWizard**, Hinzufügen einer `CButton` Variable für Ihre Anwendung, und ändern Sie den Typ der Variablen aus `CButton` zu `CMFCColorButton`.  
  
 Farben-Auswahldialogfeld ( [CMFCColorBar Klasse](../../mfc/reference/cmfccolorbar-class.md)) wird angezeigt, die [CMFCColorButton::OnShowColorPopup](#onshowcolorpopup) -Methode, wenn das Framework Ruft die `OnLButtonDown` -Ereignishandler. Die [CMFCColorButton::OnShowColorPopup](#onshowcolorpopup) Methode kann überschrieben werden, um benutzerdefinierte Farbauswahl zu unterstützen.  
  
 Die `CMFCColorButton` -Objekt benachrichtigt, die das übergeordnete Element, die eine Farbe geändert wird, indem er sendet eine `WM_COMMAND | BN_CLICKED` Benachrichtigung. Das übergeordnete Element verwendet die [CMFCColorButton::GetColor](#getcolor) Methode zum Abrufen der aktuellen Farbe.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie eine farbenschaltfläche zu konfigurieren, indem Sie mit verschiedenen Methoden in der `CMFCColorButton` Klasse. Die Methoden legen Sie die Farbe der Schaltfläche für die Farbe und die Anzahl der Spalten, und aktivieren Sie die automatische und die anderen Schaltflächen. Dieses Beispiel ist Teil der [Status Leiste Demobeispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StatusBarDemo&#10;](../../mfc/reference/codesnippet/cpp/cmfccolorbutton-class_1.h)]  
[!code-cpp[NVC_MFC_StatusBarDemo&#11;](../../mfc/reference/codesnippet/cpp/cmfccolorbutton-class_2.cpp)]  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcolorbutton.h  
  
##  <a name="cmfccolorbutton"></a>CMFCColorButton::CMFCColorButton  
 Erstellt ein neues `CMFCColorButton`-Objekt.  
  
```  
CMFCColorButton();
```  
  
##  <a name="enableautomaticbutton"></a>CMFCColorButton::EnableAutomaticButton  
 Aktivieren Sie oder deaktivieren Sie die Schaltfläche 'Automatische' ein Farben-Auswahlsteuerelement, und legen Sie die Farbe Automatic (Standard).  
  
```  
void EnableAutomaticButton(
    LPCTSTR lpszLabel,  
    COLORREF colorAutomatic,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszLabel`  
 Gibt die automatische Schaltfläche Text.  
  
 [in] `colorAutomatic`  
 RGB-Wert, der automatisch die Farbe der Schaltfläche Standard angibt.  
  
 [in] `bEnable`  
 Gibt an, ob die automatische Schaltfläche aktiviert oder deaktiviert ist.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="enableotherbutton"></a>CMFCColorButton::EnableOtherButton  
 Aktivieren Sie oder deaktivieren Sie die "other" Schaltfläche unterhalb der regulären Schaltflächen angezeigt wird.  
  
```  
void EnableOtherButton(
    LPCTSTR lpszLabel,  
    BOOL bAltColorDlg=TRUE,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszLabel`  
 Gibt den Text der Schaltfläche.  
  
 [in] `bAltColorDlg`  
 Gibt an, ob die [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) Dialogfeld oder das Dialogfeld Farbe wird geöffnet, wenn der Benutzer auf die Schaltfläche klickt.  
  
 [in] `bEnable`  
 Gibt an, ob die Schaltfläche "other" aktiviert oder deaktiviert ist.  
  
### <a name="remarks"></a>Hinweise  
 Klicken Sie auf die Schaltfläche "other" um ein Dialogfeld anzuzeigen. Wenn die *bAltColorDlg* Parameter ist `TRUE`, [CMFCColorDialog Klasse](../../mfc/reference/cmfccolordialog-class.md) wird angezeigt; andernfalls wird das Dialogfeld Farbe angezeigt.  
  
##  <a name="getautomaticcolor"></a>CMFCColorButton::GetAutomaticColor  
 Ruft die aktuelle Farbe Automatic (Standard).  
  
```  
COLORREF GetAutomaticColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein RGB-Wert, der die aktuelle Farbe darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Die aktuelle Farbe wird festgelegt, indem die [CMFCColorButton::EnableAutomaticButton](#enableautomaticbutton) Methode.  
  
##  <a name="getcolor"></a>CMFCColorButton::GetColor  
 Ruft die derzeit ausgewählte Farbe ab.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 RGB-Wert.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isdrawxptheme"></a>CMFCColorButton::IsDrawXPTheme  
 Gibt an, ob die Schaltfläche für die aktuelle Farbe im Stil von Windows XP angezeigt wird.  
  
```  
BOOL IsDrawXPTheme() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn visuelle Stile werden unterstützt, und die Schaltfläche für die aktuelle Farbe wird im Stil von Windows XP angezeigt. andernfalls `FALSE`.  
  
##  <a name="m_benabledincustomizemode"></a>CMFCColorButton::m_bEnabledInCustomizeMode  
 Legt eine Farbschaltfläche auf Anpassungsmodus fest.  
  
```  
BOOL m_bEnabledInCustomizeMode;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie eine Anpassung des Dialogfelds Seite eine farbenschaltfläche hinzufügen (oder den Benutzer eine andere Farbe Auswahl bei der Anpassung) möchten, aktivieren Sie die Schaltfläche, indem Sie die `m_bEnabledInCustomizeMode` Element `TRUE`. Standardmäßig ist dieser Member auf festgelegt `FALSE`.  
  
##  <a name="ondraw"></a>CMFCColorButton::OnDraw  
 Aufgerufen, um ein Bild der Schaltfläche zu rendern.  
  
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
 Ein Rechteck, das die Schaltfläche umschließt.  
  
 [in] `uiState`  
 Gibt den visuellen Zustand der Schaltfläche.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, um das Rendern zu anpassen.  
  
##  <a name="ondrawborder"></a>CMFCColorButton::OnDrawBorder  
 Aufgerufen, um die Rahmen der Schaltfläche anzuzeigen.  
  
```  
virtual void OnDrawBorder(
    CDC* pDC,  
    CRect& rectClient,  
    UINT uiState);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Verweist auf den Gerätekontext zum Zeichnen des Rahmens verwendet.  
  
 [in] `rectClient`  
 Ein Rechteck in den Gerätekontext, der durch angegeben ist die der `pDC` Parameter, definieren die Grenzen der Schaltfläche gezeichnet werden.  
  
 [in] `uiState`  
 Gibt den visuellen Zustand der Schaltfläche.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, um die der farbenschaltfläche Rahmen Darstellung anpassen.  
  
##  <a name="ondrawfocusrect"></a>CMFCColorButton::OnDrawFocusRect  
 Aufgerufen, um ein Fokusrechteck angezeigt wird, wenn die Schaltfläche den Fokus besitzt.  
  
```  
virtual void OnDrawFocusRect(
    CDC* pDC,  
    const CRect& rectClient);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Verweist auf den Gerätekontext zum Zeichnen des Fokusrechtecks verwendet.  
  
 [in] `rectClient`  
 Ein Rechteck in den angegebenen Gerätekontext der `pDC` -Parameter, der die Grenzen der Schaltfläche definiert.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, um die Darstellung des Fokusrechtecks anpassen.  
  
##  <a name="onshowcolorpopup"></a>CMFCColorButton::OnShowColorPopup  
 Aufgerufen, bevor der Farbleiste Popupfenster angezeigt wird.  
  
```  
virtual void OnShowColorPopup();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="rebuildpalette"></a>CMFCColorButton::RebuildPalette  
 Initialisiert den `m_pPalette` -Datenmember auf die angegebene Palette oder die System-Standardpalette geschützt.  
  
```  
void RebuildPalette(CPalette* pPal);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `pPal`|Ein Zeiger auf eine logische Palette oder `NULL`. Wenn `NULL`, die System-Standardpalette wird verwendet.|  
  
##  <a name="setcolor"></a>CMFCColorButton::SetColor  
 Gibt die Farbe der Schaltfläche.  
  
```  
void SetColor(COLORREF color);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `color`  
 RGB-Wert.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setcolorname"></a>CMFCColorButton::SetColorName  
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
 Name der Farbe.  
  
### <a name="remarks"></a>Hinweise  
 Die Liste der Farben ist global pro Anwendung. Diese Methode überträgt folglich seine Parameter [CMFCColorBar::SetColorName](../../mfc/reference/cmfccolorbar-class.md#setcolorname).  
  
##  <a name="setcolumnsnumber"></a>CMFCColorButton::SetColumnsNumber  
 Definiert die Anzahl der Spalten, die in der Tabelle der Farben angezeigt werden, die dem Benutzer bei Auswahl Farbe des Benutzers angezeigt wird.  
  
```  
void SetColumnsNumber(int nColumns);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nColumns`  
 Gibt die Anzahl der Spalten an.  
  
### <a name="remarks"></a>Hinweise  
 Der Benutzer kann eine Farbe aus einer Popup-Farbleiste auswählen, die eine Tabelle der vordefinierten Farben angezeigt. Verwenden Sie diese Methode, um die Anzahl der Spalten in der Tabelle zu definieren.  
  
##  <a name="setdocumentcolors"></a>CMFCColorButton::SetDocumentColors  
 Gibt einen Satz von Farben und Namen des Satzes. Der Satz von Farben wird angezeigt, mit einem [CMFCColorBar Klasse](../../mfc/reference/cmfccolorbar-class.md) Objekt.  
  
```  
void SetDocumentColors(
    LPCTSTR lpszLabel,  
    CList<COLORREF,COLORREF>& lstColors);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszLabel`  
 Gibt die Bezeichnung für den Satz von Dokumentfarben angezeigt werden.  
  
 [in] `lstColors`  
 Ein Verweis auf eine Liste der RGB-Werte.  
  
### <a name="remarks"></a>Hinweise  
 Ein `CMFCColorButton` Objekt verwaltet eine Liste der RGB-Werte, die zum Übertragen einer [CMFCColorBar Klasse](../../mfc/reference/cmfccolorbar-class.md) Objekt. Bei der Farbleiste angezeigt wird, werden diese Farben angezeigt, in einem speziellen Abschnitt, dessen Bezeichnung, indem angegeben wird, die `lpszLabel` Parameter.  
  
##  <a name="setpalette"></a>CMFCColorButton::SetPalette  
 Gibt die Standardfarben auf die Farbleiste Popup angezeigt.  
  
```  
void SetPalette(CPalette* pPalette);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pPalette`  
 Ein Zeiger auf eine Farbpalette.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="sizetocontent"></a>CMFCColorButton::SizeToContent  
 Ändert das Schaltflächen-Steuerelement, um Text und Bild passen.  
  
```  
virtual CSize SizeToContent(BOOL bCalcOnly=FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bCalcOnly`  
 Ein Wert ungleich NULL, die neue Größe des Button-Steuerelements wird berechnet, aber die tatsächliche Größe wird nicht geändert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CSize` Objekt, das eine neue Schaltfläche Steuerelementgröße angibt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="updatecolor"></a>CMFCColorButton::UpdateColor  
 Vom Framework aufgerufen, wenn der Benutzer eine Farbe aus der Farbleiste, die zeigt auswählt, wenn der Benutzer eine Farbe klickt.  
  
```  
virtual void UpdateColor(COLORREF color);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `color`  
 Ein vom Benutzer ausgewählten Farbe.  
  
### <a name="remarks"></a>Hinweise  
 Der `UpdateColor` Funktion ändert sich die Farbe der ausgewählten Schaltfläche und benachrichtigt das übergeordnete Element durch Senden einer `WM_COMMAND` -Nachricht mit einer `BN_CLICKED` standardbenachrichtigung. Verwenden der [CMFCColorButton::GetColor](#getcolor) Methode, um die ausgewählte Farbe abzurufen.  
  
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

