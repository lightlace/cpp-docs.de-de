---
title: CAnimationRect-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimationRect
- afxanimationcontroller/CAnimationRect
dev_langs:
- C++
helpviewer_keywords:
- CAnimationRect class
ms.assetid: 0294156d-241e-4a57-92b2-31234fe557d6
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
ms.openlocfilehash: f935884301030166572e356fffe88439f843f2c7
ms.lasthandoff: 02/24/2017

---
# <a name="canimationrect-class"></a>CAnimationRect-Klasse
Implementiert die Funktion eines Rechtecks, dessen Seiten animiert werden können.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CAnimationRect : public CAnimationBaseObject;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationRect::CAnimationRect](#canimationrect)|Überladen. Erstellt eine Animation Rect-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationRect::AddTransition](#addtransition)|Fügt Übergänge für die linken, oberen, rechten und unteren Koordinaten hinzu.|  
|[CAnimationRect::GetBottom](#getbottom)|Bietet Zugriff auf CAnimationVariable, die untere Koordinate darstellt.|  
|[CAnimationRect::GetDefaultValue](#getdefaultvalue)|Gibt die Standardwerte für die Grenzen von Rechteck zurück.|  
|[CAnimationRect::GetLeft](#getleft)|Bietet Zugriff auf CAnimationVariable, die linke Koordinate darstellt.|  
|[CAnimationRect::GetRight](#getright)|Bietet Zugriff auf CAnimationVariable, die rechte Koordinate darstellt.|  
|[CAnimationRect::GetTop](#gettop)|Bietet Zugriff auf CAnimationVariable, die obere Koordinate darstellt.|  
|[CAnimationRect::GetValue](#getvalue)|Gibt den aktuellen Wert zurück.|  
|[CAnimationRect::SetDefaultValue](#setdefaultvalue)|Legt den Standardwert fest.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationRect::GetAnimationVariableList](#getanimationvariablelist)|Fügt die gekapselten Animationsvariablen in eine Liste. (Überschreibt [CAnimationBaseObject:: GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationRect::operator RECT](#operator_rect)|Konvertiert einen CAnimationRect in Rect.|  
|[CAnimationRect::operator =](#operator_eq)|Weist CAnimationRect Rect zu.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationRect::m_bFixedSize](#m_bfixedsize)|Gibt an, ob das Rechteck eine feste Größe hat.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationRect::m_bottomValue](#m_bottomvalue)|Die gekapselte Animationsvariable, die untere repräsentiert gebunden Animation Rechtecks.|  
|[CAnimationRect::m_leftValue](#m_leftvalue)|Die gekapselte Animationsvariable, die Links gebunden Animation Rechtecks.|  
|[CAnimationRect::m_rightValue](#m_rightvalue)|Die gekapselte Animationsvariable, die rechts gebunden Animation Rechtecks.|  
|[CAnimationRect::m_szInitial](#m_szinitial)|Gibt die Anfangsgröße der Animation Rechteck.|  
|[CAnimationRect::m_topValue](#m_topvalue)|Die gekapselte Animationsvariable, die obere repräsentiert gebunden Animation Rechtecks.|  
  
## <a name="remarks"></a>Hinweise  
 CAnimationRect-Klasse kapselt vier CAnimationVariable-Objekte und kann in Clientanwendungen ein Rechteck darstellen. Zum Verwenden dieser Klasse in der Anwendung einfach instanziieren Sie ein Objekt dieser Klasse, Animationscontroller AddAnimationObject fügen Sie hinzu und rufen Sie AddTransition für jeden Übergang auf die linke, rechte obere oder untere Koordinate angewendet werden.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 `CAnimationRect`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxanimationcontroller.h  
  
##  <a name="a-nameaddtransitiona--canimationrectaddtransition"></a><a name="addtransition"></a>CAnimationRect::AddTransition  
 Fügt Übergänge für die linken, oberen, rechten und unteren Koordinaten hinzu.  
  
```  
void AddTransition(
    CBaseTransition* pLeftTransition,  
    CBaseTransition* pTopTransition,  
    CBaseTransition* pRightTransition,  
    CBaseTransition* pBottomTransition);
```  
  
### <a name="parameters"></a>Parameter  
 `pLeftTransition`  
 Gibt Übergang für die linke Seite.  
  
 `pTopTransition`  
 Gibt Übergang für die obere Seite an.  
  
 `pRightTransition`  
 Gibt Übergang für die rechte Seite.  
  
 `pBottomTransition`  
 Gibt Übergang für die Unterseite.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um die angegebenen Übergänge hinzuzufügen, das der internen Liste von Übergängen, die auf Animationsvariablen für die einzelnen Seiten des Rechtecks angewendet werden. Wenn Sie Übergänge hinzufügen, werden sie nicht sofort angewendet und in einer internen Liste gespeichert. Übergänge werden angewendet (einem Storyboard für einen bestimmten Wert hinzugefügt) Wenn Sie CAnimationController:: AnimateGroup aufrufen. Wenn Sie keinen Übergang auf eine der Rechteckseiten anwenden müssen, können Sie NULL übergeben.  
  
##  <a name="a-namecanimationrecta--canimationrectcanimationrect"></a><a name="canimationrect"></a>CAnimationRect::CAnimationRect  
 Erstellt ein CAnimationRect-Objekt.  
  
```  
CAnimationRect();

 
CAnimationRect(
    const CRect& rect,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);

 
CAnimationRect(
    const CPoint& pt,  
    const CSize& sz,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);

 
CAnimationRect(
    int nLeft,  
    int nTop,  
    int nRight,  
    int nBottom,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `rect`  
 Standardrechteck angibt.  
  
 `nGroupID`  
 Gibt die Gruppen-ID.  
  
 `nObjectID`  
 Gibt die Objekt-ID.  
  
 `dwUserData`  
 Gibt die benutzerdefinierten Daten.  
  
 `pt`  
 Die Koordinate der oberen linken Ecke.  
  
 `sz`  
 Die Größe des Rechtecks.  
  
 `nLeft`  
 Gibt Koordinate der linken Grenze an.  
  
 `nTop`  
 Gibt Koordinate der oberen Grenze an.  
  
 `nRight`  
 Gibt Koordinate der rechten Grenze an.  
  
 `nBottom`  
 Gibt Koordinate unterer Grenze an.  
  
### <a name="remarks"></a>Hinweise  
 Das Objekt wird erstellt, mit Standardwerten für Links, oben, rechts und unten, Objekt-ID und Gruppen-ID, die auf 0 festgelegt werden. Sie können zur Laufzeit mit SetDefaultValue und SetID später geändert werden.  
  
##  <a name="a-namegetanimationvariablelista--canimationrectgetanimationvariablelist"></a><a name="getanimationvariablelist"></a>CAnimationRect::GetAnimationVariableList  
 Fügt die gekapselten Animationsvariablen in eine Liste.  
  
```  
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*, 
    CAnimationVariable*>& lst);
```  
  
### <a name="parameters"></a>Parameter  
 `lst`  
 Wenn die Funktion zurückgibt, enthält Zeiger auf vier CAnimationVariable-Objekte, die Koordinaten des Rechtecks darstellen.  
  
##  <a name="a-namegetbottoma--canimationrectgetbottom"></a><a name="getbottom"></a>CAnimationRect::GetBottom  
 Bietet Zugriff auf CAnimationVariable, die untere Koordinate darstellt.  
  
```  
CAnimationVariable& GetBottom();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf gekapselte CAnimationVariable, untere Koordinate darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Sie können diese Methode, um direkten Zugriff auf die zugrunde liegende CAnimationVariable, die die untere Koordinate darstellt erhalten aufrufen.  
  
##  <a name="a-namegetdefaultvaluea--canimationrectgetdefaultvalue"></a><a name="getdefaultvalue"></a>CAnimationRect::GetDefaultValue  
 Gibt die Standardwerte für die Grenzen von Rechteck zurück.  
  
```  
CRect GetDefaultValue();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein CRect-Wert, die Standardwerte für Links, rechts, oben und unten enthält.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um den Standardwert abzurufen, der zuvor vom Konstruktor oder mit SetDefaultValue festgelegt wurde.  
  
##  <a name="a-namegetlefta--canimationrectgetleft"></a><a name="getleft"></a>CAnimationRect::GetLeft  
 Bietet Zugriff auf CAnimationVariable, die linke Koordinate darstellt.  
  
```  
CAnimationVariable& GetLeft();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf gekapselte CAnimationVariable, die linke Koordinate darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Sie können diese Methode, um direkten Zugriff auf die zugrunde liegende CAnimationVariable, die die linke Koordinate darstellt erhalten aufrufen.  
  
##  <a name="a-namegetrighta--canimationrectgetright"></a><a name="getright"></a>CAnimationRect::GetRight  
 Bietet Zugriff auf CAnimationVariable, die rechte Koordinate darstellt.  
  
```  
CAnimationVariable& GetRight();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf gekapselte CAnimationVariable, die rechte Koordinate darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Sie können diese Methode, um direkten Zugriff auf die zugrunde liegende CAnimationVariable, die die rechte Koordinate darstellt erhalten aufrufen.  
  
##  <a name="a-namegettopa--canimationrectgettop"></a><a name="gettop"></a>CAnimationRect::GetTop  
 Bietet Zugriff auf CAnimationVariable, die obere Koordinate darstellt.  
  
```  
CAnimationVariable& GetTop();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf gekapselte CAnimationVariable, die obere Koordinate darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Sie können diese Methode, um direkten Zugriff auf die zugrunde liegende CAnimationVariable, die die obere Koordinate darstellt erhalten aufrufen.  
  
##  <a name="a-namegetvaluea--canimationrectgetvalue"></a><a name="getvalue"></a>CAnimationRect::GetValue  
 Gibt den aktuellen Wert zurück.  
  
```  
BOOL GetValue(CRect& rect);
```  
  
### <a name="parameters"></a>Parameter  
 `rect`  
 Die Ausgabe. Enthält den aktuellen Wert an, wenn diese Methode zurückgegeben wird.  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn der aktuelle Wert erfolgreich abgerufen wurde. andernfalls FALSE.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um den aktuellen Wert der Animation Rechteck abzurufen. Wenn diese Methode fehlschlägt oder zugrunde liegende COM-Objekte für Left, Top, Right und Bottom nicht initialisiert wurden, enthält Rect einen Standardwert, der zuvor im Konstruktor oder mit SetDefaultValue festgelegt wurde.  
  
##  <a name="a-namembfixedsizea--canimationrectmbfixedsize"></a><a name="m_bfixedsize"></a>CAnimationRect::m_bFixedSize  
 Gibt an, ob das Rechteck eine feste Größe hat.  
  
```  
BOOL m_bFixedSize;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn dieses Element auf true festgelegt ist, werden dann ist die Größe des Rechtecks, festen und rechten und unteren Werte berechnet jedes Mal, wenn die linke obere Ecke, entsprechend der feste Größe verschoben wird. Legen Sie diesen Wert auf TRUE, um das Rechteck auf dem Bildschirm leicht zu verschieben. In diesem Fall werden die an den rechten und unteren Koordinaten übernommene Übergänge ignoriert. Die Größe wird intern gespeichert, wenn Sie das Objekt erstellen, und/oder SetDefaultValue aufrufen. Standardmäßig ist dieser Member auf FALSE festgelegt.  
  
##  <a name="a-namembottomvaluea--canimationrectmbottomvalue"></a><a name="m_bottomvalue"></a>CAnimationRect::m_bottomValue  
 Die gekapselte Animationsvariable, die untere repräsentiert gebunden Animation Rechtecks.  
  
```  
CAnimationVariable m_bottomValue;  
```  
  
##  <a name="a-namemleftvaluea--canimationrectmleftvalue"></a><a name="m_leftvalue"></a>CAnimationRect::m_leftValue  
 Die gekapselte Animationsvariable, die Links gebunden Animation Rechtecks.  
  
```  
CAnimationVariable m_leftValue;  
```  
  
##  <a name="a-namemrightvaluea--canimationrectmrightvalue"></a><a name="m_rightvalue"></a>CAnimationRect::m_rightValue  
 Die gekapselte Animationsvariable, die rechts gebunden Animation Rechtecks.  
  
```  
CAnimationVariable m_rightValue;  
```  
  
##  <a name="a-namemszinitiala--canimationrectmszinitial"></a><a name="m_szinitial"></a>CAnimationRect::m_szInitial  
 Gibt die Anfangsgröße der Animation Rechteck.  
  
```  
CSize m_szInitial;  
```  
  
##  <a name="a-namemtopvaluea--canimationrectmtopvalue"></a><a name="m_topvalue"></a>CAnimationRect::m_topValue  
 Die gekapselte Animationsvariable, die obere repräsentiert gebunden Animation Rechtecks.  
  
```  
CAnimationVariable m_topValue;  
```  
  
##  <a name="a-nameoperatorrecta--canimationrectoperator-rect"></a><a name="operator_rect"></a>CAnimationRect::operator RECT  
 Konvertiert einen CAnimationRect in Rect.  
  
```  
operator RECT();
```   
  
### <a name="return-value"></a>Rückgabewert  
 Aktuellen Wert der Animation Rechteck als Rect.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ruft intern GetValue. Wenn GetValue aus irgendeinem Grund fehlschlägt, enthält das zurückgegebene RECT Standardwerte für alle Koordinaten für das Rechteck.  
  
##  <a name="a-nameoperatoreqa--canimationrectoperator"></a><a name="operator_eq"></a>CAnimationRect::operator =  
 Weist CAnimationRect Rect zu.  
  
```  
void operator=(const RECT& rect);
```  
  
### <a name="parameters"></a>Parameter  
 `rect`  
 Der neue Wert der Animation Rechteck.  
  
### <a name="remarks"></a>Hinweise  
 Wurde empfohlen, dies vor dem Animationsstart, durchzuführen, da dieser Operator SetDefaultValue aufruft, die die zugrunde liegenden COM-Objekte für Farbkomponenten neu erstellt, wenn sie bereits erstellt wurden. Wenn Sie dieses Animationsobjekt Ereignisse (ValueChanged oder IntegerValueChanged) abonniert haben, müssen Sie diese Ereignisse erneut aktivieren.  
  
##  <a name="a-namesetdefaultvaluea--canimationrectsetdefaultvalue"></a><a name="setdefaultvalue"></a>CAnimationRect::SetDefaultValue  
 Legt den Standardwert fest.  
  
```  
void SetDefaultValue(const CRect& rect);
```  
  
### <a name="parameters"></a>Parameter  
 `rect`  
 Gibt neue Standardwerte für Links, oben, rechts und unten an.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, um einen Standardwert auf Animationsobjekt festzulegen. Diese Methoden den Grenzen des Rechteck Standardwerte zugewiesen. Auch neu zugrunde liegende COM-Objekte, wenn sie bereits erstellt wurden. Wenn Sie dieses Animationsobjekt Ereignisse (ValueChanged oder IntegerValueChanged) abonniert haben, müssen Sie diese Ereignisse erneut aktivieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

