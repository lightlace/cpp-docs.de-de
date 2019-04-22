---
title: CListView-Klasse
ms.date: 11/04/2016
f1_keywords:
- CListView
- AFXCVIEW/CListView
- AFXCVIEW/CListView::CListView
- AFXCVIEW/CListView::GetListCtrl
- AFXCVIEW/CListView::RemoveImageList
helpviewer_keywords:
- CListView [MFC], CListView
- CListView [MFC], GetListCtrl
- CListView [MFC], RemoveImageList
ms.assetid: 7626bdb2-a1b8-4eab-b631-6743710a8432
ms.openlocfilehash: 698e37b2853a2ca3698ee0a426c8ded688c99c58
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58776621"
---
# <a name="clistview-class"></a>CListView-Klasse

Vereinfacht die Verwendung des Listensteuerelements und von [CListCtrl](../../mfc/reference/clistctrl-class.md), die Klasse, die Listensteuerelement-Funktionalität mit MFC Dokument-/ Ansichtsarchitektur kapselt.

## <a name="syntax"></a>Syntax

```
class CListView : public CCtrlView
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CListView::CListView](#clistview)|Erstellt ein `CListView`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CListView::GetListCtrl](#getlistctrl)|Gibt zurück, das Listensteuerelement, das der Ansicht zugeordnet.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CListView::RemoveImageList](#removeimagelist)|Entfernt die angegebene Bild-Liste in der Listenansicht angezeigt.|

## <a name="remarks"></a>Hinweise

Weitere Informationen zu dieser Architektur, finden Sie unter der Übersicht für die [CView](../../mfc/reference/cview-class.md) -Klasse und die Querverweise genannten vorhanden.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CCtrlView](../../mfc/reference/cctrlview-class.md)

`CListView`

## <a name="requirements"></a>Anforderungen

**Header:** afxcview.h

##  <a name="clistview"></a>  CListView::CListView

Erstellt ein `CListView`-Objekt.

```
CListView();
```

##  <a name="getlistctrl"></a>  CListView::GetListCtrl

Rufen Sie diese Memberfunktion zum Abrufen eines Verweises auf das Listensteuerelement, das der Ansicht zugeordnet.

```
CListCtrl& GetListCtrl() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das Listensteuerelement, das der Ansicht zugeordnet.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCListView#7](../../atl/reference/codesnippet/cpp/clistview-class_1.cpp)]

##  <a name="removeimagelist"></a>  CListView::RemoveImageList

Entfernt die angegebene Bild-Liste in der Listenansicht angezeigt.

```
void RemoveImageList(int nImageList);
```

### <a name="parameters"></a>Parameter

*nImageList*<br/>
Der nullbasierte Index des zu entfernenden Bildes.

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel ROWLIST](../../overview/visual-cpp-samples.md)<br/>
[CCtrlView-Klasse](../../mfc/reference/cctrlview-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CCtrlView-Klasse](../../mfc/reference/cctrlview-class.md)
