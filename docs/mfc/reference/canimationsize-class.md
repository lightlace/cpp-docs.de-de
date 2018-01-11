---
title: CAnimationSize-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimationSize
- AFXANIMATIONCONTROLLER/CAnimationSize
- AFXANIMATIONCONTROLLER/CAnimationSize::CAnimationSize
- AFXANIMATIONCONTROLLER/CAnimationSize::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationSize::GetCX
- AFXANIMATIONCONTROLLER/CAnimationSize::GetCY
- AFXANIMATIONCONTROLLER/CAnimationSize::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationSize::GetValue
- AFXANIMATIONCONTROLLER/CAnimationSize::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationSize::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationSize::m_cxValue
- AFXANIMATIONCONTROLLER/CAnimationSize::m_cyValue
dev_langs: C++
helpviewer_keywords:
- CAnimationSize [MFC], CAnimationSize
- CAnimationSize [MFC], AddTransition
- CAnimationSize [MFC], GetCX
- CAnimationSize [MFC], GetCY
- CAnimationSize [MFC], GetDefaultValue
- CAnimationSize [MFC], GetValue
- CAnimationSize [MFC], SetDefaultValue
- CAnimationSize [MFC], GetAnimationVariableList
- CAnimationSize [MFC], m_cxValue
- CAnimationSize [MFC], m_cyValue
ms.assetid: ea06d1b5-502c-44a3-82ca-8bd6ba6a9364
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e2acbdad3ec5b08ef5d83b3a6cfdb2eadd3c0e17
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="canimationsize-class"></a>CAnimationSize-Klasse
Implementiert die Funktion eines Größenobjekts, dessen Dimensionen animiert werden können.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CAnimationSize : public CAnimationBaseObject;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationSize::CAnimationSize](#canimationsize)|Überladen. Erstellt eine Animation Größe-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationSize::AddTransition](#addtransition)|Fügt die Übergänge für Breite und Höhe.|  
|[CAnimationSize::GetCX](#getcx)|Bietet Zugriff auf CAnimationVariable, Breite darstellt.|  
|[CAnimationSize::GetCY](#getcy)|Bietet Zugriff auf CAnimationVariable, Höhe darstellt.|  
|[CAnimationSize::GetDefaultValue](#getdefaultvalue)|Gibt die Standardwerte für die Breite und Höhe.|  
|[CAnimationSize::GetValue](#getvalue)|Gibt den aktuellen Wert zurück.|  
|[CAnimationSize::SetDefaultValue](#setdefaultvalue)|Legt den Standardwert fest.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationSize::GetAnimationVariableList](#getanimationvariablelist)|Legt die gekapselten Animationsvariablen in einer Liste an. (Überschreibt [CAnimationBaseObject:: GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationSize::operator CSize](#operator_csize)|Konvertiert einen CAnimationSize in einen CSize.|  
|[CAnimationSize::operator =](#operator_eq)|CAnimationSize SzSrc zugewiesen.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CAnimationSize::m_cxValue](#m_cxvalue)|Die gekapselte Animationsvariable, die Breite des Animation darstellt.|  
|[CAnimationSize::m_cyValue](#m_cyvalue)|Die gekapselte Animationsvariable, die Höhe der Animationsgröße darstellt.|  
  
## <a name="remarks"></a>Hinweise  
 CAnimationSize-Klasse kapselt zwei CAnimationVariable-Objekte und kann in Anwendungen eine Größe dar. Beispielsweise können diese Klasse zum Animieren einer Größe von zwei dimensionalen Objekt auf dem Bildschirm (Rechteck, Steuerelement usw.). Zum Verwenden dieser Klasse in der Anwendung einfach instanziieren Sie ein Objekt dieser Klasse, Animationscontroller AddAnimationObject hinzugefügt, und rufen Sie AddTransition für jeden Übergang auf Breite und/oder Höhe angewendet werden soll.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 `CAnimationSize` 
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxanimationcontroller.h  
  
##  <a name="addtransition"></a>CAnimationSize::AddTransition  
 Fügt die Übergänge für Breite und Höhe.  
  
```  
void AddTransition(
    CBaseTransition* pCXTransition,  
    CBaseTransition* pCYTransition);
```  
  
### <a name="parameters"></a>Parameter  
 `pCXTransition`  
 Ein Zeiger auf den Übergang für Breite.  
  
 `pCYTransition`  
 Ein Zeiger auf den Übergang für die Höhe.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um die interne Liste der Übergänge anzuwendende Animationsvariablen für Breite und Höhe der angegebenen Übergänge hinzuzufügen. Wenn Sie Übergänge hinzufügen, werden sie nicht sofort angewendet und in einer internen Liste gespeichert. Übergänge werden angewendet (ein Storyboard für einen bestimmten Wert hinzugefügt) beim CAnimationController:: AnimateGroup aufrufen. Wenn Sie keinen Übergang auf eine der Dimensionen anwenden müssen, können Sie NULL übergeben.  
  
##  <a name="canimationsize"></a>CAnimationSize::CAnimationSize  
 Erstellt eine Animation Größe-Objekt.  
  
```  
CAnimationSize();

 
CAnimationSize(
    const CSize& szDefault,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `szDefault`  
 Gibt die Standardgröße an.  
  
 `nGroupID`  
 Gibt Gruppen-ID.  
  
 `nObjectID`  
 Gibt die Objekt-ID.  
  
 `dwUserData`  
 Gibt die benutzerdefinierten Daten.  
  
### <a name="remarks"></a>Hinweise  
 Das Objekt erstellt wird, mit Standardwerten für Breite, Höhe, Objekt-ID und Gruppen-ID, die auf 0 festgelegt werden. Sie können später mithilfe von SetDefaultValue und SetID zur Laufzeit geändert werden.  
  
##  <a name="getanimationvariablelist"></a>CAnimationSize::GetAnimationVariableList  
 Legt die gekapselten Animationsvariablen in einer Liste an.  
  
```  
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*, 
    CAnimationVariable*>& lst);
```  
  
### <a name="parameters"></a>Parameter  
 `lst`  
 Wenn die Funktion zurückgibt, enthält Zeiger auf zwei CAnimationVariable-Objekte, die die Breite und Höhe darstellt.  
  
##  <a name="getcx"></a>CAnimationSize::GetCX  
 Bietet Zugriff auf CAnimationVariable, Breite darstellt.  
  
```  
CAnimationVariable& GetCX();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf gekapselte CAnimationVariable, Breite darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Abrufen von direkten Zugriffs auf die zugrunde liegende CAnimationVariable, Breite darstellt.  
  
##  <a name="getcy"></a>CAnimationSize::GetCY  
 Bietet Zugriff auf CAnimationVariable, Höhe darstellt.  
  
```  
CAnimationVariable& GetCY();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf gekapselte CAnimationVariable, Höhe darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Abrufen von direkten Zugriffs auf die zugrunde liegende CAnimationVariable Höhe darstellt.  
  
##  <a name="getdefaultvalue"></a>CAnimationSize::GetDefaultValue  
 Gibt die Standardwerte für die Breite und Höhe.  
  
```  
CSize GetDefaultValue();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein CSize-Objekt, das Standardwerte enthält.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird zum Abrufen von Standardwert, der zuvor vom Konstruktor oder mit SetDefaultValue festgelegt wurde.  
  
##  <a name="getvalue"></a>CAnimationSize::GetValue  
 Gibt den aktuellen Wert zurück.  
  
```  
BOOL GetValue(CSize& szValue);
```  
  
### <a name="parameters"></a>Parameter  
 `szValue`  
 Die Ausgabe. Enthält den aktuellen Wert an, wenn diese Methode zurückgegeben wird.  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn der aktuelle Wert erfolgreich abgerufen wurde. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird zum Abrufen des aktuellen Wert der Animationsgröße. Wenn diese Methode fehlschlägt oder zugrunde liegenden COM-Objekte für die Breite und Größe nicht initialisiert wurden, enthält szValue einen Standardwert, der zuvor im Konstruktor oder mit SetDefaultValue festgelegt wurde.  
  
##  <a name="m_cxvalue"></a>CAnimationSize::m_cxValue  
 Die gekapselte Animationsvariable, die Breite des Animation darstellt.  
  
```  
CAnimationVariable m_cxValue;  
```  
  
##  <a name="m_cyvalue"></a>CAnimationSize::m_cyValue  
 Die gekapselte Animationsvariable, die Höhe der Animationsgröße darstellt.  
  
```  
CAnimationVariable m_cyValue;  
```  
  
##  <a name="operator_csize"></a>CAnimationSize::operator CSize  
 Konvertiert einen CAnimationSize in einen CSize.  
  
```  
operator CSize();
```   
  
### <a name="return-value"></a>Rückgabewert  
 Aktuelle Wert der Animationsgröße als CSize.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ruft intern GetValue. Wenn GetValue aus irgendeinem Grund fehlschlägt, enthält die zurückgegebene Größe Standardwerte für Breite und Höhe.  
  
##  <a name="operator_eq"></a>CAnimationSize::operator =  
 CAnimationSize SzSrc zugewiesen.  
  
```  
void operator=(const CSize& szSrc);
```  
  
### <a name="parameters"></a>Parameter  
 `szSrc`  
 Bezieht sich auf CSize "oder" Größe ".  
  
### <a name="remarks"></a>Hinweise  
 CAnimationSize SzSrc zugewiesen. Es wird empfohlen, vor Beginn der Animation, dazu werden sollen, da dieser Operator SetDefaultValue aufruft, die die zugrunde liegenden COM-Objekte für die Breite und Höhe neu erstellt, wenn sie erstellt wurden. Wenn Sie dieses Animationsobjekt auf Ereignisse (ValueChanged oder IntegerValueChanged) abonniert haben, müssen Sie diese Ereignisse erneut zu aktivieren.  
  
##  <a name="setdefaultvalue"></a>CAnimationSize::SetDefaultValue  
 Legt den Standardwert fest.  
  
```  
void SetDefaultValue(const CSize& szDefault);
```  
  
### <a name="parameters"></a>Parameter  
 `szDefault`  
 Gibt neue Standardgröße an.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, um einen Standardwert zum Animationsobjekts festzulegen. Diese Methoden weisen Standardwerte zu Breite und Höhe der Animationsgröße. Zugrunde liegende COM-Objekte erstellt auch neu, wenn sie erstellt wurden. Wenn Sie dieses Animationsobjekt auf Ereignisse (ValueChanged oder IntegerValueChanged) abonniert haben, müssen Sie diese Ereignisse erneut zu aktivieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)
