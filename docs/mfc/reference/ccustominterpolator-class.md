---
title: CCustomInterpolator-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- CCustomInterpolator class
ms.assetid: 28d85595-989a-40a3-b003-e0e38437a94d
caps.latest.revision: 17
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
ms.sourcegitcommit: 73410ae17465880f455e5b15026f6cc010803c19
ms.openlocfilehash: 4d0b38543092dc68c2527f7e1385712164faf996
ms.lasthandoff: 02/24/2017

---
# <a name="ccustominterpolator-class"></a>CCustomInterpolator-Klasse
Implementiert einen einfachen Interpolator.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CCustomInterpolator;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CCustomInterpolator::CCustomInterpolator](#ccustominterpolator)|Überladen. Ein benutzerdefinierter Interpolator-Objekt erstellt und initialisiert Dauer und Geschwindigkeit mit angegebenen Werten.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CCustomInterpolator::GetDependencies](#getdependencies)|Ruft die Interpolator Abhängigkeiten ab.|  
|[CCustomInterpolator::GetDuration](#getduration)|Ruft die Dauer des Interpolators ab.|  
|[CCustomInterpolator::GetFinalValue](#getfinalvalue)|Ruft den endgültigen Wert zu dem der Interpolator führt.|  
|[CCustomInterpolator:: Init](#init)|Initialisiert Dauer und endgültigen Wert.|  
|[CCustomInterpolator::InterpolateValue](#interpolatevalue)|Interpoliert den Wert an einem angegebenen Offset.|  
|[CCustomInterpolator::InterpolateVelocity](#interpolatevelocity)|Interpoliert die Geschwindigkeit bei einem angegebenen offset|  
|[CCustomInterpolator::SetDuration](#setduration)|Legt die Dauer des Interpolators fest.|  
|[CCustomInterpolator::SetInitialValueAndVelocity](#setinitialvalueandvelocity)|Anfangswert und die Geschwindigkeit des Interpolators festgelegt.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CCustomInterpolator::m_currentValue](#m_currentvalue)|Der interpolierten Wert.|  
|[CCustomInterpolator::m_currentVelocity](#m_currentvelocity)|Die interpolierte Geschwindigkeit.|  
|[CCustomInterpolator::m_duration](#m_duration)|Die Dauer des Übergangs.|  
|[CCustomInterpolator::m_finalValue](#m_finalvalue)|Der Endwert einer Variablen am Ende des Übergangs.|  
|[CCustomInterpolator::m_initialValue](#m_initialvalue)|Der Wert der Variablen am Anfang des Übergangs.|  
|[CCustomInterpolator::m_initialVelocity](#m_initialvelocity)|Die Geschwindigkeit der Variablen am Anfang des Übergangs.|  
  
## <a name="remarks"></a>Hinweise  
 Leiten Sie eine Klasse von CCustomInterpolator ab, und überschreiben Sie alle erforderlichen Methoden, um einen benutzerdefinierten Interpolationsalgorithmus implementieren. Ein Zeiger auf diese Klasse sollte an CCustomTransitions als Parameter übergeben werden.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CCustomInterpolator`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxanimationcontroller.h  
  
##  <a name="ccustominterpolator"></a>CCustomInterpolator::CCustomInterpolator  
 Erstellt einen benutzerdefinierten Interpolator-Objekt und legt alle Werte auf den Standardwert 0.  
  
```  
CCustomInterpolator();

 
CCustomInterpolator(
    UI_ANIMATION_SECONDS duration,  
    DOUBLE finalValue);
```  
  
### <a name="parameters"></a>Parameter  
 `duration`  
 Die Dauer des Übergangs.  
  
 `finalValue`  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie CCustomInterpolator:: init, um die Dauer und den Endwert später im Code zu initialisieren.  
  
##  <a name="getdependencies"></a>CCustomInterpolator::GetDependencies  
 Ruft die Interpolator Abhängigkeiten ab.  
  
```  
virtual BOOL GetDependencies(
    UI_ANIMATION_DEPENDENCIES* initialValueDependencies,  
    UI_ANIMATION_DEPENDENCIES* initialVelocityDependencies,  
    UI_ANIMATION_DEPENDENCIES* durationDependencies);
```  
  
### <a name="parameters"></a>Parameter  
 `initialValueDependencies`  
 Die Ausgabe. Aspekte des Interpolators, die abhängig von der Anfangswert an SetInitialValueAndVelocity übergebenen.  
  
 `initialVelocityDependencies`  
 Die Ausgabe. Aspekte des Interpolators, die abhängig von der ursprünglichen Geschwindigkeit an SetInitialValueAndVelocity übergebenen.  
  
 `durationDependencies`  
 Die Ausgabe. Aspekte des Interpolators, die abhängig von der Dauer, die an SetDuration übergeben werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Grundlegende Implementierung gibt immer "true". Gibt FALSE in der überschriebenen Implementierung zurück, wenn das Ereignis fehlschlagen soll.  
  
##  <a name="getduration"></a>CCustomInterpolator::GetDuration  
 Ruft die Dauer des Interpolators ab.  
  
```  
virtual BOOL GetDuration(UI_ANIMATION_SECONDS* duration);
```  
  
### <a name="parameters"></a>Parameter  
 `duration`  
 Die Ausgabe. Die Dauer des Übergangs, in Sekunden.  
  
### <a name="return-value"></a>Rückgabewert  
 Grundlegende Implementierung gibt immer "true". Gibt FALSE in der überschriebenen Implementierung zurück, wenn das Ereignis fehlschlagen soll.  
  
##  <a name="getfinalvalue"></a>CCustomInterpolator::GetFinalValue  
 Ruft den endgültigen Wert zu dem der Interpolator führt.  
  
```  
virtual BOOL GetFinalValue(DOUBLE* value);
```  
  
### <a name="parameters"></a>Parameter  
 `value`  
 Die Ausgabe. Der Endwert einer Variablen am Ende des Übergangs.  
  
### <a name="return-value"></a>Rückgabewert  
 Grundlegende Implementierung gibt immer "true". Gibt FALSE in der überschriebenen Implementierung zurück, wenn das Ereignis fehlschlagen soll.  
  
##  <a name="init"></a>CCustomInterpolator:: Init  
 Initialisiert Dauer und endgültigen Wert.  
  
```  
void Init(
    UI_ANIMATION_SECONDS duration,  
    DOUBLE finalValue);
```  
  
### <a name="parameters"></a>Parameter  
 `duration`  
 Die Dauer des Übergangs.  
  
 `finalValue`  
 Der Endwert einer Variablen am Ende des Übergangs.  
  
##  <a name="interpolatevalue"></a>CCustomInterpolator::InterpolateValue  
 Interpoliert den Wert an einem angegebenen Offset.  
  
```  
virtual BOOL InterpolateValue(
    UI_ANIMATION_SECONDS */,  
    DOUBLE* value);
```  
  
### <a name="parameters"></a>Parameter  
 `value`  
 Die Ausgabe. Der interpolierten Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 Grundlegende Implementierung gibt immer "true". Gibt FALSE in der überschriebenen Implementierung zurück, wenn das Ereignis fehlschlagen soll.  
  
##  <a name="interpolatevelocity"></a>CCustomInterpolator::InterpolateVelocity  
 Interpoliert die Geschwindigkeit bei einem angegebenen offset  
  
```  
virtual BOOL InterpolateVelocity(
    UI_ANIMATION_SECONDS */,  
    DOUBLE* velocity);
```  
  
### <a name="parameters"></a>Parameter  
 `velocity`  
 Die Ausgabe. Die Geschwindigkeit der Variable beim Offset.  
  
### <a name="return-value"></a>Rückgabewert  
 Grundlegende Implementierung gibt immer "true". Gibt FALSE in der überschriebenen Implementierung zurück, wenn das Ereignis fehlschlagen soll.  
  
##  <a name="m_currentvalue"></a>CCustomInterpolator::m_currentValue  
 Der interpolierten Wert.  
  
```  
DOUBLE m_currentValue;  
```  
  
##  <a name="m_currentvelocity"></a>CCustomInterpolator::m_currentVelocity  
 Die interpolierte Geschwindigkeit.  
  
```  
DOUBLE m_currentVelocity;  
```  
  
##  <a name="m_duration"></a>CCustomInterpolator::m_duration  
 Die Dauer des Übergangs.  
  
```  
UI_ANIMATION_SECONDS m_duration;  
```  
  
##  <a name="m_finalvalue"></a>CCustomInterpolator::m_finalValue  
 Der Endwert einer Variablen am Ende des Übergangs.  
  
```  
DOUBLE m_finalValue;  
```  
  
##  <a name="m_initialvalue"></a>CCustomInterpolator::m_initialValue  
 Der Wert der Variablen am Anfang des Übergangs.  
  
```  
DOUBLE m_initialValue;  
```  
  
##  <a name="m_initialvelocity"></a>CCustomInterpolator::m_initialVelocity  
 Die Geschwindigkeit der Variablen am Anfang des Übergangs.  
  
```  
DOUBLE m_initialVelocity;  
```  
  
##  <a name="setduration"></a>CCustomInterpolator::SetDuration  
 Legt die Dauer des Interpolators fest.  
  
```  
virtual BOOL SetDuration(UI_ANIMATION_SECONDS duration);
```  
  
### <a name="parameters"></a>Parameter  
 `duration`  
 Die Dauer des Übergangs.  
  
### <a name="return-value"></a>Rückgabewert  
 Grundlegende Implementierung gibt immer "true". Gibt FALSE in der überschriebenen Implementierung zurück, wenn das Ereignis fehlschlagen soll.  
  
##  <a name="setinitialvalueandvelocity"></a>CCustomInterpolator::SetInitialValueAndVelocity  
 Anfangswert und die Geschwindigkeit des Interpolators festgelegt.  
  
```  
virtual BOOL SetInitialValueAndVelocity(
    DOUBLE initialValue,  
    DOUBLE initialVelocity);
```  
  
### <a name="parameters"></a>Parameter  
 `initialValue`  
 Der Wert der Variablen am Anfang des Übergangs.  
  
 `initialVelocity`  
 Die Geschwindigkeit der Variablen am Anfang des Übergangs.  
  
### <a name="return-value"></a>Rückgabewert  
 Die grundlegende Implementierung gibt immer "true". Gibt FALSE in der überschriebenen Implementierung zurück, wenn das Ereignis fehlschlagen soll.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

