---
title: Cmfcoutlookbarpane-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCOutlookBarPane
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::AddButton
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::CanBeAttached
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::ClearAll
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::Create
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::EnablePageScrollMode
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::GetRegularColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::IsBackgroundTexture
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::IsDrawShadedHighlight
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::RemoveButton
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetBackColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetBackImage
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetDefaultState
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetExtraSpace
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetTextColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::SetTransparentColor
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::EnableContextMenuItems
- AFXOUTLOOKBARPANE/CMFCOutlookBarPane::RemoveAllButtons
helpviewer_keywords:
- CMFCOutlookBarPane [MFC], AddButton
- CMFCOutlookBarPane [MFC], CanBeAttached
- CMFCOutlookBarPane [MFC], ClearAll
- CMFCOutlookBarPane [MFC], Create
- CMFCOutlookBarPane [MFC], EnablePageScrollMode
- CMFCOutlookBarPane [MFC], GetRegularColor
- CMFCOutlookBarPane [MFC], IsBackgroundTexture
- CMFCOutlookBarPane [MFC], IsDrawShadedHighlight
- CMFCOutlookBarPane [MFC], RemoveButton
- CMFCOutlookBarPane [MFC], SetBackColor
- CMFCOutlookBarPane [MFC], SetBackImage
- CMFCOutlookBarPane [MFC], SetDefaultState
- CMFCOutlookBarPane [MFC], SetExtraSpace
- CMFCOutlookBarPane [MFC], SetTextColor
- CMFCOutlookBarPane [MFC], SetTransparentColor
- CMFCOutlookBarPane [MFC], EnableContextMenuItems
- CMFCOutlookBarPane [MFC], RemoveAllButtons
ms.assetid: 094e2ef3-a118-487e-a4cc-27626108fe08
ms.openlocfilehash: 9ef6a06a4889119e39e72a9e495e5d4f9e17cf56
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505150"
---
# <a name="cmfcoutlookbarpane-class"></a>Cmfcoutlookbarpane-Klasse

Weitere Informationen finden Sie im Quellcode, der sich im **Ordner\\VC atlmfc\\\\src MFC** Ihrer Visual Studio-Installation befindet.

Ein von der [cmfctoolbar-Klasse](../../mfc/reference/cmfctoolbar-class.md) abgeleitetes Steuerelement, das in eine Outlook-Leiste ( [CMFCOutlookBar-Klasse](../../mfc/reference/cmfcoutlookbar-class.md)) eingefügt werden kann. Der Outlook-Leistenbereich enthält eine Spalte mit großen Schaltflächen. Der Benutzer kann einen Bildlauf durchführen, um die Liste der Schaltflächen nach oben bzw. unten zu verschieben, wenn sie größer ist als der Bereich. Wenn der Benutzer einen Outlook-Leistenbereich von der Outlook-Leiste trennt, ist er frei positionierbar oder kann im Hauptrahmenfenster andocken.

## <a name="syntax"></a>Syntax

```
class CMFCOutlookBarPane : public CMFCToolBar
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|`CMFCOutlookBarPane::CMFCOutlookBarPane`|Standardkonstruktor|
|`CMFCOutlookBarPane::~CMFCOutlookBarPane`|Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCOutlookBarPane::AddButton](#addbutton)|Fügt dem Bereich der Outlook-Leiste eine Schaltfläche hinzu.|
|[Cmfcoutlookbarpane:: canbeattached](#canbeattached)|Bestimmt, ob der Bereich an einen anderen Bereich oder Rahmen Fenster angedockt werden kann. (Überschreibt [cbasepane:: canbeattached](../../mfc/reference/cbasepane-class.md#canbeattached).)|
|`CMFCOutlookBarPane::CanBeRestored`|Bestimmt, ob das System nach der Anpassung den ursprünglichen Zustand einer Symbolleiste wiederherstellen kann. (Überschreibt [cmfctoolbar:: canberestored](../../mfc/reference/cmfctoolbar-class.md#canberestored).)|
|[CMFCOutlookBarPane::ClearAll](#clearall)|Gibt die Ressourcen frei, die von den Bildern im Outlook-Balken Bereich verwendet werden.|
|[CMFCOutlookBarPane::Create](#create)|Erstellt den Bereich der Outlook-Leiste.|
|`CMFCOutlookBarPane::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|
|`CMFCOutlookBarPane::Dock`|Wird von Framework aufgerufen, um den Bereich der Outlook-Leiste zu docken. (Überschreibt `CPane::Dock`.)|
|[CMFCOutlookBarPane::EnablePageScrollMode](#enablepagescrollmode)|Gibt an, ob die Bild Lauf Pfeile im Bereich der Outlook-Leiste die Liste der Schaltflächen nach Seite oder durch Schaltfläche nach oben verschieben.|
|[CMFCOutlookBarPane::GetRegularColor](#getregularcolor)|Gibt die reguläre (nicht ausgewählte) Textfarbe des Outlook-leisten Bereichs zurück.|
|`CMFCOutlookBarPane::GetThisClass`|Wird vom Framework verwendet, um einen Zeiger auf das [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt abzurufen, das diesem Klassentyp zugeordnet ist.|
|[CMFCOutlookBarPane::IsBackgroundTexture](#isbackgroundtexture)|Bestimmt, ob für den Bereich der Outlook-Leiste ein Hintergrundbild geladen wurde.|
|`CMFCOutlookBarPane::IsChangeState`|Bestimmt, ob ein Gleit Komma angedockt werden kann. (Überschreibt `CPane::IsChangeState`.)|
|[CMFCOutlookBarPane::IsDrawShadedHighlight](#isdrawshadedhighlight)|Bestimmt, ob der Schaltflächen Rahmen schattiert wird, wenn eine Schaltfläche markiert wird und ein Hintergrundbild angezeigt wird.|
|`CMFCOutlookBarPane::OnBeforeFloat`|Wird von Framework aufgerufen, wenn ein Bereich im Begriff ist, zu float zu werden. (Überschreibt [CPANE:: onbeforefloat](../../mfc/reference/cpane-class.md#onbeforefloat).)|
|[CMFCOutlookBarPane::RemoveButton](#removebutton)|Entfernt die Schaltfläche mit einer angegebenen Befehls-ID.|
|`CMFCOutlookBarPane::RestoreOriginalstate`|Stellt den originalen Zustand einer Symbolleiste wieder her. (Überschreibt [cmfctoolbar:: restoreoriginalstate](../../mfc/reference/cmfctoolbar-class.md#restoreoriginalstate).)|
|[CMFCOutlookBarPane::SetBackColor](#setbackcolor)|Legt die Hintergrundfarbe fest.|
|[CMFCOutlookBarPane::SetBackImage](#setbackimage)|Legt das Hintergrundbild fest.|
|[CMFCOutlookBarPane::SetDefaultState](#setdefaultstate)|Setzt den Bereich der Outlook-Leiste auf den ursprünglichen Satz von Schaltflächen zurück.|
|[CMFCOutlookBarPane::SetExtraSpace](#setextraspace)|Legt die Anzahl der in den Schaltflächen im Bereich der Outlook-Leiste verwendeten Auffüll Zeichen fest.|
|[CMFCOutlookBarPane::SetTextColor](#settextcolor)|Legt die Farben für regulären und markierten Text im Bereich der Outlook-Leiste fest.|
|[CMFCOutlookBarPane::SetTransparentColor](#settransparentcolor)|Legt die transparente Farbe für den Bereich der Outlook-Leiste fest.|
|`CMFCOutlookBarPane::SmartUpdate`|Wird intern verwendet, um die Outlook-Leiste zu aktualisieren. (Überschreibt `CMFCToolBar::SmartUpdate`.)|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCOutlookBarPane::EnableContextMenuItems](#enablecontextmenuitems)|Gibt an, welche Kontextmenü Elemente im Anpassungsmodus angezeigt werden.|
|[CMFCOutlookBarPane::RemoveAllButtons](#removeallbuttons)|Entfernt alle Schaltflächen aus dem Bereich der Outlook-Leiste. (Überschreibt [cmfctoolbar:: removeallbuttons](../../mfc/reference/cmfctoolbar-class.md#removeallbuttons).)|

## <a name="remarks"></a>Hinweise

Informationen dazu, wie Sie eine Outlook-Leiste implementieren, finden Sie unter [CMFCOutlookBar-Klasse](../../mfc/reference/cmfcoutlookbar-class.md).

Ein Beispiel für eine Outlook-Leiste finden Sie im Beispiel Projekt "OutlookDemo".

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie verschiedene Methoden der `CMFCOutlookBarPane` -Klasse verwendet werden. Das Beispiel zeigt, wie Sie einen Outlook-Leistenbereich erstellen, den Seitenbild Lauf Modus aktivieren, Andocken aktivieren und die Hintergrundfarbe der Outlook-Leiste festlegen. Dieser Code Ausschnitt ist Teil des Outlook-Beispiels mit [mehreren Ansichten](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_OutlookMultiViews#3](../../mfc/reference/codesnippet/cpp/cmfcoutlookbarpane-class_1.h)]
[!code-cpp[NVC_MFC_OutlookMultiViews#4](../../mfc/reference/codesnippet/cpp/cmfcoutlookbarpane-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)

[CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

[CMFCOutlookBarPane](../../mfc/reference/cmfcoutlookbarpane-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxoutlookbarpane. h

##  <a name="addbutton"></a>Cmfcoutlookbarpane:: AddButton

Fügt dem Bereich der Outlook-Leiste eine Schaltfläche hinzu.

```
BOOL AddButton(
    UINT uiImage,
    LPCTSTR lpszLabel,
    UINT iIdCommand,
    int iInsertAt=-1);

BOOL AddButton(
    UINT uiImage,
    UINT uiLabel,
    UINT iIdCommand,
    int iInsertAt=-1);

BOOL AddButton(
    LPCTSTR szBmpFileName,
    LPCTSTR szLabel,
    UINT iIdCommand,
    int iInsertAt=-1);

BOOL AddButton(
    HBITMAP hBmp,
    LPCTSTR lpszLabel,
    UINT iIdCommand,
    int iInsertAt=-1);

BOOL AddButton(
    HICON hIcon,
    LPCTSTR lpszLabel,
    UINT iIdCommand,
    int iInsertAt=-1,
    BOOL bAlphaBlend=FALSE);
```

### <a name="parameters"></a>Parameter

*uiImage*<br/>
in Gibt den Ressourcen Bezeichner einer Bitmap an.

*lpszLabel*<br/>
in Gibt den Text der Schaltfläche an.

*iIdCommand*<br/>
in Gibt die ID des Schaltflächen-Steuer Elements an.

*iInsertAt*<br/>
in Gibt den NULL basierten Index auf der Seite der Outlook-Leiste an, an der die Schaltfläche eingefügt werden soll.

*uiLabel*<br/>
in Eine Zeichen folgen Ressourcen-ID.

*szBmpFileName*<br/>
in Gibt den Namen der zu ladenden Datenträger Image Datei an.

*szLabel*<br/>
in Gibt den Text der Schaltfläche an.

*hBmp*<br/>
in Ein Handle für die Bitmap einer Schaltfläche.

*hIcon*<br/>
in Ein Handle für das Symbol der Schaltflächen.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn eine Schaltfläche erfolgreich hinzugefügt wurde. andernfalls false.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode, um eine neue Schaltfläche in die Seite einer Outlook-Leiste einzufügen. Das Bild der Schaltfläche kann entweder aus den Anwendungs Ressourcen oder aus einer Datenträger Datei geladen werden.

Wenn die von *uipageid* angegebene Seiten-ID-1 ist, wird die Schaltfläche in die erste Seite eingefügt.

Wenn der von *iinsertat* angegebene Index-1 ist, wird die Schaltfläche am Ende der Seite hinzugefügt.

##  <a name="canbeattached"></a>Cmfcoutlookbarpane:: canbeattached

Weitere Informationen finden Sie im Quellcode, der sich im **Ordner\\VC atlmfc\\\\src MFC** Ihrer Visual Studio-Installation befindet.

```
virtual BOOL CanBeAttached() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="clearall"></a>Cmfcoutlookbarpane:: ClearAll

Gibt die Ressourcen frei, die von den Bildern im Bereich der Outlook-Leiste verwendet werden.

```
void ClearAll();
```

### <a name="remarks"></a>Hinweise

Diese Methode ruft direkt [cmfctoolbarimages:: Clear](../../mfc/reference/cmfctoolbarimages-class.md#clear)auf, die für die Bilder aufgerufen wird, die im Bereich der Outlook-Leiste verwendet werden.

##  <a name="create"></a>Cmfcoutlookbarpane:: Create

Erstellt den Bereich der Outlook-Leiste.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle=AFX_DEFAULT_TOOLBAR_STYLE,
    UINT uiID=(UINT)-1,
    DWORD dwControlBarStyle=0);
```

### <a name="parameters"></a>Parameter

*pParentWnd*<br/>
in Gibt das übergeordnete Fenster des Outlook-Leistenbereich-Steuer Elements an. Darf nicht NULL sein.

*dwStyle*<br/>
in Der Fenster Stil.  Eine Liste der Fenster Stile finden Sie unter [Fenster Stile](../../mfc/reference/styles-used-by-mfc.md#window-styles).

*uiID*<br/>
in Die Steuerelement-ID. Muss eindeutig sein, um das Speichern des Zustands des Steuer Elements zu ermöglichen.

*dwControlBarStyle*<br/>
in Gibt spezielle Stile an, die das Verhalten des Outlook-Steuerelement Fensters definieren, wenn es von der Outlook-Leiste getrennt wird.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die Methode erfolgreich war. andernfalls false.

### <a name="remarks"></a>Hinweise

Um ein `CMFCOutlookBarPane` -Objekt zu erstellen, müssen Sie zuerst den-Konstruktor `Create`und dann den-Konstruktor aufzurufen, der das Outlook- `CMFCOutlookBarPane` leisten Bereichs Steuerelement erstellt und an das-Objekt bindet.

Weitere Informationen `dwControlBarStyle` finden Sie unter [cbasepane::](../../mfc/reference/cbasepane-class.md#createex)up-Ex.

##  <a name="enablecontextmenuitems"></a>Cmfcoutlookbarpane:: enablecontextmenuitems

Gibt an, welche Kontextmenü Elemente im Anpassungsmodus angezeigt werden.

```
virtual BOOL EnableContextMenuItems(
    CMFCToolBarButton* pButton,
    CMenu* pPopup);
```

### <a name="parameters"></a>Parameter

*pButton*<br/>
in Ein Zeiger auf eine Symbolleisten Schaltfläche, auf die Benutzer geklickt haben.

*pPopup*<br/>
in Ein Zeiger auf das Kontextmenü.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn das Kontextmenü angezeigt werden soll. andernfalls false.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode, um das Framework Standard-Kontextmenü zu ändern, das das Framework im Anpassungsmodus anzeigt.

Die Standard Implementierung überprüft den Anpassungsmodus ( [cmfctoolbar:: iscustomizemode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)). wenn der Wert auf true festgelegt ist, werden alle Kontextmenü Elemente außer **Delete**deaktiviert. Anschließend werden die Eingabeparameter einfach an weiter `CMFCToolBar::EnableContextMenuItems`geleitet.

> [!NOTE]
> Das *Kontextmenü* ist ein Synonym für das Kontextmenü.

##  <a name="enablepagescrollmode"></a>Cmfcoutlookbarpane:: enablepagescrollmode

Gibt an, ob die Bild Lauf Pfeile im Bereich der Outlook-Leiste die Liste der Schaltflächen nach Seite oder Schaltfläche durch Schaltfläche nach oben verschieben.

```
void EnablePageScrollMode(BOOL bPageScroll=TRUE);
```

### <a name="parameters"></a>Parameter

*bPageScroll*<br/>
in Wenn der Wert true ist, wird der Seiten Scrollmodus aktiviert. Wenn der Wert false ist, deaktivieren Sie den Seiten Scrollmodus.

##  <a name="getregularcolor"></a>Cmfcoutlookbarpane:: getregularcolor

Gibt die reguläre (d. h. nicht ausgewählte) Textfarbe des Outlook-leisten Bereichs zurück.

```
DECLARE_MESSAGE_MAPCOLORREF GetRegularColor() const;
```

### <a name="return-value"></a>Rückgabewert

Die aktuelle Textfarbe als RGB-Farbwert.

### <a name="remarks"></a>Hinweise

Verwenden Sie [cmfcoutlookbarpane:: SetTextColor](#settextcolor) , um die aktuelle Textfarbe (regulär und ausgewählt) der Outlook-Leiste festzulegen. Sie können die Standard Textfarbe abrufen, indem Sie die [GetSysColor](/windows/win32/api/winuser/nf-winuser-getsyscolor) -Funktion mit dem COLOR_WINDOW-Index aufrufen.

##  <a name="isbackgroundtexture"></a>Cmfcoutlookbarpane:: isbackgroundtexture

Bestimmt, ob für den Bereich der Outlook-Leiste ein Hintergrundbild geladen wurde.

```
BOOL IsBackgroundTexture() const;
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn das Hintergrundbild angezeigt werden soll. andernfalls false.

### <a name="remarks"></a>Hinweise

Sie können ein Hintergrundbild hinzufügen, indem Sie die [cmfcoutlookbarpane:: setbackimage](#setbackimage) -Funktion aufrufen.

Wenn kein Hintergrundbild vorhanden ist, wird der Hintergrund mit einer Farbe gezeichnet, die mit [cmfcoutlookbarpane:: setBackColor](#setbackcolor)angegeben wird.

##  <a name="isdrawshadedhighlight"></a>Cmfcoutlookbarpane:: isdrawshadedhighlight

Bestimmt, ob der Schaltflächen Rahmen schattiert wird, wenn eine Schaltfläche markiert wird und ein Hintergrundbild angezeigt wird.

```
BOOL IsDrawShadedHighlight() const;
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die Rahmen der Schaltfläche schattiert werden. andernfalls false.

##  <a name="removeallbuttons"></a>Cmfcoutlookbarpane:: removeallbuttons

Entfernt alle Schaltflächen aus dem Bereich der Outlook-Leiste.

```
virtual void RemoveAllButtons();
```

##  <a name="removebutton"></a>Cmfcoutlookbarpane:: RemoveButton

Entfernt die Schaltfläche mit einer angegebenen Befehls-ID.

```
BOOL RemoveButton(UINT iIdCommand);
```

### <a name="parameters"></a>Parameter

*iIdCommand*<br/>
in Gibt die Befehls-ID einer Schaltfläche an, die entfernt werden soll.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die Schaltfläche erfolgreich entfernt wurde. FALSE, wenn die angegebene Befehls-ID ungültig ist.

##  <a name="setbackcolor"></a>Cmfcoutlookbarpane:: setBackColor

Legt die Hintergrundfarbe der Outlook-Leiste fest.

```
void SetBackColor(COLORREF color);
```

### <a name="parameters"></a>Parameter

*Farbe*<br/>
in Gibt die neue Hintergrundfarbe an.

### <a name="remarks"></a>Hinweise

Mit dieser Funktion wird die aktuelle Hintergrundfarbe für die Outlook-Leiste festgelegt. Die Hintergrundfarbe wird nur verwendet, wenn kein Hintergrundbild vorhanden ist.

##  <a name="setbackimage"></a>Cmfcoutlookbarpane:: setbackimage

Legt das Hintergrundbild fest.

```
void SetBackImage(UINT uiImageID);
```

### <a name="parameters"></a>Parameter

*uiImageID*<br/>
in Gibt die Image-Ressourcen-ID an.

### <a name="remarks"></a>Hinweise

Ruft diese Methode auf, um das Hintergrundbild der Outlook-Leiste festzulegen. Die Liste der Hintergrundbilder wird vom eingebetteten [cmfctoolbarimages-Klassen](../../mfc/reference/cmfctoolbarimages-class.md) Objekt verwaltet.

##  <a name="setdefaultstate"></a>Cmfcoutlookbarpane:: setdefaultstate

Setzt den Bereich der Outlook-Leiste auf den ursprünglichen Satz von Schaltflächen zurück.

```
void SetDefaultState();
```

### <a name="remarks"></a>Hinweise

Diese Methode stellt die Outlook-Balken Schaltflächen für den ursprünglichen Satz wieder her. Diese Methode ähnelt `CMFCOutlookBarPane::RestoreOriginalstate`, mit der Ausnahme, dass Sie keinen Neuzeichnen des Bereichs der Outlook-Leiste auslöst.

##  <a name="setextraspace"></a>Cmfcoutlookbarpane:: abtextraspace

Legt die Anzahl der in den Schaltflächen im Bereich der Outlook-Leiste verwendeten Auffüll Zeichen fest.

```
void SetExtraSpace()
```

##  <a name="settextcolor"></a>Cmfcoutlookbarpane:: SetTextColor

Legt die Farben für regulären und markierten Text im Bereich der Outlook-Leiste fest.

```
void SetTextColor(
    COLORREF clrRegText,
    COLORREF clrSelText=0);
```

### <a name="parameters"></a>Parameter

*clrRegText*<br/>
in Gibt die neue Farbe für nicht ausgewählten Text an.

*clrSelText*<br/>
in Gibt die neue Farbe für den ausgewählten Text an.

##  <a name="settransparentcolor"></a>Cmfcoutlookbarpane:: settransparentcolor

Legt die transparente Farbe für den Bereich der Outlook-Leiste fest.

```
void SetTransparentColor(COLORREF color);
```

### <a name="parameters"></a>Parameter

*Farbe*<br/>
Gibt die neue transparente Farbe an.

### <a name="remarks"></a>Hinweise

Die transparente Farbe ist erforderlich, um transparente Bilder anzuzeigen. Alle Vorkommen dieser Farbe in einem Bild werden stattdessen mit der Hintergrundfarbe gezeichnet.  Es gibt keine Mischung aus Hintergrund-und Vordergrund Bildern.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar-Klasse](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCOutlookBar-Klasse](../../mfc/reference/cmfcoutlookbar-class.md)<br/>
[CMFCOutlookBarTabCtrl-Klasse](../../mfc/reference/cmfcoutlookbartabctrl-class.md)
