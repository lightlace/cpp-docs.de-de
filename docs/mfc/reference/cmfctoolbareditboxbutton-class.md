---
title: Cmfctoolbareditboxbutton-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarEditBoxButton
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::CMFCToolBarEditBoxButton
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::CanBeStretched
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::CopyFrom
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetByCmd
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetContentsAll
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetContextMenuID
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetEditBorder
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetHwnd
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetInvalidateRect
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::HaveHotBorder
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::IsFlatMode
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::NotifyCommand
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnAddToCustomizePage
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnChangeParentWnd
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnClick
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnCtlColor
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnGlobalFontsChanged
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnMove
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnShow
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnSize
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnUpdateToolTip
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::SetContextMenuID
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::SetFlatMode
helpviewer_keywords:
- CMFCToolBarEditBoxButton [MFC], CMFCToolBarEditBoxButton
- CMFCToolBarEditBoxButton [MFC], CanBeStretched
- CMFCToolBarEditBoxButton [MFC], CopyFrom
- CMFCToolBarEditBoxButton [MFC], GetByCmd
- CMFCToolBarEditBoxButton [MFC], GetContentsAll
- CMFCToolBarEditBoxButton [MFC], GetContextMenuID
- CMFCToolBarEditBoxButton [MFC], GetEditBorder
- CMFCToolBarEditBoxButton [MFC], GetHwnd
- CMFCToolBarEditBoxButton [MFC], GetInvalidateRect
- CMFCToolBarEditBoxButton [MFC], HaveHotBorder
- CMFCToolBarEditBoxButton [MFC], IsFlatMode
- CMFCToolBarEditBoxButton [MFC], NotifyCommand
- CMFCToolBarEditBoxButton [MFC], OnAddToCustomizePage
- CMFCToolBarEditBoxButton [MFC], OnChangeParentWnd
- CMFCToolBarEditBoxButton [MFC], OnClick
- CMFCToolBarEditBoxButton [MFC], OnCtlColor
- CMFCToolBarEditBoxButton [MFC], OnGlobalFontsChanged
- CMFCToolBarEditBoxButton [MFC], OnMove
- CMFCToolBarEditBoxButton [MFC], OnShow
- CMFCToolBarEditBoxButton [MFC], OnSize
- CMFCToolBarEditBoxButton [MFC], OnUpdateToolTip
- CMFCToolBarEditBoxButton [MFC], SetContextMenuID
- CMFCToolBarEditBoxButton [MFC], SetFlatMode
ms.assetid: b21d9b67-6bf7-4ca9-bd62-b237756e0ab3
ms.openlocfilehash: 3e988d789ca6a038ce41bca829850f6509fd9df1
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504726"
---
# <a name="cmfctoolbareditboxbutton-class"></a>Cmfctoolbareditboxbutton-Klasse

Eine Symbolleisten-Schaltfläche, die ein Bearbeitungs Steuerelement ( [CEdit-Klasse](../../mfc/reference/cedit-class.md)) enthält.

## <a name="syntax"></a>Syntax

```
class CMFCToolBarEditBoxButton : public CMFCToolBarButton
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMFCToolBarEditBoxButton::CMFCToolBarEditBoxButton](#cmfctoolbareditboxbutton)|Erstellt ein `CMFCToolBarEditBoxButton`-Objekt.|
|`CMFCToolBarEditBoxButton::~CMFCToolBarEditBoxButton`|Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCToolBarEditBoxButton::CanBeStretched](#canbestretched)|Gibt an, ob ein Benutzer die Schaltfläche während der Anpassung Strecken kann. (Überschreibt [cmfctoolbarbutton:: canbegestreckt](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched).)|
|[CMFCToolBarEditBoxButton::CopyFrom](#copyfrom)|Kopiert die Eigenschaften einer anderen Symbolleisten Schaltfläche in die aktuelle Schaltfläche. (Überschreibt [cmfctoolbarbutton:: CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::CreateEdit](#createedit)|Erstellt ein neues Bearbeitungs Steuerelement in der Schaltfläche.|
|`CMFCToolBarEditBoxButton::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|
|[CMFCToolBarEditBoxButton::GetByCmd](#getbycmd)|Ruft das erste `CMFCToolBarEditBoxButton` Objekt in der Anwendung ab, das über die angegebene Befehls-ID verfügt.|
|[CMFCToolBarEditBoxButton::GetContentsAll](#getcontentsall)|Ruft den Text des ersten Symbolleisten-Steuer Elements des Bearbeitungs Felds ab, das über die angegebene Befehls-ID verfügt.|
|[CMFCToolBarEditBoxButton::GetContextMenuID](#getcontextmenuid)|Ruft die Ressourcen-ID des Kontextmenüs ab, das der Schaltfläche zugeordnet ist.|
|[CMFCToolBarEditBoxButton::GetEditBorder](#geteditborder)|Ruft das umgebende Rechteck für den Bearbeitungsbereich der Schaltfläche "Bearbeitungsfeld" ab.|
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::GetEditBox](#geteditbox)|Gibt einen Zeiger auf das Bearbeitungs Steuerelement zurück, das in die Schaltfläche eingebettet ist.|
|[CMFCToolBarEditBoxButton::GetHwnd](#gethwnd)|Ruft das Fenster Handle ab, das der Symbolleisten Schaltfläche zugeordnet ist. (Überschreibt [cmfctoolbarbutton:: GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd).)|
|[CMFCToolBarEditBoxButton::GetInvalidateRect](#getinvalidaterect)|Ruft den Bereich des Client Bereichs der Schaltfläche ab, die neu gezeichnet werden muss. (Überschreibt [cmfctoolbarbutton:: getinvalidateru.](../../mfc/reference/cmfctoolbarbutton-class.md#getinvalidaterect))|
|`CMFCToolBarEditBoxButton::GetThisClass`|Wird vom Framework verwendet, um einen Zeiger auf das [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt abzurufen, das diesem Klassentyp zugeordnet ist.|
|[CMFCToolBarEditBoxButton::HaveHotBorder](#havehotborder)|Bestimmt, ob ein Rahmen der Schaltfläche angezeigt wird, wenn ein Benutzer auf die Schaltfläche klickt. (Überschreibt [cmfctoolbarbutton:: havehotborder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder).)|
|[CMFCToolBarEditBoxButton::IsFlatMode](#isflatmode)|Bestimmt, ob Bearbeitungsfeld Schaltflächen einen flachen Stil aufweisen.|
|[CMFCToolBarEditBoxButton::NotifyCommand](#notifycommand)|Gibt an, ob die Schaltfläche die [WM_COMMAND](/windows/win32/menurc/wm-command) -Nachricht verarbeitet. (Überschreibt [cmfctoolbarbutton:: notifycommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand).)|
|[CMFCToolBarEditBoxButton::OnAddToCustomizePage](#onaddtocustomizepage)|Wird von Framework aufgerufen, wenn die Schaltfläche einem anpassbaren Dialogfeld hinzugefügt wird. (Überschreibt [cmfctoolbarbutton:: onaddto customizepage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage).)|
|`CMFCToolBarEditBoxButton::OnCalculateSize`|Wird von Framework aufgerufen, um die Größe der Schaltfläche für den angegebenen Gerätekontext und den Andock Zustand zu berechnen. (Überschreibt [cmfctoolbarbutton:: oncalculatesize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|
|[CMFCToolBarEditBoxButton::OnChangeParentWnd](#onchangeparentwnd)|Wird von Framework aufgerufen, wenn die Schaltfläche in eine neue Symbolleiste eingefügt wird. (Überschreibt [cmfctoolbarbutton:: onchangeparser](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd).)|
|[CMFCToolBarEditBoxButton::OnClick](#onclick)|Wird von Framework aufgerufen, wenn der Benutzer auf die Maustaste klickt. (Überschreibt [cmfctoolbarbutton:: OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|
|[CMFCToolBarEditBoxButton::OnCtlColor](#onctlcolor)|Wird von Framework aufgerufen, wenn die übergeordnete Symbolleiste eine WM_CTLCOLOR-Meldung behandelt. (Überschreibt [cmfctoolbarbutton:: onctlcolor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor).)|
|`CMFCToolBarEditBoxButton::OnDraw`|Wird von Framework aufgerufen, um die Schaltfläche mithilfe der angegebenen Stile und Optionen zu zeichnen. (Überschreibt [cmfctoolbarbutton:: OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|
|`CMFCToolBarEditBoxButton::OnDrawOnCustomizeList`|Wird von Framework aufgerufen, um die Schaltfläche im **Befehls** Bereich des Dialog Felds **Anpassen** zu zeichnen. (Überschreibt [cmfctoolbarbutton:: ondrawoncustomizelist](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).)|
|[CMFCToolBarEditBoxButton::OnGlobalFontsChanged](#onglobalfontschanged)|Wird von Framework aufgerufen, wenn sich die globale Schriftart geändert hat. (Überschreibt [cmfctoolbarbutton:: onglobalfontschge](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged).)|
|[CMFCToolBarEditBoxButton::OnMove](#onmove)|Wird von Framework aufgerufen, wenn die übergeordnete Symbolleiste verschoben wird. (Überschreibt [cmfctoolbarbutton:: OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove).)|
|[CMFCToolBarEditBoxButton::OnShow](#onshow)|Wird von Framework aufgerufen, wenn die Schaltfläche sichtbar oder unsichtbar wird. (Überschreibt [cmfctoolbarbutton:: onShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow).)|
|[CMFCToolBarEditBoxButton::OnSize](#onsize)|Wird von Framework aufgerufen, wenn die Größe oder Position der übergeordneten Symbolleiste geändert wird, und diese Änderung bewirkt, dass die Schaltfläche die Größe ändert. (Überschreibt [cmfctoolbarbutton:: OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize).)|
|[CMFCToolBarEditBoxButton::OnUpdateToolTip](#onupdatetooltip)|Wird von Framework aufgerufen, wenn die übergeordnete Symbolleiste ihren QuickInfo-Text aktualisiert. (Überschreibt [cmfctoolbarbutton:: onupdatetooltip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip).)|
|`CMFCToolBarEditBoxButton::Serialize`|Liest dieses Objekt aus einem Archiv oder schreibt es in ein Archiv. (Überschreibt [cmfctoolbarbutton:: Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize).)|
|`CMFCToolBarEditBoxButton::SetACCData`|Füllt das angegebene `CAccessibilityData` -Objekt mit Barrierefreiheits Daten über die Symbolleisten Schaltfläche auf. (Überschreibt [cmfctoolbarbutton:: setaccdata](../../mfc/reference/cmfctoolbarbutton-class.md#setaccdata).)|
|`CMFCToolBarEditBoxButton::`[Cmfctoolbareditboxbutton:: setContent](#setcontents)|Legt den Text im Bearbeitungs Steuerelement der Schaltfläche fest.|
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::SetContentsAll](#setcontentsall)|Sucht die Schaltfläche zum Bearbeiten von Steuerelementen, die über eine angegebene Befehls-ID verfügt, und legt den Text im Bearbeitungs Steuerelement dieser Schaltfläche fest.|
|[CMFCToolBarEditBoxButton::SetContextMenuID](#setcontextmenuid)|Gibt die Ressourcen-ID des Kontextmenüs an, das der Schaltfläche zugeordnet ist.|
|[CMFCToolBarEditBoxButton::SetFlatMode](#setflatmode)|Gibt die Darstellung der Schaltflächen im flachen Stil in der Anwendung an.|
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::SetStyle](#setstyle)|Gibt den Stil der Schaltfläche an. (Überschreibt [cmfctoolbarbutton:: SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle).)|

## <a name="remarks"></a>Hinweise

Gehen Sie folgendermaßen vor, um einer Symbolleiste eine Schaltfläche zum Bearbeiten eines Felds hinzuzufügen:

1. Reservieren Sie eine Platzhalterressourcen-ID für die Schaltfläche in der übergeordneten Symbolleistenressource.

2. Konstruieren Sie ein `CMFCToolBarEditBoxButton`-Objekt.

3. Ersetzen Sie im Meldungs Handler, der die AFX_WM_RESETTOOLBAR-Nachricht verarbeitet, die Dummy-Schaltfläche durch die Schaltfläche Neues Kombinations Feld, indem Sie [cmfctoolbar:: replacebutton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)verwenden.

Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Einfügen von Steuerelementen in](../../mfc/walkthrough-putting-controls-on-toolbars.md)Symbolleisten.

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Verwendung verschiedener Methoden in der `CMFCToolBarEditBoxButton` -Klasse. In dem Beispiel wird gezeigt, wie angegeben wird, dass ein Benutzer die Schaltfläche während der Anpassung Strecken kann. Geben Sie an, dass ein Rahmen der Schaltfläche angezeigt wird, wenn ein Benutzer auf die Schaltfläche klickt, den Text im Textfeld-Steuerelement festlegen und die Darstellung der Schaltflächen im flachen Format im Applaus angeben. und geben den Stil eines Steuer Elements für die Symbolleisten Bearbeitung an.

[!code-cpp[NVC_MFC_RibbonApp#40](../../mfc/reference/codesnippet/cpp/cmfctoolbareditboxbutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

`CMFCToolBarEditBoxButton`

## <a name="requirements"></a>Anforderungen

**Header:** afxtoolbareditboxbutton. h

##  <a name="canbestretched"></a>Cmfctoolbareditboxbutton:: canbegestreckt

Gibt an, ob ein Benutzer die Schaltfläche während der Anpassung Strecken kann.

```
virtual BOOL CanBeStretched() const;
```

### <a name="return-value"></a>Rückgabewert

Diese Methode gibt "true" zurück.

### <a name="remarks"></a>Hinweise

Standardmäßig ist es dem Benutzer nicht gestattet, eine Symbolleisten-Schaltfläche während der Anpassung zu Strecken. Diese Methode erweitert die Basisklassen Implementierung ( [cmfctoolbarbutton:: canbegestreckt](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched)), indem der Benutzer während der Anpassung eine Symbolleisten Schaltfläche für das Bearbeitungsfeld Strecken kann.

##  <a name="cmfctoolbareditboxbutton"></a>Cmfctoolbareditboxbutton:: cmfctoolbareditboxbutton

Erstellt ein [cmfctoolbareditboxbutton](../../mfc/reference/cmfctoolbareditboxbutton-class.md) -Objekt.

```
CMFCToolBarEditBoxButton(
    UINT uiID,
    int iImage,
    DWORD dwStyle=ES_AUTOHSCROLL,
    int iWidth=0);
```

### <a name="parameters"></a>Parameter

*uiID*<br/>
in Gibt die Steuerelement-ID an.

*iImage*<br/>
in Gibt den NULL basierten Index eines Symbolleisten Bilds an. Das Image befindet sich im [cmfctoolbarimages-Klassen](../../mfc/reference/cmfctoolbarimages-class.md) Objekt, das von der [cmfctoolbar-Klassen](../../mfc/reference/cmfctoolbar-class.md) Klasse verwaltet wird.

*dwStyle*<br/>
in Gibt den Stil für das Bearbeitungs Steuerelement an.

*iWidth*<br/>
in Gibt die Breite des Bearbeitungs Steuer Elements in Pixel an.

### <a name="remarks"></a>Hinweise

Der Standardkonstruktor legt den Stil des Bearbeitungs Steuer Elements auf die folgende Kombination fest:

WS_CHILD | WS_VISIBLE | ES_AUTOHSCROLL

Die Standardbreite des-Steuer Elements beträgt 150 Pixel.

##  <a name="copyfrom"></a>Cmfctoolbareditboxbutton:: CopyFrom

Kopiert die Eigenschaften einer anderen Symbolleisten Schaltfläche in die aktuelle Schaltfläche.

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>Parameter

*src*<br/>
in Ein Verweis auf die Quell Schaltfläche, von der kopiert werden soll.

### <a name="remarks"></a>Hinweise

Mit dieser Methode können Sie eine weitere Symbolleisten Schaltfläche auf diese Symbolleisten Schaltfläche *src* muss den Typ `CMFCToolBarEditBoxButton`aufweisen.

##  <a name="createedit"></a>Cmfctoolbareditboxbutton:: kreateedit

Erstellt ein neues Bearbeitungs Steuerelement in der Schaltfläche.

```
virtual CEdit* CreateEdit(
    CWnd* pWndParent,
    const CRect& rect);
```

### <a name="parameters"></a>Parameter

*pWndParent*<br/>
in Gibt das übergeordnete Fenster des Bearbeitungs Steuer Elements an. Er darf nicht NULL sein.

*Rect*<br/>
in Gibt die Größe und Position des Bearbeitungs Steuer Elements an.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das neu erstellte Bearbeitungs Steuerelement. der Wert ist NULL, wenn die Erstellung und Anlage des Steuer Elements fehlschlagen.

### <a name="remarks"></a>Hinweise

Sie erstellen ein `CMFCToolBarEditBoxButton` -Objekt in zwei Schritten. Nennen Sie zuerst den-Konstruktor, und `CreateEdit`geben Sie dann an, wodurch das Windows-Bearbeitungs Steuerelement `CMFCToolBarEditBoxButton` erstellt und an das-Objekt angefügt wird.

##  <a name="getbycmd"></a>Cmfctoolbareditboxbutton:: getbycmd

Ruft das erste `CMFCToolBarEditBoxButton` Objekt in der Anwendung ab, das über die angegebene Befehls-ID verfügt.

```
static CMFCToolBarEditBoxButton* __stdcall GetByCmd(UINT uiCmd);
```

### <a name="parameters"></a>Parameter

*uiCmd*<br/>
in Die Befehls-ID der abzurufenden Schaltfläche.

### <a name="return-value"></a>Rückgabewert

Das erste `CMFCToolBarEditBoxButton` Objekt in der Anwendung, das über die angegebene Befehls-ID verfügt, oder NULL, wenn kein solches Objekt vorhanden ist.

### <a name="remarks"></a>Hinweise

Diese Shared Utility-Methode wird von Methoden wie [cmfctoolbareditboxbutton:: setcontentsall](#setcontentsall) und [cmfctoolbareditboxbutton:: getcontentsall](#getcontentsall) verwendet, um den Text des ersten Symbolleisten-Steuer Elements mit der angegebenen Befehls-ID festzulegen oder zu erhalten.

##  <a name="getcontentsall"></a>Cmfctoolbareditboxbutton:: getcontentsall

Ruft den Text des ersten Symbolleisten-Steuer Elements des Bearbeitungs Felds ab, das über die angegebene Befehls-ID verfügt.

```
static CString __stdcall GetContentsAll(UINT uiCmd);
```

### <a name="parameters"></a>Parameter

*uiCmd*<br/>
in Die Befehls-ID der Schaltfläche, von der Inhalte abgerufen werden sollen.

### <a name="return-value"></a>Rückgabewert

Ein `CString` -Objekt, das den Text des ersten Symbolleisten-Steuer Elements mit der angegebenen Befehls-ID enthält.

### <a name="remarks"></a>Hinweise

Diese Methode gibt die leere Zeichenfolge zurück `CMFCToolBarEditBoxButton` , wenn keine Objekte über die angegebene Befehls-ID verfügen.

##  <a name="getcontextmenuid"></a>Cmfctoolbareditboxbutton:: getContextMenuId

Ruft die Ressourcen-ID des Kontextmenüs ab, das der Schaltfläche zugeordnet ist.

```
UINT GetContextMenuID();
```

### <a name="return-value"></a>Rückgabewert

Die Ressourcen-ID des Kontextmenüs, das der Schaltfläche zugeordnet ist, oder 0, wenn der Schaltfläche kein Kontextmenü zugeordnet ist.

### <a name="remarks"></a>Hinweise

Das Framework verwendet die Ressourcen-ID, um das Kontextmenü zu erstellen, wenn der Benutzer mit der rechten Maustaste auf die Schaltfläche klickt.

##  <a name="geteditborder"></a>Cmfctoolbareditboxbutton:: geteditborder

Ruft das umgebende Rechteck für den Bearbeitungsbereich der Schaltfläche "Bearbeitungsfeld" ab.

```
virtual void GetEditBorder(CRect& rectBorder);
```

### <a name="parameters"></a>Parameter

*rectBorder*<br/>
vorgenommen Ein Verweis auf das `CRect` -Objekt, das das umgebende Rechteck empfängt.

### <a name="remarks"></a>Hinweise

Diese Methode ruft das umgebende Rechteck des Bearbeitungs Steuer Elements in Client Koordinaten ab. Dadurch wird die Größe des Rechtecks in jeder Richtung um ein Pixel erweitert.

Die [CMFCVisualManager:: ondraweditborder](../../mfc/reference/cmfcvisualmanager-class.md#ondraweditborder) -Methode ruft diese Methode auf, wenn Sie den Rahmen `CMFCToolBarEditBoxButton` um ein-Objekt zeichnet.

##  <a name="geteditbox"></a>Cmfctoolbareditboxbutton:: geteditbox

Gibt einen Zeiger auf das [CEdit-Klassen](../../mfc/reference/cedit-class.md) Steuerelement zurück, das in die Schaltfläche eingebettet ist.

```
CEdit* GetEditBox() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das [CEdit-Klassen](../../mfc/reference/cedit-class.md) Steuerelement, das die Schaltfläche enthält. Der Wert ist NULL, `CEdit` wenn das Steuerelement noch nicht erstellt wurde.

### <a name="remarks"></a>Hinweise

Sie erstellen das `CEdit` Steuerelement, indem Sie [cmfctoolbareditboxbutton:: createedit](#createedit)aufrufen.

##  <a name="gethwnd"></a>Cmfctoolbareditboxbutton:: GetHwnd

Ruft das Fenster Handle ab, das der Symbolleisten Schaltfläche zugeordnet ist.

```
virtual HWND GetHwnd();
```

### <a name="return-value"></a>Rückgabewert

Das Fenster Handle, das der Schaltfläche zugeordnet ist.

### <a name="remarks"></a>Hinweise

Diese Methode überschreibt die [cmfctoolbarbutton:: GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd) -Methode, indem das Fenster Handle des Bearbeitungs Steuerelement-Teils der Schaltfläche "Bearbeitungsfeld" zurückgegeben wird.

##  <a name="getinvalidaterect"></a>Cmfctoolbareditboxbutton:: getinvalidatup

Ruft den Bereich des Client Bereichs der Schaltfläche ab, die neu gezeichnet werden muss.

```
virtual const CRect GetInvalidateRect() const;
```

### <a name="return-value"></a>Rückgabewert

Ein `CRect` -Objekt, das den Bereich angibt, der neu gezeichnet werden muss.

### <a name="remarks"></a>Hinweise

Diese Methode erweitert die Basisklassen Implementierung [cmfctoolbarbutton:: getinvalidaterudurch](../../mfc/reference/cmfctoolbarbutton-class.md#getinvalidaterect)einschließen in den Bereich der Text Bezeichnung.

##  <a name="havehotborder"></a>Cmfctoolbareditboxbutton:: havehotborder

Bestimmt, ob ein Rahmen der Schaltfläche angezeigt wird, wenn ein Benutzer auf die Schaltfläche klickt.

```
virtual BOOL HaveHotBorder() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn eine Schaltfläche den Rahmen anzeigt, wenn Sie ausgewählt wird. andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Methode erweitert die Basisklassen Implementierung [cmfctoolbarbutton:: havehotborder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder), indem ein Wert ungleich 0 (null) zurückgegeben wird, wenn das Steuerelement sichtbar ist.

##  <a name="isflatmode"></a>Cmfctoolbareditboxbutton:: isflatmode

Bestimmt, ob Bearbeitungsfeld Schaltflächen einen flachen Stil aufweisen.

```
static BOOL __stdcall IsFlatMode();
```

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Schaltflächen einen flachen Stil aufweisen; andernfalls 0.

### <a name="remarks"></a>Hinweise

Standardmäßig haben Schaltflächen für Bearbeitungsfelder einen flachen Stil. Verwenden Sie die [cmfctoolbareditboxbutton:: setflatmode](#setflatmode) -Methode, um die Darstellung des flachen Stils für Ihre Anwendung zu ändern.

##  <a name="notifycommand"></a>Cmfctoolbareditboxbutton:: notifycommand

Gibt an, ob die Schaltfläche die [WM_COMMAND](/windows/win32/menurc/wm-command) -Nachricht verarbeitet.

```
virtual BOOL NotifyCommand(int iNotifyCode);
```

### <a name="parameters"></a>Parameter

*iNotifyCode*<br/>
in Die Benachrichtigungs Meldung, die dem Befehl zugeordnet ist.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die Schaltfläche die WM_COMMAND-Nachricht verarbeitet, oder false, um anzugeben, dass die Nachricht von der übergeordneten Symbolleiste behandelt werden muss.

### <a name="remarks"></a>Hinweise

Das Framework ruft diese Methode auf, wenn es im Begriff ist, eine [WM_COMMAND](/windows/win32/menurc/wm-command) -Nachricht an das übergeordnete Fenster zu senden.

Diese Methode erweitert die Basisklassen Implementierung ( [cmfctoolbarbutton:: notifycommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand)) durch Verarbeitung der [EN_UPDATE](/windows/win32/Controls/en-update) -Benachrichtigung. Für jedes Bearbeitungsfeld mit derselben Befehls-ID wie dieses Objekt wird seine Text Bezeichnung auf die Text Bezeichnung dieses Objekts festgelegt.

##  <a name="onaddtocustomizepage"></a>Cmfctoolbareditboxbutton:: onaddto customizepage

Wird von Framework aufgerufen, wenn die Schaltfläche einem anpassbaren Dialogfeld hinzugefügt wird.

```
virtual void OnAddToCustomizePage();
```

### <a name="remarks"></a>Hinweise

Diese Methode erweitert die Basisklassen Implementierung ( [cmfctoolbarbutton:: onaddtocustomizepage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage)), indem die Eigenschaften aus dem Bearbeitungsfeld-Steuerelement in einer beliebigen Symbolleiste kopiert werden, die dieselbe Befehls-ID wie dieses Objekt aufweist. Diese Methode führt keine Aktion aus, wenn keine Symbolleiste über ein Bearbeitungsfeld-Steuerelement verfügt, das dieselbe Befehls-ID wie dieses Objekt aufweist.

Weitere Informationen zum Dialogfeld **Anpassen** finden Sie unter [cmfctoolbarscustomizedialog-Klasse](../../mfc/reference/cmfctoolbarscustomizedialog-class.md).

##  <a name="onchangeparentwnd"></a>Cmfctoolbareditboxbutton:: onchangepartwnd

Wird von Framework aufgerufen, wenn die Schaltfläche in eine neue Symbolleiste eingefügt wird.

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>Parameter

*pWndParent*<br/>
in Ein Zeiger auf das neue übergeordnete Fenster.

### <a name="remarks"></a>Hinweise

Diese Methode überschreibt die Basisklassen Implementierung ( [cmfctoolbarbutton:: onchangeparser](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)), indem das interne `CEdit` -Objekt neu erstellt wird.

##  <a name="onclick"></a>Cmfctoolbareditboxbutton:: OnClick

Wird von Framework aufgerufen, wenn der Benutzer auf die Maustaste klickt.

```
virtual BOOL OnClick(
    CWnd* pWnd,
    BOOL bDelay = TRUE);
```

### <a name="parameters"></a>Parameter

*pWnd*<br/>
in Genutzt.

*bDelay*<br/>
in Genutzt.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Schaltfläche die Klick Nachricht verarbeitet. andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Methode überschreibt die Basisklassen Implementierung ( [cmfctoolbarbutton:: OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick)), indem Sie einen Wert ungleich 0 (NULL `CEdit` ) zurückgibt, wenn das interne Objekt sichtbar ist.

##  <a name="onctlcolor"></a>Cmfctoolbareditboxbutton:: onctlcolor

Wird von Framework aufgerufen, wenn die übergeordnete Symbolleiste eine WM_CTLCOLOR-Meldung behandelt.

```
virtual HBRUSH OnCtlColor(
    CDC* pDC,
    UINT nCtlColor);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
in Der Gerätekontext, der die Schaltfläche anzeigt.

*nCtlColor*<br/>
in Genutzt.

### <a name="return-value"></a>Rückgabewert

Ein Handle für den globalen Fenster Pinsel.

### <a name="remarks"></a>Hinweise

Diese Methode überschreibt die Basisklassen Implementierung ( [cmfctoolbarbutton:: onctlcolor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor)), indem die Text-und Hintergrundfarben des bereitgestellten Geräte Kontexts auf die globalen Text-bzw. Hintergrundfarben festgelegt werden.

Weitere Informationen zu globalen Optionen, die für Ihre Anwendung verfügbar sind, finden Sie unter [AFX_GLOBAL_DATA Structure](../../mfc/reference/afx-global-data-structure.md).

##  <a name="onglobalfontschanged"></a>Cmfctoolbareditboxbutton:: onglobalfontschge

Wird von Framework aufgerufen, wenn sich die globale Schriftart geändert hat.

```
virtual void OnGlobalFontsChanged();
```

### <a name="remarks"></a>Hinweise

Diese Methode erweitert die Basisklassen Implementierung ( [cmfctoolbarbutton:: onglobalfontschge](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged)) durch Ändern der Schriftart des Steuer Elements in die der globalen Schriftart.

Weitere Informationen zu globalen Optionen, die für Ihre Anwendung verfügbar sind, finden Sie unter [AFX_GLOBAL_DATA Structure](../../mfc/reference/afx-global-data-structure.md).

##  <a name="onmove"></a>Cmfctoolbareditboxbutton:: OnMove

Wird von Framework aufgerufen, wenn die übergeordnete Symbolleiste verschoben wird.

```
virtual void OnMove();
```

### <a name="remarks"></a>Hinweise

Diese Methode überschreibt die Standard-Klassen Implementierung ( [cmfctoolbarbutton:: OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove)), indem die Position des internen `CEdit` Objekts aktualisiert wird.

##  <a name="onshow"></a>Cmfctoolbareditboxbutton:: onShow

Wird von Framework aufgerufen, wenn die Schaltfläche sichtbar oder unsichtbar wird.

```
virtual void OnShow(BOOL bShow);
```

### <a name="parameters"></a>Parameter

*bShow*<br/>
in Gibt an, ob die Schaltfläche sichtbar ist. Wenn dieser Parameter true ist, wird die Schaltfläche angezeigt. Andernfalls ist die Schaltfläche nicht sichtbar.

### <a name="remarks"></a>Hinweise

Diese Methode erweitert die Basisklassen Implementierung ( [cmfctoolbarbutton:: onShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow)) durch Anzeigen der Schaltfläche, wenn *bShow* auf true festgelegt ist. Andernfalls blendet diese Methode die Schaltfläche aus.

##  <a name="onsize"></a>Cmfctoolbareditboxbutton:: OnSize

Wird von Framework aufgerufen, wenn die Größe oder Position der übergeordneten Symbolleiste geändert wird, und diese Änderung bewirkt, dass die Schaltfläche die Größe ändert.

```
virtual void OnSize(int iSize);
```

### <a name="parameters"></a>Parameter

*iSize*<br/>
in Die neue Breite der Schaltfläche in Pixel.

### <a name="remarks"></a>Hinweise

Diese Methode überschreibt die Standard Implementierung der-Klasse [cmfctoolbarbutton:: OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize)durch Aktualisieren der Größe und Position des internen `CEdit` Objekts.

##  <a name="onupdatetooltip"></a>Cmfctoolbareditboxbutton:: onupdatetooltip

Wird von Framework aufgerufen, wenn die übergeordnete Symbolleiste ihren QuickInfo-Text aktualisiert.

```
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,
    int iButtonIndex,
    CToolTipCtrl& wndToolTip,
    CString& str);
```

### <a name="parameters"></a>Parameter

*pWndParent*<br/>
in Genutzt.

*iButtonIndex*<br/>
in Genutzt.

*wndToolTip*<br/>
in Das Steuerelement, das den QuickInfo-Text anzeigt.

*str*<br/>
vorgenommen Ein `CString` -Objekt, das den aktualisierten QuickInfo-Text empfängt.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Methode den QuickInfo-Text aktualisiert. andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Methode erweitert die Basisklassen Implementierung ( [cmfctoolbarbutton:: onupdatetooltip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip)), indem der QuickInfo-Text angezeigt wird, der dem Bearbeitungs Teil der Schaltfläche zugeordnet ist. Wenn das interne `CEdit` -Objekt NULL ist oder das Fenster Handle `CEdit` des-Objekts kein vorhandenes Fenster identifiziert, führt diese Methode keine Aktion aus und gibt false zurück.

##  <a name="setcontents"></a>Cmfctoolbareditboxbutton:: setContent

Legt den Text im Textfeld-Steuerelement fest.

```
virtual void SetContents(const CString& sContents);
```

### <a name="parameters"></a>Parameter

*Scontent*<br/>
in Gibt den neuen festzulegenden Text an.

##  <a name="setcontentsall"></a>Cmfctoolbareditboxbutton:: setcontentsall

Sucht ein [cmfctoolbareditboxbutton](../../mfc/reference/cmfctoolbareditboxbutton-class.md) -Objekt, das über eine angegebene Befehls-ID verfügt, und legt den angegebenen Text in seinem Textfeld fest.

```
static BOOL SetContentsAll(
    UINT uiCmd,
    const CString& strContents);
```

### <a name="parameters"></a>Parameter

*uiCmd*<br/>
in Gibt die Befehls-ID des Steuer Elements an, für das der Text geändert wird.

*strContents*<br/>
in Gibt den neuen festzulegenden Text an.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn der Text festgelegt wurde. 0, wenn `CMFCToolBarEditBoxButton` das Steuerelement mit der angegebenen Befehls-ID nicht vorhanden ist.

##  <a name="setcontextmenuid"></a>Cmfctoolbareditboxbutton:: setcontextmenuid

Gibt die Ressourcen-ID des Kontextmenüs an, das der Schaltfläche zugeordnet ist.

```
void SetContextMenuID(UINT uiResID);
```

### <a name="parameters"></a>Parameter

*uiCmd*<br/>
in Die Ressourcen-ID des Kontextmenüs.

### <a name="remarks"></a>Hinweise

Das Framework verwendet die Ressourcen-ID zum Erstellen des Kontextmenüs, wenn der Benutzer mit der rechten Maustaste auf die Symbolleisten Schaltfläche klickt.

##  <a name="setflatmode"></a>Cmfctoolbareditboxbutton:: setflatmode

Gibt die Darstellung der Schaltflächen im flachen Stil in der Anwendung an.

```
static void __stdcall SetFlatMode(BOOL bFlat = TRUE);
```

### <a name="parameters"></a>Parameter

*bFlat*<br/>
in Die FlatStyle-Schaltfläche für Bearbeitungsfelder. Wenn dieser Parameter true ist, ist die flache Darstellung aktiviert. Andernfalls ist die flache Darstellung deaktiviert.

### <a name="remarks"></a>Hinweise

Die Standard Schaltfläche für das Optionsfeld "FlatStyle" ist true. Verwenden Sie die [cmfctoolbareditboxbutton:: isflatmode](#isflatmode) -Methode, um die flache Darstellung der Anwendung abzurufen.

##  <a name="setstyle"></a>Cmfctoolbareditboxbutton:: SetStyle

Gibt den Stil eines Steuer Elements für die Symbolleisten Bearbeitung an.

```
virtual void SetStyle(UINT nStyle);
```

### <a name="parameters"></a>Parameter

*nStyle*<br/>
in Ein neuer festzulegende Stil.

### <a name="remarks"></a>Hinweise

Diese Methode legt [cmfctoolbarbutton:: m_nStyle](../../mfc/reference/cmfctoolbarbutton-class.md#m_nstyle) auf *nstyle* fest. Sie deaktiviert außerdem das Textfeld, wenn sich die Anwendung im Anpassungsmodus befindet, und aktiviert Sie, wenn sich die Anwendung nicht im Anpassungsmodus befindet (siehe [cmfctoolbar:: setcustomizemode](../../mfc/reference/cmfctoolbar-class.md#setcustomizemode) und). [Cmfctoolbar:: iscustomizemode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)). Eine Liste gültiger stilflags finden Sie unter Symbolleisten- [Steuerelement Stile](../../mfc/reference/toolbar-control-styles.md) .

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarButton-Klasse](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[CEdit-Klasse](../../mfc/reference/cedit-class.md)<br/>
[CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[Exemplarische Vorgehensweise: Einfügen von Steuerelementen in eine Symbolleiste](../../mfc/walkthrough-putting-controls-on-toolbars.md)
