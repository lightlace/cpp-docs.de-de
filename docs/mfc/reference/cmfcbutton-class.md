---
title: Cmfcbutton-Klasse
ms.date: 08/28/2018
f1_keywords:
- CMFCButton
- AFXBUTTON/CMFCButton
- AFXBUTTON/CMFCButton::CleanUp
- AFXBUTTON/CMFCButton::EnableFullTextTooltip
- AFXBUTTON/CMFCButton::EnableMenuFont
- AFXBUTTON/CMFCButton::EnableWindowsTheming
- AFXBUTTON/CMFCButton::GetToolTipCtrl
- AFXBUTTON/CMFCButton::IsAutoCheck
- AFXBUTTON/CMFCButton::IsAutorepeatCommandMode
- AFXBUTTON/CMFCButton::IsCheckBox
- AFXBUTTON/CMFCButton::IsChecked
- AFXBUTTON/CMFCButton::IsHighlighted
- AFXBUTTON/CMFCButton::IsPressed
- AFXBUTTON/CMFCButton::IsPushed
- AFXBUTTON/CMFCButton::IsRadioButton
- AFXBUTTON/CMFCButton::IsWindowsThemingEnabled
- AFXBUTTON/CMFCButton::SetAutorepeatMode
- AFXBUTTON/CMFCButton::SetCheckedImage
- AFXBUTTON/CMFCButton::SetFaceColor
- AFXBUTTON/CMFCButton::SetImage
- AFXBUTTON/CMFCButton::SetMouseCursor
- AFXBUTTON/CMFCButton::SetMouseCursorHand
- AFXBUTTON/CMFCButton::SetStdImage
- AFXBUTTON/CMFCButton::SetTextColor
- AFXBUTTON/CMFCButton::SetTextHotColor
- AFXBUTTON/CMFCButton::SetTooltip
- AFXBUTTON/CMFCButton::SizeToContent
- AFXBUTTON/CMFCButton::OnDraw
- AFXBUTTON/CMFCButton::OnDrawBorder
- AFXBUTTON/CMFCButton::OnDrawFocusRect
- AFXBUTTON/CMFCButton::OnDrawText
- AFXBUTTON/CMFCButton::OnFillBackground
- AFXBUTTON/CMFCButton::SelectFont
- AFXBUTTON/CMFCButton::m_bDrawFocus
- AFXBUTTON/CMFCButton::m_bHighlightChecked
- AFXBUTTON/CMFCButton::m_bRightImage
- AFXBUTTON/CMFCButton::m_bTransparent
- AFXBUTTON/CMFCButton::m_nAlignStyle
- AFXBUTTON/CMFCButton::m_nFlatStyle
helpviewer_keywords:
- CMFCButton [MFC], CleanUp
- CMFCButton [MFC], EnableFullTextTooltip
- CMFCButton [MFC], EnableMenuFont
- CMFCButton [MFC], EnableWindowsTheming
- CMFCButton [MFC], GetToolTipCtrl
- CMFCButton [MFC], IsAutoCheck
- CMFCButton [MFC], IsAutorepeatCommandMode
- CMFCButton [MFC], IsCheckBox
- CMFCButton [MFC], IsChecked
- CMFCButton [MFC], IsHighlighted
- CMFCButton [MFC], IsPressed
- CMFCButton [MFC], IsPushed
- CMFCButton [MFC], IsRadioButton
- CMFCButton [MFC], IsWindowsThemingEnabled
- CMFCButton [MFC], SetAutorepeatMode
- CMFCButton [MFC], SetCheckedImage
- CMFCButton [MFC], SetFaceColor
- CMFCButton [MFC], SetImage
- CMFCButton [MFC], SetMouseCursor
- CMFCButton [MFC], SetMouseCursorHand
- CMFCButton [MFC], SetStdImage
- CMFCButton [MFC], SetTextColor
- CMFCButton [MFC], SetTextHotColor
- CMFCButton [MFC], SetTooltip
- CMFCButton [MFC], SizeToContent
- CMFCButton [MFC], OnDraw
- CMFCButton [MFC], OnDrawBorder
- CMFCButton [MFC], OnDrawFocusRect
- CMFCButton [MFC], OnDrawText
- CMFCButton [MFC], OnFillBackground
- CMFCButton [MFC], SelectFont
- CMFCButton [MFC], m_bDrawFocus
- CMFCButton [MFC], m_bHighlightChecked
- CMFCButton [MFC], m_bRightImage
- CMFCButton [MFC], m_bTransparent
- CMFCButton [MFC], m_nAlignStyle
- CMFCButton [MFC], m_nFlatStyle
ms.assetid: 4b32f57c-7a53-4734-afb9-d47e3359f62e
ms.openlocfilehash: 7628ac353d01c2a6853e35a35bd1f702d3bb041e
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505858"
---
# <a name="cmfcbutton-class"></a>Cmfcbutton-Klasse

Die `CMFCButton` -Klasse fügt der [CButton](../../mfc/reference/cbutton-class.md) -Klasse Funktionen hinzu, z. b. das Ausrichten von Schaltflächen Text, das Kombinieren von Schaltflächen Text und ein Bild, das Auswählen eines Cursors und das Angeben einer Quick

## <a name="syntax"></a>Syntax

```
class CMFCButton : public CButton
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|`CMFCButton::CMFCButton`|Standardkonstruktor|
|`CMFCButton::~CMFCButton`|Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[Cmfcbutton:: Cleanup](#cleanup)|Setzt interne Variablen zurück und gibt zugeordnete Ressourcen wie Bilder, Bitmaps und Symbole frei.|
|`CMFCButton::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|
|`CMFCButton::DrawItem`|Wird von Framework aufgerufen, wenn sich ein visueller Aspekt einer vom Besitzer gezeichneten Schaltfläche geändert hat. (Überschreibt [CButton::D rawitem](../../mfc/reference/cbutton-class.md#drawitem).)|
|[CMFCButton::EnableFullTextTooltip](#enablefulltexttooltip)|Gibt an, ob der vollständige Text einer QuickInfo in einem großen QuickInfo-Fenster oder eine gekürzte Version des Texts in einem kleinen QuickInfo-Fenster angezeigt werden soll.|
|[CMFCButton::EnableMenuFont](#enablemenufont)|Gibt an, ob die Schaltflächen Text Schriftart mit der Anwendungsmenü Schriftart identisch ist.|
|[CMFCButton::EnableWindowsTheming](#enablewindowstheming)|Gibt an, ob der Stil des Schaltflächen Rahmens dem aktuellen Windows-Design entspricht.|
|`CMFCButton::GetThisClass`|Wird vom Framework verwendet, um einen Zeiger auf das [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt abzurufen, das diesem Klassentyp zugeordnet ist.|
|[CMFCButton::GetToolTipCtrl](#gettooltipctrl)|Gibt einen Verweis auf das zugrunde liegende QuickInfo-Steuerelement zurück.|
|[CMFCButton::IsAutoCheck](#isautocheck)|Gibt an, ob ein Kontrollkästchen oder Optionsfeld eine automatische Schaltfläche ist.|
|[CMFCButton::IsAutorepeatCommandMode](#isautorepeatcommandmode)|Gibt an, ob eine Schaltfläche auf den automatischen Wiederholungsmodus festgelegt ist.|
|[CMFCButton::IsCheckBox](#ischeckbox)|Gibt an, ob eine Schaltfläche eine Kontrollkästchen Schaltfläche ist.|
|[CMFCButton::IsChecked](#ischecked)|Gibt an, ob die aktuelle Schaltfläche aktiviert ist.|
|[CMFCButton::IsHighlighted](#ishighlighted)|Gibt an, ob eine Schaltfläche hervorgehoben ist.|
|[CMFCButton::IsPressed](#ispressed)|Gibt an, ob eine Schaltfläche gedrückt und hervorgehoben wird.|
|[Cmfcbutton:: ispushed](#ispushed)|Gibt an, ob eine Schaltfläche gedrückt wird.|
|[CMFCButton::IsRadioButton](#isradiobutton)|Gibt an, ob eine Schaltfläche eine Options Schaltfläche ist.|
|[CMFCButton::IsWindowsThemingEnabled](#iswindowsthemingenabled)|Gibt an, ob der Stil des Schaltflächen Rahmens dem aktuellen Windows-Design entspricht.|
|`CMFCButton::OnDrawParentBackground`|Zeichnet den Hintergrund des übergeordneten Elements einer Schaltfläche im angegebenen Bereich. (Überschreibt [AFX_GLOBAL_DATA::D rawparser background](../../mfc/reference/afx-global-data-structure.md)|
|`CMFCButton::PreTranslateMessage`|Übersetzt Fenster Meldungen, bevor diese an die Windows-Funktionen [translatemess](/windows/win32/api/winuser/nf-winuser-translatemessage) und [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) gesendet werden. (Überschreibt [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|
|[CMFCButton::SetAutorepeatMode](#setautorepeatmode)|Legt eine Schaltfläche auf den automatischen Wiederholungsmodus fest.|
|[CMFCButton::SetCheckedImage](#setcheckedimage)|Legt das Bild für eine aktivierte Schaltfläche fest.|
|[CMFCButton::SetFaceColor](#setfacecolor)|Legt die Hintergrundfarbe für den Schaltflächen Text fest.|
|[CMFCButton::SetImage](#setimage)|Legt das Bild für eine Schaltfläche fest.|
|[CMFCButton::SetMouseCursor](#setmousecursor)|Legt das Cursor Bild fest.|
|[CMFCButton::SetMouseCursorHand](#setmousecursorhand)|Legt den Cursor auf das Bild einer Hand fest.|
|[CMFCButton::SetStdImage](#setstdimage)|Verwendet ein `CMenuImages` -Objekt, um das Schaltflächen Bild festzulegen.|
|[CMFCButton::SetTextColor](#settextcolor)|Legt die Farbe des Schaltflächen Texts für eine Schaltfläche fest, die nicht ausgewählt ist.|
|[CMFCButton::SetTextHotColor](#settexthotcolor)|Legt die Farbe des Schaltflächen Texts für eine Schaltfläche fest, die ausgewählt ist.|
|[CMFCButton::SetTooltip](#settooltip)|Verknüpft eine QuickInfo mit einer Schaltfläche.|
|[CMFCButton::SizeToContent](#sizetocontent)|Ändert die Größe einer Schaltfläche, sodass Sie den Schaltflächen Text und das Bild enthält.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCButton::OnDraw](#ondraw)|Wird vom Framework aufgerufen, um eine Schaltfläche zu zeichnen.|
|[CMFCButton::OnDrawBorder](#ondrawborder)|Wird von Framework aufgerufen, um den Rahmen einer Schaltfläche zu zeichnen.|
|[CMFCButton::OnDrawFocusRect](#ondrawfocusrect)|Wird von Framework aufgerufen, um das Fokus Rechteck für eine Schaltfläche zu zeichnen.|
|[CMFCButton::OnDrawText](#ondrawtext)|Wird vom Framework aufgerufen, um den Schaltflächen Text zu zeichnen.|
|[CMFCButton::OnFillBackground](#onfillbackground)|Wird von Framework aufgerufen, um den Hintergrund des Schaltflächen Texts zu zeichnen.|
|[CMFCButton::SelectFont](#selectfont)|Ruft die Schriftart ab, die dem angegebenen Gerätekontext zugeordnet ist.|

### <a name="data-members"></a>Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CMFCButton::m_nAlignStyle](#m_nalignstyle)|Gibt die Ausrichtung des Schaltflächen Texts an.|
|[CMFCButton::m_bDontUseWinXPTheme](#m_bDontUseWinXPTheme)|Gibt an, ob Windows XP-Designs verwendet werden sollen.|
|[CMFCButton::m_bDrawFocus](#m_bdrawfocus)|Gibt an, ob ein Fokus Rechteck um eine Schaltfläche gezeichnet werden soll.|
|[CMFCButton::m_nFlatStyle](#m_nflatstyle)|Gibt den Stil der Schaltfläche an, z. b. Borderless, Flat, Semi-Flat oder 3D.|
|[CMFCButton::m_bGrayDisabled](#m_bGrayDisabled)|Wenn der Wert true ist, kann eine deaktivierte Schaltfläche als abgeblendet gezeichnet werden.|
|[CMFCButton::m_bHighlightChecked](#m_bhighlightchecked)|Gibt an, ob eine BS_CHECKBOX-Schaltfläche hervorgehoben werden soll, wenn der Cursor darauf zeigt.|
|[CMFCButton::m_bResponseOnButtonDown](#m_bResponseOnButtonDown)|Gibt an, ob auf Schaltflächen-down-Ereignisse reagiert wird.|
|[CMFCButton::m_bRightImage](#m_brightimage)|Gibt an, ob ein Bild auf der rechten Seite der Schaltfläche angezeigt werden soll.|
|[CMFCButton::m_bTopImage](#m_bTopImage)| Gibt an, ob sich das Bild oberhalb der Schaltfläche befindet.|
|[CMFCButton::m_bTransparent](#m_btransparent)|Gibt an, ob die Schaltfläche transparent ist.|
|[CMFCButton::m_bWasDblClk](#m_bWasDblClk)| Gibt an, ob das letzte Click-Ereignis ein Doppelklick war.|

## <a name="remarks"></a>Hinweise

Andere Typen von Schaltflächen werden von der `CMFCButton` -Klasse abgeleitet, wie z. b. die [cmfcurrllinkbutton](../../mfc/reference/cmfclinkctrl-class.md) -Klasse, `CMFCColorButton` die Hyperlinks unterstützt, und die-Klasse, die ein Farbauswahl-Dialogfeld unterstützt.

`CMFCButton` Das Format eines-Objekts kann *3D*, *Flat*, *Semi-Flat* oder *No Border*lauten. Schaltflächen Text kann Links, oben oder zentriert einer Schaltfläche ausgerichtet werden. Zur Laufzeit können Sie steuern, ob die Schaltfläche Text, ein Bild oder einen Text und ein Bild anzeigt. Sie können auch angeben, dass ein bestimmtes Cursor Bild angezeigt werden soll, wenn der Cursor über eine Schaltfläche bewegt wird.

Erstellen Sie ein Schaltflächen-Steuerelement direkt im Code oder mit dem **MFC-Klassen-Assistenten** Tool und einer Dialogfeld Vorlage. Wenn Sie ein Schaltflächen-Steuerelement direkt erstellen `CMFCButton` , fügen Sie der Anwendung eine Variable hinzu, und rufen Sie `Create` dann den Konstruktor und die Methoden des `CMFCButton` Objekts auf. Wenn Sie den **MFC-Klassen-Assistenten**verwenden, `CButton` fügen Sie der Anwendung eine Variable hinzu, und ändern Sie dann den Typ `CButton` der `CMFCButton`Variablen von in.

Zum Verarbeiten von Benachrichtigungs Meldungen in einer Dialogfeld Anwendung fügen Sie einen Meldungs Zuordnungs Eintrag und einen Ereignishandler für jede Benachrichtigung hinzu. Die von einem `CMFCButton` -Objekt gesendeten Benachrichtigungen sind identisch mit denen, die `CButton` von einem-Objekt gesendet werden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie die Eigenschaften der Schaltfläche mithilfe verschiedener Methoden in der `CMFCButton` -Klasse konfiguriert werden. Das Beispiel ist Teil des Beispiels " [neue Steuerelemente](../../overview/visual-cpp-samples.md)".

[!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#31](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_2.cpp)]
[!code-cpp[NVC_MFC_NewControls#32](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_3.cpp)]
[!code-cpp[NVC_MFC_NewControls#33](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_4.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCButton](../../mfc/reference/cmfcbutton-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxbutton. h

##  <a name="cleanup"></a>Cmfcbutton:: Cleanup

Setzt interne Variablen zurück und gibt zugeordnete Ressourcen wie Bilder, Bitmaps und Symbole frei.

```
virtual void CleanUp();
```

##  <a name="enablefulltexttooltip"></a>Cmfcbutton:: enablefulltexttooltip

Gibt an, ob der vollständige Text einer QuickInfo in einem großen QuickInfo-Fenster oder eine gekürzte Version des Texts in einem kleinen QuickInfo-Fenster angezeigt werden soll.

```
void EnableFullTextTooltip(BOOL bOn=TRUE);
```

### <a name="parameters"></a>Parameter

*bOn*<br/>
in TRUE, um den gesamten Text anzuzeigen. FALSE, wenn der abgeschnittene Text angezeigt werden soll.

### <a name="remarks"></a>Hinweise

##  <a name="enablemenufont"></a>Cmfcbutton:: enablemenufont

Gibt an, ob die Schaltflächen Text Schriftart mit der Anwendungsmenü Schriftart identisch ist.

```
void EnableMenuFont(
    BOOL bOn=TRUE,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>Parameter

*bOn*<br/>
in TRUE, wenn die Anwendungsmenü Schriftart als Text Schriftart der Schaltfläche verwendet werden soll. FALSE, wenn die System Schriftart verwendet werden soll. Der Standardwert ist "true".

*bRedraw*<br/>
in TRUE, um den Bildschirm sofort neu zu zeichnen. andernfalls false. Der Standardwert ist "true".

### <a name="remarks"></a>Hinweise

Wenn Sie diese Methode nicht verwenden, um die Text Schriftart der Schaltfläche anzugeben, können Sie die Schriftart mit der [CWnd:: SetFont](../../mfc/reference/cwnd-class.md#setfont) -Methode angeben. Wenn Sie überhaupt keine Schriftart angeben, legt das Framework eine Standard Schriftart fest.

##  <a name="enablewindowstheming"></a>Cmfcbutton:: enablewindowstheming

Gibt an, ob der Stil des Schaltflächen Rahmens dem aktuellen Windows-Design entspricht.

```
static void EnableWindowsTheming(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parameter

*bEnable*<br/>
in TRUE, wenn das aktuelle Windows-Design zum Zeichnen von Schaltflächen Rahmen verwendet werden soll. FALSE, wenn das Windows-Design nicht verwendet werden soll. Der Standardwert ist "true".

### <a name="remarks"></a>Hinweise

Diese Methode wirkt sich auf alle Schaltflächen in der Anwendung aus, `CMFCButton` die von der-Klasse abgeleitet werden.

##  <a name="gettooltipctrl"></a>Cmfcbutton:: gettooltipctrl

Gibt einen Verweis auf das zugrunde liegende QuickInfo-Steuerelement zurück.

```
CToolTipCtrl& GetToolTipCtrl();
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das zugrunde liegende QuickInfo-Steuerelement.

### <a name="remarks"></a>Hinweise

##  <a name="isautocheck"></a>Cmfcbutton:: isautocheck

Gibt an, ob ein Kontrollkästchen oder Optionsfeld eine automatische Schaltfläche ist.

```
BOOL IsAutoCheck() const;
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die Schaltfläche den Stil BS_AUTOCHECKBOX oder BS_AUTORADIOBUTTON aufweist. andernfalls false.

### <a name="remarks"></a>Hinweise

##  <a name="isautorepeatcommandmode"></a>Cmfcbutton:: isautoreetatcommandmode

Gibt an, ob eine Schaltfläche auf den automatischen Wiederholungsmodus festgelegt ist.

```
BOOL IsAutorepeatCommandMode() const;
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die Schaltfläche auf den automatischen Wiederholungsmodus festgelegt ist. andernfalls false.

### <a name="remarks"></a>Hinweise

Verwenden Sie die [cmfcbutton:: setautorepeer atmode](#setautorepeatmode) -Methode, um eine Schaltfläche auf den automatischen Wiederholungsmodus festzulegen.

##  <a name="ischeckbox"></a>Cmfcbutton:: ischeckbox

Gibt an, ob eine Schaltfläche eine Kontrollkästchen Schaltfläche ist.

```
BOOL IsCheckBox() const;
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die Schaltfläche entweder BS_CHECKBOX oder BS_AUTOCHECKBOX Style hat. andernfalls false.

### <a name="remarks"></a>Hinweise

##  <a name="ischecked"></a>Cmfcbutton:: IsChecked

Gibt an, ob die aktuelle Schaltfläche aktiviert ist.

```
BOOL IsChecked() const;
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die aktuelle Schaltfläche aktiviert ist. andernfalls false.

### <a name="remarks"></a>Hinweise

Das Framework verwendet verschiedene Möglichkeiten, um anzugeben, dass verschiedene Arten von Schaltflächen geprüft werden. Beispielsweise wird ein Optionsfeld aktiviert, wenn es einen Punkt enthält. ein Kontrollkästchen wird aktiviert, wenn es ein **X**enthält.

##  <a name="ishighlighted"></a>Cmfcbutton:: ishervor gehoben

Gibt an, ob eine Schaltfläche hervorgehoben ist.

```
BOOL IsHighlighted() const;
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die Schaltfläche hervorgehoben ist. andernfalls false.

### <a name="remarks"></a>Hinweise

Eine Schaltfläche wird hervorgehoben, wenn mit dem Mauszeiger auf die Schaltfläche gezeigt wird.

##  <a name="ispressed"></a>Cmfcbutton:: ispree

Gibt an, ob eine Schaltfläche gedrückt und hervorgehoben wird.

```
BOOL IsPressed() const;
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die Schaltfläche gedrückt wird. andernfalls false.

### <a name="remarks"></a>Hinweise

##  <a name="ispushed"></a>Cmfcbutton:: ispushed

Gibt an, ob eine Schaltfläche gedrückt wird.

```
BOOL IsPushed() const;
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die Schaltfläche gedrückt wird. andernfalls false.

### <a name="remarks"></a>Hinweise

##  <a name="isradiobutton"></a>Cmfcbutton:: isradiobutton

Gibt an, ob eine Schaltfläche eine Options Schaltfläche ist.

```
BOOL IsRadioButton() const;
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn das Schaltflächen Format BS_RADIOBUTTON oder BS_AUTORADIOBUTTON ist. andernfalls false.

### <a name="remarks"></a>Hinweise

##  <a name="iswindowsthemingenabled"></a>Cmfcbutton:: iswindowsthemingenabled

Gibt an, ob der Stil des Schaltflächen Rahmens dem aktuellen Windows-Design entspricht.

```
static BOOL IsWindowsThemingEnabled();
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn der Stil des Schaltflächen Rahmens dem aktuellen Windows-Design entspricht. andernfalls false.

## <a name="a-namem_bdontusewinxptheme-cmfcbuttonm_bdontusewinxptheme"></a><a name="m_bDontUseWinXPTheme"/>Cmfcbutton:: m_bDontUseWinXPTheme

Gibt an, ob beim Zeichnen der Schaltfläche Windows XP-Designs verwendet werden sollen.

```
BOOL m_bDontUseWinXPTheme;
```

##  <a name="m_bdrawfocus"></a>Cmfcbutton:: m_bDrawFocus

Gibt an, ob ein Fokus Rechteck um eine Schaltfläche gezeichnet werden soll.

```
BOOL m_bDrawFocus;
```

### <a name="remarks"></a>Hinweise

Legen Sie `m_bDrawFocus` den Member auf true fest, um anzugeben, dass das Framework ein Fokus Rechteck um den Text und das Bild der Schaltfläche zeichnet, wenn die Schaltfläche den Fokus erhält.

Der `CMFCButton` Konstruktor initialisiert diesen Member als true.

##  <a name="m_bGrayDisabled"></a>Cmfcbutton:: m_bGrayDisabled

Wenn der Wert true ist, kann eine deaktivierte Schaltfläche als abgeblendet gezeichnet werden.

```
BOOL m_bGrayDisabled;
```

##  <a name="m_bhighlightchecked"></a>Cmfcbutton:: m_bHighlightChecked

Gibt an, ob eine BS_CHECKBOX-Schaltfläche hervorgehoben werden soll, wenn der Cursor darauf zeigt.

```
BOOL m_bHighlightChecked;
```

### <a name="remarks"></a>Hinweise

Legen Sie `m_bHighlightChecked` den Member auf true fest, um anzugeben, dass das Framework eine BS_CHECKBOX-Schaltfläche hervorheben soll, wenn mit dem Mauszeiger darauf gezeigt wird.

##  <a name="m_bResponseOnButtonDown"></a>Cmfcbutton:: m_bResponseOnButtonDown

Gibt an, ob auf Schaltflächen-down-Ereignisse reagiert wird.

```
BOOL m_bResponseOnButtonDown;
```

##  <a name="m_brightimage"></a>Cmfcbutton:: m_bRightImage

Gibt an, ob ein Bild auf der rechten Seite der Schaltfläche angezeigt werden soll.

```
BOOL m_bRightImage;
```

##  <a name="m_bTopImage"></a>Cmfcbutton:: m_bTopImage] (#m_bTopImage)

Gibt an, ob sich das Bild oberhalb der Schaltfläche befindet.

```
BOOL m_bTopImage;
```

### <a name="remarks"></a>Hinweise

Legen Sie `m_bRightImage` den Member auf true fest, um anzugeben, dass das Framework das Bild der Schaltfläche rechts neben der Text Bezeichnung der Schaltfläche anzeigt.

##  <a name="m_btransparent"></a>Cmfcbutton:: m_bTransparent

Gibt an, ob die Schaltfläche transparent ist.

```
BOOL m_bTransparent;
```

### <a name="remarks"></a>Hinweise

Legen Sie `m_bTransparent` den Member auf true fest, um anzugeben, dass die Schaltfläche durch das Framework transparent wird. Der `CMFCButton` Konstruktor initialisiert diesen Member mit false.

##  <a name="m_nalignstyle"></a>Cmfcbutton:: m_nAlignStyle

Gibt die Ausrichtung des Schaltflächen Texts an.

```
AlignStyle m_nAlignStyle;
```

### <a name="remarks"></a>Hinweise

Verwenden Sie einen der folgenden `CMFCButton::AlignStyle` Enumerationswerte, um die Ausrichtung des Schaltflächen Texts anzugeben:

|Wert|Beschreibung|
|-----------|-----------------|
|ALIGN_CENTER|Vorgegebene Richtet den Schaltflächen Text an der Mitte der Schaltfläche aus.|
|ALIGN_LEFT|Richtet den Schaltflächen Text auf der linken Seite der Schaltfläche aus.|
|ALIGN_RIGHT|Richtet den Schaltflächen Text auf der rechten Seite der Schaltfläche aus.|

Der `CMFCButton` Konstruktor initialisiert diesen Member mit ALIGN_CENTER.

##  <a name="m_bWasDblClk"></a>Cmfcbutton:: m_bWasDblClk] (#m_bWasDblClk) |

Gibt an, ob das letzte Click-Ereignis ein Doppelklick war. |

```
BOOL m_bWasDblClk;
```

##  <a name="m_nflatstyle"></a>Cmfcbutton:: m_nFlatStyle

Gibt den Stil der Schaltfläche an, z. b. Borderless, Flat, Semi-Flat oder 3D.

```
FlatStyle  m_nFlatStyle;
```

### <a name="remarks"></a>Hinweise

In der folgenden Tabelle sind `CMFCButton::m_nFlatStyle` die Enumerationswerte aufgelistet, die die Darstellung einer Schaltfläche angeben.

|Wert|Beschreibung|
|-----------|-----------------|
|BUTTONSTYLE_3D|Vorgegebene Die Schaltfläche wird mit einer hohen, dreidimensionalen Seite angezeigt. Wenn auf die Schaltfläche geklickt wird, wird die Schaltfläche in einen tiefen Einzug gedrückt.|
|BUTTONSTYLE_FLAT|Wenn die Maus nicht über die Schaltfläche bewegt wird, scheint die Schaltfläche zweidimensional zu sein und hat keine Seiten. Wenn die Maus über der Schaltfläche angehalten wird, scheint die Schaltfläche eine niedrige, dreidimensionale Seite zu haben. Wenn auf die Schaltfläche geklickt wird, wird die Schaltfläche in einen flachen Einzug gedrückt.|
|BUTTONSTYLE_SEMIFLAT|Die Schaltfläche scheint eine niedrige, dreidimensionale Seite zu haben. Wenn auf die Schaltfläche geklickt wird, wird die Schaltfläche in einen tiefen Einzug gedrückt.|
|BUTTONSTYLE_NOBORDERS|Die Schaltfläche weist keine angehobenen Seiten auf und wird immer zweidimensional angezeigt. Die Schaltfläche wird anscheinend nicht in einen Einzug gedrückt, wenn darauf geklickt wird.|

Der `CMFCButton` Konstruktor initialisiert diesen Member mit BUTTONSTYLE_3D.

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie die Werte der `m_nFlatStyle` Member-Variable in der `CMFCButton` -Klasse festgelegt werden. Dieses Beispiel ist Teil des Beispiels " [neue Steuerelemente](../../overview/visual-cpp-samples.md)".

[!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#29](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_5.cpp)]

##  <a name="ondraw"></a>Cmfcbutton:: OnDraw

Wird vom Framework aufgerufen, um eine Schaltfläche zu zeichnen.

```
virtual void OnDraw(
    CDC* pDC,
    const CRect& rect,
    UINT uiState);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
in Ein Zeiger auf einen Gerätekontext.

*Rect*<br/>
in Ein Verweis auf ein Rechteck, das die Schaltfläche umschließt.

*uiState*<br/>
in Der aktuelle Schaltflächen Zustand. Weitere Informationen finden Sie im `itemState` Thema zum-Element der [drawitemstruct-Struktur](/windows/win32/api/winuser/ns-winuser-drawitemstruct) .

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode, um Ihren eigenen Code zum Zeichnen einer Schaltfläche zu verwenden.

##  <a name="ondrawborder"></a>Cmfcbutton:: ondrawborder

Wird von Framework aufgerufen, um den Rahmen einer Schaltfläche zu zeichnen.

```
virtual void OnDrawBorder(
    CDC* pDC,
    CRect& rectClient,
    UINT uiState);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
in Ein Zeiger auf einen Gerätekontext.

*rectClient*<br/>
in Ein Verweis auf ein Rechteck, das die Schaltfläche umschließt.

*uiState*<br/>
in Der aktuelle Schaltflächen Zustand. Weitere Informationen finden Sie im `itemState` Thema zum-Element der [drawitemstruct-Struktur](/windows/win32/api/winuser/ns-winuser-drawitemstruct) .

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode, um Ihren eigenen Code zum Zeichnen des Rahmens zu verwenden.

##  <a name="ondrawfocusrect"></a>Cmfcbutton:: ondrawfocurect

Wird von Framework aufgerufen, um das Fokus Rechteck für eine Schaltfläche zu zeichnen.

```
virtual void OnDrawFocusRect(
    CDC* pDC,
    const CRect& rectClient);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
in Ein Zeiger auf einen Gerätekontext.

*rectClient*<br/>
in Ein Verweis auf ein Rechteck, das die Schaltfläche umschließt.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode, um den eigenen Code zum Zeichnen des Fokus Rechtecks zu verwenden.

##  <a name="ondrawtext"></a>Cmfcbutton:: ondrawtext

Wird vom Framework aufgerufen, um den Schaltflächen Text zu zeichnen.

```
virtual void OnDrawText(
    CDC* pDC,
    const CRect& rect,
    const CString& strText,
    UINT uiDTFlags,
    UINT uiState);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
in Ein Zeiger auf einen Gerätekontext.

*Rect*<br/>
in Ein Verweis auf ein Rechteck, das die Schaltfläche umschließt.

*strText*<br/>
in Der zu zeichnende Text.

*uidtflags*<br/>
in Flags, die angeben, wie der Text formatiert werden soll. Weitere Informationen finden Sie unter dem *nformat* -Parameter der [CDC::D rawtext](../../mfc/reference/cdc-class.md#drawtext) -Methode.

*uiState*<br/>
[in] Reserviert.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode, um Ihren eigenen Code zum Zeichnen des Schaltflächen Texts zu verwenden.

##  <a name="onfillbackground"></a>Cmfcbutton:: onfillbackground

Wird von Framework aufgerufen, um den Hintergrund des Schaltflächen Texts zu zeichnen.

```
virtual void OnFillBackground(
    CDC* pDC,
    const CRect& rectClient);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
in Ein Zeiger auf einen Gerätekontext.

*rectClient*<br/>
in Ein Verweis auf ein Rechteck, das die Schaltfläche umschließt.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode, um Ihren eigenen Code zum Zeichnen des Hintergrunds einer Schaltfläche zu verwenden.

##  <a name="selectfont"></a>Cmfcbutton:: selectfont

Ruft die Schriftart ab, die dem angegebenen Gerätekontext zugeordnet ist.

```
virtual CFont* SelectFont(CDC* pDC);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
in Ein Zeiger auf einen Gerätekontext.

### <a name="return-value"></a>Rückgabewert

Überschreiben Sie diese Methode, um Ihren eigenen Code zum Abrufen der Schriftart zu verwenden.

### <a name="remarks"></a>Hinweise

##  <a name="setautorepeatmode"></a>Cmfcbutton:: abtautorepeer atmode

Legt eine Schaltfläche auf den automatischen Wiederholungsmodus fest.

```
void SetAutorepeatMode(int nTimeDelay=500);
```

### <a name="parameters"></a>Parameter

*nTimeDelay*<br/>
in Eine nicht negative Zahl, die das Intervall zwischen Nachrichten angibt, die an das übergeordnete Fenster gesendet werden. Das Intervall wird in Millisekunden gemessen, und der Standardwert beträgt 500 Millisekunden. Geben Sie NULL an, um den automatischen Wiederholungs Nachrichten Modus zu deaktivieren.

### <a name="remarks"></a>Hinweise

Diese Methode bewirkt, dass die Schaltfläche WM_COMMAND-Nachrichten ständig an das übergeordnete Fenster sendet, bis die Schaltfläche losgelassen wird, oder der *ntimedelay* -Parameter ist auf NULL festgelegt.

##  <a name="setcheckedimage"></a>Cmfcbutton:: setcheckedimage

Legt das Bild für eine aktivierte Schaltfläche fest.

```
void SetCheckedImage(
    HICON hIcon,
    BOOL bAutoDestroy=TRUE,
    HICON hIconHot=NULL,
    HICON hIconDisabled=NULL,
    BOOL bAlphaBlend=FALSE);

void SetCheckedImage(
    HBITMAP hBitmap,
    BOOL bAutoDestroy=TRUE,
    HBITMAP hBitmapHot=NULL,
    BOOL bMap3dColors=TRUE,
    HBITMAP hBitmapDisabled=NULL);

void SetCheckedImage(
    UINT uiBmpResId,
    UINT uiBmpHotResId=0,
    UINT uiBmpDsblResID=0);
```

### <a name="parameters"></a>Parameter

*hIcon*<br/>
in Handle für das Symbol, das die Bitmap und Maske für das neue Bild enthält.

*bAutoDestroy*<br/>
in TRUE, um anzugeben, dass Bitmapressourcen automatisch zerstört werden sollen. andernfalls false. Der Standardwert ist "true".

*hIconHot*<br/>
in Handle für das Symbol, das das Bild für den ausgewählten Zustand enthält.

*hBitmap*<br/>
in Handle für die Bitmap, die das Bild für den nicht ausgewählten Zustand enthält.

*hBitmapHot*<br/>
in Handle für die Bitmap, die das Bild für den ausgewählten Zustand enthält.

*bMap3dColors*<br/>
in Gibt eine transparente Farbe für den Hintergrund der Schaltfläche an. Das heißt, die Vorderseite der Schaltfläche. TRUE, wenn der Farbwert RGB (192, 192, 192) verwendet werden soll. FALSE, wenn der von definierte Farbwert `AFX_GLOBAL_DATA::clrBtnFace`verwendet werden soll.

*uiBmpResId*<br/>
in Die Ressourcen-ID für das nicht ausgewählte Image.

*uiBmpHotResId*<br/>
in Die Ressourcen-ID für das ausgewählte Image.

*hIconDisabled*<br/>
in Handle für das Symbol für das deaktivierte Bild.

*hBitmapDisabled*<br/>
in Handle für die Bitmap, die das deaktivierte Bild enthält.

*uiBmpDsblResID*<br/>
in Die Ressourcen-ID der deaktivierten Bitmap.

*bAlphaBlend*<br/>
in "True", um nur 32-Bit-Images zu verwenden, die den Alphakanal verwenden. FALSE, wenn nicht nur Alphakanal Bilder verwendet werden sollen. Der Standardwert ist false.

### <a name="remarks"></a>Hinweise

##  <a name="setfacecolor"></a>Cmfcbutton:: setfakecolor

Legt die Hintergrundfarbe für den Schaltflächen Text fest.

```
void SetFaceColor(
    COLORREF crFace,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>Parameter

*crFace*<br/>
in Ein RGB-Farbwert.

*bRedraw*<br/>
in TRUE, um den Bildschirm sofort neu zu zeichnen. andernfalls false.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode, um eine neue Füllfarbe für den Hintergrund der Schaltfläche (Gesicht) zu definieren. Beachten Sie, dass der Hintergrund nicht ausgefüllt wird, wenn die [cmfcbutton:: m_bTransparent](#m_btransparent) -Member-Variable den Wert true hat.

##  <a name="setimage"></a>Cmfcbutton:: abtimage

Legt das Bild für eine Schaltfläche fest.

```
void SetImage(
    HICON hIcon,
    BOOL bAutoDestroy=TRUE,
    HICON hIconHot=NULL,
    HICON hIconDisabled=NULL,
    BOOL bAlphaBlend=FALSE);

void SetImage(
    HBITMAP hBitmap,
    BOOL bAutoDestroy=TRUE,
    HBITMAP hBitmapHot=NULL,
    BOOL bMap3dColors=TRUE,
    HBITMAP hBitmapDisabled=NULL);

void SetImage(
    UINT uiBmpResId,
    UINT uiBmpHotResId=0,
    UINT uiBmpDsblResID=0);
```

### <a name="parameters"></a>Parameter

*hIcon*<br/>
in Handle für das Symbol, das die Bitmap und Maske für das neue Bild enthält.

*bAutoDestroy*<br/>
in TRUE, um anzugeben, dass Bitmapressourcen automatisch zerstört werden sollen. andernfalls false. Der Standardwert ist "true".

*hIconHot*<br/>
in Handle für das Symbol, das das Bild für den ausgewählten Zustand enthält.

*hBitmap*<br/>
in Handle für die Bitmap, die das Bild für den nicht ausgewählten Zustand enthält.

*hBitmapHot*<br/>
in Handle für die Bitmap, die das Bild für den ausgewählten Zustand enthält.

*uiBmpResId*<br/>
in Die Ressourcen-ID für das nicht ausgewählte Image.

*uiBmpHotResId*<br/>
in Die Ressourcen-ID für das ausgewählte Image.

*bMap3dColors*<br/>
in Gibt eine transparente Farbe für den Hintergrund der Schaltfläche an. Das heißt, die Vorderseite der Schaltfläche. TRUE, wenn der Farbwert RGB (192, 192, 192) verwendet werden soll. FALSE, wenn der von definierte Farbwert `AFX_GLOBAL_DATA::clrBtnFace`verwendet werden soll.

*hIconDisabled*<br/>
in Handle für das Symbol für das deaktivierte Bild.

*hBitmapDisabled*<br/>
in Handle für die Bitmap, die das deaktivierte Bild enthält.

*uiBmpDsblResID*<br/>
in Die Ressourcen-ID der deaktivierten Bitmap.

*bAlphaBlend*<br/>
in "True", um nur 32-Bit-Images zu verwenden, die den Alphakanal verwenden. FALSE, wenn nicht nur Alphakanal Bilder verwendet werden sollen. Der Standardwert ist false.

### <a name="remarks"></a>Hinweise

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie verschiedene Versionen der `SetImage` -Methode in der `CMFCButton` -Klasse verwendet werden. Das Beispiel ist Teil des Beispiels " [neue Steuerelemente](../../overview/visual-cpp-samples.md)".

[!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#31](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_2.cpp)]

##  <a name="setmousecursor"></a>Cmfcbutton:: abktmousecursor

Legt das Cursor Bild fest.

```
void SetMouseCursor(HCURSOR hcursor);
```

### <a name="parameters"></a>Parameter

*hcursor*<br/>
in Das Handle eines Cursors.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode, um ein Cursor Bild, z. b. den Hand Cursor, mit der Schaltfläche zuzuordnen. Der Cursor wird aus den Anwendungs Ressourcen geladen.

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie die `SetMouseCursor` -Methode in `CMFCButton` der-Klasse verwendet wird. Das Beispiel ist Teil des Codes im Beispiel " [neue Steuerelemente](../../overview/visual-cpp-samples.md)".

[!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#30](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_6.cpp)]

##  <a name="setmousecursorhand"></a>Cmfcbutton:: abktmousecursorhand

Legt den Cursor auf das Bild einer Hand fest.

```
void SetMouseCursorHand();
```

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode, um das Cursor Bild einer Hand mit der Schaltfläche zuzuordnen. Der Cursor wird aus den Anwendungs Ressourcen geladen.

##  <a name="setstdimage"></a>Cmfcbutton:: setstdimage

Verwendet ein `CMenuImages` -Objekt, um das Schaltflächen Bild festzulegen.

```
void SetStdImage(
    CMenuImages::IMAGES_IDS id,
    CMenuImages::IMAGE_STATE state=CMenuImages::ImageBlack,
    CMenuImages::IMAGES_IDS idDisabled=(CMenuImages::IMAGES_IDS)0);
```

### <a name="parameters"></a>Parameter

*ID*<br/>
in Einer der Bezeichner der Schaltflächen Bilder, der in der `CMenuImage::IMAGES_IDS` -Enumeration definiert ist. Die Bildwerte geben Bilder an, z. b. Pfeile, Pins und Options Felder.

*state*<br/>
in Einer der Schaltflächen-Bild Zustands Bezeichner, der in der `CMenuImages::IMAGE_STATE` -Enumeration definiert ist. Die Bild Zustände geben Schaltflächen Farben an, z. b. schwarz, grau, hellgrau, weiß und dunkelgrau. Der Standardwert ist `CMenuImages::ImageBlack`.

*idDisabled*<br/>
in Einer der Bezeichner der Schaltflächen Bilder, der in der `CMenuImage::IMAGES_IDS` -Enumeration definiert ist. Das Bild gibt an, dass die Schaltfläche deaktiviert ist. Der Standardwert ist das erste Schaltflächen Bild `CMenuImages::IdArrowDown`().

### <a name="remarks"></a>Hinweise

##  <a name="settextcolor"></a>Cmfcbutton:: SetTextColor

Legt die Farbe des Schaltflächen Texts für eine Schaltfläche fest, die nicht ausgewählt ist.

```
void SetTextColor(COLORREF clrText);
```

### <a name="parameters"></a>Parameter

*clrText*<br/>
in Ein RGB-Farbwert.

### <a name="remarks"></a>Hinweise

##  <a name="settexthotcolor"></a>Cmfcbutton:: settexthotcolor

Legt die Farbe des Schaltflächen Texts für eine Schaltfläche fest, die ausgewählt ist.

```
void SetTextHotColor(COLORREF clrTextHot);
```

### <a name="parameters"></a>Parameter

*clrTextHot*<br/>
in Ein RGB-Farbwert.

### <a name="remarks"></a>Hinweise

##  <a name="settooltip"></a>Cmfcbutton:: SetToolTip

Verknüpft eine QuickInfo mit einer Schaltfläche.

```
void SetTooltip(LPCTSTR lpszToolTipText);
```

### <a name="parameters"></a>Parameter

*lpszToolTipText*<br/>
in Zeiger auf den Text für die QuickInfo. Geben Sie NULL an, um die QuickInfo zu deaktivieren.

### <a name="remarks"></a>Hinweise

##  <a name="sizetocontent"></a>Cmfcbutton:: sizeto Content

Ändert die Größe einer Schaltfläche, sodass Sie den Schaltflächen Text und das Bild enthält.

```
virtual CSize SizeToContent(BOOL bCalcOnly=FALSE);
```

### <a name="parameters"></a>Parameter

*bCalcOnly*<br/>
in TRUE, wenn die neue Größe der Schaltfläche berechnet, aber nicht geändert werden soll. FALSE, um die Größe der Schaltfläche zu ändern. Der Standardwert ist false.

### <a name="return-value"></a>Rückgabewert

Ein `CSize` -Objekt, das die neue Größe der Schaltfläche enthält.

### <a name="remarks"></a>Hinweise

Standardmäßig berechnet diese Methode eine neue Größe, die einen horizontalen Rand von 10 Pixeln und einen vertikalen Rand von 5 Pixeln umfasst.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCLinkCtrl-Klasse](../../mfc/reference/cmfclinkctrl-class.md)<br/>
[CMFCColorButton-Klasse](../../mfc/reference/cmfccolorbutton-class.md)<br/>
[CMFCMenuButton-Klasse](../../mfc/reference/cmfcmenubutton-class.md)
