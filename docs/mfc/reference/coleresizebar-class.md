---
title: COleResizeBar-Klasse
ms.date: 11/04/2016
f1_keywords:
- COleResizeBar
- AFXOLE/COleResizeBar
- AFXOLE/COleResizeBar::COleResizeBar
- AFXOLE/COleResizeBar::Create
helpviewer_keywords:
- COleResizeBar [MFC], COleResizeBar
- COleResizeBar [MFC], Create
ms.assetid: 56a708d9-28c5-4eb0-9404-77b688d91c63
ms.openlocfilehash: c4b7ce80762cdb49b6007eac7f6b26019b108795
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50445109"
---
# <a name="coleresizebar-class"></a>COleResizeBar-Klasse

Ein Steuerleistentyp, die Größenanpassung von direkten OLE-Elementen unterstützt.

## <a name="syntax"></a>Syntax

```
class COleResizeBar : public CControlBar
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[COleResizeBar::COleResizeBar](#coleresizebar)|Erstellt ein `COleResizeBar`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[COleResizeBar::Create](#create)|Erstellt und initialisiert ein untergeordnetes Fenster von Windows und ordnet es die `COleResizeBar` Objekt.|

## <a name="remarks"></a>Hinweise

`COleResizeBar` Objekte werden als eine [CRectTracker](../../mfc/reference/crecttracker-class.md) mit schraffiert und äußeren Handles zur Größenänderung.

`COleResizeBar` Objekte sind in der Regel eingebettete Elemente der abgeleitete Rahmenfenster Objekte der [COleIPFrameWnd](../../mfc/reference/coleipframewnd-class.md) Klasse.

Weitere Informationen finden Sie im Artikel [Aktivierung](../../mfc/activation-cpp.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CControlBar](../../mfc/reference/ccontrolbar-class.md)

`COleResizeBar`

## <a name="requirements"></a>Anforderungen

**Header:** afxole.h

##  <a name="coleresizebar"></a>  COleResizeBar::COleResizeBar

Erstellt ein `COleResizeBar`-Objekt.

```
COleResizeBar();
```

### <a name="remarks"></a>Hinweise

Rufen Sie `Create` das Ändern der Größe Bar-Objekt zu erstellen.

##  <a name="create"></a>  COleResizeBar::Create

Erstellt ein untergeordnetes Fenster und ordnet ihn dem `COleResizeBar` Objekt.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE,
    UINT nID = AFX_IDW_RESIZE_BAR);
```

### <a name="parameters"></a>Parameter

*pParentWnd*<br/>
Zeiger auf das übergeordnete Fenster der Größe angezeigt.

*dwStyle*<br/>
Gibt an, die [Fensterstil](../../mfc/reference/styles-used-by-mfc.md#window-styles) Attribute.

*nID*<br/>
Die Größe des Balkens untergeordneten Fensters-ID.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Größenänderung Leiste erstellt wurde; andernfalls 0.

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel SUPERPAD](../../visual-cpp-samples.md)<br/>
[CControlBar-Klasse](../../mfc/reference/ccontrolbar-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[COleServerDoc-Klasse](../../mfc/reference/coleserverdoc-class.md)
