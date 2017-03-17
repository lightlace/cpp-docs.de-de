---
title: CAnimationSize-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
dev_langs:
- C++
helpviewer_keywords:
- CAnimationSize class
ms.assetid: ea06d1b5-502c-44a3-82ca-8bd6ba6a9364
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
ms.openlocfilehash: 84b9ae3b81f72f6c0ae8e88f78357c29e8d82ffd
ms.lasthandoff: 02/24/2017

---
# <a name="canimationsize-class"></a>CAnimationSize-Klasse
Implementiert die Funktion eines Größenobjekts, dessen Dimensionen animiert werden können.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CAnimationSize : public CAnimationBaseObject;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationSize::CAnimationSize](#canimationsize)|Überladen. Erstellt ein Objekt der Animation Größe.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationSize::AddTransition](#addtransition)|Fügt Übergänge für Breite und Höhe.|  
|[CAnimationSize::GetCX](#getcx)|Bietet Zugriff auf CAnimationVariable, die Breite darstellt.|  
|[CAnimationSize::GetCY](#getcy)|Bietet Zugriff auf CAnimationVariable, die Höhe darstellt.|  
|[CAnimationSize::GetDefaultValue](#getdefaultvalue)|Gibt die Standardwerte für Breite und Höhe zurück.|  
|[CAnimationSize::GetValue](#getvalue)|Gibt den aktuellen Wert zurück.|  
|[CAnimationSize::SetDefaultValue](#setdefaultvalue)|Legt den Standardwert fest.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationSize::GetAnimationVariableList](#getanimationvariablelist)|Fügt die gekapselten Animationsvariablen in eine Liste. (Überschreibt [CAnimationBaseObject:: GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationSize::operator CSize](#operator_csize)|Konvertiert einen CAnimationSize in einen CSize.|  
|[CAnimationSize::operator =](#operator_eq)|Weist CAnimationSize SzSrc zu.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationSize::m_cxValue](#m_cxvalue)|Die gekapselte Animationsvariable, die Breite der Animationsgröße darstellt.|  
|[CAnimationSize::m_cyValue](#m_cyvalue)|Die gekapselte Animationsvariable, die Höhe der Animationsgröße darstellt.|  
  
## <a name="remarks"></a>Hinweise  
 CAnimationSize-Klasse kapselt zwei CAnimationVariable-Objekte und kann in Clientanwendungen eine Größe dar. Beispielsweise können diese Klasse so animieren Sie eine Größe von zwei zweidimensionalen Objekts auf dem Bildschirm (Rechteck, Steuerelement usw.). Zum Verwenden dieser Klasse in der Anwendung einfach instanziieren Sie ein Objekt dieser Klasse, Animationscontroller AddAnimationObject fügen Sie hinzu und rufen Sie AddTransition für jeden Übergang auf die Breite bzw. Höhe angewendet werden.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 `CAnimationSize` 
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxanimationcontroller.h  
  
##  <a name="addtransition"></a>CAnimationSize::AddTransition  
 Fügt Übergänge für Breite und Höhe.  
  
```  
void AddTransition(
    CBaseTransition* pCXTransition,  
    CBaseTransition* pCYTransition);
```  
  
### <a name="parameters"></a>Parameter  
 `pCXTransition`  
 Ein Zeiger auf Übergang für die Breite.  
  
 `pCYTransition`  
 Ein Zeiger auf Übergang für Höhe.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um die angegebenen Übergänge hinzuzufügen, der internen Liste von Übergängen, die auf Animationsvariablen für Breite und Höhe angewendet werden. Wenn Sie Übergänge hinzufügen, werden sie nicht sofort angewendet und in einer internen Liste gespeichert. Übergänge werden angewendet (einem Storyboard für einen bestimmten Wert hinzugefügt) Wenn Sie CAnimationController:: AnimateGroup aufrufen. Wenn Sie keinen Übergang auf eine der Dimensionen anwenden müssen, können Sie NULL übergeben.  
  
##  <a name="canimationsize"></a>CAnimationSize::CAnimationSize  
 Erstellt ein Objekt der Animation Größe.  
  
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
 Gibt die Standardgröße.  
  
 `nGroupID`  
 Gibt die Gruppen-ID.  
  
 `nObjectID`  
 Gibt die Objekt-ID.  
  
 `dwUserData`  
 Gibt die benutzerdefinierten Daten.  
  
### <a name="remarks"></a>Hinweise  
 Das Objekt erstellt wird, mit Standardwerten für Breite, Höhe, Objekt-ID und Gruppen-ID, die auf 0 festgelegt werden. Sie können zur Laufzeit mit SetDefaultValue und SetID später geändert werden.  
  
##  <a name="getanimationvariablelist"></a>CAnimationSize::GetAnimationVariableList  
 Fügt die gekapselten Animationsvariablen in eine Liste.  
  
```  
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*, 
    CAnimationVariable*>& lst);
```  
  
### <a name="parameters"></a>Parameter  
 `lst`  
 Wenn die Funktion zurückgibt, enthält Zeiger auf zwei CAnimationVariable-Objekte, die die Breite und Höhe darstellt.  
  
##  <a name="getcx"></a>CAnimationSize::GetCX  
 Bietet Zugriff auf CAnimationVariable, die Breite darstellt.  
  
```  
CAnimationVariable& GetCX();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf gekapselte CAnimationVariable, die Breite darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Sie können diese Methode, um direkten Zugriff auf die zugrunde liegende CAnimationVariable, die für Breite erhalten aufrufen.  
  
##  <a name="getcy"></a>CAnimationSize::GetCY  
 Bietet Zugriff auf CAnimationVariable, die Höhe darstellt.  
  
```  
CAnimationVariable& GetCY();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf gekapselte CAnimationVariable, die Höhe darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Sie können diese Methode, um direkten Zugriff auf die zugrunde liegende CAnimationVariable, Höhe darstellt erhalten aufrufen.  
  
##  <a name="getdefaultvalue"></a>CAnimationSize::GetDefaultValue  
 Gibt die Standardwerte für Breite und Höhe zurück.  
  
```  
CSize GetDefaultValue();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein CSize-Objekt, das Standardwerte enthält.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um den Standardwert abzurufen, der zuvor vom Konstruktor oder mit SetDefaultValue festgelegt wurde.  
  
##  <a name="getvalue"></a>CAnimationSize::GetValue  
 Gibt den aktuellen Wert zurück.  
  
```  
BOOL GetValue(CSize& szValue);
```  
  
### <a name="parameters"></a>Parameter  
 `szValue`  
 Die Ausgabe. Enthält den aktuellen Wert an, wenn diese Methode zurückgegeben wird.  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn der aktuelle Wert erfolgreich abgerufen wurde. andernfalls FALSE.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um den aktuellen Wert der Animationsgröße abzurufen. Wenn diese Methode fehlschlägt oder zugrunde liegende COM-Objekte für Width und Size nicht initialisiert wurden, enthält szValue einen Standardwert, der zuvor im Konstruktor oder mit SetDefaultValue festgelegt wurde.  
  
##  <a name="m_cxvalue"></a>CAnimationSize::m_cxValue  
 Die gekapselte Animationsvariable, die Breite der Animationsgröße darstellt.  
  
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
 Aktuellen Wert der Animationsgröße als CSize.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ruft intern GetValue. Wenn GetValue aus irgendeinem Grund fehlschlägt, enthält die zurückgegebene Größe Standardwerte für Breite und Höhe.  
  
##  <a name="operator_eq"></a>CAnimationSize::operator =  
 Weist CAnimationSize SzSrc zu.  
  
```  
void operator=(const CSize& szSrc);
```  
  
### <a name="parameters"></a>Parameter  
 `szSrc`  
 Verweist auf CSize oder Größe.  
  
### <a name="remarks"></a>Hinweise  
 Weist CAnimationSize SzSrc zu. Wurde empfohlen, dies vor dem Animationsstart, durchzuführen, da dieser Operator SetDefaultValue aufruft, die die zugrunde liegenden COM-Objekte für Breite und Höhe neu erstellt, wenn sie bereits erstellt wurden. Wenn Sie dieses Animationsobjekt Ereignisse (ValueChanged oder IntegerValueChanged) abonniert haben, müssen Sie diese Ereignisse erneut aktivieren.  
  
##  <a name="setdefaultvalue"></a>CAnimationSize::SetDefaultValue  
 Legt den Standardwert fest.  
  
```  
void SetDefaultValue(const CSize& szDefault);
```  
  
### <a name="parameters"></a>Parameter  
 `szDefault`  
 Gibt neue Standardgröße an.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, um einen Standardwert auf Animationsobjekt festzulegen. Diese Methoden weisen Standardwerte auf Breite und Höhe der Animationsgröße. Auch neu zugrunde liegende COM-Objekte, wenn sie bereits erstellt wurden. Wenn Sie dieses Animationsobjekt Ereignisse (ValueChanged oder IntegerValueChanged) abonniert haben, müssen Sie diese Ereignisse erneut aktivieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

