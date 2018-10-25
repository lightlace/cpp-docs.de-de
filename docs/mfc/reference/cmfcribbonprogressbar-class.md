---
title: CMFCRibbonProgressBar-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonProgressBar
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::CMFCRibbonProgressBar
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetPos
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetRangeMax
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetRangeMin
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetRegularSize
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::IsInfiniteMode
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::OnDraw
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::SetInfiniteMode
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::SetPos
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::SetRange
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonProgressBar [MFC], CMFCRibbonProgressBar
- CMFCRibbonProgressBar [MFC], GetPos
- CMFCRibbonProgressBar [MFC], GetRangeMax
- CMFCRibbonProgressBar [MFC], GetRangeMin
- CMFCRibbonProgressBar [MFC], GetRegularSize
- CMFCRibbonProgressBar [MFC], IsInfiniteMode
- CMFCRibbonProgressBar [MFC], OnDraw
- CMFCRibbonProgressBar [MFC], SetInfiniteMode
- CMFCRibbonProgressBar [MFC], SetPos
- CMFCRibbonProgressBar [MFC], SetRange
ms.assetid: de3d9f2e-ed59-480e-aa7d-08a33ab36c67
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c056ce5a9747be280e465e2054402f43761c64e2
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50071572"
---
# <a name="cmfcribbonprogressbar-class"></a>CMFCRibbonProgressBar-Klasse

Implementiert ein Steuerelement, das den Fortschritt einer längeren Operation visuell darstellt.

## <a name="syntax"></a>Syntax

```
class CMFCRibbonProgressBar : public CMFCRibbonBaseElement
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMFCRibbonProgressBar::CMFCRibbonProgressBar](#cmfcribbonprogressbar)|Erstellt und initialisiert ein `CMFCRibbonProgressBar`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCRibbonProgressBar::GetPos](#getpos)|Gibt den aktuellen Status zurück.|
|[CMFCRibbonProgressBar::GetRangeMax](#getrangemax)|Gibt den maximalen Wert des aktuellen Bereichs zurück.|
|[CMFCRibbonProgressBar::GetRangeMin](#getrangemin)|Der minimale Wert des aktuellen Bereichs zurückgegeben.|
|[CMFCRibbonProgressBar::GetRegularSize](#getregularsize)|Gibt die reguläre Größe des Menübandelements zurück. (Überschreibt [cmfcribbonbaseelement:: Getregularsize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize).)|
|[CMFCRibbonProgressBar::IsInfiniteMode](#isinfinitemode)|Gibt an, ob die Statusanzeige im unendliche-Modus ausgeführt wird.|
|[CMFCRibbonProgressBar::OnDraw](#ondraw)|Wird vom Framework aufgerufen, um das Menübandelement zu zeichnen. (Überschreibt [cmfcribbonbaseelement:: OnDraw](../../mfc/reference/cmfcribbonbaseelement-class.md#ondraw).)|
|[CMFCRibbonProgressBar::SetInfiniteMode](#setinfinitemode)|Legt die Statusanzeige für unbegrenzte Modus fest.|
|[CMFCRibbonProgressBar::SetPos](#setpos)|Legt den aktuellen Status fest.|
|[CMFCRibbonProgressBar::SetRange](#setrange)|Legt die minimalen und maximalen Werte.|

## <a name="remarks"></a>Hinweise

Ein `CMFCRibbonProgressBar` kann in zwei Modi betrieben werden: reguläre und unendlich. Im regulären Modus die Statusanzeige von links nach rechts gefüllt und wird beendet, wenn sie den maximalen Wert erreicht. Im Modus "unendlich" ist die Statusanzeige wiederholt aus der minimale Wert auf den maximalen Wert gefüllt werden. Sie können unbegrenzte Modus verwenden, um anzugeben, dass ein Vorgang ausgeführt wird, aber die Dauer unbekannt ist.

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Verwendung verschiedener Methoden in der `CMFCRibbonProgressBar` -Klasse. Das Beispiel zeigt die Statusanzeige in der Sie arbeiten unendliche-Modus (wobei die Dauer eines Vorgangs unbekannt ist) festlegen, legen Sie die minimalen und maximalen Werte für die Statusanzeige, und legen Sie die aktuelle Position der Statusanzeige. Dieser Codeausschnitt ist Teil der [MS Office 2007-Demo-Beispiel](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_MSOffice2007Demo#11](../../mfc/reference/codesnippet/cpp/cmfcribbonprogressbar-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonProgressBar](../../mfc/reference/cmfcribbonprogressbar-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxRibbonProgressBar.h

##  <a name="cmfcribbonprogressbar"></a>  CMFCRibbonProgressBar::CMFCRibbonProgressBar

Erstellt und initialisiert ein [CMFCRibbonProgressBar](../../mfc/reference/cmfcribbonprogressbar-class.md) Objekt.

```
CMFCRibbonProgressBar();

CMFCRibbonProgressBar(
    UINT nID,
    int nWidth = 90,
    int nHeight = 22);
```

### <a name="parameters"></a>Parameter

*nID*<br/>
[in] Gibt die Befehls-ID für die Menüband-Statusanzeige an.

*nWidth*<br/>
[in] Gibt die Breite des der Menüband-Statusanzeige in Pixel an.

*nHeight*<br/>
[in] Gibt die Höhe des der Menüband-Statusanzeige in Pixel an.

##  <a name="getpos"></a>  CMFCRibbonProgressBar::GetPos

Gibt die aktuelle Position der Statusanzeige zurück.

```
int GetPos () const;
```

### <a name="return-value"></a>Rückgabewert

Ein Wert, der die aktuelle Position der Statusanzeige darstellt.

### <a name="remarks"></a>Hinweise

Bereich, der festgelegt wird muss innerhalb des Bereichs, der gemäß der [CMFCRibbonProgressBar::SetRange](#setrange) Methode.

##  <a name="getrangemax"></a>  CMFCRibbonProgressBar::GetRangeMax

Gibt zurück, die Statusanzeige, die aktuelle maximale Wert.

```
int GetRangeMax() const;
```

### <a name="return-value"></a>Rückgabewert

Der maximale Wert des aktuellen Bereichs.

### <a name="remarks"></a>Hinweise

##  <a name="getrangemin"></a>  CMFCRibbonProgressBar::GetRangeMin

Gibt zurück, die Statusanzeige, die aktuelle minimalen Bereichswert.

```
int GetRangeMin() const;
```

### <a name="return-value"></a>Rückgabewert

Der minimale Wert des aktuellen Bereichs.

##  <a name="getregularsize"></a>  CMFCRibbonProgressBar::GetRegularSize

Weitere Informationen finden Sie im Quellcode der **VC\\Atlmfc\\Src\\Mfc** Ordner von Visual Studio-Installation.

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>Parameter

[in] *pDC*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="isinfinitemode"></a>  CMFCRibbonProgressBar::IsInfiniteMode

Gibt an, ob die Statusanzeige im unendliche-Modus ausgeführt wird.

```
BOOL IsInfiniteMode() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn die Statusanzeige im unendliche-Modus. andernfalls "false".

### <a name="remarks"></a>Hinweise

Im Modus "unendlich" füllt die Statusanzeige wiederholt aus der minimale Wert auf den maximalen Wert. Sie können unbegrenzte Modus verwenden, um anzugeben, dass ein Vorgang ausgeführt wird, aber die Dauer unbekannt ist.

##  <a name="ondraw"></a>  CMFCRibbonProgressBar::OnDraw

Weitere Informationen finden Sie im Quellcode der **VC\\Atlmfc\\Src\\Mfc** Ordner von Visual Studio-Installation.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parameter

[in] *pDC*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="setinfinitemode"></a>  CMFCRibbonProgressBar::SetInfiniteMode

Legt die Statusanzeige für unbegrenzte Modus fest.

```
void SetInfiniteMode(BOOL bSet = TRUE);
```

### <a name="parameters"></a>Parameter

*bSet*<br/>
[in] "True", um anzugeben, dass die Statusanzeige im unendliche Modus; andernfalls "false".

### <a name="remarks"></a>Hinweise

In der Regel ist die Statusanzeige im unendliche Modus, ist es die Benutzer darüber informiert, dass ein Vorgang ausgeführt wird, aber die Dauer unbekannt ist. Daher füllt die Statusanzeige wiederholt aus der minimale Wert auf den maximalen Wert.

##  <a name="setpos"></a>  CMFCRibbonProgressBar::SetPos

Legt die aktuelle Position der Statusanzeige an.

```
void SetPos(
    int nPos,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>Parameter

*nPos*<br/>
[in] Gibt die Position, die auf der die Statusanzeige festgelegt ist.

*bRedraw*<br/>
[in] Gibt an, ob die Statusanzeige neu gezeichnet werden muss.

### <a name="remarks"></a>Hinweise

Bereich, der festgelegt wird muss innerhalb des Bereichs, der gemäß der [CMFCRibbonProgressBar::SetRange](#setrange) Methode.

##  <a name="setrange"></a>  CMFCRibbonProgressBar::SetRange

Legt die minimalen und maximalen Werte für die Statusanzeige.

```
void SetRange(
    int nMin,
    int nMax);
```

### <a name="parameters"></a>Parameter

*nmin.*<br/>
[in] Gibt den Mindestwert des Bereichs an.

*nmax.*<br/>
[in] Gibt den Höchstwert des Bereichs an.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode, um den Bereich der Statusanzeige zu definieren, durch Festlegen der minimalen und maximalen Werte.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonBaseElement-Klasse](../../mfc/reference/cmfcribbonbaseelement-class.md)<br/>
[CMFCRibbonBar-Klasse](../../mfc/reference/cmfcribbonbar-class.md)
