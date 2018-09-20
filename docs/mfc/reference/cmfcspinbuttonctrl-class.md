---
title: CMFCSpinButtonCtrl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCSpinButtonCtrl
- AFXSPINBUTTONCTRL/CMFCSpinButtonCtrl
- AFXSPINBUTTONCTRL/CMFCSpinButtonCtrl::OnDraw
dev_langs:
- C++
helpviewer_keywords:
- CMFCSpinButtonCtrl [MFC], OnDraw
ms.assetid: 8773f259-4d3f-4bca-a71c-09e0c71bc843
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 756cdffc8f9f726e63b129f5f87a19eec01cd429
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46440016"
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
