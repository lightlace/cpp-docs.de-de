---
title: Cmfccolorbutton-Klasse
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
ms.openlocfilehash: ac49957f075f8798607535286d6c4518c0eeeeae
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505358"
---
# <a name="cmfccolorbutton-class"></a>Cmfccolorbutton-Klasse

Die `CMFCColorButton` Klassen Klassen und [cmfccolorbar](../../mfc/reference/cmfccolorbar-class.md) werden verwendet, um ein Farbauswahl-Steuerelement zu implementieren.

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
|[CMFCColorButton::EnableAutomaticButton](#enableautomaticbutton)|Aktiviert und deaktiviert die Schaltfläche "automatisch", die über den regulären Farb Schaltflächen positioniert ist. (Die automatische Standard Schaltfläche des Systems wird **automatisch**bezeichnet.)|
|[CMFCColorButton::EnableOtherButton](#enableotherbutton)|Aktiviert und deaktiviert eine "andere" Schaltfläche, die unter den regulären Farb Schaltflächen positioniert ist. (Die Standard Schaltfläche "andere" des Systems ist mit **mehr Farben**gekennzeichnet.)|
|[CMFCColorButton::GetAutomaticColor](#getautomaticcolor)|Ruft die aktuelle automatische Farbe ab.|
|[CMFCColorButton::GetColor](#getcolor)|Ruft die Farbe einer Schaltfläche ab.|
|[CMFCColorButton::SetColor](#setcolor)|Legt die Farbe einer Schaltfläche fest.|
|[CMFCColorButton::SetColorName](#setcolorname)|Legt einen Farbnamen fest.|
|[CMFCColorButton::SetColumnsNumber](#setcolumnsnumber)|Legt die Anzahl der Spalten im Dialogfeld Farbauswahl fest.|
|[CMFCColorButton::SetDocumentColors](#setdocumentcolors)|Gibt eine Liste von Dokument spezifischen Farben an, die im Dialogfeld Farbauswahl angezeigt werden.|
|[CMFCColorButton::SetPalette](#setpalette)|Gibt eine Palette von Standard Anzeige Farben an.|
|[CMFCColorButton::SizeToContent](#sizetocontent)|Ändert die Größe des Schaltflächen-Steuer Elements, je nach Text und Bildgröße.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[Cmfccolorbutton:: isdrawxptheme](#isdrawxptheme)|Gibt an, ob die aktuelle Farb Schaltfläche im visuellen Stil von Windows XP angezeigt wird.|
|[CMFCColorButton::OnDraw](#ondraw)|Wird von Framework aufgerufen, um ein Bild der Schaltfläche anzuzeigen.|
|[CMFCColorButton::OnDrawBorder](#ondrawborder)|Wird von Framework aufgerufen, um den Rahmen der Schaltfläche anzuzeigen.|
|[CMFCColorButton::OnDrawFocusRect](#ondrawfocusrect)|Wird von Framework aufgerufen, um ein Fokus Rechteck anzuzeigen, wenn die Schaltfläche den Fokus besitzt.|
|[CMFCColorButton::OnShowColorPopup](#onshowcolorpopup)|Wird von Framework aufgerufen, wenn das Dialogfeld Farbauswahl angezeigt wird.|
|[CMFCColorButton::RebuildPalette](#rebuildpalette)|Initialisiert den `m_pPalette` geschützten Datenmember mit der angegebenen Palette oder der Standardsystem Palette.|
|[CMFCColorButton::UpdateColor](#updatecolor)|Wird von Framework aufgerufen, wenn der Benutzer eine Farbe aus der Palette des Dialog Felds Farbauswahl auswählt.|

### <a name="data-members"></a>Datenmember

|Name|Beschreibung|
|----------|-----------------|
|`m_bAltColorDlg`|Ein boolescher Wert. Wenn true, zeigt das Framework das Dialogfeld [cmfccolordialog](../../mfc/reference/cmfccolordialog-class.md) -Farbe an, wenn auf die *andere* Schaltfläche geklickt wird, oder, wenn false, das Dialogfeld System Farbe. Der Standardwert ist "true". Weitere Informationen finden Sie unter [cmfccolorbutton:: enableotherbutton](#enableotherbutton).|
|`m_bAutoSetFocus`|Ein boolescher Wert. Wenn true, legt das Framework den Fokus auf das Farbmenü fest, wenn das Menü angezeigt wird, oder wenn false, den Fokus nicht ändert. Der Standardwert ist "true".|
|[CMFCColorButton::m_bEnabledInCustomizeMode](#m_benabledincustomizemode)|Gibt an, ob der Anpassungsmodus für die Farb Schaltfläche aktiviert ist.|
|`m_Color`|Ein [COLORREF](/windows/win32/gdi/colorref) -Wert. Enthält die aktuell ausgewählte Farbe.|
|`m_ColorAutomatic`|Ein [COLORREF](/windows/win32/gdi/colorref) -Wert. Enthält die aktuell ausgewählte Standardfarbe.|
|`m_Colors`|Ein [Karray](../../mfc/reference/carray-class.md) von [COLORREF](/windows/win32/gdi/colorref) -Werten. Enthält die aktuell verfügbaren Farben.|
|`m_lstDocColors`|Ein [CLIST](../../mfc/reference/clist-class.md) von [COLORREF](/windows/win32/gdi/colorref) -Werten. Enthält die aktuellen Dokument Farben.|
|`m_nColumns`|Eine ganze Zahl. Enthält die Anzahl der Spalten, die im Raster der Farben in einem Farbauswahl Menü angezeigt werden sollen.|
|`m_pPalette`|Ein Zeiger auf eine [CPalette](../../mfc/reference/cpalette-class.md). Enthält die Farben, die im aktuellen Farbauswahl Menü verfügbar sind.|
|`m_pPopup`|Ein Zeiger auf ein [cmfccolorpopupmenu-Klassen](../../mfc/reference/cmfccolorpopupmenu-class.md) Objekt. Das Farbauswahl Menü, das angezeigt wird, wenn Sie auf die Farb Schaltfläche klicken.|
|`m_strAutoColorText`|Eine Zeichenfolge. Die Bezeichnung der Schaltfläche "automatisch" in einem Farbauswahl Menü.|
|`m_strDocColorsText`|Eine Zeichenfolge. Die Bezeichnung der Schaltfläche in einem Farbauswahl Menü, in dem die Dokument Farben angezeigt werden.|
|`m_strOtherText`|Eine Zeichenfolge. Die Bezeichnung der "anderen"-Schaltfläche in einem Farbauswahl Menü.|

## <a name="remarks"></a>Hinweise

Standardmäßig verhält sich `CMFCColorButton` die-Klasse als pushschaltfläche, die ein Farbauswahl-Dialogfeld öffnet. Das Dialogfeld Farbauswahl enthält ein Array kleiner Farb Schaltflächen und eine "andere" Schaltfläche, auf der eine benutzerdefinierte Farbauswahl angezeigt wird. (Die Standard Schaltfläche "andere" des Systems ist mit **mehr Farben**gekennzeichnet.) Wenn ein Benutzer eine neue Farbe auswählt, `CMFCColorButton` spiegelt das Objekt die Änderung wider und zeigt die ausgewählte Farbe an.

Erstellen Sie ein Farb Schaltflächen-Steuerelement direkt im Code oder mithilfe des **ClassWizard** -Tools und einer Dialogfeld Vorlage. Wenn Sie ein Steuerelement für eine Farb Schaltfläche `CMFCColorButton` direkt erstellen, fügen Sie der Anwendung eine Variable hinzu, und `Create` rufen Sie dann `CMFCColorButton` den Konstruktor und die Methoden des Objekts auf. Wenn Sie den **Klassen-Assistenten**verwenden, fügen `CButton` Sie der Anwendung eine Variable hinzu, und ändern Sie dann den Typ der `CButton` Variablen `CMFCColorButton`von in.

Das Dialogfeld Farbauswahl ( [cmfccolorbar](../../mfc/reference/cmfccolorbar-class.md)) wird von der [cmfccolorbutton:: onshowcolorpopup](#onshowcolorpopup) -Methode angezeigt, wenn das Framework den `OnLButtonDown` Ereignishandler aufruft. Die [cmfccolorbutton:: onshowcolorpopup](#onshowcolorpopup) -Methode kann überschrieben werden, um die benutzerdefinierte Farbauswahl zu unterstützen.

Das `CMFCColorButton` -Objekt benachrichtigt das übergeordnete Element, dass sich eine Farbe ändert, indem es eine WM_COMMAND sendet | BN_CLICKED-Benachrichtigung. Das übergeordnete Element verwendet die [cmfccolorbutton:: GetColor](#getcolor) -Methode, um die aktuelle Farbe abzurufen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie eine Farb Schaltfläche mithilfe verschiedener Methoden in `CMFCColorButton` der-Klasse konfiguriert wird. Die-Methoden legen die Farbe der Farb Schaltfläche und deren Anzahl von Spalten fest und aktivieren die automatischen und die anderen Schaltflächen. Dieses Beispiel ist Teil des Demo Beispiels der [Status Leiste](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_StatusBarDemo#10](../../mfc/reference/codesnippet/cpp/cmfccolorbutton-class_1.h)]
[!code-cpp[NVC_MFC_StatusBarDemo#11](../../mfc/reference/codesnippet/cpp/cmfccolorbutton-class_2.cpp)]

## <a name="requirements"></a>Anforderungen

**Header:** afxcolorbutton. h

##  <a name="cmfccolorbutton"></a>Cmfccolorbutton:: cmfccolorbutton

Erstellt ein neues `CMFCColorButton`-Objekt.

```
CMFCColorButton();
```

##  <a name="enableautomaticbutton"></a>Cmfccolorbutton:: enableautomaticbutton

Aktivieren oder deaktivieren Sie die Schaltfläche "automatisch" eines Farbauswahl-Steuer Elements, und legen Sie die automatische (Standard-) Farbe fest.

```
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parameter

*lpszLabel*<br/>
in Gibt den Text der automatischen Schaltfläche an.

*colorAutomatic*<br/>
in Ein RGB-Wert, der die Standardfarbe der automatischen Schaltfläche angibt.

*bEnable*<br/>
in Gibt an, ob die Schaltfläche automatisch aktiviert oder deaktiviert ist.

### <a name="remarks"></a>Hinweise

##  <a name="enableotherbutton"></a>Cmfccolorbutton:: enableotherbutton

Aktivieren oder deaktivieren Sie die Schaltfläche "andere", die unter Reguläre Farb Schaltflächen angezeigt wird.

```
void EnableOtherButton(
    LPCTSTR lpszLabel,
    BOOL bAltColorDlg=TRUE,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parameter

*lpszLabel*<br/>
in Gibt den Text der Schaltfläche an.

*bAltColorDlg*<br/>
in Gibt an, ob das Dialogfeld [cmfccolordialog](../../mfc/reference/cmfccolordialog-class.md) oder das Dialogfeld System Farbe geöffnet wird, wenn der Benutzer auf die Schaltfläche klickt.

*bEnable*<br/>
in Gibt an, ob die Schaltfläche "andere" aktiviert oder deaktiviert ist.

### <a name="remarks"></a>Hinweise

Klicken Sie auf die Schaltfläche "andere", um ein Dialogfeld für die Farbe anzuzeigen. Wenn der Parameter " *baltcolordlg* " auf "true" festgelegt ist, wird die [cmfccolordialog-Klasse](../../mfc/reference/cmfccolordialog-class.md) angezeigt. Andernfalls wird das Dialogfeld System Farbe angezeigt.

##  <a name="getautomaticcolor"></a>Cmfccolorbutton:: getautomaticcolor

Ruft die aktuelle (Standard-) Farbe ab.

```
COLORREF GetAutomaticColor() const;
```

### <a name="return-value"></a>Rückgabewert

Ein RGB-Wert, der die aktuelle automatische Farbe darstellt.

### <a name="remarks"></a>Hinweise

Die aktuelle automatische Farbe wird von der [cmfccolorbutton:: enableautomaticbutton](#enableautomaticbutton) -Methode festgelegt.

##  <a name="getcolor"></a>Cmfccolorbutton:: GetColor

Ruft die aktuell ausgewählte Farbe ab.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Rückgabewert

Ein RGB-Wert.

### <a name="remarks"></a>Hinweise

##  <a name="isdrawxptheme"></a>Cmfccolorbutton:: isdrawxptheme

Gibt an, ob die aktuelle Farb Schaltfläche im visuellen Stil von Windows XP angezeigt wird.

```
BOOL IsDrawXPTheme() const;
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn visuelle Stile unterstützt werden und die aktuelle Farb Schaltfläche im visuellen Stil von Windows XP angezeigt wird. andernfalls false.

##  <a name="m_benabledincustomizemode"></a>Cmfccolorbutton:: m_bEnabledInCustomizeMode

Legt eine Farb Schaltfläche auf den Anpassungsmodus fest.

```
BOOL m_bEnabledInCustomizeMode;
```

### <a name="remarks"></a>Hinweise

Wenn Sie der Seite eines Anpassungs Dialogfelds eine Farb Schaltfläche hinzufügen müssen (oder wenn der Benutzer während der Anpassung eine andere Farbauswahl treffen soll), aktivieren `m_bEnabledInCustomizeMode` Sie die Schaltfläche, indem Sie den Member auf true setzen. Standardmäßig ist dieser Member auf false festgelegt.

##  <a name="ondraw"></a>Cmfccolorbutton:: OnDraw

Wird von Framework aufgerufen, um ein Bild der Schaltfläche zu erzeugen.

```
virtual void OnDraw(
    CDC* pDC,
    const CRect& rect,
    UINT uiState);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
in Verweist auf den Gerätekontext, der zum Rendering des Bilds der Schaltfläche verwendet wird.

*Rect*<br/>
in Ein Rechteck, das die Schaltfläche umschließt.

*uiState*<br/>
in Gibt den visuellen Zustand der Schaltfläche an.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode, um den Renderingprozess anzupassen.

##  <a name="ondrawborder"></a>Cmfccolorbutton:: ondrawborder

Wird von Framework aufgerufen, um den Rahmen der Schaltfläche anzuzeigen.

```
virtual void OnDrawBorder(
    CDC* pDC,
    CRect& rectClient,
    UINT uiState);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
in Zeigt auf den Gerätekontext, der zum Zeichnen des Rahmens verwendet wurde.

*rectClient*<br/>
in Ein Rechteck im Gerätekontext, das durch den *PDC* -Parameter angegeben wird, der die Begrenzungen der zu Zeichenden Schaltfläche definiert.

*uiState*<br/>
in Gibt den visuellen Zustand der Schaltfläche an.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Funktion, um die Rahmen Darstellung der Farb Schaltfläche anzupassen.

##  <a name="ondrawfocusrect"></a>Cmfccolorbutton:: ondrawfocurect

Wird von Framework aufgerufen, um ein Fokus Rechteck anzuzeigen, wenn die Schaltfläche den Fokus besitzt.

```
virtual void OnDrawFocusRect(
    CDC* pDC,
    const CRect& rectClient);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
in Zeigt auf den Gerätekontext, der zum Zeichnen des Fokus Rechtecks verwendet wird.

*rectClient*<br/>
in Ein Rechteck in dem vom *PDC* -Parameter angegebenen Gerätekontext, das die Begrenzungen der Schaltfläche definiert.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode, um die Darstellung des Fokus Rechtecks anzupassen.

##  <a name="onshowcolorpopup"></a>Cmfccolorbutton:: onshowcolorpopup

Wird aufgerufen, bevor die Popup Farbleiste angezeigt wird.

```
virtual void OnShowColorPopup();
```

### <a name="remarks"></a>Hinweise

##  <a name="rebuildpalette"></a>Cmfccolorbutton:: rebuildpalette

Initialisiert den `m_pPalette` geschützten Datenmember mit der angegebenen Palette oder der Standardsystem Palette.

```
void RebuildPalette(CPalette* pPal);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*pPal*|in Ein Zeiger auf eine logische Palette oder NULL. Wenn der Wert NULL ist, wird die standardmäßige Systempalette verwendet.|

##  <a name="setcolor"></a>Cmfccolorbutton:: setColor

Gibt die Farbe der Schaltfläche an.

```
void SetColor(COLORREF color);
```

### <a name="parameters"></a>Parameter

*Farbe*<br/>
in Ein RGB-Wert.

### <a name="remarks"></a>Hinweise

##  <a name="setcolorname"></a>Cmfccolorbutton:: setcolorname

Gibt den Namen einer Farbe an.

```
static void SetColorName(
    COLORREF color,
    const CString& strName);
```

### <a name="parameters"></a>Parameter

*Farbe*<br/>
in Der RGB-Wert der Farbe.

*strName*<br/>
in Der Name der Farbe.

### <a name="remarks"></a>Hinweise

Die Liste der Farbnamen ist Global pro Anwendung. Folglich überträgt diese Methode ihre Parameter an [cmfccolorbar:: setcolorname](../../mfc/reference/cmfccolorbar-class.md#setcolorname).

##  <a name="setcolumnsnumber"></a>Cmfccolorbutton:: setcolumnsnumber

Definiert die Anzahl von Spalten, die in der Tabelle der Farben angezeigt werden, die dem Benutzer während der Farbauswahl des Benutzers angezeigt werden.

```
void SetColumnsNumber(int nColumns);
```

### <a name="parameters"></a>Parameter

*nColumns*<br/>
in Gibt die Anzahl der Spalten an.

### <a name="remarks"></a>Hinweise

Der Benutzer kann eine Farbe aus einer Popup Farbleiste auswählen, in der eine Tabelle mit vordefinierten Farben angezeigt wird. Verwenden Sie diese Methode, um die Anzahl der Spalten in der Tabelle zu definieren.

##  <a name="setdocumentcolors"></a>Cmfccolorbutton:: setdocumentcolors

Gibt eine Gruppe von Farben und den Namen des Satzes an. Der Satz von Farben wird mithilfe eines [cmfccolorbar-Klassen](../../mfc/reference/cmfccolorbar-class.md) Objekts angezeigt.

```
void SetDocumentColors(
    LPCTSTR lpszLabel,
    CList<COLORREF,COLORREF>& lstColors);
```

### <a name="parameters"></a>Parameter

*lpszLabel*<br/>
in Gibt die Bezeichnung an, die mit dem Satz von Dokument Farben angezeigt werden soll.

*lstColors*<br/>
in Ein Verweis auf eine Liste der RGB-Werte.

### <a name="remarks"></a>Hinweise

Ein `CMFCColorButton` -Objekt verwaltet eine Liste von RGB-Werten, die an ein [cmfccolorbar-Klassen](../../mfc/reference/cmfccolorbar-class.md) Objekt übertragen werden. Wenn die Farbleiste angezeigt wird, werden diese Farben in einem speziellen Abschnitt angezeigt, dessen Bezeichnung durch den *lpszlabel* -Parameter angegeben wird.

##  <a name="setpalette"></a>Cmfccolorbutton:: SetPalette

Gibt die Standardfarben an, die auf der Popup Farbleiste angezeigt werden sollen.

```
void SetPalette(CPalette* pPalette);
```

### <a name="parameters"></a>Parameter

*pPalette*<br/>
in Ein Zeiger auf eine Farbpalette.

### <a name="remarks"></a>Hinweise

##  <a name="sizetocontent"></a>Cmfccolorbutton:: sizeto Content

Passt die Größe des Schaltflächen-Steuer Elements an den Text und das Bild an.

```
virtual CSize SizeToContent(BOOL bCalcOnly=FALSE);
```

### <a name="parameters"></a>Parameter

*bCalcOnly*<br/>
in Wenn ungleich 0 (null), wird die neue Größe des Schaltflächen-Steuer Elements berechnet, aber die tatsächliche Größe wird nicht geändert.

### <a name="return-value"></a>Rückgabewert

Ein `CSize` -Objekt, das die Größe des neuen Schaltflächen Steuer Elements angibt.

### <a name="remarks"></a>Hinweise

##  <a name="updatecolor"></a>Cmfccolorbutton:: updatecolor

Wird von Framework aufgerufen, wenn der Benutzer eine Farbe aus der Farbleiste auswählt, die angezeigt wird, wenn der Benutzer auf die Farb Schaltfläche klickt.

```
virtual void UpdateColor(COLORREF color);
```

### <a name="parameters"></a>Parameter

*Farbe*<br/>
in Eine Farbe, die vom Benutzer ausgewählt wurde.

### <a name="remarks"></a>Hinweise

Die `UpdateColor` -Funktion ändert die Farbe der aktuell ausgewählten Schaltfläche und benachrichtigt das übergeordnete Element, indem eine WM_COMMAND-Nachricht mit einer BN_CLICKED-Standard Benachrichtigung gesendet wird. Verwenden Sie die [cmfccolorbutton:: GetColor](#getcolor) -Methode, um die ausgewählte Farbe abzurufen.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCButton-Klasse](../../mfc/reference/cmfcbutton-class.md)<br/>
[CMFCColorBar-Klasse](../../mfc/reference/cmfccolorbar-class.md)<br/>
[CMFCColorButton::OnShowColorPopup](#onshowcolorpopup)<br/>
[COLORREF](/windows/win32/gdi/colorref)<br/>
[CPalette-Klasse](../../mfc/reference/cpalette-class.md)<br/>
[CArray-Klasse](../../mfc/reference/carray-class.md)<br/>
[CList-Klasse](../../mfc/reference/clist-class.md)<br/>
[CString](../../atl-mfc-shared/reference/cstringt-class.md)
