---
title: CInterpolatorBase-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- CInterpolatorBase class
ms.assetid: bbc3dce7-8398-47f9-b97e-e4fd2d737232
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 44c67eef38b34a2a3cf677b42a40304c01668b42
ms.lasthandoff: 02/24/2017

---
# <a name="cinterpolatorbase-class"></a>CInterpolatorBase-Klasse
Implementiert einen Rückruf, der von der Animations-API aufgerufen wird, wenn ein neuer Wert einer Animationsvariablen berechnet werden muss.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CInterpolatorBase : public CUIAnimationInterpolatorBase<CInterpolatorBase>;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CInterpolatorBase::CInterpolatorBase](#cinterpolatorbase)|Erstellt die `CInterpolatorBase` Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CInterpolatorBase::CreateInstance](#createinstance)|Erstellt eine Instanz des `CInterpolatorBase` und speichert einen Zeiger auf benutzerdefinierten Interpolator, der Ereignisse behandelt.|  
|[CInterpolatorBase::GetDependencies](#getdependencies)|Ruft die Interpolator Abhängigkeiten ab. (Überschreibt `CUIAnimationInterpolatorBase::GetDependencies`.)|  
|[CInterpolatorBase::GetDuration](#getduration)|Ruft die Dauer des Interpolators ab. (Überschreibt `CUIAnimationInterpolatorBase::GetDuration`.)|  
|[CInterpolatorBase::GetFinalValue](#getfinalvalue)|Ruft den endgültigen Wert zu dem der Interpolator führt. (Überschreibt `CUIAnimationInterpolatorBase::GetFinalValue`.)|  
|[CInterpolatorBase::InterpolateValue](#interpolatevalue)|Interpoliert den Wert bei einem angegebenen Offset (überschreibt `CUIAnimationInterpolatorBase::InterpolateValue`.)|  
|[CInterpolatorBase::InterpolateVelocity](#interpolatevelocity)|Interpoliert die Geschwindigkeit bei einem angegebenen Offset (überschreibt `CUIAnimationInterpolatorBase::InterpolateVelocity`.)|  
|[CInterpolatorBase::SetCustomInterpolator](#setcustominterpolator)|Speichert einen Zeiger auf benutzerdefinierten Interpolator, der Ereignisse behandelt.|  
|[CInterpolatorBase::SetDuration](#setduration)|Legt die Dauer des Interpolators (überschreibt `CUIAnimationInterpolatorBase::SetDuration`.)|  
|[CInterpolatorBase::SetInitialValueAndVelocity](#setinitialvalueandvelocity)|Anfangswert und die Geschwindigkeit des Interpolators festgelegt. (Überschreibt `CUIAnimationInterpolatorBase::SetInitialValueAndVelocity`.)|  
  
## <a name="remarks"></a>Hinweise  
 Dieser Handler wird erstellt und an `IUIAnimationTransitionFactory::CreateTransition` bei einem `CCustomTransition` Objekt als Teil der Animation Initialisierungsprozess erstellt wird (gestartet, indem `CAnimationController::AnimateGroup`). In der Regel müssen Sie nicht diese Klasse direkt verwenden, es einfach weitergeleitet wird, alle Ereignisse in einem `CCustomInterpolator`-abgeleitete Klasse, deren Zeiger wird an den Konstruktor übergeben `CCustomTransition`.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationInterpolatorBase`  
  
 `CInterpolatorBase`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxanimationcontroller.h  
  
##  <a name="cinterpolatorbase"></a>CInterpolatorBase::CInterpolatorBase  
 Erstellt das CInterpolatorBase-Objekt.  
  
```  
CInterpolatorBase();
```  
  
##  <a name="createinstance"></a>CInterpolatorBase::CreateInstance  
 Erstellt eine Instanz von CInterpolatorBase und speichert einen Zeiger auf benutzerdefinierten Interpolator, der Ereignisse behandelt.  
  
```  
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CCustomInterpolator* pInterpolator,  
    IUIAnimationInterpolator** ppHandler);
```  
  
### <a name="parameters"></a>Parameter  
 `pInterpolator`  
 Ein Zeiger auf benutzerdefinierten Interpolator.  
  
 `ppHandler`  
 Die Ausgabe. Einen Zeiger auf die Instanz von CInterpolatorBase enthält, wenn die Funktion zurückgibt.  
  
### <a name="return-value"></a>Rückgabewert  
  
##  <a name="getdependencies"></a>CInterpolatorBase::GetDependencies  
 Ruft die Interpolator Abhängigkeiten ab.  
  
```  
IFACEMETHOD(GetDependencies)(
    __out UI_ANIMATION_DEPENDENCIES* initialValueDependencies,
    __out UI_ANIMATION_DEPENDENCIES* initialVelocityDependencies,
    __out UI_ANIMATION_DEPENDENCIES* durationDependencies);
```  
  
### <a name="parameters"></a>Parameter  
 `initialValueDependencies`  
 Die Ausgabe. Aspekte des Interpolators, die abhängig von der Anfangswert an SetInitialValueAndVelocity übergebenen.  
  
 `initialVelocityDependencies`  
 Die Ausgabe. Aspekte des Interpolators, die abhängig von der ursprünglichen Geschwindigkeit an SetInitialValueAndVelocity übergebenen.  
  
 `durationDependencies`  
 Die Ausgabe. Aspekte des Interpolators, die abhängig von der Dauer, die an SetDuration übergeben werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Gibt E_FAIL zurück, wenn CCustomInterpolator nicht festgelegt oder die benutzerdefinierte Implementierung gibt FALSE von der GetDependencies-Methode zurück.  
  
##  <a name="getduration"></a>CInterpolatorBase::GetDuration  
 Ruft die Dauer des Interpolators ab.  
  
```  
IFACEMETHOD(GetDuration)(__out UI_ANIMATION_SECONDS* duration);
```  
  
### <a name="parameters"></a>Parameter  
 `duration`  
 Die Ausgabe. Die Dauer des Übergangs, in Sekunden.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Gibt E_FAIL zurück, wenn CCustomInterpolator nicht festgelegt oder die benutzerdefinierte Implementierung gibt FALSE von der GetDuration-Methode zurück.  
  
##  <a name="getfinalvalue"></a>CInterpolatorBase::GetFinalValue  
 Ruft den endgültigen Wert zu dem der Interpolator führt.  
  
```  
IFACEMETHOD(GetFinalValue)(__out DOUBLE* value);
```  
  
### <a name="parameters"></a>Parameter  
 `value`  
 Die Ausgabe. Der Endwert einer Variablen am Ende des Übergangs.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Gibt E_FAIL zurück, wenn CCustomInterpolator nicht festgelegt oder die benutzerdefinierte Implementierung gibt FALSE, aus der GetFinalValue-Methode zurück.  
  
##  <a name="interpolatevalue"></a>CInterpolatorBase::InterpolateValue  
 Interpoliert den Wert bei einem angegebenen offset  
  
```  
IFACEMETHOD(InterpolateValue)(
  __in UI_ANIMATION_SECONDS offset, 
  __out DOUBLE* value);
```  
  
### <a name="parameters"></a>Parameter  
 `offset`  
 Der Offset vom Beginn des Übergangs. Der Offset ist immer größer als oder gleich&0; und kleiner als die Dauer des Übergangs. Diese Methode wird nicht aufgerufen, wenn die Dauer des Übergangs&0; (null) ist.  
  
 `value`  
 Die Ausgabe. Der interpolierten Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Gibt E_FAIL zurück, wenn CCustomInterpolator nicht festgelegt oder die benutzerdefinierte Implementierung gibt FALSE von der InterpolateValue-Methode zurück.  
  
##  <a name="interpolatevelocity"></a>CInterpolatorBase::InterpolateVelocity  
 Interpoliert die Geschwindigkeit bei einem angegebenen offset  
  
```  
IFACEMETHOD(InterpolateVelocity)(
  __in UI_ANIMATION_SECONDS offset,
  __out DOUBLE* velocity);
```  
  
### <a name="parameters"></a>Parameter  
 `offset`  
 Der Offset vom Beginn des Übergangs. Der Offset ist immer größer als oder gleich&0; und kleiner oder gleich der Dauer des Übergangs. Diese Methode wird nicht aufgerufen, wenn die Dauer des Übergangs&0; (null) ist.  
  
 `velocity`  
 Die Ausgabe. Die Geschwindigkeit der Variable beim Offset.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Gibt E_FAIL zurück, wenn CCustomInterpolator nicht festgelegt oder die benutzerdefinierte Implementierung gibt FALSE, aus der InterpolateVelocity-Methode zurück.  
  
##  <a name="setcustominterpolator"></a>CInterpolatorBase::SetCustomInterpolator  
 Speichert einen Zeiger auf benutzerdefinierten Interpolator, der Ereignisse behandelt.  
  
```  
void SetCustomInterpolator(CCustomInterpolator* pInterpolator);
```  
  
### <a name="parameters"></a>Parameter  
 `pInterpolator`  
 Ein Zeiger auf benutzerdefinierten Interpolator.  
  
##  <a name="setduration"></a>CInterpolatorBase::SetDuration  
 Legt die Dauer des Interpolators  
  
```  
IFACEMETHOD(SetDuration)(__in UI_ANIMATION_SECONDS duration);
```  
  
### <a name="parameters"></a>Parameter  
 `duration`  
 Die Dauer des Übergangs.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Gibt E_FAIL zurück, wenn CCustomInterpolator nicht festgelegt oder die benutzerdefinierte Implementierung gibt FALSE von der SetDuration-Methode zurück.  
  
##  <a name="setinitialvalueandvelocity"></a>CInterpolatorBase::SetInitialValueAndVelocity  
 Anfangswert und die Geschwindigkeit des Interpolators festgelegt.  
  
```  
IFACEMETHOD(SetInitialValueAndVelocity)(
  __in DOUBLE initialValue, 
  __in DOUBLE initialVelocity);
```  
  
### <a name="parameters"></a>Parameter  
 `initialValue`  
 Der Wert der Variablen am Anfang des Übergangs.  
  
 `initialVelocity`  
 Die Geschwindigkeit der Variablen am Anfang des Übergangs.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Gibt E_FAIL zurück, wenn CCustomInterpolator nicht festgelegt oder die benutzerdefinierte Implementierung gibt FALSE von der SetInitialValueAndVelocity-Methode zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

