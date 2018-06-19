---
title: CAnimationColor-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor::CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationColor::GetB
- AFXANIMATIONCONTROLLER/CAnimationColor::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationColor::GetG
- AFXANIMATIONCONTROLLER/CAnimationColor::GetR
- AFXANIMATIONCONTROLLER/CAnimationColor::GetValue
- AFXANIMATIONCONTROLLER/CAnimationColor::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationColor::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationColor::m_bValue
- AFXANIMATIONCONTROLLER/CAnimationColor::m_gValue
- AFXANIMATIONCONTROLLER/CAnimationColor::m_rValue
dev_langs:
- C++
helpviewer_keywords:
- CAnimationColor [MFC], CAnimationColor
- CAnimationColor [MFC], AddTransition
- CAnimationColor [MFC], GetB
- CAnimationColor [MFC], GetDefaultValue
- CAnimationColor [MFC], GetG
- CAnimationColor [MFC], GetR
- CAnimationColor [MFC], GetValue
- CAnimationColor [MFC], SetDefaultValue
- CAnimationColor [MFC], GetAnimationVariableList
- CAnimationColor [MFC], m_bValue
- CAnimationColor [MFC], m_gValue
- CAnimationColor [MFC], m_rValue
ms.assetid: 88bfabd4-efeb-4652-87e8-304253d8e48c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f564b70e850f3020956711ef15ab1fe9285a6ae4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33354147"
---
# <a name="canimationcolor-class"></a>CAnimationColor-Klasse
Implementiert die Funktion einer Farbe, deren Rot-, Grün- und Blauanteil animiert werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CAnimationColor : public CAnimationBaseObject;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationColor::CAnimationColor](#canimationcolor)|Überladen. Erstellt eine Animation Farbe-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationColor::AddTransition](#addtransition)|Fügt die Übergänge für Rot, Grün und Blau-Komponenten.|  
|[CAnimationColor::GetB](#getb)|Bietet Zugriff auf CAnimationVariable, die blaue Komponente darstellt.|  
|[CAnimationColor::GetDefaultValue](#getdefaultvalue)|Gibt die Standardwerte für Farbkomponenten zurück.|  
|[CAnimationColor::GetG](#getg)|Bietet Zugriff auf CAnimationVariable, Green-Komponente darstellt.|  
|[CAnimationColor::GetR](#getr)|Bietet Zugriff auf CAnimationVariable, Red-Komponente darstellt.|  
|[CAnimationColor::GetValue](#getvalue)|Gibt den aktuellen Wert zurück.|  
|[CAnimationColor::SetDefaultValue](#setdefaultvalue)|Legt den Standardwert fest.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationColor::GetAnimationVariableList](#getanimationvariablelist)|Legt die gekapselten Animationsvariablen in einer Liste an. (Überschreibt [CAnimationBaseObject:: GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationColor::operator COLORREF](#operator_colorref)||  
|[CAnimationColor::operator =](#operator_eq)|CAnimationColor Farbe zugewiesen.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CAnimationColor::m_bValue](#m_bvalue)|Die gekapselte Animationsvariable, die Blauanteil der Animationsfarbe darstellt.|  
|[CAnimationColor::m_gValue](#m_gvalue)|Die gekapselte Animationsvariable, die Animationsfarbe Grün-Komponente darstellt.|  
|[CAnimationColor::m_rValue](#m_rvalue)|Die gekapselte Animationsvariable, die Rot-Komponente der Animationsfarbe darstellt.|  
  
## <a name="remarks"></a>Hinweise  
 CAnimationColor-Klasse kapselt drei CAnimationVariable-Objekte und kann in Anwendungen eine Farbe darstellen. Sie können z. B. diese Klasse zum Animieren von Farben eines beliebigen Objekts auf dem Bildschirm verwenden (wie die Textfarbe, Hintergrundfarbe usw.). Zum Verwenden dieser Klasse in der Anwendung einfach instanziieren Sie ein Objekt dieser Klasse, Animationscontroller AddAnimationObject hinzugefügt, und rufen Sie AddTransition für jeden Übergang auf Rot, Grün und Blau-Komponenten angewendet werden soll.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 `CAnimationColor`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxanimationcontroller.h  
  
##  <a name="addtransition"></a>  CAnimationColor::AddTransition  
 Fügt die Übergänge für Rot, Grün und Blau-Komponenten.  
  
```  
void AddTransition(
    CBaseTransition* pRTransition,  
    CBaseTransition* pGTransition,  
    CBaseTransition* pBTransition);
```  
  
### <a name="parameters"></a>Parameter  
 `pRTransition`  
 Übergang für Red-Komponente.  
  
 `pGTransition`  
 Übergang für Green-Komponente.  
  
 `pBTransition`  
 Übergang für Blue-Komponente.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird die interne Liste der Übergänge Animation Variablenliste Farbkomponenten anzuwendende angegebenen Übergänge hinzugefügt werden. Wenn Sie Übergänge hinzufügen, werden sie nicht sofort angewendet und in einer internen Liste gespeichert. Übergänge werden angewendet (ein Storyboard für einen bestimmten Wert hinzugefügt) beim CAnimationController:: AnimateGroup aufrufen. Wenn Sie keinen Übergang zu einem der Farbkomponenten anwenden müssen, können Sie NULL übergeben.  
  
##  <a name="canimationcolor"></a>  CAnimationColor::CAnimationColor  
 Erstellt ein CAnimationColor-Objekt.  
  
```  
CAnimationColor();
 
CAnimationColor(
    COLORREF color,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `color`  
 Gibt die Standardfarbe.  
  
 `nGroupID`  
 Gibt Gruppen-ID.  
  
 `nObjectID`  
 Gibt die Objekt-ID.  
  
 `dwUserData`  
 Gibt die benutzerdefinierten Daten.  
  
### <a name="remarks"></a>Hinweise  
 Das Objekt wird erstellt, mit Standardwerten für Rot, Grün, Blau, Objekt-ID und Gruppen-ID, die auf 0 festgelegt werden. Sie können später mithilfe von SetDefaultValue und SetID zur Laufzeit geändert werden.  
  
##  <a name="getanimationvariablelist"></a>  CAnimationColor::GetAnimationVariableList  
 Legt die gekapselten Animationsvariablen in einer Liste an.  
  
```  
virtual void GetAnimationVariableList(CList<CAnimationVariable*>& lst);
```  
  
### <a name="parameters"></a>Parameter  
 `lst`  
 Wenn die Funktion zurückgibt, enthält Zeiger auf drei CAnimationVariable-Objekte, die rote, grünen und blaue Komponenten darstellt.  
  
##  <a name="getb"></a>  CAnimationColor::GetB  
 Bietet Zugriff auf CAnimationVariable, die blaue Komponente darstellt.  
  
```  
CAnimationVariable& GetB();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf gekapselte CAnimationVariable, Blauanteils darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Sie können diese Methode, um direkten Zugriff auf zugrunde liegende CAnimationVariable darstellt Blauanteils erhalten aufrufen.  
  
##  <a name="getdefaultvalue"></a>  CAnimationColor::GetDefaultValue  
 Gibt die Standardwerte für Farbkomponenten zurück.  
  
```  
COLORREF GetDefaultValue();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein COLORREF-Wert, der Standardwerte für die RGB-Komponenten enthält.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird zum Abrufen von Standardwert, der zuvor vom Konstruktor oder mit SetDefaultValue festgelegt wurde.  
  
##  <a name="getg"></a>  CAnimationColor::GetG  
 Bietet Zugriff auf CAnimationVariable, Green-Komponente darstellt.  
  
```  
CAnimationVariable& GetG();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf gekapselte CAnimationVariable darstellen Grünanteils.  
  
### <a name="remarks"></a>Hinweise  
 Sie können diese Methode zum Abrufen von direkten Zugriffs auf die zugrunde liegende CAnimationVariable darstellen Grünanteils aufrufen.  
  
##  <a name="getr"></a>  CAnimationColor::GetR  
 Bietet Zugriff auf CAnimationVariable, Red-Komponente darstellt.  
  
```  
CAnimationVariable& GetR();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf gekapselte CAnimationVariable, Red-Komponente darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Sie können diese Methode zum Abrufen von direkten Zugriffs auf die zugrunde liegende CAnimationVariable darstellt Rotanteils aufrufen.  
  
##  <a name="getvalue"></a>  CAnimationColor::GetValue  
 Gibt den aktuellen Wert zurück.  
  
```  
BOOL GetValue(COLORREF& color);
```  
  
### <a name="parameters"></a>Parameter  
 `color`  
 Die Ausgabe. Enthält den aktuellen Wert an, wenn diese Methode zurückgegeben wird.  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn der aktuelle Wert erfolgreich abgerufen wurde. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird zum Abrufen des aktuellen Wert der Animationsfarbe. Wenn diese Methode fehlschlägt oder zugrunde liegenden COM-Objekte für Farbkomponenten nicht initialisiert wurden, enthält die Farbe Standardwert, der zuvor im Konstruktor oder mit SetDefaultValue festgelegt wurde.  
  
##  <a name="m_bvalue"></a>  CAnimationColor::m_bValue  
 Die gekapselte Animationsvariable, die Blauanteil der Animationsfarbe darstellt.  
  
```  
CAnimationVariable m_bValue;  
```  
  
##  <a name="m_gvalue"></a>  CAnimationColor::m_gValue  
 Die gekapselte Animationsvariable, die Animationsfarbe Grün-Komponente darstellt.  
  
```  
CAnimationVariable m_gValue;  
```  
  
##  <a name="m_rvalue"></a>  CAnimationColor::m_rValue  
 Die gekapselte Animationsvariable, die Rot-Komponente der Animationsfarbe darstellt.  
  
```  
CAnimationVariable m_rValue;  
```  
  
##  <a name="operator_colorref"></a>  CAnimationColor::operator COLORREF  
  
```  
operator COLORREF();
```   
  
### <a name="return-value"></a>Rückgabewert  
  
##  <a name="operator_eq"></a>  CAnimationColor::operator =  
 CAnimationColor Farbe zugewiesen.  
  
```  
void operator=(COLORREF color);
```  
  
### <a name="parameters"></a>Parameter  
 `color`  
 Gibt an, neuer Wert Animationsfarbe.  
  
### <a name="remarks"></a>Hinweise  
 Es wird empfohlen, vor Beginn der Animation, dazu werden sollen, da dieser Operator SetDefaultValue aufruft, die die zugrunde liegenden COM-Objekte für Farbkomponenten neu erstellt, wenn sie erstellt wurden. Wenn Sie dieses Animationsobjekt auf Ereignisse (ValueChanged oder IntegerValueChanged) abonniert haben, müssen Sie diese Ereignisse erneut zu aktivieren.  
  
##  <a name="setdefaultvalue"></a>  CAnimationColor::SetDefaultValue  
 Legt den Standardwert fest.  
  
```  
void SetDefaultValue(COLORREF color);
```  
  
### <a name="parameters"></a>Parameter  
 `color`  
 Gibt neue Standardwerte für Rot, Grün und Blau-Komponenten an.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, um einen Standardwert zum Animationsobjekts festzulegen. Diese Methoden Farbkomponenten der Animationsfarbe Standardwerte zugewiesen. Zugrunde liegende COM-Objekte erstellt auch neu, wenn sie erstellt wurden. Wenn Sie dieses Animationsobjekt auf Ereignisse (ValueChanged oder IntegerValueChanged) abonniert haben, müssen Sie diese Ereignisse erneut zu aktivieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)
