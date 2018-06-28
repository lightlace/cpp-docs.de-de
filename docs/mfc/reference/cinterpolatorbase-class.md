---
title: CInterpolatorBase-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 81ad51fe00a0b205000b15a05ede9497850f488e
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2018
ms.locfileid: "37041272"
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
|[CInterpolatorBase::CInterpolatorBase](#cinterpolatorbase)|Erstellt die `CInterpolatorBase` Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CInterpolatorBase::CreateInstance](#createinstance)|Erstellt eine Instanz des `CInterpolatorBase` und speichert einen Zeiger auf benutzerdefinierten Interpolator, der Ereignisse behandelt.|  
|[CInterpolatorBase::GetDependencies](#getdependencies)|Ruft die Interpolators Abhängigkeiten ab. (Überschreibt `CUIAnimationInterpolatorBase::GetDependencies`.)|  
|[CInterpolatorBase::GetDuration](#getduration)|Ruft die Dauer des Interpolators ab. (Überschreibt `CUIAnimationInterpolatorBase::GetDuration`.)|  
|[CInterpolatorBase::GetFinalValue](#getfinalvalue)|Ruft den endgültigen Wert zu dem der Interpolator führt. (Überschreibt `CUIAnimationInterpolatorBase::GetFinalValue`.)|  
|[CInterpolatorBase::InterpolateValue](#interpolatevalue)|Interpoliert den Wert an einem angegebenen Offset (überschreibt `CUIAnimationInterpolatorBase::InterpolateValue`.)|  
|[CInterpolatorBase::InterpolateVelocity](#interpolatevelocity)|Interpoliert die Geschwindigkeit an einem angegebenen Offset (überschreibt `CUIAnimationInterpolatorBase::InterpolateVelocity`.)|  
|[CInterpolatorBase::SetCustomInterpolator](#setcustominterpolator)|Speichert einen Zeiger auf benutzerdefinierten Interpolator, der Ereignisse behandelt.|  
|[CInterpolatorBase::SetDuration](#setduration)|Legt die Dauer des Interpolators (Außerkraftsetzungen `CUIAnimationInterpolatorBase::SetDuration`.)|  
|[CInterpolatorBase::SetInitialValueAndVelocity](#setinitialvalueandvelocity)|Anfangswert und Geschwindigkeit des Interpolators festgelegt. (Überschreibt `CUIAnimationInterpolatorBase::SetInitialValueAndVelocity`.)|  
  
## <a name="remarks"></a>Hinweise  
 Dieser Handler erstellt und übergeben `IUIAnimationTransitionFactory::CreateTransition` bei einem `CCustomTransition` Objekt wird als Teil der Animation Initialisierungsprozess erstellt (gestartet, indem `CAnimationController::AnimateGroup`). In der Regel müssen Sie nicht direkt verwenden Sie diese Klasse, die es nur routs alle Ereignisse in einem `CCustomInterpolator`-abgeleitete Klasse, deren Zeiger wird, an den Konstruktor der übergeben `CCustomTransition`.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationInterpolatorBase`  
  
 `CInterpolatorBase`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxanimationcontroller.h  
  
##  <a name="cinterpolatorbase"></a>  CInterpolatorBase::CInterpolatorBase  
 Erstellt das CInterpolatorBase-Objekt.  
  
```  
CInterpolatorBase();
```  
  
##  <a name="createinstance"></a>  CInterpolatorBase::CreateInstance  
 Erstellt eine Instanz von CInterpolatorBase und speichert einen Zeiger auf benutzerdefinierten Interpolator, der Ereignisse behandelt.  
  
```  
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CCustomInterpolator* pInterpolator,  
    IUIAnimationInterpolator** ppHandler);
```  
  
### <a name="parameters"></a>Parameter  
 *pInterpolator*  
 Ein Zeiger auf benutzerdefinierten Interpolator.  
  
 *ppHandler*  
 Die Ausgabe. Einen Zeiger auf die Instanz von CInterpolatorBase enthält, wenn die Funktion zurückgibt.  
  
### <a name="return-value"></a>Rückgabewert  
  
##  <a name="getdependencies"></a>  CInterpolatorBase::GetDependencies  
 Ruft die Interpolators Abhängigkeiten ab.  
  
```  
IFACEMETHOD(GetDependencies)(
    __out UI_ANIMATION_DEPENDENCIES* initialValueDependencies,
    __out UI_ANIMATION_DEPENDENCIES* initialVelocityDependencies,
    __out UI_ANIMATION_DEPENDENCIES* durationDependencies);
```  
  
### <a name="parameters"></a>Parameter  
 *initialValueDependencies*  
 Die Ausgabe. Aspekte des Interpolators, die den anfänglichen Wert abhängig sind, die an SetInitialValueAndVelocity übergeben werden.  
  
 *initialVelocityDependencies*  
 Die Ausgabe. Aspekte des Interpolators, die von der ursprünglichen Geschwindigkeit abhängen, die an SetInitialValueAndVelocity übergeben werden.  
  
 *durationDependencies*  
 Die Ausgabe. Aspekte des Interpolators, von die die Dauer abhängen, die an SetDuration übergeben werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Es gibt E_FAIL zurück, wenn CCustomInterpolator nicht festgelegt oder die benutzerdefinierte Implementierung gibt "false", aus der GetDependencies-Methode zurück.  
  
##  <a name="getduration"></a>  CInterpolatorBase::GetDuration  
 Ruft die Dauer des Interpolators ab.  
  
```  
IFACEMETHOD(GetDuration)(__out UI_ANIMATION_SECONDS* duration);
```  
  
### <a name="parameters"></a>Parameter  
 *Dauer*  
 Die Ausgabe. Die Dauer des Übergangs, in Sekunden.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Es gibt E_FAIL zurück, wenn CCustomInterpolator nicht festgelegt oder die benutzerdefinierte Implementierung gibt "false", aus der GetDuration-Methode zurück.  
  
##  <a name="getfinalvalue"></a>  CInterpolatorBase::GetFinalValue  
 Ruft den endgültigen Wert zu dem der Interpolator führt.  
  
```  
IFACEMETHOD(GetFinalValue)(__out DOUBLE* value);
```  
  
### <a name="parameters"></a>Parameter  
 *Wert*  
 Die Ausgabe. Der endgültige Wert einer Variablen am Ende des Übergangs.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Es gibt E_FAIL zurück, wenn CCustomInterpolator nicht festgelegt oder die benutzerdefinierte Implementierung gibt "false", aus der GetFinalValue-Methode zurück.  
  
##  <a name="interpolatevalue"></a>  CInterpolatorBase::InterpolateValue  
 Den Wert mit einem bestimmten Offset interpoliert  
  
```  
IFACEMETHOD(InterpolateValue)(
  __in UI_ANIMATION_SECONDS offset, 
  __out DOUBLE* value);
```  
  
### <a name="parameters"></a>Parameter  
 *offset*  
 Der Offset vom Beginn des Übergangs. Der Offset ist immer größer als oder gleich 0 (null) und kleiner als die Dauer des Übergangs. Diese Methode wird nicht aufgerufen, wenn die Dauer des Übergangs 0 (null) ist.  
  
 *Wert*  
 Die Ausgabe. Den interpolierten Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Es gibt E_FAIL zurück, wenn CCustomInterpolator nicht festgelegt oder die benutzerdefinierte Implementierung gibt "false", aus der InterpolateValue-Methode zurück.  
  
##  <a name="interpolatevelocity"></a>  CInterpolatorBase::InterpolateVelocity  
 Die Geschwindigkeit an einem angegebenen Offset interpoliert  
  
```  
IFACEMETHOD(InterpolateVelocity)(
  __in UI_ANIMATION_SECONDS offset,
  __out DOUBLE* velocity);
```  
  
### <a name="parameters"></a>Parameter  
 *offset*  
 Der Offset vom Beginn des Übergangs. Der Offset ist immer größer als oder gleich 0 (null) und kleiner oder gleich der Dauer des Übergangs. Diese Methode wird nicht aufgerufen, wenn die Dauer des Übergangs 0 (null) ist.  
  
 *Geschwindigkeit*  
 Die Ausgabe. Die Geschwindigkeit der Animationsvariablen am Offset.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Es gibt E_FAIL zurück, wenn CCustomInterpolator nicht festgelegt oder die benutzerdefinierte Implementierung gibt "false", aus der InterpolateVelocity-Methode zurück.  
  
##  <a name="setcustominterpolator"></a>  CInterpolatorBase::SetCustomInterpolator  
 Speichert einen Zeiger auf benutzerdefinierten Interpolator, der Ereignisse behandelt.  
  
```  
void SetCustomInterpolator(CCustomInterpolator* pInterpolator);
```  
  
### <a name="parameters"></a>Parameter  
 *pInterpolator*  
 Ein Zeiger auf benutzerdefinierten Interpolator.  
  
##  <a name="setduration"></a>  CInterpolatorBase::SetDuration  
 Legt die Dauer des Interpolators  
  
```  
IFACEMETHOD(SetDuration)(__in UI_ANIMATION_SECONDS duration);
```  
  
### <a name="parameters"></a>Parameter  
 *Dauer*  
 Die Dauer des Übergangs.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Es gibt E_FAIL zurück, wenn CCustomInterpolator nicht festgelegt oder die benutzerdefinierte Implementierung gibt "false", aus der SetDuration-Methode zurück.  
  
##  <a name="setinitialvalueandvelocity"></a>  CInterpolatorBase::SetInitialValueAndVelocity  
 Anfangswert und Geschwindigkeit des Interpolators festgelegt.  
  
```  
IFACEMETHOD(SetInitialValueAndVelocity)(
  __in DOUBLE initialValue, 
  __in DOUBLE initialVelocity);
```  
  
### <a name="parameters"></a>Parameter  
 *initialValue*  
 Der Wert der Variablen zu Beginn des Übergangs.  
  
 *initialVelocity*  
 Die Geschwindigkeit der Variablen zu Beginn des Übergangs.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Es gibt E_FAIL zurück, wenn CCustomInterpolator nicht festgelegt oder die benutzerdefinierte Implementierung gibt "false", aus der SetInitialValueAndVelocity-Methode zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)
