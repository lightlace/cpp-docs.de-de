---
title: Cmscribbonlinkctrl-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonLinkCtrl
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::CMFCRibbonLinkCtrl
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::CopyFrom
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::GetCompactSize
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::GetLink
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::GetRegularSize
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::GetToolTipText
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::IsDrawTooltipImage
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::OnDraw
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::OnDrawMenuImage
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::OnMouseMove
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::OnSetIcon
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::OpenLink
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::SetLink
helpviewer_keywords:
- CMFCRibbonLinkCtrl [MFC], CMFCRibbonLinkCtrl
- CMFCRibbonLinkCtrl [MFC], CopyFrom
- CMFCRibbonLinkCtrl [MFC], GetCompactSize
- CMFCRibbonLinkCtrl [MFC], GetLink
- CMFCRibbonLinkCtrl [MFC], GetRegularSize
- CMFCRibbonLinkCtrl [MFC], GetToolTipText
- CMFCRibbonLinkCtrl [MFC], IsDrawTooltipImage
- CMFCRibbonLinkCtrl [MFC], OnDraw
- CMFCRibbonLinkCtrl [MFC], OnDrawMenuImage
- CMFCRibbonLinkCtrl [MFC], OnMouseMove
- CMFCRibbonLinkCtrl [MFC], OnSetIcon
- CMFCRibbonLinkCtrl [MFC], OpenLink
- CMFCRibbonLinkCtrl [MFC], SetLink
ms.assetid: 77ae1941-e0ab-4a9d-911e-1752d34c079b
ms.openlocfilehash: 12a83e45176f7fc6020da1f0d0ee5923ef0f466c
ms.sourcegitcommit: bd7ddc044f9083246614b602ef6a758775313214
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2019
ms.locfileid: "68866164"
---
# <a name="cmfcribbonlinkctrl-class"></a>Cmscribbonlinkctrl-Klasse

Implementiert einen Hyperlink, der auf einem Menüband positioniert wird. Wenn Sie den Hyperlink anklicken, wird eine Webseite geöffnet.
Weitere Informationen finden Sie im Quellcode, der sich im **Ordner\\VC atlmfc\\\\src MFC** Ihrer Visual Studio-Installation befindet.

## <a name="syntax"></a>Syntax

```
class CMFCRibbonLinkCtrl : public CMFCRibbonButton
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMFCRibbonLinkCtrl::CMFCRibbonLinkCtrl](#cmfcribbonlinkctrl)|Erstellt und initialisiert ein `CMFCRibbonLinkCtrl`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCRibbonLinkCtrl::CopyFrom](#copyfrom)|(Überschreibt `CMFCRibbonButton::CopyFrom`.)|
|[CMFCRibbonLinkCtrl::GetCompactSize](#getcompactsize)|(Überschreibt [cmfcribbonbutton:: getcompactsize](../../mfc/reference/cmfcribbonbutton-class.md#getcompactsize).)|
|[CMFCRibbonLinkCtrl::GetLink](#getlink)|Gibt den Wert des Links zurück.|
|[CMFCRibbonLinkCtrl::GetRegularSize](#getregularsize)|(Überschreibt [cmfcribbonbutton:: getregularsize](../../mfc/reference/cmfcribbonbutton-class.md#getregularsize).)|
|[CMFCRibbonLinkCtrl::GetToolTipText](#gettooltiptext)|(Überschreibt [cmfcribbonbutton:: GetToolTipText](../../mfc/reference/cmfcribbonbutton-class.md#gettooltiptext).)|
|[CMFCRibbonLinkCtrl::IsDrawTooltipImage](#isdrawtooltipimage)|(Überschreibt `CMFCRibbonButton::IsDrawTooltipImage`.)|
|[CMFCRibbonLinkCtrl::OnDraw](#ondraw)|(Überschreibt [cmfcribbonbutton:: OnDraw](../../mfc/reference/cmfcribbonbutton-class.md#ondraw).)|
|[CMFCRibbonLinkCtrl::OnDrawMenuImage](#ondrawmenuimage)|(Überschreibt [CMF cribbonbaseelement:: ondrawmenuimage](../../mfc/reference/cmfcribbonbaseelement-class.md#ondrawmenuimage).)|
|[CMFCRibbonLinkCtrl::OnMouseMove](#onmousemove)|(Überschreibt `CMFCRibbonButton::OnMouseMove`.)|
|[CMFCRibbonLinkCtrl::OnSetIcon](#onseticon)||
|[CMFCRibbonLinkCtrl::OpenLink](#openlink)|Öffnet die im Link angegebene Webseite.|
|[CMFCRibbonLinkCtrl::SetLink](#setlink)|Legt den Wert des Links fest.|

## <a name="remarks"></a>Hinweise

Nachdem Sie einen Link erstellt haben, fügen Sie ihn einem Panel hinzu, indem Sie [CMFCRibbonPanel:: Add](../../mfc/reference/cmfcribbonpanel-class.md#add)aufrufen.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)\
└&nbsp;[CMF cribbonbaseelement](../../mfc/reference/cmfcribbonbaseelement-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[Cmfcribbonbutton](../../mfc/reference/cmfcribbonbutton-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CMF cribbonlinkctrl](../../mfc/reference/cmfcribbonlinkctrl-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxRibbonLinkCtrl.h

##  <a name="cmfcribbonlinkctrl"></a>CMF cribbonlinkctrl:: CMF-bbonlinkctrl

Erstellt und initialisiert ein [CMF cribbonlinkctrl](../../mfc/reference/cmfcribbonlinkctrl-class.md) -Objekt.

```
CMFCRibbonLinkCtrl(
    UINT nID,
    LPCTSTR lpszText,
    LPCTSTR lpszLink);
```

### <a name="parameters"></a>Parameter

*nID*<br/>
in Gibt die Befehls-ID des Befehls an, der ausgeführt wird, wenn auf das Link Steuerelement geklickt wird.

*lpszText*<br/>
in Gibt die Bezeichnung an, die im Link Steuerelement angezeigt werden soll.

*lpszLink*<br/>
in Gibt den Link an, der dem Link Steuerelement zugeordnet ist.

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie der Konstruktor der `CMFCRibbonLinkCtrl` -Klasse verwendet wird. Dieser Code Ausschnitt ist Teil des Menübands [Gadgets Sample](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_RibbonGadgets#1](../../mfc/reference/codesnippet/cpp/cmfcribbonlinkctrl-class_1.cpp)]

##  <a name="copyfrom"></a>CMF cribbonlinkctrl:: CopyFrom

```
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```

### <a name="parameters"></a>Parameter

[in] *src*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="getcompactsize"></a>CMF cribbonlinkctrl:: getcompactsize

```
virtual CSize GetCompactSize(CDC* pDC);
```

### <a name="parameters"></a>Parameter

[in] *pDC*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="getlink"></a>CMF cribbonlinkctrl:: getlink

Gibt den Wert des Links zurück.

```
LPCTSTR GetLink() const;
```

### <a name="return-value"></a>Rückgabewert

Der aktuelle Wert des Links.

### <a name="remarks"></a>Hinweise

##  <a name="getregularsize"></a>CMF cribbonlinkctrl:: getregularsize

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>Parameter

[in] *pDC*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="gettooltiptext"></a>CMF cribbonlinkctrl:: GetToolTipText

```
virtual CString GetToolTipText() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="ondrawmenuimage"></a>CMF cribbonlinkctrl:: ondrawmenuimage

```
virtual BOOL OnDrawMenuImage(CDC*, CRect);
```

### <a name="parameters"></a>Parameter

in *CDC&#42;*<br/>
in *CRect*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="isdrawtooltipimage"></a>Cmocribbonlinkctrl:: isdrawtooltipimage

```
virtual BOOL IsDrawTooltipImage() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="ondraw"></a>CMF cribbonlinkctrl:: OnDraw

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parameter

[in] *pDC*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="onmousemove"></a>CMF cribbonlinkctrl:: onmouonmove

```
virtual void OnMouseMove(CPoint point);
```

### <a name="parameters"></a>Parameter

in *Punkt*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="onseticon"></a>CMF cribbonlinkctrl:: ononticon

```
virtual void OnSetIcon();
```

### <a name="remarks"></a>Hinweise

##  <a name="openlink"></a>CMF cribbonlinkctrl:: OpenLink

Öffnet die im Link angegebene Webseite.

```
BOOL OpenLink();
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die zugehörige Webseite erfolgreich geöffnet wurde. andernfalls false.

### <a name="remarks"></a>Hinweise

Öffnet eine Webseite mit dem Hyperlink, der dem `CMFCRibbonLinkCtrl` Objekt zugeordnet ist.

##  <a name="setlink"></a>CMF cribbonlinkctrl:: SetLink

Legt den Wert des Links fest.

```
void SetLink(LPCTSTR lpszLink);
```

### <a name="parameters"></a>Parameter

*lpszLink*<br/>
in Gibt den Hyperlink-Text an.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton-Klasse](../../mfc/reference/cmfcribbonbutton-class.md)
