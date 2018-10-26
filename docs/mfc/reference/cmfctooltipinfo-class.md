---
title: CMFCToolTipInfo-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCToolTipInfo
- AFXTOOLTIPCTRL/CMFCToolTipInfo
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bBalloonTooltip
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bBoldLabel
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bDrawDescription
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bDrawIcon
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bDrawSeparator
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bRoundedCorners
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bVislManagerTheme
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrBorder
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrFill
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrFillGradient
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrText
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_nGradientAngle
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_nMaxDescrWidth
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolTipInfo [MFC], m_bBalloonTooltip
- CMFCToolTipInfo [MFC], m_bBoldLabel
- CMFCToolTipInfo [MFC], m_bDrawDescription
- CMFCToolTipInfo [MFC], m_bDrawIcon
- CMFCToolTipInfo [MFC], m_bDrawSeparator
- CMFCToolTipInfo [MFC], m_bRoundedCorners
- CMFCToolTipInfo [MFC], m_bVislManagerTheme
- CMFCToolTipInfo [MFC], m_clrBorder
- CMFCToolTipInfo [MFC], m_clrFill
- CMFCToolTipInfo [MFC], m_clrFillGradient
- CMFCToolTipInfo [MFC], m_clrText
- CMFCToolTipInfo [MFC], m_nGradientAngle
- CMFCToolTipInfo [MFC], m_nMaxDescrWidth
ms.assetid: f9d3d7f8-1f08-4342-a7b2-683860e5d2a5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4685b050f7fca71a8aaaf05b072069bdd985ccdc
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50061677"
---
# <a name="cmfctooltipinfo-class"></a>CMFCToolTipInfo-Klasse

Speichert Informationen über die visuelle Darstellung von QuickInfos.

## <a name="syntax"></a>Syntax

```
class CMFCToolTipInfo
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCToolTipInfo::operator =](#operator_eq)||

### <a name="data-members"></a>Datenmember

|name|Beschreibung|
|----------|-----------------|
|[CMFCToolTipInfo::m_bBalloonTooltip](#m_bballoontooltip)|Eine boolesche Variable, die angibt, ob die QuickInfo über eine Sprechblasendarstellung verfügt.|
|[CMFCToolTipInfo::m_bBoldLabel](#m_bboldlabel)|Eine boolesche Variable, die angibt, ob die QuickInfo-Bezeichnungen in fett formatierter Schrift angezeigt werden.|
|[CMFCToolTipInfo::m_bDrawDescription](#m_bdrawdescription)|Eine boolesche Variable, die angibt, ob die QuickInfo eine Beschreibung enthält.|
|[CMFCToolTipInfo::m_bDrawIcon](#m_bdrawicon)|Eine boolesche Variable, die angibt, ob die QuickInfo ein Symbol enthält.|
|[CMFCToolTipInfo::m_bDrawSeparator](#m_bdrawseparator)|Eine boolesche Variable, die angibt, ob eine Trennzeichen zwischen der QuickInfo-Bezeichnung und der QuickInfo-Beschreibung angezeigt wird.|
|[CMFCToolTipInfo::m_bRoundedCorners](#m_broundedcorners)|Eine boolesche Variable, die angibt, ob die QuickInfo abgerundete Ecken besitzt.|
|[CMFCToolTipInfo::m_bVislManagerTheme](#m_bvislmanagertheme)|Eine boolesche Variable, der angibt, ob die Darstellung der QuickInfo durch einen visuellen Manager gesteuert werden soll (siehe [CMFCVisualManager-Klasse](../../mfc/reference/cmfcvisualmanager-class.md)).|
|[CMFCToolTipInfo::m_clrBorder](#m_clrborder)|Die Farbe des QuickInfo-Rahmens.|
|[CMFCToolTipInfo::m_clrFill](#m_clrfill)|Die Farbe des QuickInfo-Hintergrunds.|
|[CMFCToolTipInfo::m_clrFillGradient](#m_clrfillgradient)|Die Farbe der Verlaufsfläche in der QuickInfo.|
|[CMFCToolTipInfo::m_clrText](#m_clrtext)|Die Textfarbe in der QuickInfo.|
|[CMFCToolTipInfo::m_nGradientAngle](#m_ngradientangle)|Der Winkel der Verlaufsfläche in der QuickInfo.|
|[CMFCToolTipInfo::m_nMaxDescrWidth](#m_nmaxdescrwidth)|Die maximal mögliche Breite der Beschreibung in der QuickInfo in Pixel.|

## <a name="remarks"></a>Hinweise

Verwendung [CMFCToolTipCtrl-Klasse](../../mfc/reference/cmfctooltipctrl-class.md), `CMFCToolTipInfo`, und [CTooltipManager-Klasse](../../mfc/reference/ctooltipmanager-class.md) zusammen, um benutzerdefinierte QuickInfos in Ihrer Anwendung zu implementieren. Ein Beispiel zur Verwendung dieser QuickInfo-Klassen finden Sie unter den [CMFCToolTipCtrl-Klasse](../../mfc/reference/cmfctooltipctrl-class.md) Thema.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird die Festlegung der Werte für die verschiedenen Membervariablen in der `CMFCToolTipInfo`-Klasse veranschaulicht.

[!code-cpp[NVC_MFC_RibbonApp#42](../../mfc/reference/codesnippet/cpp/cmfctooltipinfo-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxtooltipctrl.h

##  <a name="m_bballoontooltip"></a>  CMFCToolTipInfo::m_bBalloonTooltip

Gibt die Art der Anzeige aller QuickInfos.

```
BOOL m_bBalloonTooltip;
```

### <a name="remarks"></a>Hinweise

"True" gibt an, dass QuickInfos der sprechblasenformat verwenden, "false" gibt an, dass QuickInfos den rechteckigen Stil.

##  <a name="m_bboldlabel"></a>  CMFCToolTipInfo::m_bBoldLabel

Gibt an, ob die Schriftart des QuickInfo-Text fett formatiert ist.

```
BOOL m_bBoldLabel;
```

### <a name="remarks"></a>Hinweise

Legen Sie dieses Element auf "true" Anzeige QuickInfo-Text durch Fettdruck, oder "false" zum Anzeigen von QuickInfo-Bezeichnungen in nicht fette Schriftart an.

##  <a name="m_bdrawdescription"></a>  CMFCToolTipInfo::m_bDrawDescription

Gibt an, ob jede QuickInfo Beschreibungstext angezeigt.

```
BOOL m_bDrawDescription;
```

### <a name="remarks"></a>Hinweise

Stellen Sie dieses Element auf "true" Anzeige der Beschreibung oder "false", um die Beschreibung ausblenden. Sie können die Beschreibung für eine QuickInfo angeben, durch den Aufruf [CMFCToolTipCtrl::SetDescription](../../mfc/reference/cmfctooltipctrl-class.md#setdescription)

##  <a name="m_bdrawicon"></a>  CMFCToolTipInfo::m_bDrawIcon

Gibt an, ob alle Symbole in QuickInfos.

```
BOOL m_bDrawIcon;
```

### <a name="remarks"></a>Hinweise

Dieses Element auf "true", ein Symbol für jede QuickInfo anzuzeigen oder "false" zum Anzeigen von QuickInfos ohne Symbole festgelegt.

##  <a name="m_bdrawseparator"></a>  CMFCToolTipInfo::m_bDrawSeparator

Gibt an, ob jede QuickInfo ein Trennzeichen zwischen der Bezeichnung und eine Beschreibung verfügt.

```
BOOL m_bDrawSeparator;
```

### <a name="remarks"></a>Hinweise

Dieser Member auf "true", Trennzeichen zwischen den QuickInfo-Bezeichnung und eine Beschreibung anzuzeigen oder "false" zum Anzeigen von QuickInfos ohne Trennzeichen festgelegt.

##  <a name="m_broundedcorners"></a>  CMFCToolTipInfo::m_bRoundedCorners

Gibt an, ob alle QuickInfos Ecken erstellt abgerundeten.

```
BOOL m_bRoundedCorners;
```

### <a name="remarks"></a>Hinweise

Stellen Sie dieses Element auf "true" angezeigt, die gerundet Ecken in QuickInfos oder "false" rechteckige Ecken auf QuickInfos angezeigt.

##  <a name="m_clrborder"></a>  CMFCToolTipInfo::m_clrBorder

Gibt die Farbe des Rahmens für alle QuickInfos an.

```
COLORREF m_clrBorder;
```

##  <a name="m_clrfill"></a>  CMFCToolTipInfo::m_clrFill

Gibt die Farbe des QuickInfo-Hintergrund.

```
COLORREF m_clrFill;
```

### <a name="remarks"></a>Hinweise

Wenn [CMFCToolTipInfo::m_clrFillGradient](#m_clrfillgradient) -1 ist, wird die Farbe des QuickInfo-Hintergrunds `m_clrFill`. Andernfalls `m_clrFill` gibt die Farbe für den Anfang des Farbverlaufs und `m_clrFillGradient` gibt die Farbe am Ende des Farbverlaufs entspricht. [CMFCToolTipInfo::m_nGradientAngle](#m_ngradientangle) bestimmt die Richtung des Farbverlaufs entspricht.

##  <a name="m_clrfillgradient"></a>  CMFCToolTipInfo::m_clrFillGradient

Gibt die Endfarbe für den Hintergrund mit Farbverlauf für QuickInfos an.

```
COLORREF m_clrFillGradient;
```

### <a name="remarks"></a>Hinweise

Wenn `m_clrFillGradient` ist-1, es wird kein Farbverlauf. Anfängliche Verlaufsfarbe entspricht, andernfalls von [CMFCToolTipInfo::m_clrFill](#m_clrfill) und die Farbe des Farbverlaufs "Fertig stellen" wird angegeben, indem `m_clrFillGradient`. [CMFCToolTipInfo::m_nGradientAngle](#m_ngradientangle) bestimmt die Richtung des Farbverlaufs entspricht.

##  <a name="m_clrtext"></a>  CMFCToolTipInfo::m_clrText

Gibt die Textfarbe für alle QuickInfos an.

```
COLORREF m_clrText;
```

##  <a name="m_ngradientangle"></a>  CMFCToolTipInfo::m_nGradientAngle

Gibt den Winkel an dem ein Farbverlauf im Hintergrund der QuickInfo gezeichnet wird.

```
int m_nGradientAngle;
```

### <a name="remarks"></a>Hinweise

`m_nGradientAngle` Gibt den Winkel in Grad, von der horizontalen Farbverlauf im Hintergrund von QuickInfos versetzt ist. Wenn `m_nGradientAngle` gleich 0 ist, der Farbverlauf von links nach rechts gezeichnet wird. Wenn `m_nGradientAngle` ist zwischen 1 und 360, ist der Gradient um diese Anzahl von Grad im Uhrzeigersinn drehen. Wenn `m_nGradientAngle` 1. Dadurch wird der Standardwert ist, wird der Farbverlauf von oben nach unten gezeichnet wird. Dies ist identisch mit dem Festlegen `m_nGradientAngle` auf 90.

[CMFCToolTipInfo::m_clrFill](#m_clrfill) `clrFill` gibt die Farbe für den Anfang des Farbverlaufs und [CMFCToolTipInfo::m_clrFillGradient](#m_clrfillgradient) `clrFillGradient` gibt die Farbe am Ende des Farbverlaufs entspricht. Wenn `m_clrFillGradient` ist-1, es wird kein Farbverlauf.

##  <a name="m_nmaxdescrwidth"></a>  CMFCToolTipInfo::m_nMaxDescrWidth

Gibt die maximale Breite der Beschreibung, die sie in jeder QuickInfo angezeigt. Wenn die Breite der Beschreibung den angegebenen Wert überschreitet, wird der Text umbrochen.

```
int m_nMaxDescrWidth;
```

##  <a name="m_bvislmanagertheme"></a>  CMFCToolTipInfo::m_bVislManagerTheme

Gibt an, ob es sich bei den visuelle Manager der Anwendung die Darstellung aller QuickInfos steuert.

```
BOOL m_bVislManagerTheme;
```

### <a name="remarks"></a>Hinweise

Wenn `m_bVislManagerTheme` ist "true", jedes QuickInfo fordert ein neues [CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md) aus dem visual-Manager, der die Anwendung, bevor sie auf dem Bildschirm angezeigt, und die Werte in diesem Objekt verwendet, um ihre Darstellung zu bestimmen. Die anderen Mitglieder des Ihre [CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md) werden ignoriert.

##  <a name="operator_eq"></a>  CMFCToolTipInfo::operator =

Weitere Informationen finden Sie im Quellcode der **VC\\Atlmfc\\Src\\Mfc** Ordner von Visual Studio-Installation.

```
CMFCToolTipInfo& operator=(CMFCToolTipInfo& src);
```

### <a name="parameters"></a>Parameter

[in] *Src*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CTooltipManager-Klasse](../../mfc/reference/ctooltipmanager-class.md)<br/>
[CMFCToolTipCtrl-Klasse](../../mfc/reference/cmfctooltipctrl-class.md)
