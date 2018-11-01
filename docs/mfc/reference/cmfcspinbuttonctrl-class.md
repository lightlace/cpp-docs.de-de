---
title: CMFCSpinButtonCtrl-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCSpinButtonCtrl
- AFXSPINBUTTONCTRL/CMFCSpinButtonCtrl
- AFXSPINBUTTONCTRL/CMFCSpinButtonCtrl::OnDraw
helpviewer_keywords:
- CMFCSpinButtonCtrl [MFC], OnDraw
ms.assetid: 8773f259-4d3f-4bca-a71c-09e0c71bc843
ms.openlocfilehash: ecc8a010b534515850752f7d83c9a9976f14ddfc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50567517"
---
# <a name="cmfcspinbuttonctrl-class"></a>CMFCSpinButtonCtrl-Klasse

Die `CMFCSpinButtonCtrl` -Klasse unterstützt einen visuellen Manager, der ein Drehfeldsteuerelement zeichnet.

## <a name="syntax"></a>Syntax

```
class CMFCSpinButtonCtrl : public CSpinButtonCtrl
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|`CMFCSpinButtonCtrl::CMFCSpinButtonCtrl`|Standardkonstruktor|
|`CMFCSpinButtonCtrl::~CMFCSpinButtonCtrl`|Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCSpinButtonCtrl::OnDraw](#ondraw)|Zeichnet die aktuelle Drehfeld-Steuerelement neu.|

## <a name="remarks"></a>Hinweise

Um einen visuellen Manager verwenden, die um in der Anwendung ein Drehfeld-Steuerelement zu zeichnen, ersetzen Sie alle Instanzen von der `CSpinButtonCtrl` -Klasse mit der `CMFCSpinButtonCtrl` Klasse.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird veranschaulicht, wie zum Erstellen eines Objekts von der `CMFCSpinButtonCtrl` Klasse, und verwenden dessen `Create` Methode.

[!code-cpp[NVC_MFC_RibbonApp#25](../../mfc/reference/codesnippet/cpp/cmfcspinbuttonctrl-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CSpinButtonCtrl](../../mfc/reference/cspinbuttonctrl-class.md)

[CMFCSpinButtonCtrl](../../mfc/reference/cmfcspinbuttonctrl-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxspinbuttonctrl.h

##  <a name="ondraw"></a>  CMFCSpinButtonCtrl::OnDraw

Zeichnet die aktuelle Drehfeld-Steuerelement neu.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
[in] Ein Zeiger auf einen Gerätekontext.

### <a name="remarks"></a>Hinweise

Das Framework Ruft die `CMFCSpinButtonCtrl::OnPaint` Methode zum Behandeln der [CWnd::OnPaint](../../mfc/reference/cwnd-class.md#onpaint) Nachricht und dass die Methode ruft wiederum diese `CMFCSpinButtonCtrl::OnDraw` Methode. Überschreiben Sie diese Methode, um anzupassen, wie das Framework die Drehfeldsteuerelement zeichnet.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCVisualManager-Klasse](../../mfc/reference/cmfcvisualmanager-class.md)
