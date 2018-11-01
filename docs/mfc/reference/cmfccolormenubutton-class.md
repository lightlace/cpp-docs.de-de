---
title: CMFCColorMenuButton-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCColorMenuButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::CMFCColorMenuButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableAutomaticButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableDocumentColors
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableOtherButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableTearOff
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::GetAutomaticColor
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::GetColor
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::GetColorByCmdID
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OnChangeParentWnd
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OpenColorDialog
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColor
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColorByCmdID
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColorName
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColumnsNumber
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::CopyFrom
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::CreatePopupMenu
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::IsEmptyMenuAllowed
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OnDraw
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OnDrawOnCustomizeList
helpviewer_keywords:
- CMFCColorMenuButton [MFC], CMFCColorMenuButton
- CMFCColorMenuButton [MFC], EnableAutomaticButton
- CMFCColorMenuButton [MFC], EnableDocumentColors
- CMFCColorMenuButton [MFC], EnableOtherButton
- CMFCColorMenuButton [MFC], EnableTearOff
- CMFCColorMenuButton [MFC], GetAutomaticColor
- CMFCColorMenuButton [MFC], GetColor
- CMFCColorMenuButton [MFC], GetColorByCmdID
- CMFCColorMenuButton [MFC], OnChangeParentWnd
- CMFCColorMenuButton [MFC], OpenColorDialog
- CMFCColorMenuButton [MFC], SetColor
- CMFCColorMenuButton [MFC], SetColorByCmdID
- CMFCColorMenuButton [MFC], SetColorName
- CMFCColorMenuButton [MFC], SetColumnsNumber
- CMFCColorMenuButton [MFC], CopyFrom
- CMFCColorMenuButton [MFC], CreatePopupMenu
- CMFCColorMenuButton [MFC], IsEmptyMenuAllowed
- CMFCColorMenuButton [MFC], OnDraw
- CMFCColorMenuButton [MFC], OnDrawOnCustomizeList
ms.assetid: 42685704-e994-4f7b-9553-62283c27b754
ms.openlocfilehash: adb0cdbdde90ad7bdd6aef42c1e83c7ba3fd28b0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50624886"
---
# <a name="cmfccolormenubutton-class"></a>CMFCColorMenuButton-Klasse

Die `CMFCColorMenuButton` -Klasse unterstützt einen Menübefehl oder eine Symbolleisten-Schaltfläche, die ein Farben-Auswahldialogfeld startet.

## <a name="syntax"></a>Syntax

```
class CMFCColorMenuButton : public CMFCToolBarMenuButton
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMFCColorMenuButton::CMFCColorMenuButton](#cmfccolormenubutton)|Erstellt ein `CMFCColorMenuButton`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCColorMenuButton::EnableAutomaticButton](#enableautomaticbutton)|Aktiviert und deaktiviert eine "Automatische"-Schaltfläche, die über den regulären Farbe Schaltflächen positioniert ist. (Die standardmäßige automatische Schaltfläche ist mit der Bezeichnung **automatische**.)|
|[CMFCColorMenuButton::EnableDocumentColors](#enabledocumentcolors)|Ermöglicht die Darstellung von Farben für die spezifischen, anstelle von Systemfarben an.|
|[CMFCColorMenuButton::EnableOtherButton](#enableotherbutton)|Aktiviert und deaktiviert eine "other"-Schaltfläche, die unter den regulären Farbe Schaltflächen positioniert ist. (Das Standardbetriebssystem "other" Schaltfläche ist mit **Weitere Farben**.)|
|[CMFCColorMenuButton::EnableTearOff](#enabletearoff)|Bietet die Möglichkeit zu deaktiviert einen Farbbereich zu unterbrechen.|
|[CMFCColorMenuButton::GetAutomaticColor](#getautomaticcolor)|Ruft die aktuelle Farbe ab.|
|[CMFCColorMenuButton::GetColor](#getcolor)|Ruft die aktuelle die Farbe der Schaltfläche ab.|
|[CMFCColorMenuButton::GetColorByCmdID](#getcolorbycmdid)|Ruft die Farbe, die einen angegebenen Befehls-ID entspricht.|
|[CMFCColorMenuButton::OnChangeParentWnd](#onchangeparentwnd)|Vom Framework aufgerufen, wenn das übergeordnete Fenster ändert.|
|[CMFCColorMenuButton::OpenColorDialog](#opencolordialog)|Öffnet ein Dialogfeld zur Farbauswahl.|
|[CMFCColorMenuButton::SetColor](#setcolor)|Legt die Farbe der Schaltfläche für die aktuelle Farbe fest.|
|[CMFCColorMenuButton::SetColorByCmdID](#setcolorbycmdid)|Die Farbe der Menüschaltfläche angegebene Farbe festgelegt.|
|[CMFCColorMenuButton::SetColorName](#setcolorname)|Legt einen neuen Namen für die angegebene Farbe fest.|
|[CMFCColorMenuButton::SetColumnsNumber](#setcolumnsnumber)|Legt die Anzahl der Spalten, die angezeigt werden eine `CMFCColorBar` Objekt.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCColorMenuButton::CopyFrom](#copyfrom)|Kopiert eine andere Symbolleistenschaltfläche auf die Schaltfläche mit den aktuellen.|
|[CMFCColorMenuButton::CreatePopupMenu](#createpopupmenu)|Erstellt ein Farben-Auswahldialogfeld.|
|[CMFCColorMenuButton::IsEmptyMenuAllowed](#isemptymenuallowed)|Gibt an, ob leere Menüs unterstützt werden.|
|[CMFCColorMenuButton::OnDraw](#ondraw)|Vom Framework aufgerufen, um auf eine Schaltfläche ein Bild anzuzeigen.|
|[CMFCColorMenuButton::OnDrawOnCustomizeList](#ondrawoncustomizelist)|Aufgerufen, bevor Sie eine `CMFCColorMenuButton` Objekt wird in der Liste der eines Anpassungsdialogfelds für die Symbolleiste angezeigt.|

## <a name="remarks"></a>Hinweise

Ersetzen der ursprüngliche Menübefehl oder Symbolleisten-Schaltfläche mit einer `CMFCColorMenuButton` Objekt, das Erstellen der `CMFCColorMenuButton` Objekt, und legen Sie geeignete [CMFCColorBar-Klasse](../../mfc/reference/cmfccolorbar-class.md) Formatvorlagen und rufen Sie dann die `ReplaceButton` Methode der [CMFCToolBar-Klasse](../../mfc/reference/cmfctoolbar-class.md) Klasse. Wenn Sie eine Symbolleiste angepasst haben, rufen die [CMFCToolBarsCustomizeDialog::ReplaceButton](../../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) Methode.

Die Farben-Auswahldialogfeld wird erstellt, bei der Verarbeitung der [CMFCColorMenuButton::CreatePopupMenu](#createpopupmenu) -Ereignishandler. Der Ereignishandler benachrichtigt den übergeordneten Rahmen mit einer WM_COMMAND-Meldung. Die `CMFCColorMenuButton` Objekt sendet die Steuerelement-ID, die die ursprüngliche Menü Menübefehl oder eine Symbolleisten-Schaltfläche zugewiesen ist.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird veranschaulicht, wie zum Erstellen und konfigurieren eine farbmenüschaltfläche mithilfe verschiedener Methoden in der `CMFCColorMenuButton` Klasse. Im Beispiel eine `CPalette` Objekt zuerst erstellt und dann verwendet, um das Erstellen eines Objekts von der `CMFCColorMenuButton` Klasse. Die `CMFCColorMenuButton` Objekt wird dann durch Aktivieren der automatischen und andere Schaltflächen und festlegen, dessen Farbe und die Anzahl der Spalten konfiguriert. Dieser Code ist Teil der [WordPad-Beispiels](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_WordPad#5](../../mfc/reference/codesnippet/cpp/cmfccolormenubutton-class_1.h)]
[!code-cpp[NVC_MFC_WordPad#6](../../mfc/reference/codesnippet/cpp/cmfccolormenubutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md)

[CMFCColorMenuButton](../../mfc/reference/cmfccolormenubutton-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxcolormenubutton.h

##  <a name="cmfccolormenubutton"></a>  CMFCColorMenuButton::CMFCColorMenuButton

Erstellt ein `CMFCColorMenuButton`-Objekt.

```
CMFCColorMenuButton();

CMFCColorMenuButton(
    UINT uiCmdID,
    LPCTSTR lpszText,
    CPalette* pPalette=NULL);
```

### <a name="parameters"></a>Parameter

*uiCmdID*<br/>
[in] Eine Schaltfläche-Befehls-ID.

*lpszText*<br/>
[in] Der Text der Schaltfläche.

*pPalette*<br/>
[in] Ein Zeiger auf die Schaltfläche "-Farbpalette.

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

Der erste Konstruktor ist der Standardkonstruktor. Aktuelle Farbe des Objekts und der automatischen Farbe werden auf Schwarz (RGB (0, 0, 0)) initialisiert.

Der zweite Konstruktor initialisiert die Schaltfläche, um die Farbe, die der angegebenen Befehls-ID entspricht.

##  <a name="copyfrom"></a>  CMFCColorMenuButton::CopyFrom

Kopiert eine [CMFCToolBarMenuButton-Klasse](../../mfc/reference/cmfctoolbarmenubutton-class.md)-abgeleitetes Objekt in einen anderen.

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>Parameter

*src*<br/>
[in] Quelle, um zu kopieren.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode zum Kopieren von Objekten, das von abgeleitet sind die `CMFCColorMenuButton` Objekt.

##  <a name="createpopupmenu"></a>  CMFCColorMenuButton::CreatePopupMenu

Erstellt ein Farben-Auswahldialogfeld.

```
virtual CMFCPopupMenu* CreatePopupMenu();
```

### <a name="return-value"></a>Rückgabewert

Ein Objekt, das ein Farben-Auswahldialogfeld darstellt.

### <a name="remarks"></a>Hinweise

Diese Methode wird vom Framework aufgerufen, wenn der Benutzer eine Farbe-Schaltfläche drückt.

##  <a name="enableautomaticbutton"></a>  CMFCColorMenuButton::EnableAutomaticButton

Aktiviert und deaktiviert eine "Automatische"-Schaltfläche, die über den regulären Farbe Schaltflächen positioniert ist. (Die standardmäßige automatische Schaltfläche ist mit der Bezeichnung **automatische**.)

```
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parameter

*lpszLabel*<br/>
[in] Gibt den Text der Schaltfläche, der angezeigt wird, wird die Schaltfläche zum automatischen an.

*colorAutomatic*<br/>
[in] Gibt eine neue automatische Farbe an.

*bAktivieren*<br/>
[in] Gibt an, ob die Schaltfläche zum automatischen oder nicht.

### <a name="remarks"></a>Hinweise

Die automatische Schaltfläche wendet die aktuelle Standardfarbe.

##  <a name="enabledocumentcolors"></a>  CMFCColorMenuButton::EnableDocumentColors

Ermöglicht die Darstellung von Farben für die spezifischen, anstelle von Systemfarben an.

```
void EnableDocumentColors(
    LPCTSTR lpszLabel,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parameter

*lpszLabel*<br/>
[in] Gibt den Text der Schaltfläche an.

*bAktivieren*<br/>
[in] "True", um dokumentspezifische Farben oder "false" zum Anzeigen von Systemfarben anzuzeigen.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode, um die Farben des aktuellen Dokuments oder der Farben der Systempalette anzuzeigen, klickt der Benutzer eine Farbe Menüschaltfläche.

##  <a name="enableotherbutton"></a>  CMFCColorMenuButton::EnableOtherButton

Aktiviert und deaktiviert eine "other"-Schaltfläche, die unter den regulären Farbe Schaltflächen positioniert ist. (Das Standardbetriebssystem "other" Schaltfläche ist mit **Weitere Farben**.)

```
void EnableOtherButton(
    LPCTSTR lpszLabel,
    BOOL bAltColorDlg=TRUE,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parameter

*lpszLabel*<br/>
[in] Gibt den Text der Schaltfläche an.

*bAltColorDlg*<br/>
[in] Geben Sie "true", zeigen die `CMFCColorDialog` Dialogfeld oder "false", um das Dialogfeld Farbe Standardsystem anzuzeigen.

*bAktivieren*<br/>
[in] Geben Sie "true", "other" die Schaltfläche anzuzeigen; andernfalls "false". Der Standardwert ist "true".

### <a name="remarks"></a>Hinweise

##  <a name="enabletearoff"></a>  CMFCColorMenuButton::EnableTearOff

Bietet die Möglichkeit zu deaktiviert einen Farbbereich zu unterbrechen.

```
void EnableTearOff(
    UINT uiID,
    int nVertDockColumns=-1,
    int nHorzDockRows=-1);
```

### <a name="parameters"></a>Parameter

*uiID*<br/>
[in] Gibt die ID für den Bereich der abtrennbare.

*nVertDockColumns*<br/>
[in] Gibt die Anzahl der Spalten im Bereich vertikal angedockten Farbe in abtrennbaren Zustand an.

*nHorzDockRows*<br/>
[in] Gibt die Anzahl der Zeilen für den Bereich horizontal angedockt Farbe in abtrennbaren Zustand an.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Methode, um das Feature "abtrennbare" für den Bereich der Farbe zu aktivieren, die pops registrieren, wenn die `CMFCColorMenuButton` gedrückt wird.

##  <a name="getautomaticcolor"></a>  CMFCColorMenuButton::GetAutomaticColor

Ruft die aktuelle Farbe ab.

```
COLORREF GetAutomaticColor() const;
```

### <a name="return-value"></a>Rückgabewert

Ein RGB-Farbwert, der die aktuelle Farbe darstellt.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Methode zum Abrufen von der automatischen Farbe, die festgelegt wird, indem [CMFCColorMenuButton::EnableAutomaticButton](#enableautomaticbutton).

##  <a name="getcolor"></a>  CMFCColorMenuButton::GetColor

Ruft die aktuelle die Farbe der Schaltfläche ab.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Rückgabewert

Die Farbe der Schaltfläche.

### <a name="remarks"></a>Hinweise

##  <a name="getcolorbycmdid"></a>  CMFCColorMenuButton::GetColorByCmdID

Ruft die Farbe, die einen angegebenen Befehls-ID entspricht.

```
static COLORREF GetColorByCmdID(UINT uiCmdID);
```

### <a name="parameters"></a>Parameter

*uiCmdID*<br/>
[in] Eine Befehls-ID.

### <a name="return-value"></a>Rückgabewert

Die Farbe, die der angegebenen Befehls-ID entspricht.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode, wenn Sie mehrere Farbe Schaltflächen in eine Anwendung verfügen. Klickt der Benutzer eine farbenschaltfläche, sendet die Schaltfläche die Befehls-ID in einer WM_COMMAND-Meldung an sein übergeordnetes Element an. Die `GetColorByCmdID` Methode verwendet die Befehls-ID, um die entsprechende Farbe abzurufen.

##  <a name="isemptymenuallowed"></a>  CMFCColorMenuButton::IsEmptyMenuAllowed

Gibt an, ob leere Menüs unterstützt werden.

```
virtual BOOL IsEmptyMenuAllowed() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn leere Menüs zulässig. andernfalls 0 (null).

### <a name="remarks"></a>Hinweise

Leere Menüs werden standardmäßig unterstützt. Überschreiben Sie diese Methode zum Ändern dieses Verhaltens in einer abgeleiteten Klasse.

##  <a name="onchangeparentwnd"></a>  CMFCColorMenuButton::OnChangeParentWnd

Vom Framework aufgerufen, wenn das übergeordnete Fenster ändert.

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>Parameter

*pWndParent*<br/>
[in] Ein Zeiger auf das neue übergeordnete Fenster.

### <a name="remarks"></a>Hinweise

##  <a name="ondraw"></a>  CMFCColorMenuButton::OnDraw

Vom Framework aufgerufen, um auf eine Schaltfläche ein Bild anzuzeigen.

```
virtual void OnDraw(
    CDC* pDC,
    const CRect& rect,
    CMFCToolBarImages* pImages,
    BOOL bHorz=TRUE,
    BOOL bCustomizeMode=FALSE,
    BOOL bHighlight=FALSE,
    BOOL bDrawBorder=TRUE,
    BOOL bGrayDisabledButtons=TRUE);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
[in] Ein Zeiger auf einen Gerätekontext.

*Rect*<br/>
[in] Ein Rechteck, das den Bereich zu zeichnenden umschließt.

*pImages*<br/>
[in] Verweist auf eine Liste von symbolleistenbildern.

*bHorz*<br/>
[in] True, um anzugeben, dass die Symbolleiste in einem horizontalen angedockten Zustand ist. andernfalls "false". Der Standardwert ist "true".

*bCustomizeMode*<br/>
[in] True, um anzugeben, dass die Anwendung im Anpassungsmodus befindet. andernfalls "false". Der Standardwert ist "false".

*bHighlight*<br/>
[in] True, um anzugeben, dass die Schaltfläche markiert wird. andernfalls "false". Der Standardwert ist "false".

*bDrawBorder*<br/>
[in] "True", um anzugeben, dass der Rahmen der Schaltfläche angezeigt wird; andernfalls "false". Der Standardwert ist "true".

*bGrayDisabledButtons*<br/>
[in] TRUE, um anzugeben, dass deaktivierte Schaltflächen sind abgeblendet (abgeblendet); andernfalls "false". Der Standardwert ist "true".

### <a name="remarks"></a>Hinweise

##  <a name="ondrawoncustomizelist"></a>  CMFCColorMenuButton::OnDrawOnCustomizeList

Aufgerufen, bevor Sie eine `CMFCColorMenuButton` Objekt wird in der Liste der eines Anpassungsdialogfelds für die Symbolleiste angezeigt.

```
virtual int OnDrawOnCustomizeList(
    CDC* pDC,
    const CRect& rect,
    BOOL bSelected);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
[in] Ein Zeiger auf einen Gerätekontext.

*Rect*<br/>
[in] Ein Rechteck, das die Schaltfläche gezeichnet werden umschließt.

*bSelected*<br/>
[in] "True" gibt an, dass die Schaltfläche mit der ausgewählten Zustand ist. andernfalls "false".

### <a name="return-value"></a>Rückgabewert

Die Breite der Schaltfläche.

### <a name="remarks"></a>Hinweise

Diese Methode wird aufgerufen, durch das Framework bei der ein `CMFCColorMenuButton` Objekt wird im Listenfeld angezeigt, während des Anpassungsvorgangs Symbolleiste.

##  <a name="opencolordialog"></a>  CMFCColorMenuButton::OpenColorDialog

Öffnet ein Dialogfeld zur Farbauswahl.

```
virtual BOOL OpenColorDialog(
    const COLORREF colorDefault,
    COLORREF& colorRes);
```

### <a name="parameters"></a>Parameter

*colorDefault*<br/>
[in] Die Standardfarbe, die im Dialogfeld "Farbe" ausgewählt ist.

*colorRes*<br/>
[out] Gibt die Farbe, die der Benutzer im Dialogfeld "Farbe" auswählt.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn der Benutzer eine neue Farbe auswählt; andernfalls 0 (null).

### <a name="remarks"></a>Hinweise

Wenn die Schaltfläche geklickt wird, rufen Sie diese Methode, um ein Dialogfeld zu öffnen. Wenn der Rückgabewert ungleich NULL ist, befindet sich die Farbe, die der Benutzer wählt in der *ColorRes* Parameter. Verwenden der [CMFCColorMenuButton::EnableOtherButton](#enableotherbutton) Methode, um das Dialogfeld die Standardfarbe wechseln und die [CMFCColorDialog-Klasse](../../mfc/reference/cmfccolordialog-class.md) Dialogfeld.

##  <a name="setcolor"></a>  CMFCColorMenuButton::SetColor

Legt die Farbe der Schaltfläche für die aktuelle Farbe fest.

```
virtual void SetColor(
    COLORREF clr,
    BOOL bNotify=TRUE);
```

### <a name="parameters"></a>Parameter

*CLR*<br/>
[in] Ein RGB-Farbwert.

*bNotify*<br/>
[in] "True", gelten die *Clr* Parameter Farbe an, die alle zugeordneten Menüschaltfläche oder die Symbolleisten-Schaltfläche; andernfalls "false".

### <a name="remarks"></a>Hinweise

Rufen Sie diese Methode, um die Farbe der Schaltfläche für die aktuelle Farbe zu ändern. Wenn die *bNotify* Parameter ungleich NULL ist, die Farbe der entsprechenden Schaltfläche in einem zugeordneten Popupmenü oder die Symbolleiste wird geändert, der die Farbe, die gemäß der *Clr* Parameter.

##  <a name="setcolorbycmdid"></a>  CMFCColorMenuButton::SetColorByCmdID

Die Farbe der Menüschaltfläche angegebene Farbe festgelegt.

```
static void SetColorByCmdID(
    UINT uiCmdID,
    COLORREF color);
```

### <a name="parameters"></a>Parameter

*uiCmdID*<br/>
[in] Die Ressourcen-ID einer Menüschaltfläche Farbe.

*Farbe*<br/>
[in] Ein RGB-Farbwert.

##  <a name="setcolorname"></a>  CMFCColorMenuButton::SetColorName

Legt einen neuen Namen für die angegebene Farbe fest.

```
static void SetColorName(
    COLORREF color,
    const CString& strName);
```

### <a name="parameters"></a>Parameter

*Farbe*<br/>
[in] Der RGB-Wert, der die Farbe, deren Name geändert, werden soll.

*strName*<br/>
[in] Der neue Name der Farbe.

### <a name="remarks"></a>Hinweise

##  <a name="setcolumnsnumber"></a>  CMFCColorMenuButton::SetColumnsNumber

Legt die Anzahl der Spalten für die Anzeige in ein Farben-Auswahlsteuerelement ( [CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md) Objekt).

```
void SetColumnsNumber(int nColumns);
```

### <a name="parameters"></a>Parameter

*nColumns*<br/>
[in] Die Anzahl der Spalten angezeigt werden sollen.

### <a name="remarks"></a>Hinweise

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCColorBar-Klasse](../../mfc/reference/cmfccolorbar-class.md)<br/>
[CMFCToolBar-Klasse](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBarsCustomizeDialog-Klasse](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)<br/>
[CMFCColorButton-Klasse](../../mfc/reference/cmfccolorbutton-class.md)
