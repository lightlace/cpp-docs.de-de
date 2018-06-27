---
title: CAnimationRect-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAnimationRect
- AFXANIMATIONCONTROLLER/CAnimationRect
- AFXANIMATIONCONTROLLER/CAnimationRect::CAnimationRect
- AFXANIMATIONCONTROLLER/CAnimationRect::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationRect::GetBottom
- AFXANIMATIONCONTROLLER/CAnimationRect::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationRect::GetLeft
- AFXANIMATIONCONTROLLER/CAnimationRect::GetRight
- AFXANIMATIONCONTROLLER/CAnimationRect::GetTop
- AFXANIMATIONCONTROLLER/CAnimationRect::GetValue
- AFXANIMATIONCONTROLLER/CAnimationRect::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationRect::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationRect::m_bFixedSize
- AFXANIMATIONCONTROLLER/CAnimationRect::m_bottomValue
- AFXANIMATIONCONTROLLER/CAnimationRect::m_leftValue
- AFXANIMATIONCONTROLLER/CAnimationRect::m_rightValue
- AFXANIMATIONCONTROLLER/CAnimationRect::m_szInitial
- AFXANIMATIONCONTROLLER/CAnimationRect::m_topValue
dev_langs:
- C++
helpviewer_keywords:
- CAnimationRect [MFC], CAnimationRect
- CAnimationRect [MFC], AddTransition
- CAnimationRect [MFC], GetBottom
- CAnimationRect [MFC], GetDefaultValue
- CAnimationRect [MFC], GetLeft
- CAnimationRect [MFC], GetRight
- CAnimationRect [MFC], GetTop
- CAnimationRect [MFC], GetValue
- CAnimationRect [MFC], SetDefaultValue
- CAnimationRect [MFC], GetAnimationVariableList
- CAnimationRect [MFC], m_bFixedSize
- CAnimationRect [MFC], m_bottomValue
- CAnimationRect [MFC], m_leftValue
- CAnimationRect [MFC], m_rightValue
- CAnimationRect [MFC], m_szInitial
- CAnimationRect [MFC], m_topValue
ms.assetid: 0294156d-241e-4a57-92b2-31234fe557d6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3959ae03d40bac93ca6453c254e894b8782f5333
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36957197"
---
# <a name="canimationrect-class"></a>CAnimationRect-Klasse
Implementiert die Funktion eines Rechtecks, dessen Seiten animiert werden können.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CAnimationRect : public CAnimationBaseObject;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationRect::CAnimationRect](#canimationrect)|Überladen. Erstellt eine Animation Rect-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationRect::AddTransition](#addtransition)|Fügt Übergänge für den linken, oberen, rechten und unteren Koordinaten an.|  
|[CAnimationRect::GetBottom](#getbottom)|Bietet Zugriff auf CAnimationVariable, die untere Koordinate darstellt.|  
|[CAnimationRect::GetDefaultValue](#getdefaultvalue)|Gibt die Standardwerte für die Grenzen des Rechtecks.|  
|[CAnimationRect::GetLeft](#getleft)|Bietet Zugriff auf CAnimationVariable, die linke Koordinate darstellt.|  
|[CAnimationRect::GetRight](#getright)|Bietet Zugriff auf CAnimationVariable, die rechte Koordinate darstellt.|  
|[CAnimationRect::GetTop](#gettop)|Bietet Zugriff auf CAnimationVariable, die obere Koordinate darstellt.|  
|[CAnimationRect::GetValue](#getvalue)|Gibt den aktuellen Wert zurück.|  
|[CAnimationRect::SetDefaultValue](#setdefaultvalue)|Legt den Standardwert fest.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationRect::GetAnimationVariableList](#getanimationvariablelist)|Legt die gekapselten Animationsvariablen in einer Liste an. (Überschreibt [CAnimationBaseObject:: GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationRect::operator RECT](#operator_rect)|Konvertiert einen CAnimationRect in Rect.|  
|[CAnimationRect::operator =](#operator_eq)|CAnimationRect Rect zugewiesen.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAnimationRect::m_bFixedSize](#m_bfixedsize)|Gibt an, ob das Rechteck eine feste Größe hat.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CAnimationRect::m_bottomValue](#m_bottomvalue)|Gekapselte Animationsvariablen unten stellt dar, die Grenze für Animation Rechteck.|  
|[CAnimationRect::m_leftValue](#m_leftvalue)|Animation Rechteck Grenze gekapselten Animationsvariablen, das Links darstellt.|  
|[CAnimationRect::m_rightValue](#m_rightvalue)|Animation Rechteck Grenze gekapselten Animationsvariablen, die rechts darstellt.|  
|[CAnimationRect::m_szInitial](#m_szinitial)|Gibt die Anfangsgröße der Animation Rechteck.|  
|[CAnimationRect::m_topValue](#m_topvalue)|Animation Rechteck Grenze gekapselten Animationsvariablen, die nach oben darstellt.|  
  
## <a name="remarks"></a>Hinweise  
 CAnimationRect-Klasse kapselt vier CAnimationVariable-Objekte und kann in Anwendungen ein Rechteck dargestellt. Zum Verwenden dieser Klasse in der Anwendung einfach instanziieren Sie ein Objekt dieser Klasse, Animationscontroller AddAnimationObject hinzugefügt, und rufen Sie AddTransition für jeden Übergang auf nach links, rechts oben und unten Koordinaten angewendet werden soll.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 `CAnimationRect`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxanimationcontroller.h  
  
##  <a name="addtransition"></a>  CAnimationRect::AddTransition  
 Fügt Übergänge für den linken, oberen, rechten und unteren Koordinaten an.  
  
```  
void AddTransition(
    CBaseTransition* pLeftTransition,  
    CBaseTransition* pTopTransition,  
    CBaseTransition* pRightTransition,  
    CBaseTransition* pBottomTransition);
```  
  
### <a name="parameters"></a>Parameter  
 *pLeftTransition*  
 Gibt an, für die linke Seite Übergang.  
  
 *pTopTransition*  
 Gibt an, für die obere Seite Übergang.  
  
 *pRightTransition*  
 Gibt Übergang von der rechten Seite an.  
  
 *pBottomTransition*  
 Gibt an, für die Unterseite Übergang.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um die interne Liste der Übergänge, die auf Animationsvariablen für die einzelnen Rechteckseiten angewendet werden die angegebenen Übergänge hinzuzufügen. Wenn Sie Übergänge hinzufügen, werden sie nicht sofort angewendet und in einer internen Liste gespeichert. Übergänge werden angewendet (ein Storyboard für einen bestimmten Wert hinzugefügt) beim CAnimationController:: AnimateGroup aufrufen. Wenn Sie keinen Übergang auf eine der Rechteckseiten anwenden müssen, können Sie NULL übergeben.  
  
##  <a name="canimationrect"></a>  CAnimationRect::CAnimationRect  
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
 *Rect*  
 Gibt an Standardeinstellung Rechteck.  
  
 *nGroupID*  
 Gibt Gruppen-ID.  
  
 *nObjectID*  
 Gibt die Objekt-ID.  
  
 *dwUserData*  
 Gibt die benutzerdefinierten Daten.  
  
 *pt*  
 -Koordinate der oberen linken Ecke.  
  
 *sz*  
 Die Größe des Rechtecks.  
  
 *nLeft*  
 Gibt Koordinate der linken gebunden.  
  
 *nTop*  
 Gibt Koordinate der oberen Grenze an.  
  
 *nRight*  
 Gibt Koordinate der rechten gebunden.  
  
 *nBottom*  
 Gibt Koordinate der unteren gebunden.  
  
### <a name="remarks"></a>Hinweise  
 Das Objekt wird erstellt, mit Standardwerten für Links, oben, rechts und unten, Objekt-ID und Gruppen-ID, die auf 0 festgelegt werden. Sie können später mithilfe von SetDefaultValue und SetID zur Laufzeit geändert werden.  
  
##  <a name="getanimationvariablelist"></a>  CAnimationRect::GetAnimationVariableList  
 Legt die gekapselten Animationsvariablen in einer Liste an.  
  
```  
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*, 
    CAnimationVariable*>& lst);
```  
  
### <a name="parameters"></a>Parameter  
 *lst*  
 Wenn die Funktion zurückgibt, enthält Zeiger auf vier CAnimationVariable-Objekte, die Koordinaten eines Rechtecks darstellt.  
  
##  <a name="getbottom"></a>  CAnimationRect::GetBottom  
 Bietet Zugriff auf CAnimationVariable, die untere Koordinate darstellt.  
  
```  
CAnimationVariable& GetBottom();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf gekapselte CAnimationVariable, untere Koordinate darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Abrufen von direkten Zugriffs auf die zugrunde liegende CAnimationVariable, die die untere Koordinate darstellt.  
  
##  <a name="getdefaultvalue"></a>  CAnimationRect::GetDefaultValue  
 Gibt die Standardwerte für die Grenzen des Rechtecks.  
  
```  
CRect GetDefaultValue();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein CRect-Wert, die Standardwerte für den linken, rechten, oberen und unteren enthält.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird zum Abrufen von Standardwert, der zuvor vom Konstruktor oder mit SetDefaultValue festgelegt wurde.  
  
##  <a name="getleft"></a>  CAnimationRect::GetLeft  
 Bietet Zugriff auf CAnimationVariable, die linke Koordinate darstellt.  
  
```  
CAnimationVariable& GetLeft();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf gekapselte CAnimationVariable, linke Koordinate darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Abrufen von direkten Zugriffs auf die zugrunde liegende CAnimationVariable, die die linke Koordinate darstellt.  
  
##  <a name="getright"></a>  CAnimationRect::GetRight  
 Bietet Zugriff auf CAnimationVariable, die rechte Koordinate darstellt.  
  
```  
CAnimationVariable& GetRight();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf gekapselte CAnimationVariable, rechte Koordinate darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Abrufen von direkten Zugriffs auf die zugrunde liegende CAnimationVariable, die die rechte Koordinate darstellt.  
  
##  <a name="gettop"></a>  CAnimationRect::GetTop  
 Bietet Zugriff auf CAnimationVariable, die obere Koordinate darstellt.  
  
```  
CAnimationVariable& GetTop();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf gekapselte CAnimationVariable, die obere Koordinate darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Abrufen von direkten Zugriffs auf die zugrunde liegende CAnimationVariable, die die obere Koordinate darstellt.  
  
##  <a name="getvalue"></a>  CAnimationRect::GetValue  
 Gibt den aktuellen Wert zurück.  
  
```  
BOOL GetValue(CRect& rect);
```  
  
### <a name="parameters"></a>Parameter  
 *Rect*  
 Die Ausgabe. Enthält den aktuellen Wert an, wenn diese Methode zurückgegeben wird.  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn der aktuelle Wert erfolgreich abgerufen wurde. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird zum Abrufen des aktuellen Wert der Animation Rechteck. Wenn diese Methode fehlschlägt oder die zugrunde liegende COM-Objekte für Left, oberen, rechten und unteren nicht initialisiert wurden, enthält Rect einen Standardwert, der zuvor im Konstruktor oder mit SetDefaultValue festgelegt wurde.  
  
##  <a name="m_bfixedsize"></a>  CAnimationRect::m_bFixedSize  
 Gibt an, ob das Rechteck eine feste Größe hat.  
  
```  
BOOL m_bFixedSize;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn dieses Elements auf "true" festgelegt ist, wird die Größe des Rechtecks, festen und rechten, und unteren Werte werden jedes Mal, wenn die linke obere Ecke, entsprechend der feste Größe verschoben wird berechnet. Legen Sie diesen Wert auf "true", einfache des Rechtecks auf dem Bildschirm verschieben. In diesem Fall werden angewendet, rechten und unteren Koordinaten Übergänge ignoriert. Die Größe wird intern gespeichert werden, wenn Sie das Objekt zu erstellen und/oder SetDefaultValue aufrufen. Standardmäßig ist dieses Elements auf "false" festgelegt.  
  
##  <a name="m_bottomvalue"></a>  CAnimationRect::m_bottomValue  
 Gekapselte Animationsvariablen unten stellt dar, die Grenze für Animation Rechteck.  
  
```  
CAnimationVariable m_bottomValue;  
```  
  
##  <a name="m_leftvalue"></a>  CAnimationRect::m_leftValue  
 Animation Rechteck Grenze gekapselten Animationsvariablen, das Links darstellt.  
  
```  
CAnimationVariable m_leftValue;  
```  
  
##  <a name="m_rightvalue"></a>  CAnimationRect::m_rightValue  
 Animation Rechteck Grenze gekapselten Animationsvariablen, die rechts darstellt.  
  
```  
CAnimationVariable m_rightValue;  
```  
  
##  <a name="m_szinitial"></a>  CAnimationRect::m_szInitial  
 Gibt die Anfangsgröße der Animation Rechteck.  
  
```  
CSize m_szInitial;  
```  
  
##  <a name="m_topvalue"></a>  CAnimationRect::m_topValue  
 Animation Rechteck Grenze gekapselten Animationsvariablen, die nach oben darstellt.  
  
```  
CAnimationVariable m_topValue;  
```  
  
##  <a name="operator_rect"></a>  CAnimationRect::operator RECT  
 Konvertiert einen CAnimationRect in Rect.  
  
```  
operator RECT();
```   
  
### <a name="return-value"></a>Rückgabewert  
 Aktuelle Wert der Animation Rechteck als Rect.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ruft intern GetValue. Wenn GetValue aus irgendeinem Grund fehlschlägt, enthält das zurückgegebene RECT Standardwerte für alle Koordinaten für das Rechteck.  
  
##  <a name="operator_eq"></a>  CAnimationRect::operator =  
 CAnimationRect Rect zugewiesen.  
  
```  
void operator=(const RECT& rect);
```  
  
### <a name="parameters"></a>Parameter  
 *Rect*  
 Der neue Wert der Animation Rechteck.  
  
### <a name="remarks"></a>Hinweise  
 Es wird empfohlen, vor Beginn der Animation, dazu werden sollen, da dieser Operator SetDefaultValue aufruft, die die zugrunde liegenden COM-Objekte für Farbkomponenten neu erstellt, wenn sie erstellt wurden. Wenn Sie dieses Animationsobjekt auf Ereignisse (ValueChanged oder IntegerValueChanged) abonniert haben, müssen Sie diese Ereignisse erneut zu aktivieren.  
  
##  <a name="setdefaultvalue"></a>  CAnimationRect::SetDefaultValue  
 Legt den Standardwert fest.  
  
```  
void SetDefaultValue(const CRect& rect);
```  
  
### <a name="parameters"></a>Parameter  
 *Rect*  
 Gibt neue Standardwerte für den linken, oberen, rechten und unteren an.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, um einen Standardwert zum Animationsobjekts festzulegen. Diese Methoden weisen Standardwerte zu Grenzen des Rechtecks. Zugrunde liegende COM-Objekte erstellt auch neu, wenn sie erstellt wurden. Wenn Sie dieses Animationsobjekt auf Ereignisse (ValueChanged oder IntegerValueChanged) abonniert haben, müssen Sie diese Ereignisse erneut zu aktivieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)
