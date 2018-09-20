---
title: CMFCAutoHideButton-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCAutoHideButton
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::BringToTop
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::Create
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetAlignment
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetAutoHideWindow
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetParentToolBar
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetRect
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetSize
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetTextSize
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::HighlightButton
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsActive
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsHighlighted
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsHorizontal
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsTop
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsVisible
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::Move
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::OnDraw
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::OnDrawBorder
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::OnFillBackground
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::ReplacePane
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::ShowAttachedWindow
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::ShowButton
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::UnSetAutoHideMode
dev_langs:
- C++
helpviewer_keywords:
- CMFCAutoHideButton [MFC], BringToTop
- CMFCAutoHideButton [MFC], Create
- CMFCAutoHideButton [MFC], GetAlignment
- CMFCAutoHideButton [MFC], GetAutoHideWindow
- CMFCAutoHideButton [MFC], GetParentToolBar
- CMFCAutoHideButton [MFC], GetRect
- CMFCAutoHideButton [MFC], GetSize
- CMFCAutoHideButton [MFC], GetTextSize
- CMFCAutoHideButton [MFC], HighlightButton
- CMFCAutoHideButton [MFC], IsActive
- CMFCAutoHideButton [MFC], IsHighlighted
- CMFCAutoHideButton [MFC], IsHorizontal
- CMFCAutoHideButton [MFC], IsTop
- CMFCAutoHideButton [MFC], IsVisible
- CMFCAutoHideButton [MFC], Move
- CMFCAutoHideButton [MFC], OnDraw
- CMFCAutoHideButton [MFC], OnDrawBorder
- CMFCAutoHideButton [MFC], OnFillBackground
- CMFCAutoHideButton [MFC], ReplacePane
- CMFCAutoHideButton [MFC], ShowAttachedWindow
- CMFCAutoHideButton [MFC], ShowButton
- CMFCAutoHideButton [MFC], UnSetAutoHideMode
ms.assetid: c80e6b8b-25ca-4d12-9d27-457731028ab0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 072473895bbd041f9b195f02572461b02202be32
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46386092"
---
# <a name="cmfcautohidebutton-class"></a>CMFCAutoHideButton-Klasse

Eine Schaltfläche, die [CDockablePane Class](../../mfc/reference/cdockablepane-class.md) anzeigt oder ausblendet (vorausgesetzt, die Klasse ist so konfiguriert, dass sie ausgeblendet werden kann).

Weitere Informationen finden Sie im Quellcode der **VC\\Atlmfc\\Src\\Mfc** Ordner von Visual Studio-Installation.
## <a name="syntax"></a>Syntax

```
class CMFCAutoHideButton : public CObject
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCAutoHideButton::BringToTop](#bringtotop)||
|[CMFCAutoHideButton::Create](#create)|Erstellt und initialisiert die Schaltfläche zum automatischen Ausblenden.|
|[CMFCAutoHideButton::GetAlignment](#getalignment)|Ruft die Ausrichtung der Schaltfläche zum automatischen Ausblenden ab.|
|[CMFCAutoHideButton::GetAutoHideWindow](#getautohidewindow)|Gibt die [CDockablePane](../../mfc/reference/cdockablepane-class.md) die Schaltfläche zum automatischen Ausblenden zugeordnete Objekt.|
|[CMFCAutoHideButton::GetParentToolBar](#getparenttoolbar)||
|[CMFCAutoHideButton::GetRect](#getrect)||
|[CMFCAutoHideButton::GetSize](#getsize)|Legt die Größe der Schaltfläche zum automatischen Ausblenden fest.|
|[CMFCAutoHideButton::GetTextSize](#gettextsize)|Gibt die Größe der Textbeschriftung für die Schaltfläche zum automatischen Ausblenden zurück.|
|[CMFCAutoHideButton::HighlightButton](#highlightbutton)|Hebt die Schaltfläche zum automatischen Ausblenden hervor.|
|[CMFCAutoHideButton::IsActive](#isactive)|Gibt an, ob die Schaltfläche zum automatischen Ausblenden aktiv ist.|
|[CMFCAutoHideButton::IsHighlighted](#ishighlighted)|Gibt den Hervorhebestatus der Schaltfläche zum automatischen Ausblenden zurück.|
|[CMFCAutoHideButton::IsHorizontal](#ishorizontal)|Bestimmt, ob die Schaltfläche zum automatischen Ausblenden horizontal oder vertikal ist.|
|[CMFCAutoHideButton::IsTop](#istop)||
|[CMFCAutoHideButton::IsVisible](#isvisible)|Gibt an, ob die Schaltfläche sichtbar ist.|
|[CMFCAutoHideButton::Move](#move)||
|[CMFCAutoHideButton::OnDraw](#ondraw)|Das Framework ruft diese Methode auf, wenn es die Schaltfläche zum automatischen Ausblenden zeichnet.|
|[CMFCAutoHideButton::OnDrawBorder](#ondrawborder)|Das Framework ruft diese Methode auf, wenn es den Rahmen einer Schaltfläche zum automatischen Ausblenden zeichnet.|
|[CMFCAutoHideButton::OnFillBackground](#onfillbackground)|Das Framework ruft diese Methode auf, wenn es den Hintergrund einer Schaltfläche zum automatischen Ausblenden füllt.|
|[CMFCAutoHideButton::ReplacePane](#replacepane)||
|[CMFCAutoHideButton::ShowAttachedWindow](#showattachedwindow)|Anzeigen oder Ausblenden der zugeordneten [CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md).|
|[CMFCAutoHideButton::ShowButton](#showbutton)|Blendet die Schaltfläche zum automatischen Ausblenden ein oder aus.|
|[CMFCAutoHideButton::UnSetAutoHideMode](#unsetautohidemode)||

## <a name="remarks"></a>Hinweise

Bei Erstellung der `CMFCAutoHideButton` Objekt angefügt ist eine [CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md). Das `CDockablePane`-Objekt wird ausgeblendet oder angezeigt, wenn der Benutzer mit dem `CMFCAutoHideButton`-Objekt interagiert.

Standardmäßig erstellt das Framework automatisch eine `CMFCAutoHideButton`, wenn der Benutzer das automatische Ausblenden aktiviert. Das Framework kann ein Element einer benutzerdefinierten Benutzeroberflächenklasse erstellen, anstatt der `CMFCAutoHideButton`-Klasse. Um festzulegen, welche benutzerdefinierte Benutzeroberflächenklasse das Framework verwenden soll, legen Sie die statische Membervariable `CMFCAutoHideBar::m_pAutoHideButtonRTS` auf den gleichen Wert wie die benutzerdefinierte Benutzeroberflächenklasse fest. Standardmäßig ist diese Variable auf `CMFCAutoHideButton` festgelegt.

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht das Erstellen eines `CMFCAutoHideButton`-Objekts, und die Verwendung verschiedener Methoden in der `CMFCAutoHideButton`-Klasse. Das Beispiel veranschaulicht, wie Sie ein `CMFCAutoHideButton`-Objekt mithilfe seiner `Create`-Methode initialisieren, die zugeordnete `CDockablePane`-Klasse anzeigen und die Schaltfläche zum automatischen Ausblenden anzeigen.

[!code-cpp[NVC_MFC_RibbonApp#32](../../mfc/reference/codesnippet/cpp/cmfcautohidebutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

`CMFCAutoHideButton`

## <a name="requirements"></a>Anforderungen

**Header:** afxautohidebutton.h

##  <a name="bringtotop"></a>  CMFCAutoHideButton::BringToTop


```
void BringToTop();
```

### <a name="remarks"></a>Hinweise

##  <a name="create"></a>  CMFCAutoHideButton::Create

Erstellt und initialisiert eine Schaltfläche zum automatischen ausblenden.

```
virtual BOOL Create(
    CMFCAutoHideBar* pParentBar,
    CDockablePane* pAutoHideWnd,
    DWORD dwAlignment);
```

### <a name="parameters"></a>Parameter

*pParentBar*<br/>
[in] Ein Zeiger auf der übergeordneten Symbolleiste.

*pAutoHideWnd*<br/>
[in] Ein Zeiger auf eine [CDockablePane](../../mfc/reference/cdockablepane-class.md) Objekt. Diese Schaltfläche zum automatischen Ausblenden wird ausgeblendet, und zeigt, dass `CDockablePane`.

*dwAlignment*<br/>
[in] Ein Wert, der die Ausrichtung der Schaltfläche mit dem Hauptrahmenfenster angibt.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Bei der Erstellung einer `CMFCAutoHideButton` Objekt ist, müssen Sie die Schaltfläche zum automatischen Ausblenden einer bestimmten zuordnen `CDockablePane`. Der Benutzer kann die Schaltfläche zum automatischen Ausblenden verwenden, zum aus- und Einblenden der zugeordneten `CDockablePane`.

Die *DwAlignment* Parameter gibt an, in dem die Schaltfläche "automatisch ausblenden" in der Anwendung befindet. Der Parameter kann auf einen der folgenden Werte festgelegt werden:

- CBRS_ALIGN_LEFT

- CBRS_ALIGN_RIGHT

- CBRS_ALIGN_TOP

- CBRS_ALIGN_BOTTOM

##  <a name="getalignment"></a>  CMFCAutoHideButton::GetAlignment

Ruft die Ausrichtung der Schaltfläche zum automatischen Ausblenden ab.

```
DWORD GetAlignment() const;
```

### <a name="return-value"></a>Rückgabewert

Eine DWORD-Wert, der die aktuelle Ausrichtung der automatisch ausblendbaren Schaltfläche enthält.

### <a name="remarks"></a>Hinweise

Die Ausrichtung der automatisch ausblendbaren Schaltfläche gibt an, in dem sich die Schaltfläche für die Anwendung befindet. Eine der folgenden Werte sind möglich:

- CBRS_ALIGN_LEFT

- CBRS_ALIGN_RIGHT

- CRBS_ALIGN_TOP

- CBRS_ALIGN_BOTTOM

##  <a name="getautohidewindow"></a>  CMFCAutoHideButton::GetAutoHideWindow

Gibt die [CDockablePane](../../mfc/reference/cdockablepane-class.md) die Schaltfläche zum automatischen Ausblenden zugeordnete Objekt.

```
CDockablePane* GetAutoHideWindow() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das zugeordnete `CDockablePane` Objekt.

### <a name="remarks"></a>Hinweise

Zuordnen mit eine Schaltfläche zum automatischen Ausblenden ein `CDockablePane`, übergeben die `CDockablePane` als Parameter an die [CMFCAutoHideButton::Create](#create) Methode.

##  <a name="getparenttoolbar"></a>  CMFCAutoHideButton::GetParentToolBar


```
CMFCAutoHideBar* GetParentToolBar();
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="getrect"></a>  CMFCAutoHideButton::GetRect


```
CRect GetRect() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="getsize"></a>  CMFCAutoHideButton::GetSize

Legt die Größe der Schaltfläche zum automatischen Ausblenden fest.

```
CSize GetSize() const;
```

### <a name="return-value"></a>Rückgabewert

Ein `CSize` Objekt, das die Größe der Schaltfläche enthält.

### <a name="remarks"></a>Hinweise

Die berechnete Größe umfasst die Größe des Rahmens der Schaltfläche zum automatischen ausblenden.

##  <a name="gettextsize"></a>  CMFCAutoHideButton::GetTextSize

Gibt die Größe der Textbeschriftung für die Schaltfläche zum automatischen Ausblenden zurück.

```
virtual CSize GetTextSize() const;
```

### <a name="return-value"></a>Rückgabewert

Ein [CSize](../../atl-mfc-shared/reference/csize-class.md) Objekt, das die Größe des Texts für die Schaltfläche zum automatischen Ausblenden enthält.

##  <a name="isactive"></a>  CMFCAutoHideButton::IsActive

Gibt an, ob die Schaltfläche zum automatischen Ausblenden aktiv ist.

```
BOOL IsActive() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn die Schaltfläche zum automatischen Ausblenden aktiv ist. "False" andernfalls.

### <a name="remarks"></a>Hinweise

Eine Schaltfläche zum automatischen Ausblenden ist aktiv, wenn die zugeordnete [CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md) Fenster wird angezeigt.

##  <a name="ishorizontal"></a>  CMFCAutoHideButton::IsHorizontal

Bestimmt, ob die Schaltfläche zum automatischen Ausblenden horizontal oder vertikal ist.

```
BOOL IsHorizontal() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn die Schaltfläche horizontale ist; andernfalls 0.

### <a name="remarks"></a>Hinweise

Das Framework legt fest, der die Ausrichtung des eine [CMFCAutoHideButton](../../mfc/reference/cmfcautohidebutton-class.md) Objekt, wenn Sie ihn erstellen.  Sie können die Ausrichtung steuern, mit der *DwAlignment* Parameter in der [CMFCAutoHideButton::Create](#create) Methode.

##  <a name="istop"></a>  CMFCAutoHideButton::IsTop


```
BOOL IsTop() const;
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="isvisible"></a>  CMFCAutoHideButton::IsVisible

Gibt an, ob die automatisch ausblendbaren Schaltfläche sichtbar ist.

```
virtual BOOL IsVisible() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn die Schaltfläche sichtbar ist. "False" andernfalls.

##  <a name="ondraw"></a>  CMFCAutoHideButton::OnDraw

Das Framework ruft diese Methode auf, wenn es die Schaltfläche zum automatischen Ausblenden zeichnet.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
[in] Ein Zeiger auf einen Gerätekontext.

### <a name="remarks"></a>Hinweise

Wenn Sie die Darstellung der automatisch ausblendbaren Schaltflächen in Ihrer Anwendung anpassen möchten, erstellen Sie eine neue Klasse, die von abgeleiteten `CMFCAutoHideButton`. In der abgeleiteten Klasse die überschreiben Sie diese Methode.

##  <a name="ondrawborder"></a>  CMFCAutoHideButton::OnDrawBorder

Das Framework ruft diese Methode auf, wenn es den Rahmen einer Schaltfläche zum automatischen Ausblenden zeichnet.

```
virtual void OnDrawBorder(
    CDC* pDC,
    CRect rectBounds,
    CRect rectBorderSize);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
[in] Ein Zeiger auf einen Gerätekontext.

*rectBounds*<br/>
[in] Das umschließende Rechteck der automatisch ausblendbaren Schaltfläche.

*rectBorderSize*<br/>
[in] Die Stärke des Rahmens für jede Seite der automatisch ausblendbaren Schaltfläche.

### <a name="remarks"></a>Hinweise

Wenn Sie den Rand jeder Schaltfläche zum automatischen Ausblenden in Ihrer Anwendung anpassen möchten, erstellen Sie eine neue Klasse, die von abgeleiteten der `CMFCAutoHideButton`. In der abgeleiteten Klasse die überschreiben Sie diese Methode.

##  <a name="onfillbackground"></a>  CMFCAutoHideButton::OnFillBackground

Das Framework ruft diese Methode auf, wenn es den Hintergrund einer Schaltfläche zum automatischen Ausblenden füllt.

```
virtual void OnFillBackground(
    CDC* pDC,
    CRect rect);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
[in] Ein Zeiger auf einen Gerätekontext.

*Rect*<br/>
[in] Das umschließende Rechteck der automatisch ausblendbaren Schaltfläche.

### <a name="remarks"></a>Hinweise

Wenn Sie den Hintergrund der automatisch ausblendbaren Schaltflächen in Ihrer Anwendung anpassen möchten, erstellen Sie eine neue Klasse, die von abgeleiteten der `CMFCAutoHideButton`. In der abgeleiteten Klasse die überschreiben Sie diese Methode.

##  <a name="showattachedwindow"></a>  CMFCAutoHideButton::ShowAttachedWindow

Anzeigen oder Ausblenden der zugeordneten [CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md).

```
void ShowAttachedWindow(BOOL bShow);
```

### <a name="parameters"></a>Parameter

*bShow*<br/>
[in] Ein boolescher Wert, der angibt, ob diese Methode wird der angefügte gezeigt `CDockablePane`.

##  <a name="showbutton"></a>  CMFCAutoHideButton::ShowButton

Blendet die Schaltfläche zum automatischen Ausblenden ein oder aus.

```
virtual void ShowButton(BOOL bShow);
```

### <a name="parameters"></a>Parameter

*bShow*<br/>
[in] Ein boolescher Wert, der angibt, ob die Schaltfläche "automatisch ausblenden" angezeigt.

##  <a name="move"></a>  CMFCAutoHideButton::Move


```
void Move(int nOffset);
```

### <a name="parameters"></a>Parameter

[in] *nOffset*

### <a name="remarks"></a>Hinweise

##  <a name="replacepane"></a>  CMFCAutoHideButton::ReplacePane


```
void ReplacePane(CDockablePane* pNewBar);
```

### <a name="parameters"></a>Parameter

[in] *pNewBar*

### <a name="remarks"></a>Hinweise

##  <a name="unsetautohidemode"></a>  CMFCAutoHideButton::UnSetAutoHideMode

Deaktiviert den automatischen Ausblendemodus.

```
virtual void UnSetAutoHideMode(CDockablePane* pFirstBarInGroup);
```

### <a name="parameters"></a>Parameter

*pFirstBarInGroup*<br/>
[in] Ein Zeiger auf die erste Leiste in der Gruppe.

### <a name="remarks"></a>Hinweise

##  <a name="highlightbutton"></a>  CMFCAutoHideButton::HighlightButton

Hebt die Schaltfläche zum automatischen Ausblenden hervor.

```
virtual void HighlightButton(BOOL bHighlight);
```

### <a name="parameters"></a>Parameter

*bHighlight*<br/>
Gibt an, die neue automatisch im Hintergrund Status. "True" gibt an, dass die Schaltfläche markiert wird, "false" gibt an, dass die Schaltfläche nicht hervorgehoben ist.

### <a name="remarks"></a>Hinweise

##  <a name="ishighlighted"></a>  CMFCAutoHideButton::IsHighlighted

Gibt den Zustand Hervorhebung der Schaltfläche zum automatischen Ausblenden zurück.

```
virtual BOOL IsHighlighted() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt "true", wenn die automatische Schaltfläche ausblenden hervorgehoben ist; andernfalls "false".

### <a name="remarks"></a>Hinweise

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCAutoHideBar-Klasse](../../mfc/reference/cmfcautohidebar-class.md)<br/>
[CAutoHideDockSite-Klasse](../../mfc/reference/cautohidedocksite-class.md)
