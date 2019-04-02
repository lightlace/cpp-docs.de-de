---
title: CMFCColorButton-Klasse
ms.date: 11/04/2016
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
ms.openlocfilehash: c0c9ad79342f2013aa071240c684fce168e55c9e
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58780001"
---
# <a name="cmfccolorbutton-class"></a>CMFCColorButton-Klasse

Die `CMFCColorButton` und [CMFCColorBar-Klasse](../../mfc/reference/cmfccolorbar-class.md) Klassen werden zusammen verwendet, um ein Farben-Auswahlsteuerelement zu implementieren.

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
|[CMFCColorButton::EnableAutomaticButton](#enableautomaticbutton)|Aktiviert und deaktiviert eine "Automatische"-Schaltfläche, die über den regulären Farbe Schaltflächen positioniert ist. (Die standardmäßige automatische Schaltfläche ist mit der Bezeichnung **automatische**.)|
|[CMFCColorButton::EnableOtherButton](#enableotherbutton)|Aktiviert und deaktiviert eine "other"-Schaltfläche, die unter den regulären Farbe Schaltflächen positioniert ist. (Das Standardbetriebssystem "other" Schaltfläche ist mit **Weitere Farben**.)|
|[CMFCColorButton::GetAutomaticColor](#getautomaticcolor)|Ruft die aktuelle Farbe ab.|
|[CMFCColorButton::GetColor](#getcolor)|Ruft ab, der Farbe einer Schaltfläche.|
|[CMFCColorButton::SetColor](#setcolor)|Legt fest, der Farbe einer Schaltfläche.|
|[CMFCColorButton::SetColorName](#setcolorname)|Legt einen Namen für die Farbe fest.|
|[CMFCColorButton::SetColumnsNumber](#setcolumnsnumber)|Legt die Anzahl der Spalten im Dialogfeld die Farbe fest.|
|[CMFCColorButton::SetDocumentColors](#setdocumentcolors)|Gibt eine Liste der für die spezifischen-Farben, die auf das Dialogfeld Farbe Auswahl angezeigt werden.|
|[CMFCColorButton::SetPalette](#setpalette)|Gibt eine Palette von Farben für standardmäßige Anzeige an.|
|[CMFCColorButton::SizeToContent](#sizetocontent)|Ändert die Größe des Schaltflächen-Steuerelements, je nach Größe Text- und Bilddateien.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCColorButton::IsDrawXPTheme](#isdrawxptheme)|Gibt an, ob die Schaltfläche für die aktuelle Farbe im Stil von Windows XP angezeigt wird.|
|[CMFCColorButton::OnDraw](#ondraw)|Vom Framework aufgerufen, um ein Bild der Schaltfläche anzuzeigen.|
|[CMFCColorButton::OnDrawBorder](#ondrawborder)|Wird aufgerufen, durch das Framework der Rahmen der Schaltfläche angezeigt.|
|[CMFCColorButton::OnDrawFocusRect](#ondrawfocusrect)|Wird aufgerufen, durch das Framework um ein Fokusrechteck anzuzeigen, wenn die Schaltfläche mit den Schwerpunkt besitzt.|
|[CMFCColorButton::OnShowColorPopup](#onshowcolorpopup)|Vom Framework aufgerufen, wenn das Dialogfeld Farbe Auswahl ist, angezeigt wird.|
|[CMFCColorButton::RebuildPalette](#rebuildpalette)|Initialisiert die `m_pPalette` Datenmember der angegebenen Palette oder der Systempalette standardmäßig geschützt.|
|[CMFCColorButton::UpdateColor](#updatecolor)|Vom Framework aufgerufen, wenn der Benutzer eine Farbe aus der Palette der Color-Auswahldialogfeld auswählt.|

### <a name="data-members"></a>Datenmember

|Name|Beschreibung|
|----------|-----------------|
|`m_bAltColorDlg`|Ein boolescher Wert. Bei "true", zeigt das Framework die [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) Farbe Dialogfeld bei der *andere* Schaltfläche geklickt wird, oder False gibt an, das System color-Dialogfeld. Der Standardwert ist "true". Weitere Informationen finden Sie unter [CMFCColorButton::EnableOtherButton](#enableotherbutton).|
|`m_bAutoSetFocus`|Ein boolescher Wert. Bei "true", wird das Framework der Fokus auf das Menü "Farbe", wenn Sie im Menü angezeigt wird oder wenn "FALSE" den Fokus nicht ändert. Der Standardwert ist "true".|
|[CMFCColorButton::m_bEnabledInCustomizeMode](#m_benabledincustomizemode)|Gibt an, ob für die Schaltfläche "Farbe" Anpassungsmodus aktiviert ist.|
|`m_Color`|Ein [COLORREF](/windows/desktop/gdi/colorref) Wert. Enthält die zurzeit ausgewählte Farbe an.|
|`m_ColorAutomatic`|Ein [COLORREF](/windows/desktop/gdi/colorref) Wert. Enthält die derzeit ausgewählten Standardfarbe.|
|`m_Colors`|Ein [CArray](../../mfc/reference/carray-class.md) von [COLORREF](/windows/desktop/gdi/colorref) Werte. Enthält die derzeit verfügbaren Farben an.|
|`m_lstDocColors`|Ein [CList](../../mfc/reference/clist-class.md) von [COLORREF](/windows/desktop/gdi/colorref) Werte. Enthält die Farben des aktuellen Dokuments.|
|`m_nColumns`|Eine ganze Zahl. Enthält die Anzahl der Spalten im Raster der Farben in einer Farbe Auswahlmenü angezeigt werden sollen.|
|`m_pPalette`|Ein Zeiger auf eine [CPalette](../../mfc/reference/cpalette-class.md). Enthält die Farben, die in der aktuellen Farbe Auswahlmenü verfügbar sind.|
|`m_pPopup`|Ein Zeiger auf eine [CMFCColorPopupMenu-Klasse](../../mfc/reference/cmfccolorpopupmenu-class.md) Objekt. Klicken Sie im Menü der Color-Auswahl, das angezeigt wird, wenn Sie auf die Schaltfläche "Farbe" klicken.|
|`m_strAutoColorText`|Eine Zeichenfolge. Die Bezeichnung der Schaltfläche in einem Farbe Auswahlmenü "automatisch".|
|`m_strDocColorsText`|Eine Zeichenfolge. Die Bezeichnung der Schaltfläche in einem Menü der Color-Auswahl, die die Farben anzeigt.|
|`m_strOtherText`|Eine Zeichenfolge. Die Bezeichnung der "other"-Schaltfläche in einem Auswahlmenü Farbe.|

## <a name="remarks"></a>Hinweise

In der Standardeinstellung die `CMFCColorButton` -Klasse verhält sich wie eine Schaltfläche, die ein Farben-Auswahldialogfeld wird geöffnet. Das Dialogfeld Farbe Auswahl enthält ein Array von kleinen Farbe Schaltflächen und ein "other"-Schaltfläche, die eine benutzerdefinierte Farbauswahl angezeigt. (Das Standardbetriebssystem "other" Schaltfläche ist mit **Weitere Farben**.) Wenn ein Benutzer eine neue Farbe, wählt die `CMFCColorButton` Objekt gibt die Änderung wieder und zeigt die ausgewählte Farbe.

Erstellen Sie ein Schaltflächen-Steuerelement von Farbe, entweder direkt im Code oder mithilfe der **ClassWizard** Tool und eine Dialogfeldvorlage. Wenn Sie ein Schaltflächen-Steuerelement Farbe direkt erstellen, fügen Sie eine `CMFCColorButton` Variablen zu Ihrer Anwendung, und rufen Sie dann den Konstruktor und `Create` Methoden der `CMFCColorButton` Objekt. Bei Verwendung der **ClassWizard**, Hinzufügen einer `CButton` Variablen Ihrer Anwendung und ändern Sie dann auf den Typ der Variablen vom `CButton` zu `CMFCColorButton`.

Die Farben-Auswahldialogfeld ( [CMFCColorBar-Klasse](../../mfc/reference/cmfccolorbar-class.md)) wird angezeigt, die [CMFCColorButton::OnShowColorPopup](#onshowcolorpopup) Methode, wenn das Framework Ruft die `OnLButtonDown` -Ereignishandler. Die [CMFCColorButton::OnShowColorPopup](#onshowcolorpopup) Methode kann überschrieben werden, um benutzerdefinierte Farbauswahl zu unterstützen.

Die `CMFCColorButton` Objekt benachrichtigt das übergeordnete Element, die eine Farbe geändert wird, durch Senden einer WM_COMMAND | BN_CLICKED-Benachrichtigung. Das übergeordnete Element verwendet die [CMFCColorButton::GetColor](#getcolor) Methode, um die aktuelle Farbe abzurufen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie eine Schaltfläche "Farbe" zu konfigurieren, indem Sie mithilfe verschiedener Methoden in der `CMFCColorButton` Klasse. Die Methoden legen Sie die Farbe der Schaltfläche für die Farbe und die Anzahl der Spalten, und aktivieren Sie die automatische und die anderen Schaltflächen. In diesem Beispiel ist Teil der [Status Leiste Demobeispiel](../../overview/visual-cpp-samples.md).

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

Aktivieren Sie oder deaktivieren Sie die Schaltfläche "Automatische", der ein Farben-Auswahlsteuerelement, und legen Sie die Farbe automatisch (Standard).

```
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parameter

*lpszLabel*<br/>
[in] Gibt die automatische Schaltfläche Text an.

*colorAutomatic*<br/>
[in] Ein RGB-Wert, der angibt, die automatische Schaltfläche Standardfarbe.

*bEnable*<br/>
[in] Gibt an, ob die automatische Schaltfläche aktiviert oder deaktiviert ist.

### <a name="remarks"></a>Hinweise

##  <a name="enableotherbutton"></a>  CMFCColorButton::EnableOtherButton

Aktivieren Sie oder deaktivieren Sie die Schaltfläche "other", in die folgenden regulären Farbe Schaltflächen angezeigt wird.

```
void EnableOtherButton(
    LPCTSTR lpszLabel,
    BOOL bAltColorDlg=TRUE,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parameter

*lpszLabel*<br/>
[in] Gibt an, der Text der Schaltfläche.

*bAltColorDlg*<br/>
[in] Gibt an, ob die [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) im Dialogfeld bzw. im Dialogfeld Farbe System wird geöffnet, wenn der Benutzer auf die Schaltfläche klickt.

*bEnable*<br/>
[in] Gibt an, ob die Schaltfläche "other" aktiviert oder deaktiviert ist.

### <a name="remarks"></a>Hinweise

Klicken Sie auf der "other" Schaltfläche, um ein Dialogfeld anzuzeigen. Wenn die *bAltColorDlg* Parameter TRUE ist, die [CMFCColorDialog-Klasse](../../mfc/reference/cmfccolordialog-class.md) angezeigt wird; andernfalls wird das Dialogfeld Farbe angezeigt.

##  <a name="getautomaticcolor"></a>  CMFCColorButton::GetAutomaticColor

Ruft die aktuelle Farbe für die automatisch (Standard) ab.

```
COLORREF GetAutomaticColor() const;
```

### <a name="return-value"></a>Rückgabewert

Ein RGB-Wert, der die aktuelle Farbe darstellt.

### <a name="remarks"></a>Hinweise

Die aktuelle Farbe festgelegt ist, indem die [CMFCColorButton::EnableAutomaticButton](#enableautomaticbutton) Methode.

##  <a name="getcolor"></a>  CMFCColorButton::GetColor

Ruft ab, die zurzeit ausgewählte Farbe.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Rückgabewert

Ein RGB-Wert.

### <a name="remarks"></a>Hinweise

##  <a name="isdrawxptheme"></a>  CMFCColorButton::IsDrawXPTheme

Gibt an, ob die Schaltfläche für die aktuelle Farbe im Stil von Windows XP angezeigt wird.

```
BOOL IsDrawXPTheme() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn visuelle Stile werden unterstützt, und die Schaltfläche für die aktuelle Farbe, in den visuellen Stil von Windows XP angezeigt wird. andernfalls "false".

##  <a name="m_benabledincustomizemode"></a>  CMFCColorButton::m_bEnabledInCustomizeMode

Legt eine farbenschaltfläche auf Anpassungsmodus fest.

```
BOOL m_bEnabledInCustomizeMode;
```

### <a name="remarks"></a>Hinweise

Wenn Sie eine Schaltfläche "Farbe" auf der Seite eine Anpassung hinzufügen (oder dem Benutzer ermöglichen, stellen eine andere Auswahl während der Anpassung) möchten, aktivieren Sie die Schaltfläche mit den durch Festlegen der `m_bEnabledInCustomizeMode` Member auf "true". Standardmäßig ist dieser Member auf "false" festgelegt.

##  <a name="ondraw"></a>  CMFCColorButton::OnDraw

Wird aufgerufen, durch das Framework ein Bild auf der Schaltfläche gerendert.

```
virtual void OnDraw(
    CDC* pDC,
    const CRect& rect,
    UINT uiState);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
[in] Verweist auf den Gerätekontext, der verwendet wird, um das Bild der Schaltfläche zu rendern.

*rect*<br/>
[in] Ein Rechteck, das die Schaltfläche mit den umschließt.

*uiState*<br/>
[in] Gibt den visuellen Zustand der Schaltfläche an.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode, um den Renderingprozess anpassen.

##  <a name="ondrawborder"></a>  CMFCColorButton::OnDrawBorder

Wird aufgerufen, durch das Framework die Rahmen der Schaltfläche angezeigt.

```
virtual void OnDrawBorder(
    CDC* pDC,
    CRect& rectClient,
    UINT uiState);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
[in] Verweist auf den Gerätekontext zum Zeichnen des Rahmens.

*rectClient*<br/>
[in] Ein Rechteck, in den Gerätekontext, die angegeben wird die *pDC* Parameter, der definiert, die Grenzen der Schaltfläche gezeichnet werden soll.

*uiState*<br/>
[in] Gibt den visuellen Zustand der Schaltfläche an.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Funktion zum Anpassen der Darstellung der Schaltfläche für die Farbe an.

##  <a name="ondrawfocusrect"></a>  CMFCColorButton::OnDrawFocusRect

Wird aufgerufen, durch das Framework um ein Fokusrechteck anzuzeigen, wenn die Schaltfläche den Fokus besitzt.

```
virtual void OnDrawFocusRect(
    CDC* pDC,
    const CRect& rectClient);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
[in] Verweist auf den Gerätekontext verwendet, um das Fokusrechteck gezeichnet werden soll.

*rectClient*<br/>
[in] Ein Rechteck, in den Gerätekontext, die gemäß der *pDC* Parameter, der die Grenzen der Schaltfläche definiert.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode, um die Darstellung des Fokusrechtecks anpassen.

##  <a name="onshowcolorpopup"></a>  CMFCColorButton::OnShowColorPopup

Wird aufgerufen, bevor die popupfarbleiste angezeigt wird.

```
virtual void OnShowColorPopup();
```

### <a name="remarks"></a>Hinweise

##  <a name="rebuildpalette"></a>  CMFCColorButton::RebuildPalette

Initialisiert die `m_pPalette` Datenmember der angegebenen Palette oder der Systempalette standardmäßig geschützt.

```
void RebuildPalette(CPalette* pPal);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*pPal*|[in] Ein Zeiger auf eine logische Palette, oder NULL. Wenn der Wert NULL ist, wird die Standardpalette-System verwendet.|

##  <a name="setcolor"></a>  CMFCColorButton::SetColor

Gibt die Farbe der Schaltfläche.

```
void SetColor(COLORREF color);
```

### <a name="parameters"></a>Parameter

*color*<br/>
[in] Ein RGB-Wert.

### <a name="remarks"></a>Hinweise

##  <a name="setcolorname"></a>  CMFCColorButton::SetColorName

Gibt den Namen einer Farbe.

```
static void SetColorName(
    COLORREF color,
    const CString& strName);
```

### <a name="parameters"></a>Parameter

*color*<br/>
[in] Die Farbe der RGB-Wert.

*strName*<br/>
[in] Der Name der Farbe.

### <a name="remarks"></a>Hinweise

Die Liste der Farben ist global pro Anwendung. Diese Methode überträgt daher Parameter [CMFCColorBar::SetColorName](../../mfc/reference/cmfccolorbar-class.md#setcolorname).

##  <a name="setcolumnsnumber"></a>  CMFCColorButton::SetColumnsNumber

Definiert die Anzahl der Spalten, die in der Tabelle der Farben angezeigt werden, die dem Benutzer beim Auswahlprozess für den Benutzer Farbe angezeigt werden.

```
void SetColumnsNumber(int nColumns);
```

### <a name="parameters"></a>Parameter

*nColumns*<br/>
[in] Gibt die Anzahl der Spalten an.

### <a name="remarks"></a>Hinweise

Der Benutzer kann eine Farbe aus einer popupfarbleiste auswählen, die eine Tabelle mit vordefinierter Farben anzeigt. Verwenden Sie diese Methode, um die Anzahl der Spalten in der Tabelle zu definieren.

##  <a name="setdocumentcolors"></a>  CMFCColorButton::SetDocumentColors

Gibt einen Satz von Farben und den Namen des Satzes. Der Satz von Farben wird angezeigt, mit einem [CMFCColorBar-Klasse](../../mfc/reference/cmfccolorbar-class.md) Objekt.

```
void SetDocumentColors(
    LPCTSTR lpszLabel,
    CList<COLORREF,COLORREF>& lstColors);
```

### <a name="parameters"></a>Parameter

*lpszLabel*<br/>
[in] Gibt die Bezeichnung, die mit dem Satz von Dokumentfarben angezeigt werden.

*lstColors*<br/>
[in] Ein Verweis auf eine Liste mit RGB-Werten.

### <a name="remarks"></a>Hinweise

Ein `CMFCColorButton` Objekt verwaltet eine Liste mit RGB-Werte, die zum übertragen werden eine [CMFCColorBar-Klasse](../../mfc/reference/cmfccolorbar-class.md) Objekt. Wenn der Farbleiste angezeigt wird, werden diese Farben angezeigt, in einen speziellen Bereich, dessen Bezeichnung, indem angegeben wird, die *LpszLabel* Parameter.

##  <a name="setpalette"></a>  CMFCColorButton::SetPalette

Gibt die standardmäßigen Farben, die auf die popupfarbleiste angezeigt.

```
void SetPalette(CPalette* pPalette);
```

### <a name="parameters"></a>Parameter

*pPalette*<br/>
[in] Ein Zeiger auf eine Farbpalette.

### <a name="remarks"></a>Hinweise

##  <a name="sizetocontent"></a>  CMFCColorButton::SizeToContent

Ändert die Größe der Schaltflächen-Steuerelement, entsprechend der Text- und Bilddateien.

```
virtual CSize SizeToContent(BOOL bCalcOnly=FALSE);
```

### <a name="parameters"></a>Parameter

*bCalcOnly*<br/>
[in] Wert ungleich NULL wird die neue Größe des Button-Steuerelements wird berechnet, aber die tatsächliche Größe wird nicht geändert.

### <a name="return-value"></a>Rückgabewert

Ein `CSize` Objekt, das eine neue Größe der Schaltfläche Steuerelement angibt.

### <a name="remarks"></a>Hinweise

##  <a name="updatecolor"></a>  CMFCColorButton::UpdateColor

Vom Framework aufgerufen, wenn der Benutzer eine Farbe aus der Farbleiste, die anzeigt auswählt, wenn der Benutzer die Schaltfläche "Farbe" klickt.

```
virtual void UpdateColor(COLORREF color);
```

### <a name="parameters"></a>Parameter

*color*<br/>
[in] Eine Farbe, die vom Benutzer ausgewählt wurde.

### <a name="remarks"></a>Hinweise

Die `UpdateColor` -Funktion ändert sich der aktuell ausgewählten Schaltfläche die Farbe und benachrichtigt das übergeordnete Element durch Senden einer WM_COMMAND-Meldung mit einer standardmäßigen BN_CLICKED-Benachrichtigung. Verwenden der [CMFCColorButton::GetColor](#getcolor) Methode, um die ausgewählte Farbe abzurufen.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCButton-Klasse](../../mfc/reference/cmfcbutton-class.md)<br/>
[CMFCColorBar-Klasse](../../mfc/reference/cmfccolorbar-class.md)<br/>
[CMFCColorButton::OnShowColorPopup](#onshowcolorpopup)<br/>
[COLORREF](/windows/desktop/gdi/colorref)<br/>
[CPalette-Klasse](../../mfc/reference/cpalette-class.md)<br/>
[CArray-Klasse](../../mfc/reference/carray-class.md)<br/>
[CList-Klasse](../../mfc/reference/clist-class.md)<br/>
[CString](../../atl-mfc-shared/reference/cstringt-class.md)
