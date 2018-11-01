---
title: CAnimationPoint-Klasse
ms.date: 11/04/2016
f1_keywords:
- CAnimationPoint
- AFXANIMATIONCONTROLLER/CAnimationPoint
- AFXANIMATIONCONTROLLER/CAnimationPoint::CAnimationPoint
- AFXANIMATIONCONTROLLER/CAnimationPoint::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetX
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetY
- AFXANIMATIONCONTROLLER/CAnimationPoint::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationPoint::m_xValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::m_yValue
helpviewer_keywords:
- CAnimationPoint [MFC], CAnimationPoint
- CAnimationPoint [MFC], AddTransition
- CAnimationPoint [MFC], GetDefaultValue
- CAnimationPoint [MFC], GetValue
- CAnimationPoint [MFC], GetX
- CAnimationPoint [MFC], GetY
- CAnimationPoint [MFC], SetDefaultValue
- CAnimationPoint [MFC], GetAnimationVariableList
- CAnimationPoint [MFC], m_xValue
- CAnimationPoint [MFC], m_yValue
ms.assetid: 5dc4d46f-e695-4681-b15c-544b78b3e317
ms.openlocfilehash: 15f18a43fcda76bb5531434de84d97a349cb7f39
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50497199"
---
# <a name="canimationpoint-class"></a>CAnimationPoint-Klasse

Implementiert die Funktion eines Punkts, dessen Koordinaten animiert werden können.

## <a name="syntax"></a>Syntax

```
class CAnimationPoint : public CAnimationBaseObject;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CAnimationPoint::CAnimationPoint](#canimationpoint)|Überladen. CAnimationPoint-Objekt wird erstellt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAnimationPoint::AddTransition](#addtransition)|Fügt der Übergänge für X und Y-Koordinaten.|
|[CAnimationPoint::GetDefaultValue](#getdefaultvalue)|Gibt die Standardwerte für X und Y-Koordinaten.|
|[CAnimationPoint::GetValue](#getvalue)|Gibt den aktuellen Wert zurück.|
|[CAnimationPoint::GetX](#getx)|Ermöglicht den Zugriff auf die CAnimationVariable für X-Koordinate.|
|[CAnimationPoint::GetY](#gety)|Bietet Zugriff auf CAnimationVariable für Y-Koordinate.|
|[CAnimationPoint::SetDefaultValue](#setdefaultvalue)|Legt den Standardwert fest.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAnimationPoint::GetAnimationVariableList](#getanimationvariablelist)|Legt die gekapselten Animationsvariablen in einer Liste an. (Überschreibt [CAnimationBaseObject:: GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CAnimationPoint::operator CPoint](#operator_cpoint)|Konvertiert einen CAnimationPoint in einen CPoint an.|
|[CAnimationPoint::operator =](#operator_eq)|CAnimationPoint PtSrc zugewiesen haben.|

### <a name="protected-data-members"></a>Geschützte Datenmember

|name|Beschreibung|
|----------|-----------------|
|[CAnimationPoint::m_xValue](#m_xvalue)|Die gekapselte Animationsvariable, die X steht für Koordinate des Animationspunkts.|
|[CAnimationPoint::m_yValue](#m_yvalue)|Die gekapselte Animationsvariable, die Y-Koordinate des Animationspunkts darstellt.|

## <a name="remarks"></a>Hinweise

CAnimationPoint-Klasse kapselt zwei CAnimationVariable-Objekte und kann in Anwendungen einen Zeitpunkt darstellen. Beispielsweise können Sie diese Klasse verwenden, um eine Position eines Objekts auf dem Bildschirm (z.B. Zeichenfolge, Kreis, Punkt usw.) zu animieren. Um diese Klasse in der Anwendung verwenden zu können, nur ein Objekt dieser Klasse zu instanziieren, Animationscontroller AddAnimationObject hinzufügen und Aufrufen AddTransition für jeden Übergang anzuwendende X bzw. Y-Koordinaten.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationPoint`

## <a name="requirements"></a>Anforderungen

**Header:** afxanimationcontroller.h

##  <a name="addtransition"></a>  CAnimationPoint::AddTransition

Fügt der Übergänge für X und Y-Koordinaten.

```
void AddTransition(
    CBaseTransition* pXTransition,
    CBaseTransition* pYTransition);
```

### <a name="parameters"></a>Parameter

*pXTransition*<br/>
Ein Zeiger auf den Übergang für X-Koordinaten.

*pYTransition*<br/>
Ein Zeiger auf den Übergang für Y-Koordinate.

### <a name="remarks"></a>Hinweise

Mit dieser Funktion können Sie die angegebenen Übergänge hinzugefügt werden der internen Liste von Übergängen anzuwendende Animationsvariablen für X und Y-Koordinaten. Wenn Sie Übergänge hinzufügen, werden sie nicht sofort angewendet und in einer internen Liste gespeichert werden soll. Übergänge werden angewendet (hinzugefügt zu einem Storyboard für einen bestimmten Wert) beim Aufruf CAnimationController:: AnimateGroup. Wenn Sie keine Übergang auf eine der Koordinaten anwenden müssen, können Sie NULL übergeben.

##  <a name="canimationpoint"></a>  CAnimationPoint::CAnimationPoint

CAnimationPoint-Objekt wird erstellt.

```
CAnimationPoint();

CAnimationPoint(
    const CPoint& ptDefault,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>Parameter

*ptDefault*<br/>
Gibt standardmäßige Punktkoordinaten an.

*nGroupID*<br/>
Gibt die Gruppen-ID.

*nObjectID*<br/>
Gibt die Objekt-ID.

*dwUserData*<br/>
Gibt die benutzerdefinierten Daten.

### <a name="remarks"></a>Hinweise

CAnimationPoint-Objekt mit Eigenschaften erstellt: Punktkoordinaten Standard, die Gruppen-ID und Objekt-ID werden auf 0 festgelegt.

##  <a name="getanimationvariablelist"></a>  CAnimationPoint::GetAnimationVariableList

Legt die gekapselten Animationsvariablen in einer Liste an.

```
virtual void GetAnimationVariableList(CList<CAnimationVariable*, CAnimationVariable*>& lst);
```

### <a name="parameters"></a>Parameter

*lst*<br/>
Wenn die Funktion zurückgibt, enthält Zeiger auf zwei CAnimationVariable-Objekte, die die X- und Y-Koordinaten darstellt.

##  <a name="getdefaultvalue"></a>  CAnimationPoint::GetDefaultValue

Gibt die Standardwerte für X und Y-Koordinaten.

```
CPoint GetDefaultValue();
```

### <a name="return-value"></a>Rückgabewert

Ein Punkt, der Standardwert enthält.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktion zum Abrufen von Standardwert, der zuvor vom Konstruktor oder SetDefaultValue festgelegt wurde.

##  <a name="getvalue"></a>  CAnimationPoint::GetValue

Gibt den aktuellen Wert zurück.

```
BOOL GetValue(CPoint& ptValue);
```

### <a name="parameters"></a>Parameter

*ptValue einen*<br/>
Die Ausgabe. Enthält den aktuellen Wert an, wenn diese Methode zurückgegeben wird.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn der aktuelle Wert erfolgreich abgerufen wurde. andernfalls "false".

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktion zum Abrufen von des aktuellen Wert der Animationspunkt. Wenn diese Methode fehlschlägt oder die zugrunde liegende COM-für X-Objekte und Y-Koordinaten nicht initialisiert wurden, enthält ptValue einen Standardwert, der zuvor im Konstruktor oder mit SetDefaultValue festgelegt wurde.

##  <a name="getx"></a>  CAnimationPoint::GetX

Ermöglicht den Zugriff auf die CAnimationVariable für X-Koordinate.

```
CAnimationVariable& GetX();
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf die gekapselte CAnimationVariable darstellt X zu koordinieren.

### <a name="remarks"></a>Hinweise

Sie können diese Methode, um direkten Zugriff auf zugrunde liegende CAnimationVariable darstellt X erhalten aufrufen zu koordinieren.

##  <a name="gety"></a>  CAnimationPoint::GetY

Bietet Zugriff auf CAnimationVariable für Y-Koordinate.

```
CAnimationVariable& GetY();
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf die gekapselte CAnimationVariable, Y-Koordinate darstellt.

### <a name="remarks"></a>Hinweise

Sie können diese Methode, um direkten Zugriff auf zugrunde liegende CAnimationVariable, Y-Koordinate darstellt erhalten aufrufen.

##  <a name="m_xvalue"></a>  CAnimationPoint::m_xValue

Die gekapselte Animationsvariable, die X steht für Koordinate des Animationspunkts.

```
CAnimationVariable m_xValue;
```

##  <a name="m_yvalue"></a>  CAnimationPoint::m_yValue

Die gekapselte Animationsvariable, die Y-Koordinate des Animationspunkts darstellt.

```
CAnimationVariable m_yValue;
```

##  <a name="operator_cpoint"></a>  CAnimationPoint::operator CPoint

Konvertiert einen CAnimationPoint in einen CPoint an.

```
operator CPoint();
```

### <a name="return-value"></a>Rückgabewert

Aktuelle Wert der CAnimationPoint als CPoint.

### <a name="remarks"></a>Hinweise

Diese Funktion ruft intern "GetValue". Wenn "GetValue" aus irgendeinem Grund ein Fehler auftritt, enthält der zurückgegebene Punkt Standardwerte für X und Y-Koordinaten.

##  <a name="operator_eq"></a>  CAnimationPoint::operator =

CAnimationPoint PtSrc zugewiesen haben.

```
void operator=(const CPoint& ptSrc);
```

### <a name="parameters"></a>Parameter

*ptSrc*<br/>
Bezieht sich auf CPoint oder Punkt.

### <a name="remarks"></a>Hinweise

CAnimationPoint PtSrc zugewiesen haben. Es wird empfohlen, zu tun ist, vor Beginn der Animation, da dieser Operator SetDefaultValue aufruft. der zugrunde liegenden COM erstellt Objekte für X- und Y-Koordinaten, wenn sie bereits erstellt wurden. Wenn Sie diese "Animation"-Objekts auf Ereignisse (ValueChanged oder IntegerValueChanged) abonniert haben, müssen Sie diese Ereignisse erneut zu aktivieren.

##  <a name="setdefaultvalue"></a>  CAnimationPoint::SetDefaultValue

Legt den Standardwert fest.

```
void SetDefaultValue(const POINT& ptDefault);
```

### <a name="parameters"></a>Parameter

*ptDefault*<br/>
Gibt den Standardwert für den Punkt an.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Funktion, um einen Standardwert auf "Animation"-Objekts festzulegen. Diese Methoden weist Standardwerte zu X und Y-Koordinaten des Animation an. Es erstellt auch zugrunde liegende COM-Objekte neu, wenn sie bereits erstellt wurden. Wenn Sie diese "Animation"-Objekts auf Ereignisse (ValueChanged oder IntegerValueChanged) abonniert haben, müssen Sie diese Ereignisse erneut zu aktivieren.

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
