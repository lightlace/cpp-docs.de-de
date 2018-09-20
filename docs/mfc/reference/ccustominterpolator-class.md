---
title: CCustomInterpolator-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CCustomInterpolator
- AFXANIMATIONCONTROLLER/CCustomInterpolator
- AFXANIMATIONCONTROLLER/CCustomInterpolator::CCustomInterpolator
- AFXANIMATIONCONTROLLER/CCustomInterpolator::GetDependencies
- AFXANIMATIONCONTROLLER/CCustomInterpolator::GetDuration
- AFXANIMATIONCONTROLLER/CCustomInterpolator::GetFinalValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::Init
- AFXANIMATIONCONTROLLER/CCustomInterpolator::InterpolateValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::InterpolateVelocity
- AFXANIMATIONCONTROLLER/CCustomInterpolator::SetDuration
- AFXANIMATIONCONTROLLER/CCustomInterpolator::SetInitialValueAndVelocity
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_currentValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_currentVelocity
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_duration
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_finalValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_initialValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_initialVelocity
dev_langs:
- C++
helpviewer_keywords:
- CCustomInterpolator [MFC], CCustomInterpolator
- CCustomInterpolator [MFC], GetDependencies
- CCustomInterpolator [MFC], GetDuration
- CCustomInterpolator [MFC], GetFinalValue
- CCustomInterpolator [MFC], Init
- CCustomInterpolator [MFC], InterpolateValue
- CCustomInterpolator [MFC], InterpolateVelocity
- CCustomInterpolator [MFC], SetDuration
- CCustomInterpolator [MFC], SetInitialValueAndVelocity
- CCustomInterpolator [MFC], m_currentValue
- CCustomInterpolator [MFC], m_currentVelocity
- CCustomInterpolator [MFC], m_duration
- CCustomInterpolator [MFC], m_finalValue
- CCustomInterpolator [MFC], m_initialValue
- CCustomInterpolator [MFC], m_initialVelocity
ms.assetid: 28d85595-989a-40a3-b003-e0e38437a94d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 175af6d9fdd02e24aaa9caae663db51c7dd4167a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46432820"
---
# <a name="ccustominterpolator-class"></a>CCustomInterpolator-Klasse

Implementiert einen einfachen Interpolator.

## <a name="syntax"></a>Syntax

```
class CCustomInterpolator;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CCustomInterpolator::CCustomInterpolator](#ccustominterpolator)|Überladen. Ein benutzerdefinierter Interpolator-Objekt erstellt und initialisiert, Dauer und die Geschwindigkeit mit angegebenen Werten.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CCustomInterpolator::GetDependencies](#getdependencies)|Ruft die Interpolators-Abhängigkeiten ab.|
|[CCustomInterpolator::GetDuration](#getduration)|Ruft die Dauer des Interpolators ab.|
|[CCustomInterpolator::GetFinalValue](#getfinalvalue)|Ruft ab, der endgültige Wert, der Interpolator führt.|
|[CCustomInterpolator:: Init](#init)|Initialisiert die Dauer und die endgültigen Wert.|
|[CCustomInterpolator::InterpolateValue](#interpolatevalue)|Führt den Wert am angegebenen Offset.|
|[CCustomInterpolator::InterpolateVelocity](#interpolatevelocity)|Die Geschwindigkeit an einem angegebenen Offset interpoliert|
|[CCustomInterpolator::SetDuration](#setduration)|Legt die Dauer des Interpolators fest.|
|[CCustomInterpolator::SetInitialValueAndVelocity](#setinitialvalueandvelocity)|Anfangswert und Geschwindigkeit des Interpolators festgelegt.|

### <a name="protected-data-members"></a>Geschützte Datenmember

|name|Beschreibung|
|----------|-----------------|
|[CCustomInterpolator::m_currentValue](#m_currentvalue)|Der interpolierten Wert.|
|[CCustomInterpolator::m_currentVelocity](#m_currentvelocity)|Die interpolierte Geschwindigkeit.|
|[CCustomInterpolator::m_duration](#m_duration)|Die Dauer des Übergangs.|
|[CCustomInterpolator::m_finalValue](#m_finalvalue)|Der endgültige Wert einer Variablen am Ende des Übergangs.|
|[CCustomInterpolator::m_initialValue](#m_initialvalue)|Der Wert der Variablen zu Beginn des Übergangs.|
|[CCustomInterpolator::m_initialVelocity](#m_initialvelocity)|Die Geschwindigkeit der Variable zu Beginn des Übergangs.|

## <a name="remarks"></a>Hinweise

CCustomInterpolator leiten Sie eine Klasse ab, und überschreiben Sie alle erforderlichen Methoden, um einen benutzerdefinierten Interpolationsalgorithmus implementieren. Ein Zeiger auf diese Klasse sollte als Parameter an CCustomTransition übergeben werden.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CCustomInterpolator`

## <a name="requirements"></a>Anforderungen

**Header:** afxanimationcontroller.h

##  <a name="ccustominterpolator"></a>  CCustomInterpolator::CCustomInterpolator

Erstellt ein benutzerdefinierter Interpolator-Objekt, und legt alle Werte auf den Standardwert 0.

```
CCustomInterpolator();


CCustomInterpolator(
    UI_ANIMATION_SECONDS duration,
    DOUBLE finalValue);
```

### <a name="parameters"></a>Parameter

*Dauer*<br/>
Die Dauer des Übergangs.

*finalValue*

### <a name="remarks"></a>Hinweise

Verwenden Sie CCustomInterpolator:: init, um die Dauer und die endgültigen Wert später im Code zu initialisieren.

##  <a name="getdependencies"></a>  CCustomInterpolator::GetDependencies

Ruft die Interpolators-Abhängigkeiten ab.

```
virtual BOOL GetDependencies(
    UI_ANIMATION_DEPENDENCIES* initialValueDependencies,
    UI_ANIMATION_DEPENDENCIES* initialVelocityDependencies,
    UI_ANIMATION_DEPENDENCIES* durationDependencies);
```

### <a name="parameters"></a>Parameter

*initialValueDependencies*<br/>
Die Ausgabe. Aspekte des Interpolators, die von den ursprünglichen Wert abhängen, die an SetInitialValueAndVelocity übergeben werden.

*initialVelocityDependencies*<br/>
Die Ausgabe. Aspekte des Interpolators, die die ursprüngliche Geschwindigkeit abhängig, die an SetInitialValueAndVelocity übergeben werden.

*durationDependencies*<br/>
Die Ausgabe. Aspekte des Interpolators, die abhängig von der Dauer, die an SetDuration übergeben werden.

### <a name="return-value"></a>Rückgabewert

Grundlegende Implementierung gibt immer "true". Gibt "false" aus überschriebene Implementierung zurück, wenn Sie das Ereignis fehlschlägt möchten.

##  <a name="getduration"></a>  CCustomInterpolator::GetDuration

Ruft die Dauer des Interpolators ab.

```
virtual BOOL GetDuration(UI_ANIMATION_SECONDS* duration);
```

### <a name="parameters"></a>Parameter

*Dauer*<br/>
Die Ausgabe. Die Dauer des Übergangs, in Sekunden.

### <a name="return-value"></a>Rückgabewert

Grundlegende Implementierung gibt immer "true". Gibt "false" aus überschriebene Implementierung zurück, wenn Sie das Ereignis fehlschlägt möchten.

##  <a name="getfinalvalue"></a>  CCustomInterpolator::GetFinalValue

Ruft ab, der endgültige Wert, der Interpolator führt.

```
virtual BOOL GetFinalValue(DOUBLE* value);
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
Die Ausgabe. Der endgültige Wert einer Variablen am Ende des Übergangs.

### <a name="return-value"></a>Rückgabewert

Grundlegende Implementierung gibt immer "true". Gibt "false" aus überschriebene Implementierung zurück, wenn Sie das Ereignis fehlschlägt möchten.

##  <a name="init"></a>  CCustomInterpolator:: Init

Initialisiert die Dauer und die endgültigen Wert.

```
void Init(
    UI_ANIMATION_SECONDS duration,
    DOUBLE finalValue);
```

### <a name="parameters"></a>Parameter

*Dauer*<br/>
Die Dauer des Übergangs.

*finalValue*<br/>
Der endgültige Wert einer Variablen am Ende des Übergangs.

##  <a name="interpolatevalue"></a>  CCustomInterpolator::InterpolateValue

Führt den Wert am angegebenen Offset.

```
virtual BOOL InterpolateValue(
    UI_ANIMATION_SECONDS */,
    DOUBLE* value);
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
Die Ausgabe. Der interpolierten Wert.

### <a name="return-value"></a>Rückgabewert

Grundlegende Implementierung gibt immer "true". Gibt "false" aus überschriebene Implementierung zurück, wenn Sie das Ereignis fehlschlägt möchten.

##  <a name="interpolatevelocity"></a>  CCustomInterpolator::InterpolateVelocity

Die Geschwindigkeit an einem angegebenen Offset interpoliert

```
virtual BOOL InterpolateVelocity(
    UI_ANIMATION_SECONDS */,
    DOUBLE* velocity);
```

### <a name="parameters"></a>Parameter

*Geschwindigkeit*<br/>
Die Ausgabe. Die Geschwindigkeit der Variablen mit dem Offset.

### <a name="return-value"></a>Rückgabewert

Grundlegende Implementierung gibt immer "true". Gibt "false" aus überschriebene Implementierung zurück, wenn Sie das Ereignis fehlschlägt möchten.

##  <a name="m_currentvalue"></a>  CCustomInterpolator::m_currentValue

Der interpolierten Wert.

```
DOUBLE m_currentValue;
```

##  <a name="m_currentvelocity"></a>  CCustomInterpolator::m_currentVelocity

Die interpolierte Geschwindigkeit.

```
DOUBLE m_currentVelocity;
```

##  <a name="m_duration"></a>  CCustomInterpolator::m_duration

Die Dauer des Übergangs.

```
UI_ANIMATION_SECONDS m_duration;
```

##  <a name="m_finalvalue"></a>  CCustomInterpolator::m_finalValue

Der endgültige Wert einer Variablen am Ende des Übergangs.

```
DOUBLE m_finalValue;
```

##  <a name="m_initialvalue"></a>  CCustomInterpolator::m_initialValue

Der Wert der Variablen zu Beginn des Übergangs.

```
DOUBLE m_initialValue;
```

##  <a name="m_initialvelocity"></a>  CCustomInterpolator::m_initialVelocity

Die Geschwindigkeit der Variable zu Beginn des Übergangs.

```
DOUBLE m_initialVelocity;
```

##  <a name="setduration"></a>  CCustomInterpolator::SetDuration

Legt die Dauer des Interpolators fest.

```
virtual BOOL SetDuration(UI_ANIMATION_SECONDS duration);
```

### <a name="parameters"></a>Parameter

*Dauer*<br/>
Die Dauer des Übergangs.

### <a name="return-value"></a>Rückgabewert

Grundlegende Implementierung gibt immer "true". Gibt "false" aus überschriebene Implementierung zurück, wenn Sie das Ereignis fehlschlägt möchten.

##  <a name="setinitialvalueandvelocity"></a>  CCustomInterpolator::SetInitialValueAndVelocity

Anfangswert und Geschwindigkeit des Interpolators festgelegt.

```
virtual BOOL SetInitialValueAndVelocity(
    DOUBLE initialValue,
    DOUBLE initialVelocity);
```

### <a name="parameters"></a>Parameter

*"InitialValue"*<br/>
Der Wert der Variablen zu Beginn des Übergangs.

*initialVelocity*<br/>
Die Geschwindigkeit der Variable zu Beginn des Übergangs.

### <a name="return-value"></a>Rückgabewert

Die grundlegende Implementierung gibt immer "true". Gibt "false" aus überschriebene Implementierung zurück, wenn Sie das Ereignis fehlschlägt möchten.

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
