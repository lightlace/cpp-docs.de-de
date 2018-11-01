---
title: CMFCDragFrameImpl-Klasse
ms.date: 10/18/2018
f1_keywords:
- CMFCDragFrameImpl
helpviewer_keywords:
- CMFCDragFrameImpl class [MFC]
ms.assetid: 500cd824-8188-43c2-8754-b7bb46b5648a
ms.openlocfilehash: 2769b52e03d8d3de14fdbf431279dd9226323b0c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50640699"
---
# <a name="cmfcdragframeimpl-class"></a>CMFCDragFrameImpl-Klasse

Die `CMFCDragFrameImpl` Klasse zeichnet das ziehrechteck, das angezeigt wird, wenn der Benutzer einen Bereich im standarddockmodus zieht.
Weitere Informationen finden Sie im Quellcode der **VC\\Atlmfc\\Src\\Mfc** Ordner von Visual Studio-Installation.

## <a name="syntax"></a>Syntax

```
class CMFCDragFrameImpl
```

## <a name="remarks"></a>Hinweise

Ein Objekt dieser Klasse wird in den einzelnen eingebettet [CPane-Klasse](../../mfc/reference/cpane-class.md) Objekt. Daher wird jeder Bereich, der verwendet die `CanFloat` Methode zeigt ein Rechteck aus, wenn der Benutzer es zieht.

Sie können die Breite des Rechtecks ziehen Sie steuern, indem Sie mithilfe von [AFX_GLOBAL_DATA::m_nDragFrameThicknessFloat](afx-global-data-structure.md#m_ndragframethicknessfloat) und [AFX_GLOBAL_DATA::m_nDragFrameThicknessDock](afx-global-data-structure.md#m_ndragframethicknessdock).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CMFCDragFrameImpl](../../mfc/reference/cmfcdragframeimpl-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxdragframeimpl.h

##  <a name="enddrawdragframe"></a>  CMFCDragFrameImpl::EndDrawDragFrame

```
void EndDrawDragFrame(BOOL bClearInternalRects = TRUE);
```

### <a name="parameters"></a>Parameter

[in] *bClearInternalRects*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="init"></a>  CMFCDragFrameImpl::Init

```
void Init(CWnd* pDraggedWnd);
```

### <a name="parameters"></a>Parameter

[in] *pDraggedWnd*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="movedragframe"></a>  CMFCDragFrameImpl::MoveDragFrame

```
void MoveDragFrame(BOOL bForceMove = FALSE);
```

### <a name="parameters"></a>Parameter

[in] *bForceMove*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="placetabpredocking"></a>  CMFCDragFrameImpl::PlaceTabPreDocking

```
void PlaceTabPreDocking(
    CBaseTabbedPane* pTabbedBar,
    BOOL bFirstTime);

void PlaceTabPreDocking(CWnd* pCBarToPlaceOn);
```

### <a name="parameters"></a>Parameter

[in] *pTabbedBar*<br/>

[in] *bFirstTime*<br/>

[in] *pCBarToPlaceOn*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="removetabpredocking"></a>  CMFCDragFrameImpl::RemoveTabPreDocking

```
void RemoveTabPreDocking(CDockablePane* pOldTargetBar = NULL);
```

### <a name="parameters"></a>Parameter

[in] *pOldTargetBar*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="resetstate"></a>  CMFCDragFrameImpl::ResetState

```
void ResetState();
```

### <a name="remarks"></a>Hinweise

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CPane-Klasse](../../mfc/reference/cpane-class.md)