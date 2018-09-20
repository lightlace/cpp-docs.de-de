---
title: CTreeView-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CTreeView
- AFXCVIEW/CTreeView
- AFXCVIEW/CTreeView::CTreeView
- AFXCVIEW/CTreeView::GetTreeCtrl
dev_langs:
- C++
helpviewer_keywords:
- CTreeView [MFC], CTreeView
- CTreeView [MFC], GetTreeCtrl
ms.assetid: 5df583a6-d69f-42ca-9d8d-57e04558afff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a760e567718ad7a485ebe469903c7cbd566daccc
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46375397"
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
