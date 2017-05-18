---
title: CAnimationColor-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- CAnimationColor class
ms.assetid: 88bfabd4-efeb-4652-87e8-304253d8e48c
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
ms.openlocfilehash: e053986737b8e62103666787b99b01cbf19cdc60
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="canimationcolor-class"></a>CAnimationColor-Klasse
Implementiert die Funktion einer Farbe, deren Rot-, Grün- und Blauanteil animiert werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CAnimationColor : public CAnimationBaseObject;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationColor::CAnimationColor](#canimationcolor)|Überladen. Erstellt ein Objekt der Animation-Farbe.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationColor::AddTransition](#addtransition)|Fügt Übergänge für Rot-, Grün- und Blau-Komponenten.|  
|[CAnimationColor::GetB](#getb)|Bietet Zugriff auf CAnimationVariable, die Blauanteil darstellt.|  
|[CAnimationColor::GetDefaultValue](#getdefaultvalue)|Gibt die Standardwerte für Farbkomponenten zurück.|  
|[CAnimationColor::GetG](#getg)|Bietet Zugriff auf CAnimationVariable Green-Komponente darstellt.|  
|[CAnimationColor::GetR](#getr)|Bietet Zugriff auf CAnimationVariable, Red-Komponente darstellt.|  
|[CAnimationColor::GetValue](#getvalue)|Gibt den aktuellen Wert zurück.|  
|[CAnimationColor::SetDefaultValue](#setdefaultvalue)|Legt den Standardwert fest.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationColor::GetAnimationVariableList](#getanimationvariablelist)|Fügt die gekapselten Animationsvariablen in eine Liste. (Überschreibt [CAnimationBaseObject:: GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationColor::operator COLORREF](#operator_colorref)||  
|[CAnimationColor::operator =](#operator_eq)|CAnimationColor Farbe zugewiesen.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationColor::m_bValue](#m_bvalue)|Die gekapselte Animationsvariable, die Blauanteil der Animationsfarbe darstellt.|  
|[CAnimationColor::m_gValue](#m_gvalue)|Die gekapselte Animationsvariable, die Grünanteils der Animationsfarbe darstellt.|  
|[CAnimationColor::m_rValue](#m_rvalue)|Die gekapselte Animationsvariable, die Rot-Komponente der Animationsfarbe darstellt.|  
  
## <a name="remarks"></a>Hinweise  
 CAnimationColor-Klasse kapselt drei CAnimationVariable-Objekte und kann in Clientanwendungen eine Farbe darstellen. Beispielsweise können diese Klasse zum Animieren von Farben für ein beliebiges Objekt auf dem Bildschirm (Textfarbe, Hintergrundfarbe usw.). Zum Verwenden dieser Klasse in der Anwendung nur instanziieren Sie ein Objekt dieser Klasse, Animationscontroller AddAnimationObject fügen Sie hinzu und rufen Sie AddTransition für jeden Übergang auf Rot, Grün und Blau-Komponenten angewendet werden.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 `CAnimationColor`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxanimationcontroller.h  
  
##  <a name="addtransition"></a>CAnimationColor::AddTransition  
 Fügt Übergänge für Rot-, Grün- und Blau-Komponenten.  
  
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
 Rufen Sie diese Funktion, um die angegebenen Übergänge der internen Liste von Übergängen, die Farbkomponenten darstellen Animationsvariablen anzuwendenden hinzuzufügen. Wenn Sie Übergänge hinzufügen, werden sie nicht sofort angewendet und in einer internen Liste gespeichert. Übergänge werden angewendet (einem Storyboard für einen bestimmten Wert hinzugefügt) Wenn Sie CAnimationController:: AnimateGroup aufrufen. Wenn Sie keinen Übergang auf eine der Farbkomponenten anwenden müssen, können Sie NULL übergeben.  
  
##  <a name="canimationcolor"></a>CAnimationColor::CAnimationColor  
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
 Gibt die Gruppen-ID.  
  
 `nObjectID`  
 Gibt die Objekt-ID.  
  
 `dwUserData`  
 Gibt die benutzerdefinierten Daten.  
  
### <a name="remarks"></a>Hinweise  
 Das Objekt wird erstellt, mit Standardwerten für Rot, Grün, Blau, Objekt-ID und Gruppen-ID, die auf 0 festgelegt werden. Sie können zur Laufzeit mit SetDefaultValue und SetID später geändert werden.  
  
##  <a name="getanimationvariablelist"></a>CAnimationColor::GetAnimationVariableList  
 Fügt die gekapselten Animationsvariablen in eine Liste.  
  
```  
virtual void GetAnimationVariableList(CList<CAnimationVariable*>& lst);
```  
  
### <a name="parameters"></a>Parameter  
 `lst`  
 Enthält nach dem Beenden die Funktion Zeiger auf drei CAnimationVariable-Objekte, die rote, grüne und blaue Komponenten darstellt.  
  
##  <a name="getb"></a>CAnimationColor::GetB  
 Bietet Zugriff auf CAnimationVariable, die Blauanteil darstellt.  
  
```  
CAnimationVariable& GetB();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf gekapselte CAnimationVariable, die Blauanteil darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Sie können diese Methode, um direkten Zugriff auf die zugrunde liegende CAnimationVariable, die Blauanteil darstellt erhalten aufrufen.  
  
##  <a name="getdefaultvalue"></a>CAnimationColor::GetDefaultValue  
 Gibt die Standardwerte für Farbkomponenten zurück.  
  
```  
COLORREF GetDefaultValue();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein COLORREF-Wert, der Standardwerte für RGB-Komponenten enthält.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um den Standardwert abzurufen, der zuvor vom Konstruktor oder mit SetDefaultValue festgelegt wurde.  
  
##  <a name="getg"></a>CAnimationColor::GetG  
 Bietet Zugriff auf CAnimationVariable Green-Komponente darstellt.  
  
```  
CAnimationVariable& GetG();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf gekapselte CAnimationVariable für Green-Komponente.  
  
### <a name="remarks"></a>Hinweise  
 Sie können diese Methode, um direkten Zugriff auf die zugrunde liegende CAnimationVariable darstellen Grünanteils erhalten aufrufen.  
  
##  <a name="getr"></a>CAnimationColor::GetR  
 Bietet Zugriff auf CAnimationVariable, Red-Komponente darstellt.  
  
```  
CAnimationVariable& GetR();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf gekapselte CAnimationVariable, Red-Komponente darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Sie können diese Methode, um direkten Zugriff auf die zugrunde liegende CAnimationVariable darstellt Rotanteils erhalten aufrufen.  
  
##  <a name="getvalue"></a>CAnimationColor::GetValue  
 Gibt den aktuellen Wert zurück.  
  
```  
BOOL GetValue(COLORREF& color);
```  
  
### <a name="parameters"></a>Parameter  
 `color`  
 Die Ausgabe. Enthält den aktuellen Wert an, wenn diese Methode zurückgegeben wird.  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn der aktuelle Wert erfolgreich abgerufen wurde. andernfalls FALSE.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um den aktuellen Wert der Animationsfarbe abzurufen. Wenn diese Methode fehlschlägt oder zugrunde liegende COM-Objekte für Farbkomponenten nicht initialisiert wurden, enthält Color einen Standardwert, der zuvor im Konstruktor oder mit SetDefaultValue festgelegt wurde.  
  
##  <a name="m_bvalue"></a>CAnimationColor::m_bValue  
 Die gekapselte Animationsvariable, die Blauanteil der Animationsfarbe darstellt.  
  
```  
CAnimationVariable m_bValue;  
```  
  
##  <a name="m_gvalue"></a>CAnimationColor::m_gValue  
 Die gekapselte Animationsvariable, die Grünanteils der Animationsfarbe darstellt.  
  
```  
CAnimationVariable m_gValue;  
```  
  
##  <a name="m_rvalue"></a>CAnimationColor::m_rValue  
 Die gekapselte Animationsvariable, die Rot-Komponente der Animationsfarbe darstellt.  
  
```  
CAnimationVariable m_rValue;  
```  
  
##  <a name="operator_colorref"></a>CAnimationColor::operator COLORREF  
  
```  
operator COLORREF();
```   
  
### <a name="return-value"></a>Rückgabewert  
  
##  <a name="operator_eq"></a>CAnimationColor::operator =  
 CAnimationColor Farbe zugewiesen.  
  
```  
void operator=(COLORREF color);
```  
  
### <a name="parameters"></a>Parameter  
 `color`  
 Gibt neue Wert der Animationsfarbe.  
  
### <a name="remarks"></a>Hinweise  
 Wurde empfohlen, dies vor dem Animationsstart, durchzuführen, da dieser Operator SetDefaultValue aufruft, die die zugrunde liegenden COM-Objekte für Farbkomponenten neu erstellt, wenn sie bereits erstellt wurden. Wenn Sie dieses Animationsobjekt Ereignisse (ValueChanged oder IntegerValueChanged) abonniert haben, müssen Sie diese Ereignisse erneut aktivieren.  
  
##  <a name="setdefaultvalue"></a>CAnimationColor::SetDefaultValue  
 Legt den Standardwert fest.  
  
```  
void SetDefaultValue(COLORREF color);
```  
  
### <a name="parameters"></a>Parameter  
 `color`  
 Gibt neue Standardwerte für Rot-, Grün- und Blau-Komponenten an.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, um einen Standardwert auf Animationsobjekt festzulegen. Diese Methoden weisen Standardwerte zu Komponenten der Animationsfarbe. Auch neu zugrunde liegende COM-Objekte, wenn sie bereits erstellt wurden. Wenn Sie dieses Animationsobjekt Ereignisse (ValueChanged oder IntegerValueChanged) abonniert haben, müssen Sie diese Ereignisse erneut aktivieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

