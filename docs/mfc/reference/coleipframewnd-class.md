---
title: COleIPFrameWnd-Klasse
ms.date: 11/04/2016
f1_keywords:
- COleIPFrameWnd
- AFXOLE/COleIPFrameWnd
- AFXOLE/COleIPFrameWnd::COleIPFrameWnd
- AFXOLE/COleIPFrameWnd::OnCreateControlBars
- AFXOLE/COleIPFrameWnd::RepositionFrame
helpviewer_keywords:
- COleIPFrameWnd [MFC], COleIPFrameWnd
- COleIPFrameWnd [MFC], OnCreateControlBars
- COleIPFrameWnd [MFC], RepositionFrame
ms.assetid: 24abb2cb-826c-4dda-a287-d8a8900a5763
ms.openlocfilehash: 307bf991853264fcf03dfc5b22eed8e91a3e7aa8
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57301401"
---
# <a name="coleipframewnd-class"></a>COleIPFrameWnd-Klasse

Die Basis für der Fenster zur direkten Bearbeitung der Anwendung.

## <a name="syntax"></a>Syntax

```
class COleIPFrameWnd : public CFrameWnd
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[COleIPFrameWnd::COleIPFrameWnd](#coleipframewnd)|Erstellt ein `COleIPFrameWnd`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[COleIPFrameWnd::OnCreateControlBars](#oncreatecontrolbars)|Wird vom Framework aufgerufen, wenn ein Element für direktes Editieren aktiviert ist.|
|[COleIPFrameWnd::RepositionFrame](#repositionframe)|Wird aufgerufen, durch das Framework, um das Bearbeitungsfenster des direktes neu zu positionieren.|

## <a name="remarks"></a>Hinweise

Diese Klasse erstellt, und stellen die Steuerleisten im Dokumentfenster der containeranwendung. Er führt auch von einem eingebetteten generierte Benachrichtigungen [COleResizeBar](../../mfc/reference/coleresizebar-class.md) Objekt, wenn der Benutzer das Bearbeitungsfenster des direktes ändert.

Weitere Informationen zur Verwendung von `COleIPFrameWnd`, finden Sie im Artikel [Aktivierung](../../mfc/activation-cpp.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`COleIPFrameWnd`

## <a name="requirements"></a>Anforderungen

**Header:** afxole.h

##  <a name="coleipframewnd"></a>  COleIPFrameWnd::COleIPFrameWnd

Erstellt eine `COleIPFrameWnd` -Objekt und initialisiert seine direkten Zustandsinformationen, die in einer Struktur vom Typ OLEINPLACEFRAMEINFO gespeichert wird.

```
COleIPFrameWnd();
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [OLEINPLACEFRAMEINFO](/windows/desktop/api/oleidl/ns-oleidl-tagoifi) im Windows SDK.

##  <a name="oncreatecontrolbars"></a>  COleIPFrameWnd::OnCreateControlBars

Das Framework Ruft die `OnCreateControlBars` funktionieren, wenn ein Element für direktes Editieren aktiviert ist.

```
virtual BOOL OnCreateControlBars(
    CWnd* pWndFrame,
    CWnd* pWndDoc);

virtual BOOL OnCreateControlBars(
    CFrameWnd* pWndFrame,
    CFrameWnd* pWndDoc);
```

### <a name="parameters"></a>Parameter

*pWndFrame*<br/>
Zeiger auf das Rahmenfenster der containeranwendung.

*pWndDoc*<br/>
Zeiger auf den Container auf Dokumentebene Fenster. NULL kann sein, wenn der Container eine SDI-Anwendung ist.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL bei Erfolg; andernfalls 0.

### <a name="remarks"></a>Hinweise

Bei der Standardimplementierung wird keine Aktion ausgeführt. Überschreiben Sie diese Funktion, um führen spezielle Verarbeitung erforderlich, wenn die Schiebeleisten-Steuerelemente erstellt werden.

##  <a name="repositionframe"></a>  COleIPFrameWnd::RepositionFrame

Das Framework Ruft die `RepositionFrame` Member-Funktion zum Erstellen des Layouts für Schiebeleisten-Steuerelemente und das Bearbeitungsfenster des direktes neu positionieren, damit es sichtbar ist.

```
virtual void RepositionFrame(
    LPCRECT lpPosRect,
    LPCRECT lpClipRect);
```

### <a name="parameters"></a>Parameter

*lpPosRect*<br/>
Zeiger auf eine `RECT` Struktur oder ein `CRect` frame-Objekt, das direkt mit der aktuellen Position umgewandelt, in Pixel relativ zum Clientbereich.

*lpClipRect*<br/>
Zeiger auf eine `RECT` Struktur oder ein `CRect` Objekt, das direkt mit frame-Fensters aktuelle Auswahlrechteck Koordinaten in Pixel relativ zum Clientbereich.

### <a name="remarks"></a>Hinweise

Layout von Steuerleisten im Fenster "Container" unterscheidet sich von, die von einem nicht-OLE Framefenster ausgeführt. Das nicht-OLE-Rahmenfenster berechnet die Positionen des Schiebeleisten-Steuerelemente und andere Objekte von einer bestimmten Rahmenfenster-Größe, wie in einem Aufruf von [CFrameWnd::RecalcLayout](../../mfc/reference/cframewnd-class.md#recalclayout). Der Clientbereich ist was übrig bleibt, nachdem der Speicherplatz für Schiebeleisten-Steuerelemente und andere Objekte subtrahiert wird. Ein `COleIPFrameWnd` Fenster positioniert auf der anderen Seite Symbolleisten in Übereinstimmung mit einem bestimmten Clientbereich. Das heißt, `CFrameWnd::RecalcLayout` "von außen," funktioniert, während `COleIPFrameWnd::RepositionFrame` funktioniert "von innen nach außen."

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel HIERSVR](../../visual-cpp-samples.md)<br/>
[CFrameWnd-Klasse](../../mfc/reference/cframewnd-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CFrameWnd-Klasse](../../mfc/reference/cframewnd-class.md)
