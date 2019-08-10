---
title: CInterpolatorBase-Klasse
ms.date: 11/04/2016
f1_keywords:
- CInterpolatorBase
- AFXANIMATIONCONTROLLER/CInterpolatorBase
- AFXANIMATIONCONTROLLER/CInterpolatorBase::CInterpolatorBase
- AFXANIMATIONCONTROLLER/CInterpolatorBase::CreateInstance
- AFXANIMATIONCONTROLLER/CInterpolatorBase::GetDependencies
- AFXANIMATIONCONTROLLER/CInterpolatorBase::GetDuration
- AFXANIMATIONCONTROLLER/CInterpolatorBase::GetFinalValue
- AFXANIMATIONCONTROLLER/CInterpolatorBase::InterpolateValue
- AFXANIMATIONCONTROLLER/CInterpolatorBase::InterpolateVelocity
- AFXANIMATIONCONTROLLER/CInterpolatorBase::SetCustomInterpolator
- AFXANIMATIONCONTROLLER/CInterpolatorBase::SetDuration
- AFXANIMATIONCONTROLLER/CInterpolatorBase::SetInitialValueAndVelocity
helpviewer_keywords:
- CInterpolatorBase [MFC], CInterpolatorBase
- CInterpolatorBase [MFC], CreateInstance
- CInterpolatorBase [MFC], GetDependencies
- CInterpolatorBase [MFC], GetDuration
- CInterpolatorBase [MFC], GetFinalValue
- CInterpolatorBase [MFC], InterpolateValue
- CInterpolatorBase [MFC], InterpolateVelocity
- CInterpolatorBase [MFC], SetCustomInterpolator
- CInterpolatorBase [MFC], SetDuration
- CInterpolatorBase [MFC], SetInitialValueAndVelocity
ms.assetid: bbc3dce7-8398-47f9-b97e-e4fd2d737232
ms.openlocfilehash: d1fc675b1014ab9a099e8310b52b7458f2bff65f
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2019
ms.locfileid: "68916204"
---
# <a name="cinterpolatorbase-class"></a>CInterpolatorBase-Klasse

Implementiert einen Rückruf, der von der Animations-API aufgerufen wird, wenn ein neuer Wert einer Animationsvariablen berechnet werden muss.

## <a name="syntax"></a>Syntax

```
class CInterpolatorBase : public CUIAnimationInterpolatorBase<CInterpolatorBase>;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[Cinterpolatorbase:: cinterpolatorbase](#cinterpolatorbase)|Erstellt das `CInterpolatorBase` -Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CInterpolatorBase::CreateInstance](#createinstance)|Erstellt eine Instanz von `CInterpolatorBase` und speichert einen Zeiger auf einen benutzerdefinierten Interpolator, der Ereignisse behandelt.|
|[CInterpolatorBase::GetDependencies](#getdependencies)|Ruft die Abhängigkeiten des interpolators ab. (Überschreibt `CUIAnimationInterpolatorBase::GetDependencies`.)|
|[CInterpolatorBase::GetDuration](#getduration)|Ruft die Dauer des interpolators ab. (Überschreibt `CUIAnimationInterpolatorBase::GetDuration`.)|
|[CInterpolatorBase::GetFinalValue](#getfinalvalue)|Ruft den Endwert ab, zu dem der interpolators führt. (Überschreibt `CUIAnimationInterpolatorBase::GetFinalValue`.)|
|[CInterpolatorBase::InterpolateValue](#interpolatevalue)|Interpoliert den Wert an einem angegebenen Offset (überschreibt `CUIAnimationInterpolatorBase::InterpolateValue`.)|
|[CInterpolatorBase::InterpolateVelocity](#interpolatevelocity)|Interpoliert die Geschwindigkeit an einem angegebenen Offset (überschreibt `CUIAnimationInterpolatorBase::InterpolateVelocity`.)|
|[CInterpolatorBase::SetCustomInterpolator](#setcustominterpolator)|Speichert einen Zeiger auf einen benutzerdefinierten Interpolator, der Ereignisse behandelt.|
|[CInterpolatorBase::SetDuration](#setduration)|Legt die Dauer des interpolators fest ( `CUIAnimationInterpolatorBase::SetDuration`außer Kraft setzungen).|
|[CInterpolatorBase::SetInitialValueAndVelocity](#setinitialvalueandvelocity)|Legt den Anfangswert und die Geschwindigkeit des interpolators fest. (Überschreibt `CUIAnimationInterpolatorBase::SetInitialValueAndVelocity`.)|

## <a name="remarks"></a>Hinweise

Dieser Handler wird erstellt und an das `IUIAnimationTransitionFactory::CreateTransition` -Objekt `CCustomTransition` übermittelt, wenn ein-Objekt als Teil des Animations Initialisierungs Prozesses ( `CAnimationController::AnimateGroup`gestartet von) erstellt wird. Normalerweise müssen Sie diese Klasse nicht direkt verwenden, sondern nur alle Ereignisse zu einer `CCustomInterpolator`von abgeleiteten Klasse, deren Zeiger an den Konstruktor von `CCustomTransition`übergeben wird.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CUIAnimationCallbackBase`

`CUIAnimationInterpolatorBase`

`CInterpolatorBase`

## <a name="requirements"></a>Anforderungen

**Header:** afxanimationcontroller.h

##  <a name="cinterpolatorbase"></a>Cinterpolatorbase:: cinterpolatorbase

Erstellt das cinterpolatorbase-Objekt.

```
CInterpolatorBase();
```

##  <a name="createinstance"></a>Cinterpolatorbase:: kreateingestance

Erstellt eine Instanz von cinterpolatorbase und speichert einen Zeiger auf einen benutzerdefinierten Interpolator, der Ereignisse behandelt.

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CCustomInterpolator* pInterpolator,
    IUIAnimationInterpolator** ppHandler);
```

### <a name="parameters"></a>Parameter

*pInterpolator*<br/>
Ein Zeiger auf den benutzerdefinierten Interpolator.

*ppHandler*<br/>
Ausgeben. Enthält einen Zeiger auf die cinterpolatorbase-Instanz, wenn die Funktion zurückgibt.

### <a name="return-value"></a>Rückgabewert

##  <a name="getdependencies"></a>Cinterpolatorbase:: getabhängigkeiten

Ruft die Abhängigkeiten des interpolators ab.

```
IFACEMETHOD(GetDependencies)(
    __out UI_ANIMATION_DEPENDENCIES* initialValueDependencies,
    __out UI_ANIMATION_DEPENDENCIES* initialVelocityDependencies,
    __out UI_ANIMATION_DEPENDENCIES* durationDependencies);
```

### <a name="parameters"></a>Parameter

*initialValueDependencies*<br/>
Ausgeben. Aspekte des interpolators, die vom Anfangswert abhängig sind, der an setinitialvalueandvelocity weitergegeben wurde.

*initialVelocityDependencies*<br/>
Ausgeben. Aspekte des interpolators, die von der anfänglichen Geschwindigkeit abhängig sind, die an setinitialvalueandvelocity weitergegeben wurde.

*durationabhängigkeiten*<br/>
Ausgeben. Aspekte des interpolators, die von der Dauer abhängen, die an setduration weitergegeben wurde.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ausgeführt wird, wird S_OK zurückgegeben. Sie gibt E_FAIL zurück, wenn ccustominterpolator nicht festgelegt ist, oder die benutzerdefinierte Implementierung gibt false aus der getdependen-Methode zurück.

##  <a name="getduration"></a>Cinterpolatorbase:: getduration

Ruft die Dauer des interpolators ab.

```
IFACEMETHOD(GetDuration)(__out UI_ANIMATION_SECONDS* duration);
```

### <a name="parameters"></a>Parameter

*auf*<br/>
Ausgeben. Die Dauer des Übergangs in Sekunden.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ausgeführt wird, wird S_OK zurückgegeben. Sie gibt E_FAIL zurück, wenn ccustominterpolator nicht festgelegt ist, oder die benutzerdefinierte Implementierung gibt false aus der getduration-Methode zurück.

##  <a name="getfinalvalue"></a>Cinterpolatorbase:: getfinalvalue

Ruft den Endwert ab, zu dem der interpolators führt.

```
IFACEMETHOD(GetFinalValue)(__out DOUBLE* value);
```

### <a name="parameters"></a>Parameter

*value*<br/>
Ausgeben. Der endgültige Wert einer Variablen am Ende des Übergangs.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ausgeführt wird, wird S_OK zurückgegeben. Sie gibt E_FAIL zurück, wenn ccustominterpolator nicht festgelegt ist, oder die benutzerdefinierte Implementierung gibt false aus der getfinalvalue-Methode zurück.

##  <a name="interpolatevalue"></a>Cinterpolatorbase:: InterpolateValue

Interpoliert den Wert an einem angegebenen Offset.

```
IFACEMETHOD(InterpolateValue)(
    __in UI_ANIMATION_SECONDS offset,
    __out DOUBLE* value);
```

### <a name="parameters"></a>Parameter

*offset*<br/>
Der Offset vom Beginn des Übergangs. Der Offset ist immer größer oder gleich 0 (null) und kleiner als die Dauer des Übergangs. Diese Methode wird nicht aufgerufen, wenn die Dauer des Übergangs 0 (null) ist.

*value*<br/>
Ausgeben. Der interpoliert-Wert.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ausgeführt wird, wird S_OK zurückgegeben. Sie gibt E_FAIL zurück, wenn ccustominterpolator nicht festgelegt ist, oder die benutzerdefinierte Implementierung gibt false von der InterpolateValue-Methode zurück.

##  <a name="interpolatevelocity"></a>Cinterpolatorbase:: interpolatevelocity

Interpoliert die Geschwindigkeit bei einem angegebenen Offset.

```
IFACEMETHOD(InterpolateVelocity)(
    __in UI_ANIMATION_SECONDS offset,
    __out DOUBLE* velocity);
```

### <a name="parameters"></a>Parameter

*offset*<br/>
Der Offset vom Beginn des Übergangs. Der Offset ist immer größer oder gleich 0 (null) und kleiner oder gleich der Dauer des Übergangs. Diese Methode wird nicht aufgerufen, wenn die Dauer des Übergangs 0 (null) ist.

*velocity*<br/>
Ausgeben. Die Geschwindigkeit der Variablen am Offset.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ausgeführt wird, wird S_OK zurückgegeben. Sie gibt E_FAIL zurück, wenn ccustominterpolator nicht festgelegt ist, oder die benutzerdefinierte Implementierung gibt false von der interpolatevelocity-Methode zurück.

##  <a name="setcustominterpolator"></a>Cinterpolatorbase:: setcustominterpolator

Speichert einen Zeiger auf einen benutzerdefinierten Interpolator, der Ereignisse behandelt.

```
void SetCustomInterpolator(CCustomInterpolator* pInterpolator);
```

### <a name="parameters"></a>Parameter

*pInterpolator*<br/>
Ein Zeiger auf den benutzerdefinierten Interpolator.

##  <a name="setduration"></a>Cinterpolatorbase:: setduration

Legt die Dauer des interpolators fest.

```
IFACEMETHOD(SetDuration)(__in UI_ANIMATION_SECONDS duration);
```

### <a name="parameters"></a>Parameter

*auf*<br/>
Die Dauer des Übergangs.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ausgeführt wird, wird S_OK zurückgegeben. Sie gibt E_FAIL zurück, wenn ccustominterpolator nicht festgelegt ist, oder die benutzerdefinierte Implementierung gibt false aus der setduration-Methode zurück.

##  <a name="setinitialvalueandvelocity"></a>Cinterpolatorbase:: setinitialvalueandvelocity

Legt den Anfangswert und die Geschwindigkeit des interpolators fest.

```
IFACEMETHOD(SetInitialValueAndVelocity)(
    __in DOUBLE initialValue,
    __in DOUBLE initialVelocity);
```

### <a name="parameters"></a>Parameter

*initialValue*<br/>
Der Wert der Variablen am Anfang des Übergangs.

*initialVelocity*<br/>
Die Geschwindigkeit der Variablen am Anfang des Übergangs.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ausgeführt wird, wird S_OK zurückgegeben. Sie gibt E_FAIL zurück, wenn ccustominterpolator nicht festgelegt ist, oder die benutzerdefinierte Implementierung gibt false aus der setinitialvalueandvelocity-Methode zurück.

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
