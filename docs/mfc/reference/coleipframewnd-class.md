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
ms.openlocfilehash: 483998529b83d9b28c6ab1b219c4f5288dbd8ec7
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69503835"
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
|[COleIPFrameWnd::OnCreateControlBars](#oncreatecontrolbars)|Wird von Framework aufgerufen, wenn ein Element für die direkte Bearbeitung aktiviert wird.|
|[COleIPFrameWnd::RepositionFrame](#repositionframe)|Wird von Framework aufgerufen, um das direkte Bearbeitungsfenster neu zu positionieren.|

## <a name="remarks"></a>Hinweise

Diese Klasse erstellt und positioniert Steuer leisten im Dokument Fenster der Containeranwendung. Außerdem werden von einem eingebetteten [COleResizeBar](../../mfc/reference/coleresizebar-class.md) -Objekt generierte Benachrichtigungen verarbeitet, wenn der Benutzer die Größe des Fensters für die direkte Bearbeitung ändert.

Weitere Informationen zur Verwendung von `COleIPFrameWnd`finden Sie im Artikel [Activation (Aktivierung](../../mfc/activation-cpp.md)).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`COleIPFrameWnd`

## <a name="requirements"></a>Anforderungen

**Header:** Afxole. h

##  <a name="coleipframewnd"></a>COleIPFrameWnd:: COleIPFrameWnd

Erstellt ein `COleIPFrameWnd` -Objekt und initialisiert seine direkten Zustandsinformationen, die in einer Struktur des Typs oleinplaceframeinfo gespeichert werden.

```
COleIPFrameWnd();
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [oleinplaceframeinfo](/windows/win32/api/oleidl/ns-oleidl-oifi) in der Windows SDK.

##  <a name="oncreatecontrolbars"></a>COleIPFrameWnd:: onkreatecontrolbars

Das Framework ruft die `OnCreateControlBars` -Funktion auf, wenn ein Element für die direkte Bearbeitung aktiviert wird.

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
Zeiger auf das Rahmen Fenster der Containeranwendung.

*pWndDoc*<br/>
Zeiger auf das Fenster auf Dokument Ebene des Containers. Kann NULL sein, wenn der Container eine SDI-Anwendung ist.

### <a name="return-value"></a>Rückgabewert

Nicht NULL bei Erfolg; andernfalls 0.

### <a name="remarks"></a>Hinweise

Bei der Standardimplementierung wird keine Aktion ausgeführt. Überschreiben Sie diese Funktion, um besondere Verarbeitungsschritte auszuführen, die beim Erstellen von Steuer leisten erforderlich sind.

##  <a name="repositionframe"></a>COleIPFrameWnd:: repositionframe

Das Framework ruft die `RepositionFrame` Member-Funktion auf, um Steuer leisten anzuordnen und das direkte Bearbeitungsfenster neu zu positionieren, damit alles sichtbar ist.

```
virtual void RepositionFrame(
    LPCRECT lpPosRect,
    LPCRECT lpClipRect);
```

### <a name="parameters"></a>Parameter

*lpPosRect*<br/>
Ein Zeiger auf `RECT` eine-Struktur `CRect` oder ein-Objekt, das die aktuellen Positionskoordinaten des direkten Frame Fensters in Pixel relativ zum Client Bereich enthält.

*lpClipRect*<br/>
Ein Zeiger auf `RECT` eine-Struktur `CRect` oder ein-Objekt, das die aktuellen Clipping-Rechteck-Koordinaten des direkten Frame Fensters in Pixel relativ zum Client Bereich enthält.

### <a name="remarks"></a>Hinweise

Das Layout der Steuer leisten im Containerfenster unterscheidet sich von dem, das von einem nicht-OLE-Rahmen Fenster ausgeführt wird. Das nicht-OLE-Rahmen Fenster berechnet die Positionen von Steuer leisten und anderen Objekten aus einer angegebenen Rahmen Fenstergröße, wie in einem [CFrameWnd::](../../mfc/reference/cframewnd-class.md#recalclayout)neues. Der Client Bereich bleibt, nachdem der Speicherplatz für Steuer leisten und andere Objekte subtrahiert wurden. Ein `COleIPFrameWnd` Fenster positioniert auf der anderen Seite Symbolleisten in Übereinstimmung mit einem bestimmten Client Bereich. Anders ausgedrückt: `CFrameWnd::RecalcLayout` funktioniert "von außen nach außen", während `COleIPFrameWnd::RepositionFrame` "von innen nach außen" funktioniert.

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel Hierarchien](../../overview/visual-cpp-samples.md)<br/>
[CFrameWnd-Klasse](../../mfc/reference/cframewnd-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CFrameWnd-Klasse](../../mfc/reference/cframewnd-class.md)
