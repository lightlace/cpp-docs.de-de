---
title: CMFCCaptionButton-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetHit
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetIconID
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetRect
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetSize
- AFXCAPTIONBUTTON/CMFCCaptionButton::IsMiniFrameButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::Move
- AFXCAPTIONBUTTON/CMFCCaptionButton::OnDraw
- AFXCAPTIONBUTTON/CMFCCaptionButton::SetMiniFrameButton
dev_langs:
- C++
helpviewer_keywords:
- CMFCCaptionButton [MFC], CMFCCaptionButton
- CMFCCaptionButton [MFC], GetHit
- CMFCCaptionButton [MFC], GetIconID
- CMFCCaptionButton [MFC], GetRect
- CMFCCaptionButton [MFC], GetSize
- CMFCCaptionButton [MFC], IsMiniFrameButton
- CMFCCaptionButton [MFC], Move
- CMFCCaptionButton [MFC], OnDraw
- CMFCCaptionButton [MFC], SetMiniFrameButton
ms.assetid: c5774b38-c0dd-414a-9ede-3b2f78f233ec
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8d6b1363dd77d4fd052a530a60b2e462e15a2291
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50074435"
---
# <a name="cmfccaptionbutton-class"></a>CMFCCaptionButton-Klasse

Die `CMFCCaptionButton` -Klasse implementiert eine Schaltfläche, die auf der Titelleiste für einen andockbaren Bereich oder ein Minirahmenfenster angezeigt wird. In der Regel erstellt das Framework Beschriftungsschaltflächen automatisch.

## <a name="syntax"></a>Syntax

```
class CMFCCaptionButton : public CObject
```

## <a name="members"></a>Member

### <a name="constructors"></a>Konstruktoren

|name|Beschreibung|
|----------|-----------------|
|[CMFCCaptionButton::CMFCCaptionButton](#cmfccaptionbutton)|Erstellt ein CMFCCaptionButton-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCCaptionButton::GetHit](#gethit)|Gibt zurück, den Befehl, der durch die Schaltfläche dargestellt.|
|[CMFCCaptionButton::GetIconID](#geticonid)|Gibt die Image-ID der Schaltfläche zugeordnet.|
|[CMFCCaptionButton::GetRect](#getrect)|Gibt das Rechteck, das durch die Schaltfläche mit den belegt wird.|
|[CMFCCaptionButton::GetSize](#getsize)|Gibt die Breite und Höhe der Schaltfläche.|
|[CMFCCaptionButton::IsMiniFrameButton](#isminiframebutton)|Gibt an, ob die Höhe der Titelleiste auf die kleine Größe festgelegt ist.|
|[CMFCCaptionButton::Move](#move)|Legt fest, den Schaltfläche zeichnen Speicherort und den Status des Fensters angezeigt.|
|[CMFCCaptionButton::OnDraw](#ondraw)|Zeichnet die Titelleisten-Schaltfläche.|
|[CMFCCaptionButton::SetMiniFrameButton](#setminiframebutton)|Legt fest, die kleine Größe der Titelleiste angezeigt.|

## <a name="remarks"></a>Hinweise

Sie können eine Klasse von ableiten [CPaneFrameWnd-Klasse](../../mfc/reference/cpaneframewnd-class.md) und verwenden Sie die geschützte Methode `AddButton`, um ein Mini-Rahmenfenster Titelleistenschaltflächen hinzuzufügen.

CPaneFrameWnd.h definiert die Befehls-IDs für zwei Arten von Schaltflächen mit Beschriftung:

- AFX_CAPTION_BTN_PIN, der eine Schaltfläche "anheften" angezeigt, wenn die andockbaren Bereich im Modus "automatisch ausblenden" unterstützt.

- AFX_CAPTION_BTN_CLOSE, die zeigt eine **schließen** -Schaltfläche, wenn der Bereich geschlossen oder ausgeblendet werden kann.

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht das Erstellen einer `CMFCCaptionButton` Objekt aus, und legen Sie die kleine Größe der Titelleiste angezeigt.

[!code-cpp[NVC_MFC_RibbonApp#43](../../mfc/reference/codesnippet/cpp/cmfccaptionbutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CMFCCaptionButton](../../mfc/reference/cmfccaptionbutton-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxcaptionbutton.h

##  <a name="cmfccaptionbutton"></a>  CMFCCaptionButton::CMFCCaptionButton

Erstellt ein `CMFCCaptionButton`-Objekt.

```
CMFCCaptionButton();

CMFCCaptionButton(
    UINT nHit,
    BOOL bLeftAlign = FALSE);
```

### <a name="parameters"></a>Parameter

*nHit*<br/>
[in] Der Befehl, der der Schaltfläche zugeordnet wird.

*bLeftAlign*<br/>
[in] Gibt an, ob die Schaltfläche mit der links ausgerichtet ist.

Die folgende Tabelle enthält die möglichen Werte für die *nHit* Parameter.

|Wert|Befehl|
|-----------|-------------|
|AFX_HTCLOSE|Schaltfläche "Schließen".|
|HTMINBUTTON|Minimieren Sie Schaltfläche zum.|
|HTMAXBUTTON|Maximieren Sie-Schaltfläche.|
|AFX_HTLEFTBUTTON|-Links-Taste.|
|AFX_HTRIGHTBUTTON|Pfeil nach rechts aus.|
|AFX_HTMENU|Nach-unten-Menü-Taste.|
|HTNOWHERE|Der Standardwert; stellt kein Befehl.|

### <a name="remarks"></a>Hinweise

Standardmäßig werden die Titelleistenschaltflächen nicht mit einem Befehl verknüpft.

Titelleistenschaltflächen werden entweder auf Links oder rechts ausgerichtet.

##  <a name="gethit"></a>  CMFCCaptionButton::GetHit

Gibt zurück, den Befehl, der durch die Schaltfläche dargestellt.

```
UINT GetHit() const;
```

### <a name="return-value"></a>Rückgabewert

Der Befehl, der von der Schaltfläche dargestellt.

Die folgende Tabelle enthält die möglichen Rückgabewerte.

|Wert|Befehl|
|-----------|-------------|
|AFX_HTCLOSE|Schaltfläche "Schließen".|
|HTMINBUTTON|Minimieren Sie Schaltfläche zum.|
|HTMAXBUTTON|Maximieren Sie-Schaltfläche.|
|AFX_HTLEFTBUTTON|-Links-Taste.|
|AFX_HTRIGHTBUTTON|Pfeil nach rechts aus.|
|AFX_HTMENU|Nach-unten-Menü-Taste.|
|HTNOWHERE|Der Standardwert; stellt kein Befehl.|

##  <a name="geticonid"></a>  CMFCCaptionButton::GetIconID

Gibt die Image-ID der Schaltfläche zugeordnet.

```
virtual CMenuImages::IMAGES_IDS GetIconID(
    BOOL bHorz,
    BOOL bMaximized = FALSE) const;
```

### <a name="parameters"></a>Parameter

*bHorz*<br/>
[in] "True" für die linke bzw. rechte Pfeiltaste Image-IDs werden; "False" nach oben oder unten Pfeil Image-IDs.

*bMaximized*<br/>
[in] "True" für eine Image-ID maximieren; "False" für ein minimieren-Image-ID

### <a name="return-value"></a>Rückgabewert

Die Image-ID

### <a name="remarks"></a>Hinweise

Die Parameter geben Sie Image-IDs für Minimieren oder maximieren Titelleistenschaltflächen.

##  <a name="getrect"></a>  CMFCCaptionButton::GetRect

Gibt das Rechteck, das durch die Schaltfläche mit den belegt wird.

```
virtual CRect GetRect() const;
```

### <a name="return-value"></a>Rückgabewert

Das Rechteck, das die Position der Schaltfläche darstellt.

### <a name="remarks"></a>Hinweise

Wenn die Schaltfläche nicht angezeigt wird, ist die zurückgegebene Größe 0.

##  <a name="getsize"></a>  CMFCCaptionButton::GetSize

Gibt die Breite und Höhe der Schaltfläche.

```
static CSize GetSize();
```

### <a name="return-value"></a>Rückgabewert

Die äußeren Abmessungen der Schaltfläche.

### <a name="remarks"></a>Hinweise

Die zurückgegebene Größe enthält Schaltfläche Rand und Rahmen.

##  <a name="isminiframebutton"></a>  CMFCCaptionButton::IsMiniFrameButton

Gibt an, ob die Höhe der Titelleiste auf die kleine Größe festgelegt ist.

```
BOOL IsMiniFrameButton() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn die Beschriftung zu kleine Größe festgelegt ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

##  <a name="move"></a>  CMFCCaptionButton::Move

Legt fest, den Schaltfläche zeichnen Speicherort und den Status des Fensters angezeigt.

```
void Move(
    const CPoint& ptTo,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>Parameter

*ptTo*<br/>
[in] Die neue Position.

*bHide*<br/>
[in] Ob die Schaltfläche anzuzeigen.

##  <a name="ondraw"></a>  CMFCCaptionButton::OnDraw

Zeichnet die Titelleisten-Schaltfläche.

```
virtual void OnDraw(
    CDC* pDC,
    BOOL bActive,
    BOOL bHorz = TRUE,
    BOOL bMaximized = TRUE,
    BOOL bDisabled = FALSE);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
[in] Zeiger auf einen Gerätekontext für die Schaltfläche.

*bActive*<br/>
[in] Ob eine aktive Schaltflächenbild gezeichnet werden soll.

*bHorz*<br/>
[in] Für die Verwendung in einer abgeleiteten Klasse reserviert.

*bMaximized*<br/>
[in] Ob ein Schaltflächenbild maximierten gezeichnet werden soll.

*bDeaktiviert*<br/>
[in] Ob ein Schaltflächenbild für die aktivierte gezeichnet werden soll.

### <a name="remarks"></a>Hinweise

Die *bMaximized* Parameter wird verwendet, wenn die Schaltfläche ein Maximieren ist oder die Schaltfläche zum Minimieren.

##  <a name="setminiframebutton"></a>  CMFCCaptionButton::SetMiniFrameButton

Legt fest, die kleine Größe der Titelleiste angezeigt.

```
void SetMiniFramebutton(BOOL bSet = TRUE);
```

### <a name="parameters"></a>Parameter

*bSet*<br/>
[in] "True" für die Höhe der Mini Titelleiste; Für die Höhe der Titelleiste standardmäßig "false" werden.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CPaneFrameWnd-Klasse](../../mfc/reference/cpaneframewnd-class.md)<br/>
[CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md)
