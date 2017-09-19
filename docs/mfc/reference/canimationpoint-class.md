---
title: CAnimationPoint-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CAnimationPoint class
ms.assetid: 5dc4d46f-e695-4681-b15c-544b78b3e317
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: a6a59ad85928c199a8dd911b915076ffbd0b0e37
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="canimationpoint-class"></a>CAnimationPoint-Klasse
Implementiert die Funktion eines Punkts, dessen Koordinaten animiert werden können.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CAnimationPoint : public CAnimationBaseObject;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationPoint::CAnimationPoint](#canimationpoint)|Überladen. Erstellt CAnimationPoint-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationPoint::AddTransition](#addtransition)|Fügt Übergänge für X- und Y-Koordinaten.|  
|[CAnimationPoint::GetDefaultValue](#getdefaultvalue)|Gibt die Standardwerte für X und Y-Koordinaten.|  
|[CAnimationPoint::GetValue](#getvalue)|Gibt den aktuellen Wert zurück.|  
|[CAnimationPoint::GetX](#getx)|Bietet Zugriff auf CAnimationVariable für X-Koordinate.|  
|[CAnimationPoint::GetY](#gety)|Bietet Zugriff auf CAnimationVariable für Y-Koordinate.|  
|[CAnimationPoint::SetDefaultValue](#setdefaultvalue)|Legt den Standardwert fest.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationPoint::GetAnimationVariableList](#getanimationvariablelist)|Fügt die gekapselten Animationsvariablen in eine Liste. (Überschreibt [CAnimationBaseObject:: GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationPoint::operator CPoint](#operator_cpoint)|Konvertiert einen CAnimationPoint in einen CPoint.|  
|[CAnimationPoint::operator =](#operator_eq)|Weist CAnimationPoint PtSrc zu.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationPoint::m_xValue](#m_xvalue)|Die gekapselte Animationsvariable, die X steht für-Koordinate Animationspunkts.|  
|[CAnimationPoint::m_yValue](#m_yvalue)|Die gekapselte Animationsvariable, die Y-Koordinate des Animationspunkts darstellt.|  
  
## <a name="remarks"></a>Hinweise  
 Die CAnimationPoint-Klasse kapselt zwei CAnimationVariable-Objekte und kann in Clientanwendungen einen Zeitpunkt darstellen. Diese Klasse können Sie z. B. eine Position eines beliebigen Objekts auf dem Bildschirm (z. B. Textzeichenfolge, Kreis, Punkte usw.) animieren. Zum Verwenden dieser Klasse in der Anwendung nur ein Objekt dieser Klasse instanziieren, Animationscontroller AddAnimationObject hinzufügen und rufen Sie AddTransition für jeden Übergang auf angewendet werden X und/oder Y-Koordinaten.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 `CAnimationPoint`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxanimationcontroller.h  
  
##  <a name="addtransition"></a>CAnimationPoint::AddTransition  
 Fügt Übergänge für X- und Y-Koordinaten.  
  
```  
void AddTransition(
    CBaseTransition* pXTransition,  
    CBaseTransition* pYTransition);
```  
  
### <a name="parameters"></a>Parameter  
 `pXTransition`  
 Ein Zeiger auf Übergang für X-Koordinaten.  
  
 `pYTransition`  
 Ein Zeiger auf Übergang für Y-Koordinate.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion können Sie die angegebenen Übergänge hinzuzufügen, der internen Liste von Übergängen, die auf Animationsvariablen angewendet werden, für X und Y-Koordinaten. Wenn Sie Übergänge hinzufügen, werden sie nicht sofort angewendet und in einer internen Liste gespeichert. Übergänge werden angewendet (einem Storyboard für einen bestimmten Wert hinzugefügt) Wenn Sie CAnimationController:: AnimateGroup aufrufen. Wenn Sie keinen Übergang auf eine der Koordinaten anwenden müssen, können Sie NULL übergeben.  
  
##  <a name="canimationpoint"></a>CAnimationPoint::CAnimationPoint  
 Erstellt CAnimationPoint-Objekt.  
  
```  
CAnimationPoint();

 
CAnimationPoint(
    const CPoint& ptDefault,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `ptDefault`  
 Gibt die Standardpunktkoordinaten.  
  
 `nGroupID`  
 Gibt die Gruppen-ID.  
  
 `nObjectID`  
 Gibt die Objekt-ID.  
  
 `dwUserData`  
 Gibt die benutzerdefinierten Daten.  
  
### <a name="remarks"></a>Hinweise  
 Erstellt CAnimationPoint-Objekt mit Standardeigenschaften: Standardpunktkoordinaten, Gruppen-ID und Objekt-ID werden auf 0 festgelegt.  
  
##  <a name="getanimationvariablelist"></a>CAnimationPoint::GetAnimationVariableList  
 Fügt die gekapselten Animationsvariablen in eine Liste.  
  
```  
virtual void GetAnimationVariableList(CList<CAnimationVariable*, CAnimationVariable*>& lst);
```  
  
### <a name="parameters"></a>Parameter  
 `lst`  
 Wenn die Funktion zurückgibt, enthält Zeiger auf zwei CAnimationVariable-Objekte, die die X- und Y-Koordinaten darstellt.  
  
##  <a name="getdefaultvalue"></a>CAnimationPoint::GetDefaultValue  
 Gibt die Standardwerte für X und Y-Koordinaten.  
  
```  
CPoint GetDefaultValue();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Punkt, der Standardwert enthält.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um den Standardwert abzurufen, der zuvor vom Konstruktor oder mit SetDefaultValue festgelegt wurde.  
  
##  <a name="getvalue"></a>CAnimationPoint::GetValue  
 Gibt den aktuellen Wert zurück.  
  
```  
BOOL GetValue(CPoint& ptValue);
```  
  
### <a name="parameters"></a>Parameter  
 `ptValue`  
 Die Ausgabe. Enthält den aktuellen Wert an, wenn diese Methode zurückgegeben wird.  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn der aktuelle Wert erfolgreich abgerufen wurde. andernfalls FALSE.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um den aktuellen Wert der Animationspunkt abzurufen. Wenn diese Methode fehlschlägt oder zugrunde liegende COM-für X-Objekte und Y-Koordinaten nicht initialisiert wurden, enthält ptValue einen Standardwert, der zuvor im Konstruktor oder mit SetDefaultValue festgelegt wurde.  
  
##  <a name="getx"></a>CAnimationPoint::GetX  
 Bietet Zugriff auf CAnimationVariable für X-Koordinate.  
  
```  
CAnimationVariable& GetX();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf gekapselte CAnimationVariable, X darstellt koordinieren.  
  
### <a name="remarks"></a>Hinweise  
 Sie können diese Methode, um direkten Zugriff auf die zugrunde liegende CAnimationVariable darstellt X erhalten aufrufen zu koordinieren.  
  
##  <a name="gety"></a>CAnimationPoint::GetY  
 Bietet Zugriff auf CAnimationVariable für Y-Koordinate.  
  
```  
CAnimationVariable& GetY();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf gekapselte CAnimationVariable, die Y-Koordinate darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um direkten Zugriff auf zugrunde liegende CAnimationVariable, die Y-Koordinate darstellt.  
  
##  <a name="m_xvalue"></a>CAnimationPoint::m_xValue  
 Die gekapselte Animationsvariable, die X steht für-Koordinate Animationspunkts.  
  
```  
CAnimationVariable m_xValue;  
```  
  
##  <a name="m_yvalue"></a>CAnimationPoint::m_yValue  
 Die gekapselte Animationsvariable, die Y-Koordinate des Animationspunkts darstellt.  
  
```  
CAnimationVariable m_yValue;  
```  
  
##  <a name="operator_cpoint"></a>CAnimationPoint::operator CPoint  
 Konvertiert einen CAnimationPoint in einen CPoint.  
  
```  
operator CPoint();
```   
  
### <a name="return-value"></a>Rückgabewert  
 Aktueller Wert von CAnimationPoint als CPoint.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ruft intern GetValue. Wenn GetValue aus irgendeinem Grund fehlschlägt, enthält der zurückgegebene Punkt Standardwerte für X und Y-Koordinaten.  
  
##  <a name="operator_eq"></a>CAnimationPoint::operator =  
 Weist CAnimationPoint PtSrc zu.  
  
```  
void operator=(const CPoint& ptSrc);
```  
  
### <a name="parameters"></a>Parameter  
 `ptSrc`  
 Verweist auf CPoint oder POINT.  
  
### <a name="remarks"></a>Hinweise  
 Weist CAnimationPoint PtSrc zu. Es wird empfohlen, zu diesem Zweck vor Beginn der Animation, da dieser Operator SetDefaultValue aufruft der zugrunde liegenden COM erstellt Objekte für X- und Y-Koordinaten, wenn sie bereits erstellt wurden. Wenn Sie dieses Animationsobjekt Ereignisse (ValueChanged oder IntegerValueChanged) abonniert haben, müssen Sie diese Ereignisse erneut aktivieren.  
  
##  <a name="setdefaultvalue"></a>CAnimationPoint::SetDefaultValue  
 Legt den Standardwert fest.  
  
```  
void SetDefaultValue(const POINT& ptDefault);
```  
  
### <a name="parameters"></a>Parameter  
 `ptDefault`  
 Gibt den Standardwert für den Punkt.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, um einen Standardwert auf Animationsobjekt festzulegen. Diese Methoden weist Standardwerte zu X und Y-Koordinaten des Animationspunkts. Auch neu zugrunde liegende COM-Objekte, wenn sie bereits erstellt wurden. Wenn Sie dieses Animationsobjekt Ereignisse (ValueChanged oder IntegerValueChanged) abonniert haben, müssen Sie diese Ereignisse erneut aktivieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

