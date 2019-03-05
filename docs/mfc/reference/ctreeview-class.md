---
title: CTreeView-Klasse
ms.date: 11/04/2016
f1_keywords:
- CTreeView
- AFXCVIEW/CTreeView
- AFXCVIEW/CTreeView::CTreeView
- AFXCVIEW/CTreeView::GetTreeCtrl
helpviewer_keywords:
- CTreeView [MFC], CTreeView
- CTreeView [MFC], GetTreeCtrl
ms.assetid: 5df583a6-d69f-42ca-9d8d-57e04558afff
ms.openlocfilehash: fec8379a3944d981672754274f50dd4e60f71b61
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57288869"
---
# <a name="ctreeview-class"></a>CTreeView-Klasse

Vereinfacht die Verwendung des Strukturansicht-Steuerelements und der [CTreeCtrl](../../mfc/reference/ctreectrl-class.md), die Klasse, Struktur-steuerelemenfunktionalität per MFC Dokument-/ Ansichtsarchitektur kapselt.

## <a name="syntax"></a>Syntax

```
class CTreeView : public CCtrlView
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CTreeView::CTreeView](#ctreeview)|Erstellt ein `CTreeView`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CTreeView::GetTreeCtrl](#gettreectrl)|Gibt zurück, das Strukturansicht-Steuerelement, das der Ansicht zugeordnet.|

## <a name="remarks"></a>Hinweise

Weitere Informationen zu dieser Architektur, finden Sie unter der Übersicht für die [CView](../../mfc/reference/cview-class.md) -Klasse und die Querverweise genannten vorhanden.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CCtrlView](../../mfc/reference/cctrlview-class.md)

`CTreeView`

## <a name="requirements"></a>Anforderungen

**Header:** afxcview.h

##  <a name="ctreeview"></a>  CTreeView::CTreeView

Erstellt ein `CTreeView`-Objekt.

```
CTreeView();
```

##  <a name="gettreectrl"></a>  CTreeView::GetTreeCtrl

Gibt einen Verweis auf die Strukturansicht-Steuerelement, das der Ansicht zugeordnet.

```
CTreeCtrl& GetTreeCtrl() const;
```

## <a name="see-also"></a>Siehe auch

[CCtrlView-Klasse](../../mfc/reference/cctrlview-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CView-Klasse](../../mfc/reference/cview-class.md)<br/>
[CCtrlView-Klasse](../../mfc/reference/cctrlview-class.md)<br/>
[CTreeCtrl-Klasse](../../mfc/reference/ctreectrl-class.md)
