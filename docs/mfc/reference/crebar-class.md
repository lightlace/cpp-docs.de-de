---
title: CReBar-Klasse
ms.date: 11/19/2018
f1_keywords:
- CReBar
- AFXEXT/CReBar
- AFXEXT/CReBar::AddBar
- AFXEXT/CReBar::Create
- AFXEXT/CReBar::GetReBarCtrl
helpviewer_keywords:
- CReBar [MFC], AddBar
- CReBar [MFC], Create
- CReBar [MFC], GetReBarCtrl
ms.assetid: c1ad2720-1d33-4106-8e4e-80aa84f93559
ms.openlocfilehash: 344886ca4af45d55b85cc7471c1e558d73cbebf6
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2018
ms.locfileid: "52175885"
---
# <a name="crebar-class"></a>CReBar-Klasse

Eine Steuerleiste, die Layout-, Persistenz- und Zustandsinformationen für Grundleisten-Steuerelemente bereitstellt.

## <a name="syntax"></a>Syntax

```
class CReBar : public CControlBar
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CReBar::AddBar](#addbar)|Eine grundleiste wird ein Band hinzugefügt.|
|[CReBar::Create](#create)|Erstellt das Grundleistensteuerelement, und fügt es der `CReBar` Objekt.|
|[CReBar:: GetReBarCtrl](#getrebarctrl)|Ermöglicht den direkten Zugriff auf die zugrunde liegende allgemeine-Steuerelement.|

## <a name="remarks"></a>Hinweise

Einem Grundleisten-Objekt kann es sich um eine Vielzahl untergeordneter Fenster, in der Regel andere Steuerelemente, einschließlich Bearbeitungsfelder, Symbolleisten und Listenfelder enthalten. Zugehöriges untergeordnetes Fenster kann von einem Grundleisten-Objekt über eine angegebene Bitmap anzeigen. Ihre Anwendung kann automatisch die Größe der Infoleiste oder des Benutzers kann manuell grundleiste durch Klicken oder ziehen die Ziehpunktleiste.

![Beispiel eines grundleistenmenüs](../../mfc/reference/media/vc4sc61.gif "Beispiel eines grundleistenmenüs")

## <a name="rebar-control"></a>Grundleisten-Steuerelement

Einem Grundleisten-Objekt verhält sich ähnlich wie ein Symbolleistenobjekt. Eine grundleiste verwendet den klicken und ziehen-Mechanismus zum Ändern der Größe der Bänder an. Einem Grundleisten-Steuerelement kann eine oder mehrere Bänder, die für jedes Band müssen eine beliebige Kombination von eine Ziehpunktleiste, eine Bitmap, einer textbezeichnung und einem untergeordneten Fenster enthalten. Allerdings darf keine Bänder mehr als ein untergeordnetes Fenster enthalten.

`CReBar` verwendet die [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) Klasse, um die Implementierung bereitzustellen. Sie können über das Grundleistensteuerelement zugreifen [GetReBarCtrl](#getrebarctrl) profitieren von Optionen zur Anpassung des Steuerelements. Weitere Informationen zu Grundleisten-Steuerelemente, finden Sie unter `CReBarCtrl`. Weitere Informationen zur Verwendung von Grundleisten-Steuerelemente finden Sie unter [Verwenden von CReBarCtrl](../../mfc/using-crebarctrl.md).

> [!CAUTION]
>  Infoleiste und Grundleisten-Steuerelement-Objekte unterstützen keine MFC andockbare Steuerleiste. Wenn `CRebar::EnableDocking` aufgerufen wird, wird Ihre Anwendung bestätigt.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CControlBar](../../mfc/reference/ccontrolbar-class.md)

`CReBar`

## <a name="requirements"></a>Anforderungen

**Header:** afxext.h

##  <a name="addbar"></a>  CReBar::AddBar

Rufen Sie diese Memberfunktion, um ein Band grundleiste hinzuzufügen.

```
BOOL AddBar(
    CWnd* pBar,
    LPCTSTR pszText = NULL,
    CBitmap* pbmp = NULL,
    DWORD dwStyle = RBBS_GRIPPERALWAYS | RBBS_FIXEDBMP);

BOOL AddBar(
    CWnd* pBar,
    COLORREF clrFore,
    COLORREF clrBack,
    LPCTSTR pszText = NULL,
    DWORD dwStyle = RBBS_GRIPPERALWAYS);
```

### <a name="parameters"></a>Parameter

*pBar*<br/>
Ein Zeiger auf eine `CWnd` Objekt, das das untergeordnete Fenster in der Infoleiste eingefügt werden soll. Das referenzierte Objekt muss es sich um eine WS_CHILD verfügen.

*lpszText*<br/>
Ein Zeiger auf eine Zeichenfolge, die mit dem Text auf der grundleiste angezeigt werden. Standardmäßig NULL. Der Text im *LpszText* ist nicht Teil des untergeordneten Fensters; er befindet sich auf die Infoleiste selbst.

*pbmp*<br/>
Ein Zeiger auf eine `CBitmap` Objekte über die Hintergründe grundleiste angezeigt werden. Standardmäßig NULL.

*dwStyle*<br/>
Ein DWORD, das den Stil enthält grundleiste zuweisen. Finden Sie unter den `fStyle` funktionsbeschreibung in der Struktur Win32 [REBARBANDINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarbandinfoa) für eine vollständige Liste der Stile von Band.

*clrFore*<br/>
Eine COLORREF-Wert, der die Vordergrundfarbe der Infoleiste darstellt.

*clrBack*<br/>
Eine COLORREF-Wert, der die Hintergrundfarbe der Infoleiste darstellt.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CReBarCtrl#1](../../mfc/reference/codesnippet/cpp/crebar-class_1.cpp)]

##  <a name="create"></a>  CReBar::Create

Rufen Sie diese Memberfunktion zum Erstellen einer Infoleiste.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = RBS_BANDBORDERS,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS | WS_CLIPCHILDREN | CBRS_TOP,
    UINT nID = AFX_IDW_REBAR);
```

### <a name="parameters"></a>Parameter

*pParentWnd*<br/>
Zeiger auf die `CWnd` -Objekt, dessen Windows-Fenster das übergeordnete Element der Statusleiste ist. Normalerweise Ihr Rahmenfenster.

*dwCtrlStyle*<br/>
Das Format des Grundleisten-Steuerelement. In der Standardeinstellung RBS_BANDBORDERS, die schmale Linien zum Trennen der benachbarte Bänder innerhalb des Infoleistensteuerelements anzeigt. Finden Sie unter [Stile für Grundleisten-Steuerelemente](/windows/desktop/Controls/rebar-control-styles) im Windows SDK für eine Liste der Formate.

*dwStyle*<br/>
Die Infoleiste Window-Stile.

*nID*<br/>
Die Infoleiste untergeordneten Fensters-ID.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CReBar::AddBar](#addbar).

##  <a name="getrebarctrl"></a>  CReBar:: GetReBarCtrl

Diese Memberfunktion ermöglicht den direkten Zugriff auf die zugrunde liegende allgemeine-Steuerelement.

```
CReBarCtrl& GetReBarCtrl() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf eine [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) Objekt.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Memberfunktion, um die Funktionalität der allgemeinen Windows Grundleisten-Steuerelement bei der Anpassung Ihrer Infoleiste nutzen. Beim Aufruf `GetReBarCtrl`, wird ein Verweis-Objekt, das `CReBarCtrl` Objekt, damit Sie beide Sätze von Memberfunktionen verwenden können.

Weitere Informationen zur Verwendung von `CReBarCtrl` zum Anpassen Ihrer Infoleiste finden Sie unter [Verwenden von CReBarCtrl](../../mfc/using-crebarctrl.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CReBarCtrl#2](../../mfc/reference/codesnippet/cpp/crebar-class_2.cpp)]

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel-MFCIE](../../visual-cpp-samples.md)<br/>
[CControlBar-Klasse](../../mfc/reference/ccontrolbar-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)

