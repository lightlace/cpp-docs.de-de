---
title: CAnimationPoint-Klasse | Microsoft Docs
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
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 4a770b6508067913aec51b8b3878f33e30eed4bb
ms.openlocfilehash: 81e4221ca2aa9ee653d391d9808666628010a325
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

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
|[CAnimationPoint::AddTransition](#addtransition)|Fügt der Übergänge für X und Y-Koordinaten.|  
|[CAnimationPoint::GetDefaultValue](#getdefaultvalue)|Gibt die Standardwerte für X und Y-Koordinaten.|  
|[CAnimationPoint::GetValue](#getvalue)|Gibt den aktuellen Wert zurück.|  
|[CAnimationPoint::GetX](#getx)|Bietet Zugriff auf CAnimationVariable für X-Koordinate.|  
|[CAnimationPoint::GetY](#gety)|Bietet Zugriff auf CAnimationVariable für Y-Koordinate.|  
|[CAnimationPoint::SetDefaultValue](#setdefaultvalue)|Legt den Standardwert fest.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationPoint::GetAnimationVariableList](#getanimationvariablelist)|Legt die gekapselten Animationsvariablen in einer Liste an. (Überschreibt [CAnimationBaseObject:: GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationPoint::operator CPoint](#operator_cpoint)|Konvertiert einen CAnimationPoint in einen CPoint.|  
|[CAnimationPoint::operator =](#operator_eq)|CAnimationPoint PtSrc zugewiesen.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationPoint::m_xValue](#m_xvalue)|Die gekapselte Animationsvariable, X darstellt,-Koordinate des Animation an.|  
|[CAnimationPoint::m_yValue](#m_yvalue)|Die gekapselte Animationsvariable, die Y-Koordinate des Animationspunkts darstellt.|  
  
## <a name="remarks"></a>Hinweise  
 CAnimationPoint-Klasse kapselt zwei CAnimationVariable-Objekte und kann in Anwendungen einen Zeitpunkt darstellen. Diese Klasse können Sie z. B. animieren eine Position eines Objekts auf dem Bildschirm (z. B. Textzeichenfolge, Kreis, Punkt usw.). Um diese Klasse in der Anwendung zu verwenden, nur instanziieren Sie ein Objekt dieser Klasse, Animationscontroller AddAnimationObject hinzugefügt und rufen Sie AddTransition für jeden Übergang anzuwendende X und/oder Y-Koordinaten.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 `CAnimationPoint`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxanimationcontroller.h  
  
##  <a name="addtransition"></a>CAnimationPoint::AddTransition  
 Fügt der Übergänge für X und Y-Koordinaten.  
  
```  
void AddTransition(
    CBaseTransition* pXTransition,  
    CBaseTransition* pYTransition);
```  
  
### <a name="parameters"></a>Parameter  
 `pXTransition`  
 Ein Zeiger auf den Übergang für X-Koordinaten.  
  
 `pYTransition`  
 Ein Zeiger auf den Übergang für Y-Koordinate.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird zum Hinzufügen von angegebenen Übergänge, die interne Liste der Übergänge anzuwendende Animationsvariablen für X und Y-Koordinaten. Wenn Sie Übergänge hinzufügen, werden sie nicht sofort angewendet und in einer internen Liste gespeichert. Übergänge werden angewendet (ein Storyboard für einen bestimmten Wert hinzugefügt) beim CAnimationController:: AnimateGroup aufrufen. Wenn Sie keinen Übergang auf eine der Koordinaten anwenden müssen, können Sie NULL übergeben.  
  
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
 Gibt an Standardeinstellung Punktkoordinaten.  
  
 `nGroupID`  
 Gibt Gruppen-ID.  
  
 `nObjectID`  
 Gibt die Objekt-ID.  
  
 `dwUserData`  
 Gibt die benutzerdefinierten Daten.  
  
### <a name="remarks"></a>Hinweise  
 Erstellt CAnimationPoint-Objekt mit Standardeigenschaften: Punktkoordinaten Standard, die Gruppen-ID und Objekt-ID werden auf 0 festgelegt.  
  
##  <a name="getanimationvariablelist"></a>CAnimationPoint::GetAnimationVariableList  
 Legt die gekapselten Animationsvariablen in einer Liste an.  
  
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
 Mit dieser Funktion wird zum Abrufen von Standardwert, der zuvor vom Konstruktor oder mit SetDefaultValue festgelegt wurde.  
  
##  <a name="getvalue"></a>CAnimationPoint::GetValue  
 Gibt den aktuellen Wert zurück.  
  
```  
BOOL GetValue(CPoint& ptValue);
```  
  
### <a name="parameters"></a>Parameter  
 `ptValue`  
 Die Ausgabe. Enthält den aktuellen Wert an, wenn diese Methode zurückgegeben wird.  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn der aktuelle Wert erfolgreich abgerufen wurde. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird zum Abrufen des aktuellen Wert der Animation zeigen. Wenn diese Methode fehlschlägt oder die zugrunde liegende COM-für X-Objekte und Y-Koordinaten nicht initialisiert wurden, enthält ptValue einen Standardwert, der zuvor im Konstruktor oder mit SetDefaultValue festgelegt wurde.  
  
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
 Ein Verweis auf gekapselte CAnimationVariable, Y-Koordinate darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Abrufen von direkten Zugriffs auf die zugrunde liegende CAnimationVariable, Y-Koordinate darstellt.  
  
##  <a name="m_xvalue"></a>CAnimationPoint::m_xValue  
 Die gekapselte Animationsvariable, X darstellt,-Koordinate des Animation an.  
  
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
 CAnimationPoint PtSrc zugewiesen.  
  
```  
void operator=(const CPoint& ptSrc);
```  
  
### <a name="parameters"></a>Parameter  
 `ptSrc`  
 Bezieht sich auf CPoint oder POINT.  
  
### <a name="remarks"></a>Hinweise  
 CAnimationPoint PtSrc zugewiesen. Es wird empfohlen, zu diesem Zweck vor Beginn der Animation, da dieser Operator SetDefaultValue aufruft der zugrunde liegenden COM erstellt Objekte für X- und Y-Koordinaten, wenn sie erstellt wurden. Wenn Sie dieses Animationsobjekt auf Ereignisse (ValueChanged oder IntegerValueChanged) abonniert haben, müssen Sie diese Ereignisse erneut zu aktivieren.  
  
##  <a name="setdefaultvalue"></a>CAnimationPoint::SetDefaultValue  
 Legt den Standardwert fest.  
  
```  
void SetDefaultValue(const POINT& ptDefault);
```  
  
### <a name="parameters"></a>Parameter  
 `ptDefault`  
 Gibt den Standardwert für den Punkt an.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, um einen Standardwert zum Animationsobjekts festzulegen. Diese Methoden wird zugewiesen, die Standardwerte zu X und Y-Koordinaten des Animationspunkts. Zugrunde liegende COM-Objekte erstellt auch neu, wenn sie erstellt wurden. Wenn Sie dieses Animationsobjekt auf Ereignisse (ValueChanged oder IntegerValueChanged) abonniert haben, müssen Sie diese Ereignisse erneut zu aktivieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

