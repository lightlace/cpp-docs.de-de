---
title: CMFCPropertyGridToolTipCtrl-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCPropertyGridToolTipCtrl
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Create
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Deactivate
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::GetLastRect
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Hide
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::SetTextMargin
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Track
helpviewer_keywords:
- CMFCPropertyGridToolTipCtrl [MFC], CMFCPropertyGridToolTipCtrl
- CMFCPropertyGridToolTipCtrl [MFC], Create
- CMFCPropertyGridToolTipCtrl [MFC], Deactivate
- CMFCPropertyGridToolTipCtrl [MFC], GetLastRect
- CMFCPropertyGridToolTipCtrl [MFC], Hide
- CMFCPropertyGridToolTipCtrl [MFC], SetTextMargin
- CMFCPropertyGridToolTipCtrl [MFC], Track
ms.assetid: 84b436e5-6695-4da0-9569-1a875e087711
ms.openlocfilehash: 6c14ed1f11a7a414332b34566a314459d76b911b
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57303923"
---
# <a name="cmfcpropertygridtooltipctrl-class"></a>CMFCPropertyGridToolTipCtrl-Klasse

Implementiert eine QuickInfo zu steuern, die die [CMFCPropertyGridCtrl Class](../../mfc/reference/cmfcpropertygridctrl-class.md) verwendet, um QuickInfos anzuzeigen.

## <a name="syntax"></a>Syntax

```
class CMFCPropertyGridToolTipCtrl : public CWnd
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|||
|-|-|
|Name|Beschreibung|
|[CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl](#cmfcpropertygridtooltipctrl)|Erstellt ein `CMFCPropertyGridToolTipCtrl`-Objekt.|
|`CMFCPropertyGridToolTipCtrl::~CMFCPropertyGridToolTipCtrl`|Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|||
|-|-|
|Name|Beschreibung|
|[CMFCPropertyGridToolTipCtrl::Create](#create)|Erstellt ein Fenster für das QuickInfo-Steuerelement.|
|[CMFCPropertyGridToolTipCtrl::Deactivate](#deactivate)|Deaktiviert, und blendet Sie aus dem QuickInfo-Steuerelement.|
|[CMFCPropertyGridToolTipCtrl::GetLastRect](#getlastrect)|Gibt die Koordinaten der letzten Position des QuickInfo-Steuerelements zurück.|
|[CMFCPropertyGridToolTipCtrl::Hide](#hide)|Blendet das QuickInfo-Steuerelement.|
|`CMFCPropertyGridToolTipCtrl::PreTranslateMessage`|Wird von der [CWinApp](../../mfc/reference/cwinapp-class.md) -Klasse verwendet, um Fenstermeldungen zu übersetzen, bevor diese an die Windows-Funktionen [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) und [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) gesendet werden. (Überschreibt [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|
|[CMFCPropertyGridToolTipCtrl::SetTextMargin](#settextmargin)|Legt den Abstand zwischen der QuickInfo-Text und dem Rahmen des QuickInfo-Fensters fest.|
|[CMFCPropertyGridToolTipCtrl::Track](#track)|Zeigt das QuickInfo-Steuerelement.|

## <a name="remarks"></a>Hinweise

QuickInfos werden angezeigt, wenn der Zeiger auf einen Eigenschaftennamen verbleibt. Die [CMFCPropertyGridToolTipCtrl](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md) Klasse zeigt eine QuickInfo an, sodass er vom Benutzer leicht lesbar ist. Die Position der QuickInfo wird in der Regel durch die Position des Zeigers bestimmt. Durch die Verwendung dieser Klasse wird die QuickInfo angezeigt wird, über den Eigenschaftennamen und die natürliche eigenschaftenerweiterung ähnelt, so dass der Eigenschaftenname vollständig sichtbar ist.

MFC automatisch dieses Steuerelements erstellt und verwendet ihn in das [CMFCPropertyGridCtrl Class](../../mfc/reference/cmfcpropertygridctrl-class.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird veranschaulicht, wie zum Erstellen eines Objekts von der `CMFCPropertyGridToolTipCtrl` -Klasse, und wie das QuickInfo-Steuerelement angezeigt.

[!code-cpp[NVC_MFC_RibbonApp#23](../../mfc/reference/codesnippet/cpp/cmfcpropertygridtooltipctrl-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CMFCPropertyGridToolTipCtrl](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxpropertygridtooltipctrl.h

##  <a name="cmfcpropertygridtooltipctrl"></a>  CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl

Erstellt ein `CMFCPropertyGridToolTipCtrl`-Objekt.

```
CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl();
```

##  <a name="create"></a>  CMFCPropertyGridToolTipCtrl::Create

Erstellt ein Fenster für das QuickInfo-Steuerelement.

```
BOOL Create(CWnd* pWndParent);
```

### <a name="parameters"></a>Parameter

*pWndParent*<br/>
[in] Ein Zeiger auf das übergeordnete Fenster.

### <a name="return-value"></a>Rückgabewert

True, wenn das Fenster erfolgreich erstellt wurde. andernfalls "false".

##  <a name="deactivate"></a>  CMFCPropertyGridToolTipCtrl::Deactivate

Deaktiviert, und blendet Sie aus dem QuickInfo-Steuerelement.

```
void Deactivate();
```

### <a name="remarks"></a>Hinweise

Diese Methode legt fest, die letzte Position und den Text für leere Werte, sodass zukünftige Aufrufe [CMFCPropertyGridToolTipCtrl::Track](#track) zeigen Sie die QuickInfo.

##  <a name="getlastrect"></a>  CMFCPropertyGridToolTipCtrl::GetLastRect

Gibt die Koordinaten der letzten Position des QuickInfo-Steuerelements zurück.

```
void GetLastRect(CRect& rect) const;
```

### <a name="parameters"></a>Parameter

*rect*<br/>
[out] Enthält die letzte Position des QuickInfo-Steuerelements.

##  <a name="hide"></a>  CMFCPropertyGridToolTipCtrl::Hide

Blendet das QuickInfo-Steuerelement.

```
void Hide();
```

##  <a name="settextmargin"></a>  CMFCPropertyGridToolTipCtrl::SetTextMargin

Legt den Abstand zwischen der QuickInfo-Text und dem Rahmen des QuickInfo-Fensters fest.

```
void SetTextMargin(int nTextMargin);
```

### <a name="parameters"></a>Parameter

*nTextMargin*<br/>
[in] Gibt den Abstand zwischen der QuickInfo-Text-Steuerelement und dem Rahmen des QuickInfo-Fensters. Der Standardwert ist 10 Pixel.

##  <a name="track"></a>  CMFCPropertyGridToolTipCtrl::Track

Zeigt das QuickInfo-Steuerelement.

```
void Track(
    CRect rect,
    const CString& strText);
```

### <a name="parameters"></a>Parameter

*rect*<br/>
[in] Gibt an, die Position und Größe des QuickInfo-Steuerelements.

*strText*<br/>
[in] Gibt den Text in der QuickInfo angezeigt werden.

### <a name="remarks"></a>Hinweise

Diese Methode zeigt das QuickInfo-Steuerelement an die Position und Größe, die anhand des *Rect*. Wenn die Position, Größe und Text nicht seit dem letzten geändert haben, die diese Methode aufgerufen wurde, hat diese Methode keine Auswirkungen.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)
