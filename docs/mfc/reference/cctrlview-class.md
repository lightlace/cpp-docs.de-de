---
title: Cctrlview-Klasse
ms.date: 11/04/2016
f1_keywords:
- CCtrlView
- AFXWIN/CCtrlView
- AFXWIN/CCtrlView::CCtrlView
- AFXWIN/CCtrlView::OnDraw
- AFXWIN/CCtrlView::PreCreateWindow
- AFXWIN/CCtrlView::m_dwDefaultStyle
- AFXWIN/CCtrlView::m_strClass
helpviewer_keywords:
- CCtrlView [MFC], CCtrlView
- CCtrlView [MFC], OnDraw
- CCtrlView [MFC], PreCreateWindow
- CCtrlView [MFC], m_dwDefaultStyle
- CCtrlView [MFC], m_strClass
ms.assetid: ff488596-1e71-451f-8fec-b0831a7b44e0
ms.openlocfilehash: 334f139b81afeb06d57cbd128abe9e413b1fd0e7
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507152"
---
# <a name="cctrlview-class"></a>Cctrlview-Klasse

Passt die Dokument-/Ansichtarchitektur den allgemeinen Steuerelemente an, die von Windows 98 und Windows NT-Versionen 3,51 (und höher) unterstützt werden.

## <a name="syntax"></a>Syntax

```
class CCtrlView : public CView
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CCtrlView::CCtrlView](#cctrlview)|Erstellt ein `CCtrlView`-Objekt.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CCtrlView::OnDraw](#ondraw)|Wird von Framework aufgerufen, um mit dem angegebenen Gerätekontext zu zeichnen.|
|[CCtrlView::PreCreateWindow](#precreatewindow)|Wird vor der Erstellung des an diesem `CCtrlView`-Objekt angefügten Windows-Fensters aufgerufen.|

### <a name="protected-data-members"></a>Geschützte Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CCtrlView::m_dwDefaultStyle](#m_dwdefaultstyle)|Enthält den Standardstil für die Ansichts Klasse.|
|[Cctrlview:: m_strClass](#m_strclass)|Enthält den Namen der Windows-Klasse für die Ansichts Klasse.|

## <a name="remarks"></a>Hinweise

Die Klasse `CCtrlView` und ihre Ableitungen, [CEditView](../../mfc/reference/ceditview-class.md), [CListView](../../mfc/reference/clistview-class.md), [CTreeView](../../mfc/reference/ctreeview-class.md)und [CRichEditView](../../mfc/reference/cricheditview-class.md), passen die Dokument-/Ansichtsarchitektur an die neuen allgemeinen Steuerelemente an, die von Windows 95/98 und Windows NT Version 3,51 unterstützt werden. und höher. Weitere Informationen zur Dokument-/Ansichtsarchitektur finden Sie unter [Dokument](../../mfc/document-view-architecture.md)-/Ansichtarchitektur.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

`CCtrlView`

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="cctrlview"></a>Cctrlview:: cctrlview

Erstellt ein `CCtrlView`-Objekt.

```
CCtrlView(
    LPCTSTR lpszClass,
    DWORD dwStyle);
```

### <a name="parameters"></a>Parameter

*lpszClass*<br/>
Der Name der Windows-Klasse der Ansichts Klasse.

*dwStyle*<br/>
Stil der Ansichts Klasse.

### <a name="remarks"></a>Hinweise

Das Framework ruft den Konstruktor auf, wenn ein neues Rahmen Fenster erstellt oder ein Fenster geteilt wird. Überschreiben Sie [CView:: OnInitialUpdate](../../mfc/reference/cview-class.md#oninitialupdate) , um die Sicht zu initialisieren, nachdem das Dokument angefügt wurde. Rufen Sie [CWnd:: Create](../../mfc/reference/cwnd-class.md#create) oder [CWnd:: kreateex](../../mfc/reference/cwnd-class.md#createex) auf, um das Windows-Objekt zu erstellen.

##  <a name="m_strclass"></a>Cctrlview:: m_strClass

Enthält den Namen der Windows-Klasse für die Ansichts Klasse.

```
CString m_strClass;
```

##  <a name="m_dwdefaultstyle"></a>Cctrlview:: m_dwDefaultStyle

Enthält den Standardstil für die Ansichts Klasse.

```
DWORD m_dwDefaultStyle;
```

### <a name="remarks"></a>Hinweise

Dieser Stil wird angewendet, wenn ein Fenster erstellt wird.

##  <a name="ondraw"></a>Cctrlview:: OnDraw

Wird von Framework aufgerufen, um den Inhalt des `CCtrlView` -Objekts mit dem angegebenen Gerätekontext zu zeichnen.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
Ein Zeiger auf den Gerätekontext, in dem die Zeichnung auftritt.

### <a name="remarks"></a>Hinweise

`OnDraw`wird in der Regel für die Bildschirm Anzeige aufgerufen, wobei ein von *PDC*angegebener Bildschirm Kontext übergeben wird.

##  <a name="precreatewindow"></a>Cctrlview::P neu erstellen

Wird vor der Erstellung des an diesem `CWnd`-Objekt angefügten Windows-Fensters aufgerufen.

```
virtual BOOL PreCreateWindow(CREATESTRUCT& cs);
```

### <a name="parameters"></a>Parameter

*cs*<br/>
Eine [foratestruct](/windows/win32/api/winuser/ns-winuser-createstructw) -Struktur.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Fenster Erstellung fortgesetzt werden soll. 0, um einen Erstellungs Fehler anzugeben.

### <a name="remarks"></a>Hinweise

Diese Funktion niemals direkt aufzurufen.

Die Standard Implementierung dieser Funktion prüft auf einen null-Fenster Klassennamen und ersetzt einen entsprechenden Standardwert. Überschreiben Sie diese Member-Funktion `CREATESTRUCT` , um die Struktur vor dem Erstellen des Fensters zu ändern.

Jede von `CCtrlView` abgeleitete Klasse fügt Ihrer außer Kraft Setzung von `PreCreateWindow`eine eigene Funktionalität hinzu. Entwurfs bedingt werden diese Ableitungen von `PreCreateWindow` nicht dokumentiert. Wenn Sie die für jede Klasse geeigneten Stile und die Abhängigkeiten zwischen den Stilen ermitteln möchten, können Sie den MFC-Quellcode für die Basisklasse Ihrer Anwendung untersuchen. Wenn Sie sich für das `PreCreateWindow`überschreiben entscheiden, können Sie bestimmen, ob die in der Basisklasse Ihrer Anwendung verwendeten Stile die erforderliche Funktionalität bereitstellen, indem Sie die Informationen verwenden, die aus dem MFC-Quellcode gesammelt wurden.

Weitere Informationen zum Ändern von Fenster Stilen finden Sie unter [Ändern der Stile eines Fensters, das von MFC erstellt wurde](../../mfc/changing-the-styles-of-a-window-created-by-mfc.md).

## <a name="see-also"></a>Siehe auch

[CView-Klasse](../../mfc/reference/cview-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CTreeView-Klasse](../../mfc/reference/ctreeview-class.md)<br/>
[CListView-Klasse](../../mfc/reference/clistview-class.md)<br/>
[CRichEditView-Klasse](../../mfc/reference/cricheditview-class.md)
