---
title: CMFCMenuBar-Klasse
ms.date: 10/18/2018
f1_keywords:
- CMFCMenuBar
- AFXMENUBAR/CMFCMenuBar
- AFXMENUBAR/CMFCMenuBar::AdjustLocations
- AFXMENUBAR/CMFCMenuBar::AllowChangeTextLabels
- AFXMENUBAR/CMFCMenuBar::AllowShowOnPaneMenu
- AFXMENUBAR/CMFCMenuBar::CalcFixedLayout
- AFXMENUBAR/CMFCMenuBar::CalcLayout
- AFXMENUBAR/CMFCMenuBar::CalcMaxButtonHeight
- AFXMENUBAR/CMFCMenuBar::CanBeClosed
- AFXMENUBAR/CMFCMenuBar::CanBeRestored
- AFXMENUBAR/CMFCMenuBar::Create
- AFXMENUBAR/CMFCMenuBar::CreateEx
- AFXMENUBAR/CMFCMenuBar::CreateFromMenu
- AFXMENUBAR/CMFCMenuBar::EnableHelpCombobox
- AFXMENUBAR/CMFCMenuBar::EnableMenuShadows
- AFXMENUBAR/CMFCMenuBar::GetAvailableExpandSize
- AFXMENUBAR/CMFCMenuBar::GetColumnWidth
- AFXMENUBAR/CMFCMenuBar::GetDefaultMenu
- AFXMENUBAR/CMFCMenuBar::GetDefaultMenuResId
- AFXMENUBAR/CMFCMenuBar::GetFloatPopupDirection
- AFXMENUBAR/CMFCMenuBar::GetForceDownArrows
- AFXMENUBAR/CMFCMenuBar::GetHelpCombobox
- AFXMENUBAR/CMFCMenuBar::GetHMenu
- AFXMENUBAR/CMFCMenuBar::GetMenuFont
- AFXMENUBAR/CMFCMenuBar::GetMenuItem
- AFXMENUBAR/CMFCMenuBar::GetRowHeight
- AFXMENUBAR/CMFCMenuBar::GetSystemButton
- AFXMENUBAR/CMFCMenuBar::GetSystemButtonsCount
- AFXMENUBAR/CMFCMenuBar::GetSystemMenu
- AFXMENUBAR/CMFCMenuBar::HighlightDisabledItems
- AFXMENUBAR/CMFCMenuBar::IsButtonExtraSizeAvailable
- AFXMENUBAR/CMFCMenuBar::IsHighlightDisabledItems
- AFXMENUBAR/CMFCMenuBar::IsMenuShadows
- AFXMENUBAR/CMFCMenuBar::IsRecentlyUsedMenus
- AFXMENUBAR/CMFCMenuBar::IsShowAllCommands
- AFXMENUBAR/CMFCMenuBar::IsShowAllCommandsDelay
- AFXMENUBAR/CMFCMenuBar::LoadState
- AFXMENUBAR/CMFCMenuBar::OnChangeHot
- AFXMENUBAR/CMFCMenuBar::OnDefaultMenuLoaded
- AFXMENUBAR/CMFCMenuBar::OnSendCommand
- AFXMENUBAR/CMFCMenuBar::OnSetDefaultButtonText
- AFXMENUBAR/CMFCMenuBar::OnToolHitTest
- AFXMENUBAR/CMFCMenuBar::PreTranslateMessage
- AFXMENUBAR/CMFCMenuBar::RestoreOriginalstate
- AFXMENUBAR/CMFCMenuBar::SaveState
- AFXMENUBAR/CMFCMenuBar::SetDefaultMenuResId
- AFXMENUBAR/CMFCMenuBar::SetForceDownArrows
- AFXMENUBAR/CMFCMenuBar::SetMaximizeMode
- AFXMENUBAR/CMFCMenuBar::SetMenuButtonRTC
- AFXMENUBAR/CMFCMenuBar::SetMenuFont
- AFXMENUBAR/CMFCMenuBar::SetRecentlyUsedMenus
- AFXMENUBAR/CMFCMenuBar::SetShowAllCommands
helpviewer_keywords:
- CMFCMenuBar [MFC], AdjustLocations
- CMFCMenuBar [MFC], AllowChangeTextLabels
- CMFCMenuBar [MFC], AllowShowOnPaneMenu
- CMFCMenuBar [MFC], CalcFixedLayout
- CMFCMenuBar [MFC], CalcLayout
- CMFCMenuBar [MFC], CalcMaxButtonHeight
- CMFCMenuBar [MFC], CanBeClosed
- CMFCMenuBar [MFC], CanBeRestored
- CMFCMenuBar [MFC], Create
- CMFCMenuBar [MFC], CreateEx
- CMFCMenuBar [MFC], CreateFromMenu
- CMFCMenuBar [MFC], EnableHelpCombobox
- CMFCMenuBar [MFC], EnableMenuShadows
- CMFCMenuBar [MFC], GetAvailableExpandSize
- CMFCMenuBar [MFC], GetColumnWidth
- CMFCMenuBar [MFC], GetDefaultMenu
- CMFCMenuBar [MFC], GetDefaultMenuResId
- CMFCMenuBar [MFC], GetFloatPopupDirection
- CMFCMenuBar [MFC], GetForceDownArrows
- CMFCMenuBar [MFC], GetHelpCombobox
- CMFCMenuBar [MFC], GetHMenu
- CMFCMenuBar [MFC], GetMenuFont
- CMFCMenuBar [MFC], GetMenuItem
- CMFCMenuBar [MFC], GetRowHeight
- CMFCMenuBar [MFC], GetSystemButton
- CMFCMenuBar [MFC], GetSystemButtonsCount
- CMFCMenuBar [MFC], GetSystemMenu
- CMFCMenuBar [MFC], HighlightDisabledItems
- CMFCMenuBar [MFC], IsButtonExtraSizeAvailable
- CMFCMenuBar [MFC], IsHighlightDisabledItems
- CMFCMenuBar [MFC], IsMenuShadows
- CMFCMenuBar [MFC], IsRecentlyUsedMenus
- CMFCMenuBar [MFC], IsShowAllCommands
- CMFCMenuBar [MFC], IsShowAllCommandsDelay
- CMFCMenuBar [MFC], LoadState
- CMFCMenuBar [MFC], OnChangeHot
- CMFCMenuBar [MFC], OnDefaultMenuLoaded
- CMFCMenuBar [MFC], OnSendCommand
- CMFCMenuBar [MFC], OnSetDefaultButtonText
- CMFCMenuBar [MFC], OnToolHitTest
- CMFCMenuBar [MFC], PreTranslateMessage
- CMFCMenuBar [MFC], RestoreOriginalstate
- CMFCMenuBar [MFC], SaveState
- CMFCMenuBar [MFC], SetDefaultMenuResId
- CMFCMenuBar [MFC], SetForceDownArrows
- CMFCMenuBar [MFC], SetMaximizeMode
- CMFCMenuBar [MFC], SetMenuButtonRTC
- CMFCMenuBar [MFC], SetMenuFont
- CMFCMenuBar [MFC], SetRecentlyUsedMenus
- CMFCMenuBar [MFC], SetShowAllCommands
ms.assetid: 8a3ce4c7-b012-4dc0-b4f8-53c10b4b86b8
ms.openlocfilehash: 87844e843057bb295c904b5f1b3d7dd03fa4d797
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "58775893"
---
# <a name="cmfcmenubar-class"></a>CMFCMenuBar-Klasse

Eine Menüleiste, die Andocken implementiert.
Weitere Informationen finden Sie im Quellcode der **VC\\Atlmfc\\Src\\Mfc** Ordner von Visual Studio-Installation.

## <a name="syntax"></a>Syntax

```
class CMFCMenuBar : public CMFCToolbar
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCMenuBar::AdjustLocations](#adjustlocations)|(Überschreibt `CMFCToolBar::AdjustLocations`.)|
|[CMFCMenuBar::AllowChangeTextLabels](#allowchangetextlabels)|Gibt an, ob Beschriftungen unter Bildern, auf die Symbolleisten-Schaltflächen angezeigt werden können. (Überschreibt [CMFCToolBar::AllowChangeTextLabels](../../mfc/reference/cmfctoolbar-class.md#allowchangetextlabels).)|
|[CMFCMenuBar::AllowShowOnPaneMenu](#allowshowonpanemenu)|(Überschreibt `CPane::AllowShowOnPaneMenu`.)|
|[CMFCMenuBar::CalcFixedLayout](#calcfixedlayout)|Berechnet die horizontale Größe der Symbolleiste. (Überschreibt [CMFCToolBar::CalcFixedLayout](../../mfc/reference/cmfctoolbar-class.md#calcfixedlayout).)|
|[CMFCMenuBar::CalcLayout](#calclayout)|(Überschreibt `CMFCToolBar::CalcLayout`.)|
|[CMFCMenuBar::CalcMaxButtonHeight](#calcmaxbuttonheight)|Berechnet die maximale Höhe der Schaltflächen auf der Symbolleiste an. (Überschreibt [CMFCToolBar::CalcMaxButtonHeight](../../mfc/reference/cmfctoolbar-class.md#calcmaxbuttonheight).)|
|[CMFCMenuBar::CanBeClosed](#canbeclosed)|Gibt an, ob ein Benutzer auf die Symbolleiste schließen kann. (Überschreibt [CMFCToolBar::CanBeClosed](../../mfc/reference/cmfctoolbar-class.md#canbeclosed).)|
|[CMFCMenuBar::CanBeRestored](#canberestored)|Bestimmt, ob das System nach der Anpassung eine Symbolleiste in seinen ursprünglichen Zustand wiederherstellen können. (Überschreibt [CMFCToolBar::CanBeRestored](../../mfc/reference/cmfctoolbar-class.md#canberestored).)|
|[CMFCMenuBar::Create](#create)|Erstellt ein Steuerelement, und fügt sie an einer `CMFCMenuBar` Objekt.|
|[CMFCMenuBar::CreateEx](#createex)|Erstellt eine `CMFCMenuBar` Objekt mit zusätzlichen Optionen.|
|[CMFCMenuBar::CreateFromMenu](#createfrommenu)|Initialisiert eine `CMFCMenuBar` Objekt. Akzeptiert einen HMENU-Parameter, die als Vorlage für ein gefülltes fungiert `CMFCMenuBar`.|
|[CMFCMenuBar::EnableHelpCombobox](#enablehelpcombobox)|Ermöglicht einem **Hilfe** Kombinationsfeld, das auf der rechten Seite der Menüleiste befindet.|
|[CMFCMenuBar::EnableMenuShadows](#enablemenushadows)|Gibt an, ob Shadows bei Popupmenüs angezeigt.|
|[CMFCMenuBar::GetAvailableExpandSize](#getavailableexpandsize)|(Überschreibt [CPane::GetAvailableExpandSize](../../mfc/reference/cpane-class.md#getavailableexpandsize).)|
|[CMFCMenuBar::GetColumnWidth](#getcolumnwidth)|Gibt die Breite der Symbolleisten-Schaltflächen. (Überschreibt [CMFCToolBar::GetColumnWidth](../../mfc/reference/cmfctoolbar-class.md#getcolumnwidth).)|
|[CMFCMenuBar::GetDefaultMenu](#getdefaultmenu)|Gibt ein Handle für das ursprüngliche Menü in der Ressourcendatei an.|
|[CMFCMenuBar::GetDefaultMenuResId](#getdefaultmenuresid)|Gibt den Ressourcenbezeichner für das ursprüngliche Menü in der Ressourcendatei zurück.|
|[CMFCMenuBar::GetFloatPopupDirection](#getfloatpopupdirection)||
|[CMFCMenuBar::GetForceDownArrows](#getforcedownarrows)||
|[CMFCMenuBar::GetHelpCombobox](#gethelpcombobox)|Gibt einen Zeiger auf die **Hilfe** im Kombinationsfeld.|
|[CMFCMenuBar::GetHMenu](#gethmenu)|Gibt das Handle zurück, um das Menü, das angefügt ist die `CMFCMenuBar` Objekt.|
|[CMFCMenuBar::GetMenuFont](#getmenufont)|Gibt die aktuelle globale Schriftart für den Menu-Objekte zurück.|
|[CMFCMenuBar::GetMenuItem](#getmenuitem)|Gibt die Symbolleisten-Schaltfläche zugeordneten Index des angegebenen Elements zurück.|
|[CMFCMenuBar::GetRowHeight](#getrowheight)|Gibt die Höhe von Symbolleisten-Schaltflächen. (Überschreibt [CMFCToolBar::GetRowHeight](../../mfc/reference/cmfctoolbar-class.md#getrowheight).)|
|[CMFCMenuBar::GetSystemButton](#getsystembutton)||
|[CMFCMenuBar::GetSystemButtonsCount](#getsystembuttonscount)||
|[CMFCMenuBar::GetSystemMenu](#getsystemmenu)||
|[CMFCMenuBar::HighlightDisabledItems](#highlightdisableditems)|Gibt an, ob deaktivierte Menüelemente hervorgehoben werden.|
|[CMFCMenuBar::IsButtonExtraSizeAvailable](#isbuttonextrasizeavailable)|Bestimmt, ob die Symbolleiste Schaltflächen angezeigt werden kann, die Rahmen erweitert haben. (Überschreibt [CMFCToolBar::IsButtonExtraSizeAvailable](../../mfc/reference/cmfctoolbar-class.md#isbuttonextrasizeavailable).)|
|[CMFCMenuBar::IsHighlightDisabledItems](#ishighlightdisableditems)|Gibt an, ob deaktivierte Elemente hervorgehoben werden.|
|[CMFCMenuBar::IsMenuShadows](#ismenushadows)|Gibt an, ob bei Popupmenüs Schatten gezeichnet werden.|
|[CMFCMenuBar::IsRecentlyUsedMenus](#isrecentlyusedmenus)|Gibt an, ob Befehle im zuletzt verwendeten Menü auf der Menüleiste angezeigt werden.|
|[CMFCMenuBar::IsShowAllCommands](#isshowallcommands)|Gibt an, ob Popupmenüs alle Befehle anzeigen.|
|[CMFCMenuBar::IsShowAllCommandsDelay](#isshowallcommandsdelay)|Gibt an, ob die Menüs angezeigt werden sollen alle Befehle, die nach einer kurzen Verzögerung.|
|[CMFCMenuBar::LoadState](#loadstate)|Lädt den Zustand der der `CMFCMenuBar` Objekt aus der Registrierung.|
|[CMFCMenuBar::OnChangeHot](#onchangehot)|Vom Framework aufgerufen, wenn ein Benutzer auf der Symbolleiste eine Schaltfläche auswählt. (Überschreibt [CMFCToolBar::OnChangeHot](../../mfc/reference/cmfctoolbar-class.md#onchangehot).)|
|[CMFCMenuBar::OnDefaultMenuLoaded](#ondefaultmenuloaded)|Vom Framework aufgerufen, wenn ein Rahmenfenster im Standardmenü aus der Ressourcendatei geladen wird.|
|[CMFCMenuBar::OnSendCommand](#onsendcommand)|(Überschreibt `CMFCToolBar::OnSendCommand`.)|
|[CMFCMenuBar::OnSetDefaultButtonText](#onsetdefaultbuttontext)|Vom Framework aufgerufen, wenn ein Menü im Anpassungsmodus und der Benutzer ändert den Text eines Menüelements.|
|[CMFCMenuBar::OnToolHitTest](#ontoolhittest)|(Überschreibt `CMFCToolBar::OnToolHitTest`.)|
|[CMFCMenuBar::PreTranslateMessage](#pretranslatemessage)|(Überschreibt `CMFCToolBar::PreTranslateMessage`.)|
|[CMFCMenuBar::RestoreOriginalstate](#restoreoriginalstate)|Vom Framework aufgerufen, wenn ein Menü im Anpassungsmodus und der Benutzer wählt **zurücksetzen** für eine Menüleiste.|
|[CMFCMenuBar::SaveState](#savestate)|Speichert den Zustand der `CMFCMenuBar` Objekt in der Registrierung.|
|[CMFCMenuBar::SetDefaultMenuResId](#setdefaultmenuresid)|Legt den ursprüngliche Menü in der Ressourcendatei fest.|
|[CMFCMenuBar::SetForceDownArrows](#setforcedownarrows)||
|[CMFCMenuBar::SetMaximizeMode](#setmaximizemode)|Vom Framework aufgerufen, wenn ein untergeordneten MDI-Fensters der Anzeigemodus geändert wird. Wenn das untergeordnete MDI-Fenster neu maximiert ist oder wird nicht mehr maximiert, aktualisiert diese Methode die Menüleiste aus.|
|[CMFCMenuBar::SetMenuButtonRTC](#setmenubuttonrtc)|Legt fest, die Laufzeit-Klasseninformationen an, die generiert wird, wenn der Benutzer dynamisch Menüschaltflächen erstellt.|
|[CMFCMenuBar::SetMenuFont](#setmenufont)|Legt die Schriftart für alle Menüs in der Anwendung fest.|
|[CMFCMenuBar::SetRecentlyUsedMenus](#setrecentlyusedmenus)|Gibt an, ob eine Menüleiste Befehle im zuletzt verwendeten Menü angezeigt.|
|[CMFCMenuBar::SetShowAllCommands](#setshowallcommands)|Gibt an, ob die Menüleiste alle Befehle angezeigt wird.|

## <a name="remarks"></a>Hinweise

Die `CMFCMenuBar` -Klasse ist eine Menüleiste, die Andocken Funktionalität implementiert. Es ähnelt eine Symbolleiste, obwohl es kann nicht geschlossen werden: Es wird immer angezeigt.

`CMFCMenuBar` unterstützt die Option zum Anzeigen von zuletzt verwendeten Menüobjekte. Wenn diese Option aktiviert ist, die `CMFCMenuBar` zeigt nur eine Teilmenge der verfügbaren Befehle auf den ersten. Danach werden die zuletzt verwendeten Befehle zusammen mit die ursprüngliche Teilmenge von Befehlen angezeigt. Darüber hinaus kann der Benutzer das Menü, um alle verfügbaren Befehle anzeigen erweitern. Daher ist jeder verfügbaren Befehl konfiguriert, um ständig anzuzeigen oder um anzuzeigen, wenn sie vor kurzem ausgewählt wurde.

Verwenden einer `CMFCMenuBar` Objekt, in das Hauptfenster rahmenobjekt einbetten. Bei der Verarbeitung der `WM_CREATE` message, rufen Sie `CMFCMenuBar::Create` oder `CMFCMenuBar::CreateEx`. Unabhängig von der Funktion zu erstellen, wenn Sie verwenden, übergeben eines Zeigers an das Hauptrahmenfenster. Aktivieren Sie dann durch Aufrufen von Andocken [cframewndex:: EnableDocking](../../mfc/reference/cframewndex-class.md#enabledocking). Dieses Menü durch Aufrufen von Andocken [CFrameWndEx::DockPane](../../mfc/reference/cframewndex-class.md#dockpane).

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Verwendung verschiedener Methoden in der `CMFCMenuBar` -Klasse. Das Beispiel veranschaulicht das Festlegen des Formats des Bereichs, aktivieren die Schaltfläche "anpassen", aktivieren ein Feld für die Hilfe, Schatten bei Popupmenüs zu aktivieren, und Aktualisieren der Menüleiste. Dieser Codeausschnitt ist Teil der [IE Demobeispiel](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_IEDemo#1](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_1.h)]
[!code-cpp[NVC_MFC_IEDemo#3](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)

[CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

`CMFCMenuBar`

## <a name="requirements"></a>Anforderungen

**Header:** afxmenubar.h

##  <a name="adjustlocations"></a>  CMFCMenuBar::AdjustLocations

Passt die Positionen der Menüelemente in der Menüleiste.

```
virtual void AdjustLocations();
```

### <a name="remarks"></a>Hinweise

##  <a name="allowchangetextlabels"></a>  CMFCMenuBar::AllowChangeTextLabels

Bestimmt, ob Beschriftungen unter Bildern in der Menüleiste zulässig sind.

```
virtual BOOL AllowChangeTextLabels() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn der Benutzer auswählen kann, um textbezeichnungen unter Bildern anzuzeigen.

### <a name="remarks"></a>Hinweise

##  <a name="allowshowonpanemenu"></a>  CMFCMenuBar::AllowShowOnPaneMenu

```
virtual BOOL AllowShowOnPaneMenu() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="calcfixedlayout"></a>  CMFCMenuBar::CalcFixedLayout

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>Parameter

[in] *bStretch*<br/>

[in] *bHorz*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="calclayout"></a>  CMFCMenuBar::CalcLayout

```
virtual CSize CalcLayout(
    DWORD dwMode,
    int nLength = -1);
```

### <a name="parameters"></a>Parameter

[in] *DwMode*<br/>

[in] *nLength*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="calcmaxbuttonheight"></a>  CMFCMenuBar::CalcMaxButtonHeight

```
virtual int CalcMaxButtonHeight();
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="canbeclosed"></a>  CMFCMenuBar::CanBeClosed

```
virtual BOOL CanBeClosed() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="canberestored"></a>  CMFCMenuBar::CanBeRestored

```
virtual BOOL CanBeRestored() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="create"></a>  CMFCMenuBar::Create

Erstellt ein Steuerelement, und fügt sie an einer [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) Objekt.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = AFX_DEFAULT_TOOLBAR_STYLE,
    UINT nID = AFX_IDW_MENUBAR);
```

### <a name="parameters"></a>Parameter

*pParentWnd*<br/>
[in] Zeiger auf das übergeordnete Fenster für die neue `CMFCMenuBar` Objekt.

*dwStyle*<br/>
[in] Das Format der die neue Menüleiste.

*nID*<br/>
[in] Die ID für das untergeordnete Fenster der Menüleiste.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn erfolgreich, andernfalls FALSE.

### <a name="remarks"></a>Hinweise

Wenn Sie erstellt haben, eine `CMFCMenuBar` Objekt, rufen Sie `Create`. Diese Methode erstellt die `CMFCMenuBar` steuern und fügt es der `CMFCMenuBar` Objekt.

Weitere Informationen zu den Toolbar-Stile, finden Sie unter [CBasePane::SetPaneStyle](../../mfc/reference/cbasepane-class.md#setpanestyle).

##  <a name="createex"></a>  CMFCMenuBar::CreateEx

Erstellt eine [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) Objekt mit dem angegebenen erweiterten Stile.

```
virtual BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = TBSTYLE_FLAT,
    DWORD dwStyle = AFX_DEFAULT_TOOLBAR_STYLE,
    CRect rcBorders = CRect(1,
    1,
    1,
    1),
    UINT nID =AFX_IDW_MENUBAR);
```

### <a name="parameters"></a>Parameter

*pParentWnd*<br/>
[in] Zeiger auf das übergeordnete Fenster des neuen `CMFCMenuBar` Objekt.

*dwCtrlStyle*<br/>
[in] Weitere Formate für die neue Menüleiste.

*dwStyle*<br/>
[in] Der wichtigste Stil, der die neue Menüleiste werden soll.

*rcBorders*<br/>
[in] Ein `CRect` Parameter, der angibt, der Größe der für die Rahmen der `CMFCMenuBar` Objekt.

*nID*<br/>
[in] Die ID für das untergeordnete Fenster der Menüleiste.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Methode erfolgreich ist; andernfalls 0.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Funktion statt des [CMFCMenuBar::Create](#create) Wenn Sie Formatvorlagen zusätzlich zu den Stil der Symbolleiste angeben möchten. Einige häufig verwendete Weitere Formate sind TBSTYLE_TRANSPARENT und CBRS_TOP.

Der zusätzliche Formate finden Sie unter [Toolbar-Steuerelement und Button-Stile](/windows/desktop/Controls/toolbar-control-and-button-styles), [Steuerelementtypen für die allgemeine](/windows/desktop/Controls/common-control-styles), und [allgemeine Fensterstile](/windows/desktop/winmsg/window-styles).

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie die `CreateEx` Methode der `CMFCMenuBar` Klasse. Dieser Codeausschnitt ist Teil der [IE Demobeispiel](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_IEDemo#1](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_1.h)]
[!code-cpp[NVC_MFC_IEDemo#2](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_3.cpp)]

##  <a name="createfrommenu"></a>  CMFCMenuBar::CreateFromMenu

Initialisiert eine [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) Objekt. Diese Methode Modelle die `CMFCMenuBar` Objekt nach einem HMENU-Parameter.

```
virtual void CreateFromMenu(
    HMENU hMenu,
    BOOL bDefaultMenu = FALSE,
    BOOL bForceUpdate = FALSE);
```

### <a name="parameters"></a>Parameter

*hMenu*<br/>
[in] Ein Handle für eine Menüressource. `CreateFromMenu` verwendet diese Ressource als Vorlage für die `CMFCMenuBar`.

*bDefaultMenu*<br/>
[in] Ein boolescher Wert, der angibt, ob das neue Menü das Standardmenü befindet.

*bForceUpdate*<br/>
[in] Ein boolescher Wert, der angibt, ob diese Methode erzwingt, ein Update im Menü dass.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode, wenn Sie möchten, dass ein Menüsteuerelement, damit die gleichen Menüelemente als eine Menüressource. Sie rufen diese Methode aufzurufen, nachdem Sie entweder [CMFCMenuBar::Create](#create) oder [CMFCMenuBar::CreateEx](#createex).

##  <a name="enablehelpcombobox"></a>  CMFCMenuBar::EnableHelpCombobox

Ermöglicht einem **Hilfe** Kombinationsfeld, das auf der rechten Seite der Menüleiste befindet.

```
void EnableHelpCombobox(
    UINT uiID,
    LPCTSTR lpszPrompt = NULL,
    int nComboBoxWidth = 150);
```

### <a name="parameters"></a>Parameter

*uiID*<br/>
[in] Die Befehls-ID für die Schaltfläche in der die **Hilfe** im Kombinationsfeld.

*lpszPrompt*<br/>
[in] Eine Zeichenfolge, die den Text, den das Framework im Kombinationsfeld anzeigt enthält, wenn sie leer und nicht aktiv ist. Z. B. "Geben Sie hier den Text".

*nComboBoxWidth*<br/>
[in] Die Breite der Schaltfläche für das Kombinationsfeld in Pixel.

### <a name="remarks"></a>Hinweise

Die **Hilfe** Kombinationsfeld ähnelt der **Hilfe** Kombinationsfeld in der Menüleiste von Microsoft Word.

Wenn Sie beim Aufrufen dieser Methode *UiID* auf 0 festgelegt, diese Methode blendet Sie aus dem Kombinationsfeld. Andernfalls zeigt diese Methode im Kombinationsfeld automatisch auf der rechten Seite der Menüleiste. Nachdem Sie diese Methode aufrufen, rufen [CMFCMenuBar::GetHelpCombobox](#gethelpcombobox) auf einen Zeiger auf die eingefügten abrufen [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md) Objekt.

##  <a name="enablemenushadows"></a>  CMFCMenuBar::EnableMenuShadows

Ermöglicht die Shadows bei Popupmenüs.

```
static void EnableMenuShadows(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parameter

*bAktivieren*<br/>
[in] Ein boolescher Parameter, der angibt, ob Popupmenüs Schatten aktiviert werden soll.

### <a name="remarks"></a>Hinweise

Der Algorithmus, den diese Methode wird verwendet, ist komplex und kann die Leistung der Anwendung auf die langsameren Systemen verringern.

##  <a name="getavailableexpandsize"></a>  CMFCMenuBar::GetAvailableExpandSize

```
virtual int GetAvailableExpandSize() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="getcolumnwidth"></a>  CMFCMenuBar::GetColumnWidth

```
virtual int GetColumnWidth() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="getdefaultmenu"></a>  CMFCMenuBar::GetDefaultMenu

Ruft ein Handle für den ursprünglichen Menü ab. Das Framework lädt das Menü "ursprüngliche" aus der Ressourcendatei an.

```
HMENU GetDefaultMenu() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Handle für eine Menüressource.

### <a name="remarks"></a>Hinweise

Wenn Ihre Anwendung ein Menüs angepasst hat, können Sie diese Methode, um ein Handle für den ursprünglichen Menü abzurufen.

##  <a name="getdefaultmenuresid"></a>  CMFCMenuBar::GetDefaultMenuResId

Ruft den Ressourcenbezeichner für das Standardmenü ab.

```
UINT GetDefaultMenuResId() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Bezeichner für den Menü-Ressource.

### <a name="remarks"></a>Hinweise

Das Framework, lädt das Standardmenü für die `CMFCMenuBar` Objekt aus der Ressourcendatei.

##  <a name="getfloatpopupdirection"></a>  CMFCMenuBar::GetFloatPopupDirection

```
int GetFloatPopupDirection(CMFCToolBarMenuButton* pButton);
```

### <a name="parameters"></a>Parameter

[in] *pButton*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="getforcedownarrows"></a>  CMFCMenuBar::GetForceDownArrows

```
BOOL GetForceDownArrows();
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="gethelpcombobox"></a>  CMFCMenuBar::GetHelpCombobox

Gibt einen Zeiger auf die **Hilfe** im Kombinationsfeld.

```
CMFCToolBarComboBoxButton* GetHelpCombobox();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die **Hilfe** im Kombinationsfeld. NULL, wenn die **Hilfe** Kombinationsfeld ausgeblendet oder nicht aktiviert ist.

### <a name="remarks"></a>Hinweise

Die **Hilfe** Kombinationsfeld befindet sich auf der rechten Seite der Menüleiste. Rufen Sie die Methode [CMFCMenuBar::EnableHelpCombobox](#enablehelpcombobox) dieses Kombinationsfelds zu aktivieren.

##  <a name="gethmenu"></a>  CMFCMenuBar::GetHMenu

Ruft das Handle für das Menü, das angefügt wird, um die [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) Objekt.

```
HMENU GetHMenu() const;
```

##  <a name="getmenufont"></a>  CMFCMenuBar::GetMenuFont

Ruft die aktuelle Menüschriftart ab.

```
static const CFont& GetMenuFont(BOOL bHorz = TRUE);
```

### <a name="parameters"></a>Parameter

*bHorz*<br/>
[in] Ein boolescher Parameter, der angibt, ob die horizontale oder vertikale Schriftart zurückgegeben. "True" gibt die horizontale Schriftart an.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine [CFont](../../mfc/reference/cfont-class.md) Parameter, der die aktuelle Schriftart der Menü-Leiste enthält.

### <a name="remarks"></a>Hinweise

Die zurückgegebene Schriftart ist ein globaler Parameter für die Anwendung. Zwei globale Schriftarten für alle bleiben `CMFCMenuBar` Objekte. Diese separaten Schriftarten werden für die horizontale und vertikale Menüleisten verwendet.

##  <a name="getmenuitem"></a>  CMFCMenuBar::GetMenuItem

Ruft eine [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) Objekt in einer Menüleiste basierend auf den Index des Elements.

```
CMFCToolBarButton* GetMenuItem(int iItem) const;
```

### <a name="parameters"></a>Parameter

*iItem*<br/>
[in] Der Index, der dem Menüelement, das zurückgegeben werden soll.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die `CMFCToolBarButton` -Objekt, das den angegebenen Index entspricht *iItem*. NULL, wenn der Indexwert ungültig ist.

##  <a name="getrowheight"></a>  CMFCMenuBar::GetRowHeight

```
virtual int GetRowHeight() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="getsystembutton"></a>  CMFCMenuBar::GetSystemButton

```
CMFCToolBarMenuButtonsButton* GetSystemButton(
    UINT uiBtn,
    BOOL bByCommand = TRUE) const;
```

### <a name="parameters"></a>Parameter

[in] *uiBtn*<br/>

[in] *bByCommand*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="getsystembuttonscount"></a>  CMFCMenuBar::GetSystemButtonsCount

```
int GetSystemButtonsCount() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="getsystemmenu"></a>  CMFCMenuBar::GetSystemMenu

```
CMFCToolBarSystemMenuButton* GetSystemMenu() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="highlightdisableditems"></a>  CMFCMenuBar::HighlightDisabledItems

Steuert, ob das Framework deaktivierte Menüelemente werden hervorgehoben.

```
static void HighlightDisabledItems(BOOL bHighlight = TRUE);
```

### <a name="parameters"></a>Parameter

*bHighlight*<br/>
[in] Ein boolescher Parameter, der angibt, ob das Framework nicht verfügbar Menüelemente werden hervorgehoben.

### <a name="remarks"></a>Hinweise

Standardmäßig ist das Framework nicht verfügbar Hervorheben von Menüelementen, wenn der Benutzer den Mauszeiger darauf positioniert.

##  <a name="isbuttonextrasizeavailable"></a>  CMFCMenuBar::IsButtonExtraSizeAvailable

```
virtual BOOL IsButtonExtraSizeAvailable() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="ishighlightdisableditems"></a>  CMFCMenuBar::IsHighlightDisabledItems

Gibt an, ob das Framework nicht verfügbar Menüelemente werden hervorgehoben.

```
static BOOL IsHighlightDisabledItems();
```

### <a name="return-value"></a>Rückgabewert

True, wenn, Menüelemente nicht verfügbar hervorgehoben werden. andernfalls "false".

### <a name="remarks"></a>Hinweise

Standardmäßig ist das Framework nicht verfügbar Hervorheben von Menüelementen, wenn der Benutzer den Mauszeiger darauf positioniert. Verwenden der [CMFCMenuBar::HighlightDisabledItems](#highlightdisableditems) Methode, um dieses Feature zu aktivieren.

##  <a name="ismenushadows"></a>  CMFCMenuBar::IsMenuShadows

Gibt an, ob das Framework Shadows für Popup-Menüs zeichnet.

```
static BOOL IsMenuShadows();
```

### <a name="return-value"></a>Rückgabewert

True, wenn das Framework Menü Zeichnen von Schatten. andernfalls "false".

### <a name="remarks"></a>Hinweise

Verwenden der [CMFCMenuBar::EnableMenuShadows](#enablemenushadows) zu aktivieren oder deaktivieren Sie diese Funktion.

##  <a name="isrecentlyusedmenus"></a>  CMFCMenuBar::IsRecentlyUsedMenus

Gibt an, ob Befehle im zuletzt verwendeten Menü auf der Menüleiste angezeigt werden.

```
static BOOL IsRecentlyUsedMenus();
```

### <a name="return-value"></a>Rückgabewert

Einen Wert ungleich null der `CMFCMenuBar` Objekt zeigt die zuletzt verwendeten Befehle im Menü, andernfalls 0.

### <a name="remarks"></a>Hinweise

Verwenden Sie die Funktion [CMFCMenuBar::SetRecentlyUsedMenus](#setrecentlyusedmenus) steuern, ob die Menüleiste vor kurzem zeigt Befehle im Menü verwendet.

##  <a name="isshowallcommands"></a>  CMFCMenuBar::IsShowAllCommands

Gibt an, ob die Menüs alle Befehle angezeigt werden sollen.

```
static BOOL IsShowAllCommands();
```

### <a name="return-value"></a>Rückgabewert

Einen Wert ungleich null der `CMFCMenuBar` zeigt alle Befehle, andernfalls 0.

### <a name="remarks"></a>Hinweise

Ein `CMFCMenuBar` Objekt kann so konfiguriert werden, dass alle Befehle anzeigen, oder zeigen nur eine Teilmenge der Befehle. Weitere Informationen zu diesem Feature finden Sie unter [CMFCMenuBar-Klasse](../../mfc/reference/cmfcmenubar-class.md).

`IsShowAllCommands` Informieren Sie, wie dieses Feature konfiguriert ist, für die `CMFCMenuBar` Objekt. Um zu steuern, welche Befehle im Menü angezeigt werden, verwenden Sie die Methoden [CMFCMenuBar::SetShowAllCommands](#setshowallcommands) und [CMFCMenuBar::SetRecentlyUsedMenus](#setrecentlyusedmenus).

##  <a name="isshowallcommandsdelay"></a>  CMFCMenuBar::IsShowAllCommandsDelay

Gibt an, ob die [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) Objekt zeigt alle Befehle, die nach einer kurzen Verzögerung.

```
static BOOL IsShowAllCommandsDelay();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn in die Menüleiste vollständige Menüs nach einer kurzen Verzögerung angezeigt; andernfalls 0.

### <a name="remarks"></a>Hinweise

Wenn Sie eine Menüleiste, um Anzeigeelemente, die zuletzt verwendeten konfigurieren, zeigt die Menüleiste das Menü "vollständige" auf zwei Arten:

- Zeigen Sie vollständige Menü an, nach einer programmierten Verzögerung aus, wenn der Benutzer den Cursor auf den Pfeil unten auf der Sie im Menü zeigt.

- Zeigen Sie vollständige Menü an, nachdem der Benutzer auf den Pfeil nach unten auf der Sie im Menü klickt.

In der Standardeinstellung alle `CMFCMenuBar` Objekte verwenden Sie die Option zur Anzeige des vollständigen Menüs nach einer kurzen Verzögerung. Diese Option kann nicht geändert werden programmgesteuert in die `CMFCMenuBar` Klasse. Jedoch ein Benutzer kann ändern das Verhalten beim Anpassen von Symbolleisten mithilfe der **anpassen** Dialogfeld...

##  <a name="loadstate"></a>  CMFCMenuBar::LoadState

Lädt den Zustand der Menüleiste aus der Windows-Registrierung.

```
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,
    int nIndex = -1,
    UINT uiID = (UINT)-1);
```

### <a name="parameters"></a>Parameter

*lpszProfileName*<br/>
[in] Eine Zeichenfolge, die den Pfad eines Windows-Registrierungsschlüssels enthält.

*nIndex*<br/>
[in] Die Steuerelement-ID für die Menüleiste.

*uiID*<br/>
[in] Ein reservierter Wert.

### <a name="return-value"></a>Rückgabewert

True, wenn die Methode erfolgreich war. andernfalls "false".

### <a name="remarks"></a>Hinweise

Verwenden der [CMFCMenuBar::SaveState](#savestate) Methode, um den Status der Menüleiste in der Registrierung speichern. Die gespeicherte Informationen enthält die Menüelemente der andockziel-Status und die Position der Menüleiste.

In den meisten Fällen wird Ihre Anwendung nicht aufrufen `LoadState`. Das Framework ruft diese Methode auf, wenn sie den Arbeitsbereich initialisiert.

##  <a name="onchangehot"></a>  CMFCMenuBar::OnChangeHot

```
virtual void OnChangeHot(int iHot);
```

### <a name="parameters"></a>Parameter

[in] *iHot*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="ondefaultmenuloaded"></a>  CMFCMenuBar::OnDefaultMenuLoaded

Das Framework ruft diese Methode wird beim Laden der Menüressource aus der Ressourcendatei.

```
virtual void OnDefaultMenuLoaded(HMENU hMenu);
```

### <a name="parameters"></a>Parameter

*hMenu*<br/>
[in] Das Handle für das Menü angefügt, um die `CMFCMenuBar` Objekt.

### <a name="remarks"></a>Hinweise

Bei der Standardimplementierung dieser Funktion wird keine Aktion ausgeführt. Überschreiben Sie diese Funktion, um benutzerdefinierten Code ausführen, nachdem das Framework eine Menüressource aus der Ressourcendatei geladen.

##  <a name="onsendcommand"></a>  CMFCMenuBar::OnSendCommand

```
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```

### <a name="parameters"></a>Parameter

[in] *pButton*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="onsetdefaultbuttontext"></a>  CMFCMenuBar::OnSetDefaultButtonText

Das Framework ruft diese Methode auf, wenn der Benutzer den Text eines Elements in der Menüleiste ändert.

```
virtual BOOL OnSetDefaultButtonText(CMFCToolBarButton* pButton);
```

### <a name="parameters"></a>Parameter

*pButton*<br/>
[in] Ein Zeiger auf die [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) -Objekt, das möchte, dass der Benutzer anpassen.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn das Framework wendet ändert die der Benutzer in der Menüleiste. andernfalls "false".

### <a name="remarks"></a>Hinweise

Die Standardimplementierung für diese Methode ändert den Text der Schaltfläche auf den Text, den der Benutzer bereitstellt.

##  <a name="ontoolhittest"></a>  CMFCMenuBar::OnToolHitTest

```
virtual INT_PTR OnToolHitTest(
    CPoint point,
    TOOLINFO* pTI) const;
```

### <a name="parameters"></a>Parameter

[in] *point*<br/>

[in] *pTI*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="pretranslatemessage"></a>  CMFCMenuBar::PreTranslateMessage

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>Parameter

[in] *pMsg*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="restoreoriginalstate"></a>  CMFCMenuBar::RestoreOriginalstate

Vom Framework aufgerufen, wenn der Benutzer auswählt **zurücksetzen** aus der **anpassen** Dialogfeld.

```
virtual BOOL RestoreOriginalstate();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Methode erfolgreich ist; andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Methode wird aufgerufen, wenn der Benutzer auswählt **zurücksetzen** aus das anpassungsmenü zu öffnen. Sie können diese Methode, um den Status der Menüleiste programmgesteuert zurückzusetzen, auch manuell aufrufen. Diese Methode lädt den ursprünglichen Zustand aus der Ressourcendatei an.

Diese Methode überschreiben, wenn es sich bei jeder Verarbeitung, wenn der Benutzer auswählt möchten die **zurücksetzen** Option.

##  <a name="savestate"></a>  CMFCMenuBar::SaveState

Speichert den Zustand der [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) Objekt in der Windows-Registrierung.

```
virtual BOOL SaveState (
    LPCTSTR lpszProfileName = NULL,
    int nIndex = -1,
    UINT uiID = (UINT)-1);
```

### <a name="parameters"></a>Parameter

*lpszProfileName*<br/>
[in] Eine Zeichenfolge, die den Pfad eines Windows-Registrierungsschlüssels enthält.

*nIndex*<br/>
[in] Die Steuerelement-ID für die Menüleiste.

*uiID*<br/>
[in] Ein reservierter Wert.

### <a name="return-value"></a>Rückgabewert

True, wenn erfolgreich; andernfalls "false";

### <a name="remarks"></a>Hinweise

Die Anwendung ruft normalerweise nicht `SaveState`. Das Framework ruft diese Methode auf, wenn der Arbeitsbereich serialisiert wird. Weitere Informationen finden Sie unter [CWinAppEx::SaveState](../../mfc/reference/cwinappex-class.md#savestate).

Die gespeicherte Informationen enthält die Menüelemente der andockziel-Status und die Position der Menüleiste.

##  <a name="setdefaultmenuresid"></a>  CMFCMenuBar::SetDefaultMenuResId

Legt die Standardmenü für eine [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) -Objekt auf Grundlage der Ressourcen-ID.

```
void SetDefaultMenuResId(UINT uiResId);
```

### <a name="parameters"></a>Parameter

*uiResId*<br/>
[in] Die Ressourcen-ID für die neue Standardmenü.

### <a name="remarks"></a>Hinweise

Die [CMFCMenuBar::RestoreOriginalstate](#restoreoriginalstate) Methode stellt den Standard-Menü aus der Ressourcendatei wieder her.

Verwenden der [CMFCMenuBar::GetDefaultMenuResId](#getdefaultmenuresid) Methode, um das Standardmenü abzurufen, ohne die Sicherung wiederherzustellen.

##  <a name="setforcedownarrows"></a>  CMFCMenuBar::SetForceDownArrows

```
void SetForceDownArrows(BOOL bValue);
```

### <a name="parameters"></a>Parameter

[in] *bValue*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="setmaximizemode"></a>  CMFCMenuBar::SetMaximizeMode

Das Framework ruft diese Methode auf, wenn eine MDI, dessen Anzeigemodus ändert und die Menüleiste aktualisiert werden muss.

```
void SetMaximizeMode(
    BOOL bMax,
    CWnd* pWnd = NULL,
    BOOL bRecalcLayout = TRUE);
```

### <a name="parameters"></a>Parameter

*bMax*<br/>
[in] Ein boolescher Wert, der den Modus angibt. Weitere Informationen finden Sie im Abschnitt Hinweise.

*pWnd*<br/>
[in] Ein Zeiger auf die untergeordneten MDI-Fensters, die geändert wird.

*bRecalcLayout*<br/>
[in] Ein boolescher Wert, der angibt, ob das Layout der Menüleiste sofort neu berechnet werden sollen.

### <a name="remarks"></a>Hinweise

Wenn eine untergeordnete MDI-Fenster maximiert ist, wird eine Menüleiste, die an das Hauptrahmenfenster für MDI-angefügt zeigt das Systemmenü und die **Minimieren**, **Maximieren** und **schließen** Schaltflächen. Wenn *bMax* ist "true" und *aufnehmen* ist nicht NULL ist, das untergeordnete MDI-Fenster wird maximiert und die Menüleiste muss die zusätzliche Steuerelemente enthalten. Andernfalls wird die Menüleiste auf ihren regulären Zustand zurückgegeben.

##  <a name="setmenubuttonrtc"></a>  CMFCMenuBar::SetMenuButtonRTC

Legt fest, die laufzeitklasseninformationen, die das Framework verwendet, wenn der Benutzer Menüschaltflächen erstellt.

```
void SetMenuButtonRTC(CRuntimeClass* pMenuButtonRTC);
```

### <a name="parameters"></a>Parameter

*pMenuButtonRTC*<br/>
[in] Die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Informationen für eine Klasse abgeleitet wird, aus der [CMFCMenuButton-Klasse](../../mfc/reference/cmfcmenubutton-class.md).

### <a name="remarks"></a>Hinweise

Wenn ein Benutzer neue Schaltflächen auf der Menüleiste hinzufügt, erstellt das Framework die Schaltflächen dynamisch an. Standardmäßig erstellt `CMFCMenuButton` Objekte. Überschreiben Sie diese Methode, um den Typ der Schaltfläche "-Objekte zu ändern, die das Framework erstellt.

##  <a name="setmenufont"></a>  CMFCMenuBar::SetMenuFont

Legt die Schriftart für alle Menüleisten in Ihrer Anwendung fest.

```
static BOOL SetMenuFont(
    LPLOGFONT lpLogFont,
    BOOL bHorz = TRUE);
```

### <a name="parameters"></a>Parameter

*lpLogFont*<br/>
[in] Ein Zeiger auf eine ["LogFont"](/windows/desktop/api/dimm/ns-dimm-__midl___midl_itf_dimm_0000_0000_0003) Struktur, die die Schriftart fest definiert.

*bHorz*<br/>
[in] TRUE, wenn Sie möchten die *LpLogFont* Parameter, um für die vertikale Schriftart "false" verwendet werden, wenn Sie für die horizontale Schriftart verwendet werden soll.

### <a name="return-value"></a>Rückgabewert

True, wenn die Methode erfolgreich war. andernfalls "false".

### <a name="remarks"></a>Hinweise

Zwei Schriftarten werden verwendet, für alle `CMFCMenuBar` Objekte. Diese separaten Schriftarten werden für die horizontale und vertikale Menüleisten verwendet.

Die schriftarteinstellungen sind globale Variablen und wirkt sich auf alle `CMFCMenuBar` Objekte.

##  <a name="setrecentlyusedmenus"></a>  CMFCMenuBar::SetRecentlyUsedMenus

Steuert, ob eine Menüleiste vor kurzem zeigt Befehle im Menü verwendet.

```
static void SetRecentlyUsedMenus (BOOL bOn = TRUE);
```

### <a name="parameters"></a>Parameter

*bOn*<br/>
[in] Ein boolescher Wert, der steuert, ob Befehle im zuletzt verwendeten Menü angezeigt werden.

##  <a name="setshowallcommands"></a>  CMFCMenuBar::SetShowAllCommands

Steuert, ob ein Menü alle verfügbaren Befehle anzeigt.

```
static void SetShowAllCommands(BOOL bShowAllCommands = TRUE);
```

### <a name="parameters"></a>Parameter

*bShowAllCommands*<br/>
[in] Ein boolescher Parameter, der angibt, ob das Popupmenü alle Menübefehle im angezeigt wird.

### <a name="remarks"></a>Hinweise

Wenn ein Menü die Menübefehle nicht angezeigt wird, blendet sie die Befehle, die selten verwendet werden. Weitere Informationen zum Anzeigen von Menübefehlen, finden Sie unter [CMFCMenuBar-Klasse](../../mfc/reference/cmfcmenubar-class.md).

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar-Klasse](../../mfc/reference/cmfctoolbar-class.md)
