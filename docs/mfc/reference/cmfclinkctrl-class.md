---
title: CMFCLinkCtrl-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCLinkCtrl
- AFXLINKCTRL/CMFCLinkCtrl
- AFXLINKCTRL/CMFCLinkCtrl::SetURL
- AFXLINKCTRL/CMFCLinkCtrl::SetURLPrefix
- AFXLINKCTRL/CMFCLinkCtrl::SizeToContent
- AFXLINKCTRL/CMFCLinkCtrl::OnDrawFocusRect
helpviewer_keywords:
- CMFCLinkCtrl [MFC], SetURL
- CMFCLinkCtrl [MFC], SetURLPrefix
- CMFCLinkCtrl [MFC], SizeToContent
- CMFCLinkCtrl [MFC], OnDrawFocusRect
ms.assetid: 80f3874d-7cc8-410e-9ff1-62a225f5034b
ms.openlocfilehash: a4324fad7668907600cbaebeb5c9de4ad0e7c1e4
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57302717"
---
# <a name="cmfclinkctrl-class"></a>CMFCLinkCtrl-Klasse

Die `CMFCLinkCtrl` Klasse zeigt eine Schaltfläche als Hyperlink an und ruft das Ziel des Links auf, wenn die Schaltfläche geklickt wird.

## <a name="syntax"></a>Syntax

```
class CMFCLinkCtrl : public CMFCButton
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCLinkCtrl::SetURL](#seturl)|Zeigt eine angegebene URL als Text der Schaltfläche an.|
|[CMFCLinkCtrl::SetURLPrefix](#seturlprefix)|Legt das implizite-Protokoll (z. B. "http:") der URL.|
|[CMFCLinkCtrl::SizeToContent](#sizetocontent)|Ändert die Schaltfläche, um den Text der Schaltfläche oder eine Bitmap enthält.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCLinkCtrl::OnDrawFocusRect](#ondrawfocusrect)|Wird vom Framework aufgerufen, bevor das Fokusrechteck der Schaltfläche gezeichnet wird.|

## <a name="remarks"></a>Hinweise

Beim Klicken auf eine Schaltfläche, die von abgeleitet ist die `CMFCLinkCtrl` -Klasse, die vom Framework übergeben der URL für die Schaltfläche als Parameter an die `ShellExecute` Methode. Die `ShellExecute` -Methode öffnet das Ziel der URL.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie die Größe des eine `CMFCLinkCtrl` -Objekt, und wie Sie eine Url und QuickInfo im Festlegen einer `CMFCLinkCtrl` Objekt. In diesem Beispiel ist Teil der [Beispiel neue Steuerelemente](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_NewControls#9](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#10](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCButton](../../mfc/reference/cmfcbutton-class.md)

[CMFCLinkCtrl](../../mfc/reference/cmfclinkctrl-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxlinkctrl.h

##  <a name="ondrawfocusrect"></a>  CMFCLinkCtrl::OnDrawFocusRect

Wird vom Framework aufgerufen, bevor das Fokusrechteck der Schaltfläche gezeichnet wird.

```
virtual void OnDrawFocusRect(
    CDC* pDC,
    const CRect& rectClient);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
[in] Ein Zeiger auf einen Gerätekontext.

*rectClient*<br/>
[in] Ein Rechteck, das die Link-Steuerelement umschließt.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode, wenn Sie Ihren eigenen Code zu verwenden, um die Schaltfläche "das Fokusrechteck gezeichnet werden soll.

##  <a name="seturl"></a>  CMFCLinkCtrl::SetURL

Zeigt eine angegebene URL als Text der Schaltfläche an.

```
void SetURL(LPCTSTR lpszURL);
```

### <a name="parameters"></a>Parameter

*lpszURL*<br/>
[in] Der Text der Schaltfläche angezeigt.

### <a name="remarks"></a>Hinweise

##  <a name="seturlprefix"></a>  CMFCLinkCtrl::SetURLPrefix

Legt das implizite-Protokoll (z. B. "http:") der URL.

```
void SetURLPrefix(LPCTSTR lpszPrefix);
```

### <a name="parameters"></a>Parameter

*lpszPrefix*<br/>
[in] Das Präfix des URL-Protokoll.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode, um das URL-Präfix festzulegen. Das Präfix wird nicht auf die Schaltfläche "Gesicht angezeigt, aber Sie können es an die URL Ziel suchen.

##  <a name="sizetocontent"></a>  CMFCLinkCtrl::SizeToContent

Ändert die Schaltfläche, um den Text der Schaltfläche oder eine Bitmap enthält.

```
virtual CSize SizeToContent(
    BOOL bVCenter=FALSE,
    BOOL bHCenter=FALSE);
```

### <a name="parameters"></a>Parameter

*bVCenter*<br/>
[in] True, um Text und der Schaltfläche Bitmap vertikal zwischen dem oberen und den unteren Rand des Steuerelements Links zentriert. andernfalls "false". Der Standardwert ist "false".

*bHCenter*<br/>
[in] True, um den Text der Schaltfläche und die Bitmap horizontal zwischen der linken und rechten Seite des Linksteuerelements center. andernfalls "false". Der Standardwert ist "false".

### <a name="return-value"></a>Rückgabewert

Ein [CSize](../../atl-mfc-shared/reference/csize-class.md) Objekt, das die neue Größe des Linksteuerelements enthält.

### <a name="remarks"></a>Hinweise

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CLinkCtrl-Klasse](../../mfc/reference/clinkctrl-class.md)<br/>
[CMFCButton-Klasse](../../mfc/reference/cmfcbutton-class.md)
