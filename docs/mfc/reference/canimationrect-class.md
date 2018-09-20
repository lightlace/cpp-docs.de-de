---
title: CAnimationRect-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAnimationRect
- AFXANIMATIONCONTROLLER/CAnimationRect
- AFXANIMATIONCONTROLLER/CAnimationRect::CAnimationRect
- AFXANIMATIONCONTROLLER/CAnimationRect::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationRect::GetBottom
- AFXANIMATIONCONTROLLER/CAnimationRect::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationRect::GetLeft
- AFXANIMATIONCONTROLLER/CAnimationRect::GetRight
- AFXANIMATIONCONTROLLER/CAnimationRect::GetTop
- AFXANIMATIONCONTROLLER/CAnimationRect::GetValue
- AFXANIMATIONCONTROLLER/CAnimationRect::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationRect::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationRect::m_bFixedSize
- AFXANIMATIONCONTROLLER/CAnimationRect::m_bottomValue
- AFXANIMATIONCONTROLLER/CAnimationRect::m_leftValue
- AFXANIMATIONCONTROLLER/CAnimationRect::m_rightValue
- AFXANIMATIONCONTROLLER/CAnimationRect::m_szInitial
- AFXANIMATIONCONTROLLER/CAnimationRect::m_topValue
dev_langs:
- C++
helpviewer_keywords:
- CAnimationRect [MFC], CAnimationRect
- CAnimationRect [MFC], AddTransition
- CAnimationRect [MFC], GetBottom
- CAnimationRect [MFC], GetDefaultValue
- CAnimationRect [MFC], GetLeft
- CAnimationRect [MFC], GetRight
- CAnimationRect [MFC], GetTop
- CAnimationRect [MFC], GetValue
- CAnimationRect [MFC], SetDefaultValue
- CAnimationRect [MFC], GetAnimationVariableList
- CAnimationRect [MFC], m_bFixedSize
- CAnimationRect [MFC], m_bottomValue
- CAnimationRect [MFC], m_leftValue
- CAnimationRect [MFC], m_rightValue
- CAnimationRect [MFC], m_szInitial
- CAnimationRect [MFC], m_topValue
ms.assetid: 0294156d-241e-4a57-92b2-31234fe557d6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e798862dc9e9d34d6a75461994989f685e33a554
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46436025"
---
# <a name="canimationrect-class"></a>CAnimationRect-Klasse

Implementiert die Funktion eines Rechtecks, dessen Seiten animiert werden können.

## <a name="syntax"></a>Syntax

```
class CAnimationRect : public CAnimationBaseObject;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CAnimationRect::CAnimationRect](#canimationrect)|Überladen. Erstellt eine Animation Rect-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAnimationRect::AddTransition](#addtransition)|Fügt die Übergänge für die linken, oberen, rechten und unteren Koordinaten hinzu.|
|[CAnimationRect::GetBottom](#getbottom)|Bietet Zugriff auf CAnimationVariable, die untere Koordinate darstellt.|
|[CAnimationRect::GetDefaultValue](#getdefaultvalue)|Gibt die Standardwerte für die Grenzen von Rechteck zurück.|
|[CAnimationRect::GetLeft](#getleft)|Bietet Zugriff auf CAnimationVariable, die linke Koordinate darstellt.|
|[CAnimationRect::GetRight](#getright)|Bietet Zugriff auf CAnimationVariable, die rechte Koordinate darstellt.|
|[CAnimationRect::GetTop](#gettop)|Bietet Zugriff auf CAnimationVariable, die obere Koordinate darstellt.|
|[CAnimationRect::GetValue](#getvalue)|Gibt den aktuellen Wert zurück.|
|[CAnimationRect::SetDefaultValue](#setdefaultvalue)|Legt den Standardwert fest.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAnimationRect::GetAnimationVariableList](#getanimationvariablelist)|Legt die gekapselten Animationsvariablen in einer Liste an. (Überschreibt [CAnimationBaseObject:: GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CAnimationRect::operator RECT](#operator_rect)|Konvertiert einen CAnimationRect in Rect.|
|[CAnimationRect::operator =](#operator_eq)|CAnimationRect Rect zugewiesen haben.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CAnimationRect::m_bFixedSize](#m_bfixedsize)|Gibt an, ob das Rechteck eine feste Größe hat.|

### <a name="protected-data-members"></a>Geschützte Datenmember

|name|Beschreibung|
|----------|-----------------|
|[CAnimationRect::m_bottomValue](#m_bottomvalue)|Die gekapselte Animationsvariable unten stellt dar, die Grenze des Animation Rechteck.|
|[CAnimationRect::m_leftValue](#m_leftvalue)|Die gekapselte Animationsvariable, die Links darstellt gebunden Animation Rechtecks.|
|[CAnimationRect::m_rightValue](#m_rightvalue)|Die gekapselte Animationsvariable, die Recht darstellt gebunden Animation Rechtecks.|
|[CAnimationRect::m_szInitial](#m_szinitial)|Gibt die Anfangsgröße der Animation Rechteck.|
|[CAnimationRect::m_topValue](#m_topvalue)|Die gekapselte Animationsvariable, die oberen darstellt gebunden Animation Rechtecks.|

## <a name="remarks"></a>Hinweise

CAnimationRect-Klasse kapselt die vier CAnimationVariable-Objekte und kann in Anwendungen ein Rechteck darstellen. Um diese Klasse in der Anwendung verwenden zu können, einfach instanziieren Sie ein Objekt dieser Klasse, Animationscontroller AddAnimationObject hinzugefügt, und rufen Sie AddTransition für jeden Übergang auf nach links, rechts oben und unten Koordinaten angewendet werden.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationRect`

## <a name="requirements"></a>Anforderungen

**Header:** afxanimationcontroller.h

##  <a name="addtransition"></a>  CAnimationRect::AddTransition

Fügt die Übergänge für die linken, oberen, rechten und unteren Koordinaten hinzu.

```
void AddTransition(
    CBaseTransition* pLeftTransition,
    CBaseTransition* pTopTransition,
    CBaseTransition* pRightTransition,
    CBaseTransition* pBottomTransition);
```

### <a name="parameters"></a>Parameter

*pLeftTransition*<br/>
Gibt Übergang für die linke Seite.

*pTopTransition*<br/>
Gibt Übergang für die obere Seite.

*pRightTransition*<br/>
Gibt Übergang für die rechte Seite.

*pBottomTransition*<br/>
Gibt Übergang für die Unterseite.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktion zum Hinzufügen der angegebenen Übergänge der internen Liste von Übergängen, Animation-Variablen für die einzelnen Rechteckseiten angewendet werden. Wenn Sie Übergänge hinzufügen, werden sie nicht sofort angewendet und in einer internen Liste gespeichert werden soll. Übergänge werden angewendet (hinzugefügt zu einem Storyboard für einen bestimmten Wert) beim Aufruf CAnimationController:: AnimateGroup. Wenn Sie keinen Übergang auf eine der Rechteckseiten anwenden möchten, können Sie NULL übergeben.

##  <a name="canimationrect"></a>  CAnimationRect::CAnimationRect

Erstellt ein CAnimationRect-Objekt.

```
CAnimationRect();


CAnimationRect(
    const CRect& rect,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);


CAnimationRect(
    const CPoint& pt,
    const CSize& sz,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);


CAnimationRect(
    int nLeft,
    int nTop,
    int nRight,
    int nBottom,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>Parameter

*Rect*<br/>
Gibt standardmäßige Rechteck.

*nGroupID*<br/>
Gibt die Gruppen-ID.

*nObjectID*<br/>
Gibt die Objekt-ID.

*dwUserData*<br/>
Gibt die benutzerdefinierten Daten.

*pt*<br/>
-Koordinate der oberen linken Ecke.

*sz*<br/>
Die Größe des Rechtecks.

*nLeft*<br/>
Gibt die Koordinate des linken gebunden.

*nTop*<br/>
Gibt die Koordinate der oberen Grenze an.

*nRight*<br/>
Gibt die Koordinate des rechten gebunden.

*nBottom*<br/>
Gibt die Koordinate der unteren gebunden.

### <a name="remarks"></a>Hinweise

Das Objekt wird erstellt, mit Standardwerten für Links, oben, rechts und nach unten und Objekt-ID und die Gruppen-ID, die auf 0 festgelegt werden. Sie können zur Laufzeit mithilfe SetDefaultValue und SetID später geändert werden.

##  <a name="getanimationvariablelist"></a>  CAnimationRect::GetAnimationVariableList

Legt die gekapselten Animationsvariablen in einer Liste an.

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& lst);
```

### <a name="parameters"></a>Parameter

*lst*<br/>
Wenn die Funktion zurückgibt, enthält Zeiger auf vier CAnimationVariable-Objekte, die Koordinaten des Rechtecks darstellt.

##  <a name="getbottom"></a>  CAnimationRect::GetBottom

Bietet Zugriff auf CAnimationVariable, die untere Koordinate darstellt.

```
CAnimationVariable& GetBottom();
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf die gekapselte CAnimationVariable, die untere Koordinate darstellt.

### <a name="remarks"></a>Hinweise

Sie können diese Methode, um direkten Zugriff auf zugrunde liegende CAnimationVariable, das die untere Koordinate darstellt erhalten aufrufen.

##  <a name="getdefaultvalue"></a>  CAnimationRect::GetDefaultValue

Gibt die Standardwerte für die Grenzen von Rechteck zurück.

```
CRect GetDefaultValue();
```

### <a name="return-value"></a>Rückgabewert

Ein CRect-Wert, die Standardwerte für den linken, rechten, oberen und unteren enthält.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktion zum Abrufen von Standardwert, der zuvor vom Konstruktor oder SetDefaultValue festgelegt wurde.

##  <a name="getleft"></a>  CAnimationRect::GetLeft

Bietet Zugriff auf CAnimationVariable, die linke Koordinate darstellt.

```
CAnimationVariable& GetLeft();
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf die gekapselte CAnimationVariable, die linke Koordinate darstellt.

### <a name="remarks"></a>Hinweise

Sie können diese Methode, um direkten Zugriff auf zugrunde liegende CAnimationVariable, das die linke Koordinate darstellt erhalten aufrufen.

##  <a name="getright"></a>  CAnimationRect::GetRight

Bietet Zugriff auf CAnimationVariable, die rechte Koordinate darstellt.

```
CAnimationVariable& GetRight();
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf die gekapselte CAnimationVariable, die rechte Koordinate darstellt.

### <a name="remarks"></a>Hinweise

Sie können diese Methode, um direkten Zugriff auf zugrunde liegende CAnimationVariable, das die rechte Koordinate darstellt erhalten aufrufen.

##  <a name="gettop"></a>  CAnimationRect::GetTop

Bietet Zugriff auf CAnimationVariable, die obere Koordinate darstellt.

```
CAnimationVariable& GetTop();
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf die gekapselte CAnimationVariable, die obere Koordinate darstellt.

### <a name="remarks"></a>Hinweise

Sie können diese Methode, um direkten Zugriff auf zugrunde liegende CAnimationVariable, die die obere Koordinate darstellt erhalten aufrufen.

##  <a name="getvalue"></a>  CAnimationRect::GetValue

Gibt den aktuellen Wert zurück.

```
BOOL GetValue(CRect& rect);
```

### <a name="parameters"></a>Parameter

*Rect*<br/>
Die Ausgabe. Enthält den aktuellen Wert an, wenn diese Methode zurückgegeben wird.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn der aktuelle Wert erfolgreich abgerufen wurde. andernfalls "false".

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktion, um den aktuellen Wert der Animation Rechteck abgerufen werden. Wenn diese Methode fehlschlägt oder die zugrunde liegende COM-Objekte für Left, oben, rechts und unten nicht initialisiert wurden, enthält Rect einen Standardwert, der zuvor im Konstruktor oder mit SetDefaultValue festgelegt wurde.

##  <a name="m_bfixedsize"></a>  CAnimationRect::m_bFixedSize

Gibt an, ob das Rechteck eine feste Größe hat.

```
BOOL m_bFixedSize;
```

### <a name="remarks"></a>Hinweise

Wenn dieser Member auf "true" festgelegt ist, klicken Sie dann die Größe des Rechtecks ist, behoben und rechten, und Werte unten werden neu berechnet, jedes Mal, wenn die linke obere Ecke, entsprechend der feste Größe verschoben wird. Legen Sie diesen Wert auf "true", um das Rechteck um den Bildschirm problemlos wechseln. In diesem Fall werden die Übergänge, die auf den rechten und unteren Koordinaten angewendet, ignoriert. Die Größe werden intern gespeichert werden, wenn Sie das Objekt zu erstellen und/oder SetDefaultValue aufrufen. Standardmäßig ist dieser Member auf "false" festgelegt.

##  <a name="m_bottomvalue"></a>  CAnimationRect::m_bottomValue

Die gekapselte Animationsvariable unten stellt dar, die Grenze des Animation Rechteck.

```
CAnimationVariable m_bottomValue;
```

##  <a name="m_leftvalue"></a>  CAnimationRect::m_leftValue

Die gekapselte Animationsvariable, die Links darstellt gebunden Animation Rechtecks.

```
CAnimationVariable m_leftValue;
```

##  <a name="m_rightvalue"></a>  CAnimationRect::m_rightValue

Die gekapselte Animationsvariable, die Recht darstellt gebunden Animation Rechtecks.

```
CAnimationVariable m_rightValue;
```

##  <a name="m_szinitial"></a>  CAnimationRect::m_szInitial

Gibt die Anfangsgröße der Animation Rechteck.

```
CSize m_szInitial;
```

##  <a name="m_topvalue"></a>  CAnimationRect::m_topValue

Die gekapselte Animationsvariable, die oberen darstellt gebunden Animation Rechtecks.

```
CAnimationVariable m_topValue;
```

##  <a name="operator_rect"></a>  CAnimationRect::operator RECT

Konvertiert einen CAnimationRect in Rect.

```
operator RECT();
```

### <a name="return-value"></a>Rückgabewert

Aktuellen Wert der Animation Rechteck als Rect.

### <a name="remarks"></a>Hinweise

Diese Funktion ruft intern "GetValue". Wenn GetValue aus irgendeinem Grund fehlschlägt, enthält das zurückgegebene RECT Standardwerte für alle Koordinaten für das Rechteck.

##  <a name="operator_eq"></a>  CAnimationRect::operator =

CAnimationRect Rect zugewiesen haben.

```
void operator=(const RECT& rect);
```

### <a name="parameters"></a>Parameter

*Rect*<br/>
Der neue Wert der Animation Rechteck.

### <a name="remarks"></a>Hinweise

Es wird dies vor dem Animationsstart, empfohlen, da dieser Operator SetDefaultValue aufruft, die die zugrunde liegenden COM-Objekte für Farbkomponenten neu erstellt, wenn sie bereits erstellt wurden. Wenn Sie diese "Animation"-Objekts auf Ereignisse (ValueChanged oder IntegerValueChanged) abonniert haben, müssen Sie diese Ereignisse erneut zu aktivieren.

##  <a name="setdefaultvalue"></a>  CAnimationRect::SetDefaultValue

Legt den Standardwert fest.

```
void SetDefaultValue(const CRect& rect);
```

### <a name="parameters"></a>Parameter

*Rect*<br/>
Gibt neue Standardwerte für Links, oben, rechts und unten an.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Funktion, um einen Standardwert auf "Animation"-Objekts festzulegen. Diese Methoden weisen Standardwerte des Rechtecks Grenzen. Es erstellt auch zugrunde liegende COM-Objekte neu, wenn sie bereits erstellt wurden. Wenn Sie diese "Animation"-Objekts auf Ereignisse (ValueChanged oder IntegerValueChanged) abonniert haben, müssen Sie diese Ereignisse erneut zu aktivieren.

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
