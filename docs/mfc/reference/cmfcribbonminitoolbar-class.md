---
title: CMFCRibbonMiniToolBar-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonMiniToolBar
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::IsContextMenuMode
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::IsRibbonMiniToolBar
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::SetCommands
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::Show
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::ShowWithContextMenu
helpviewer_keywords:
- CMFCRibbonMiniToolBar [MFC], IsContextMenuMode
- CMFCRibbonMiniToolBar [MFC], IsRibbonMiniToolBar
- CMFCRibbonMiniToolBar [MFC], SetCommands
- CMFCRibbonMiniToolBar [MFC], Show
- CMFCRibbonMiniToolBar [MFC], ShowWithContextMenu
ms.assetid: 7017e963-aeaf-4fe9-b540-e15a7ed41e94
ms.openlocfilehash: 394182aa0f9c967524ed0db510d0b9cc0739118e
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "58777154"
---
# <a name="cmfcribbonminitoolbar-class"></a>CMFCRibbonMiniToolBar-Klasse

Implementiert eine kontextbezogene Popup-Symbolleiste.

## <a name="syntax"></a>Syntax

```
class CMFCRibbonMiniToolBar : public CMFCRibbonPanelMenu
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|`CMFCRibbonMiniToolBar::CMFCRibbonMiniToolBar`|Standardkonstruktor|
|`CMFCRibbonMiniToolBar::~CMFCRibbonMiniToolBar`|Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|`CMFCRibbonMiniToolBar::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|
|`CMFCRibbonMiniToolBar::GetThisClass`|Durch das Framework verwendet wird, einen Zeiger zum Abrufen der [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|
|[CMFCRibbonMiniToolBar::IsContextMenuMode](#iscontextmenumode)||
|[CMFCRibbonMiniToolBar::IsRibbonMiniToolBar](#isribbonminitoolbar)|(Überschreibt `CMFCPopupMenu::IsRibbonMiniToolBar`.)|
|[CMFCRibbonMiniToolBar::SetCommands](#setcommands)|Legt die Liste der auf der Symbolleiste anzuzeigenden Befehle fest.|
|[CMFCRibbonMiniToolBar::Show](#show)|Zeigt die Minisymbolleiste an den angegebenen Bildschirmkoordinaten an.|
|[CMFCRibbonMiniToolBar::ShowWithContextMenu](#showwithcontextmenu)|Zeigt die Minisymbolleiste zusammen mit einem Kontextmenü an.|

## <a name="remarks"></a>Hinweise

Die Minisymbolleiste wird meist angezeigt, nachdem ein Benutzer ein Objekt in einem Dokument ausgewählt hat. Nachdem der Benutzer einen Textblock in einem Textverarbeitungsprogramm auswählt, zeigt die Anwendung z. B. eine Minisymbolleiste mit Textformatierungsbefehlen an.

Die Minisymbolleiste wird transparent, wenn der Mauszeiger sich außerhalb des gültigen Bereichs der Minisymbolleiste befindet.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

[CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)

[CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)

`CMFCRibbonPanelMenu`

[CMFCRibbonMiniToolBar](../../mfc/reference/cmfcribbonminitoolbar-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxRibbonMiniToolBar.h

##  <a name="setcommands"></a>  CMFCRibbonMiniToolBar::SetCommands

Legt die Liste der auf der Symbolleiste anzuzeigenden Befehle fest.

```
void SetCommands(
    CMFCRibbonBar* pRibbonBar,
    const CList<UINT,UINT>& lstCommands);
```

### <a name="parameters"></a>Parameter

*pRibbonBar*<br/>
[in] Die menübandleiste, die die Minisymbolleiste für die anzuzeigenden Schaltflächen sucht.

*lstCommands*<br/>
[in] Die Liste der Befehle aus, um auf die Minisymbolleiste angezeigt werden. Alle menübandkategorien werden durchsucht, um die zugeordneten Schaltflächen zu suchen.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Funktion, Festlegen der Liste der Befehle in die Minisymbolleiste angezeigt werden.

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie die `SetCommands` Methode der `CMFCRibbonMiniToolBar` Klasse. Dieser Codeausschnitt ist Teil der [MS Office 2007-Demo-Beispiel](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_MSOffice2007Demo#9](../../mfc/reference/codesnippet/cpp/cmfcribbonminitoolbar-class_1.cpp)]

##  <a name="show"></a>  CMFCRibbonMiniToolBar::Show

Zeigt die Minisymbolleiste an den angegebenen Bildschirmkoordinaten an.

```
BOOL Show(
    int x,
    int y);
```

### <a name="parameters"></a>Parameter

*w*<br/>
[in] Gibt die horizontale Position der Minisymbolleiste in Bildschirmkoordinaten.

*y*<br/>
[in] Gibt die vertikale Position der Minisymbolleiste in Bildschirmkoordinaten.

### <a name="return-value"></a>Rückgabewert

True, wenn die Minisymbolleiste erfolgreich angezeigt wurde. andernfalls "false".

##  <a name="showwithcontextmenu"></a>  CMFCRibbonMiniToolBar::ShowWithContextMenu

Zeigt die Minisymbolleiste zusammen mit einem Kontextmenü an.

```
BOOL ShowWithContextMenu(
    int x,
    int y,
    UINT uiMenuResID,
    CWnd* pWndOwner);
```

### <a name="parameters"></a>Parameter

*w*<br/>
[in] Gibt die horizontale Position des Kontextmenüs in Bildschirmkoordinaten.

*y*<br/>
[in] Gibt die vertikale Position des Kontextmenüs in Bildschirmkoordinaten.

*uiMenuResID*<br/>
[in] Gibt an, die Ressourcen-ID des Kontextmenüs angezeigt.

*pWndOwner*<br/>
[in] Gibt das Fenster, das Nachrichten, aus dem Kontextmenü empfängt.

### <a name="return-value"></a>Rückgabewert

True, wenn das Kontextmenü erfolgreich angezeigt wurde. andernfalls "false".

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Funktion, um eine Minisymbolleiste anzuzeigen, die ein Kontextmenü angezeigt hat. Im Kontextmenü ist positionierte 15 Pixel unterhalb der Minisymbolleiste.

##  <a name="iscontextmenumode"></a>  CMFCRibbonMiniToolBar::IsContextMenuMode

Weitere Informationen finden Sie im Quellcode der **VC\\Atlmfc\\Src\\Mfc** Ordner von Visual Studio-Installation.

```
BOOL IsContextMenuMode() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="isribbonminitoolbar"></a>  CMFCRibbonMiniToolBar::IsRibbonMiniToolBar

Weitere Informationen finden Sie im Quellcode der **VC\\Atlmfc\\Src\\Mfc** Ordner von Visual Studio-Installation.

```
virtual BOOL IsRibbonMiniToolBar() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)
