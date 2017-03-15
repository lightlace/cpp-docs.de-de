---
title: CAccelerateDecelerateTransition-Class1 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAccelerateDecelerateTransition
- afxanimationcontroller/CAccelerateDecelerateTransition
dev_langs:
- C++
helpviewer_keywords:
- CAccelerateDecelerateTransition class
ms.assetid: b1f31ee8-bb11-4ccc-b124-365fb02b025c
caps.latest.revision: 16
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: f11dc96b48695b998fb17c33735e8f56bce517b7
ms.lasthandoff: 02/24/2017

---
# <a name="cacceleratedeceleratetransition-class"></a>CAccelerateDecelerateTransition-Klasse
Implementiert einen Übergang mit Beschleunigung/Verlangsamung.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CAccelerateDecelerateTransition : public CBaseTransition;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAccelerateDecelerateTransition::CAccelerateDecelerateTransition](#cacceleratedeceleratetransition)|Erstellt ein Übergangsobjekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAccelerateDecelerateTransition::Create](#create)|Ruft die Übergangsbibliothek um gekapselte COM-Übergangsobjekt zu erstellen. (Überschreibt [CBaseTransition:: Create](../../mfc/reference/cbasetransition-class.md#create).)|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAccelerateDecelerateTransition::m_accelerationRatio](#m_accelerationratio)|Das Verhältnis der Zeit damit verbracht, Beschleunigung.|  
|[CAccelerateDecelerateTransition::m_decelerationRatio](#m_decelerationratio)|Das Verhältnis der Zeit, die der Dauer verstrichenen.|  
|[CAccelerateDecelerateTransition::m_duration](#m_duration)|Die Dauer des Übergangs.|  
|[CAccelerateDecelerateTransition::m_finalValue](#m_finalvalue)|Der Wert der Animationsvariablen am Ende des Übergangs.|  
  
## <a name="remarks"></a>Hinweise  
 Während eine schnellere-Übergang verlangsamt, Animationsvariablen beschleunigt und anschließend verlangsamt die Dauer des Übergangs, endet mit einem angegebenen Wert. Sie können steuern, wie schnell die Variable beschleunigt und durch Angabe der anderen Beschleunigung und Verlangsamung Verhältnisse unabhängig, verlangsamt. Wenn die ursprüngliche Geschwindigkeit&0; (null) ist, ist die den Anteil der Dauer, die die Variable beschäftigen beschleunigen; mit der Verlangsamungsrate. Die ursprüngliche Geschwindigkeit ungleich NULL ist, ist der Bruchteil der Zeit zwischen der Geschwindigkeit&0; (null) und das Ende des Übergangs zu erreichen. Das Beschleunigungsverhältnis und der Verlangsamungsrate sollte auf ein Maximum von 1,0 summieren. Da alle Übergänge automatisch gelöscht werden, es wird empfohlen, sie mit dem Operator new. Das gekapselte IUIAnimationTransition-COM-Objekt wird von CAnimationController:: erst erstellt, ist NULL. Ändern Membervariablen, nach der Erstellung dieses COM-Objekt hat keine Auswirkung.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 `CAccelerateDecelerateTransition`   
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxanimationcontroller.h  
  
##  <a name="a-namecacceleratedeceleratetransitiona--cacceleratedeceleratetransitioncacceleratedeceleratetransition"></a><a name="cacceleratedeceleratetransition"></a>CAccelerateDecelerateTransition::CAccelerateDecelerateTransition  
 Erstellt ein Übergangsobjekt.  
  
```  
CAccelerateDecelerateTransition(
    UI_ANIMATION_SECONDS duration,  
    DOUBLE finalValue,  
    DOUBLE accelerationRatio = 0.3,  
    DOUBLE decelerationRatio = 0.3);
```  
  
### <a name="parameters"></a>Parameter  
 `duration`  
 Die Dauer des Übergangs.  
  
 `finalValue`  
 Der Wert der Animationsvariablen am Ende des Übergangs.  
  
 `accelerationRatio`  
 Das Verhältnis der Zeit damit verbracht, Beschleunigung.  
  
 `decelerationRatio`  
 Das Verhältnis der Zeit, die der Dauer verstrichenen.  
  
##  <a name="a-namecreatea--cacceleratedeceleratetransitioncreate"></a><a name="create"></a>CAccelerateDecelerateTransition::Create  
 Ruft die Übergangsbibliothek um gekapselte COM-Übergangsobjekt zu erstellen.  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* *\not used*\);
```  
  
### <a name="parameters"></a>Parameter  
`pLibrary`  
 Ein Zeiger auf eine [IUIAnimationTransitionLibrary-Schnittstelle](https://msdn.microsoft.com/library/windows/desktop/dd371897), die eine Bibliothek mit standard-Übergänge definiert.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn der Übergang erfolgreich erstellt wird. andernfalls FALSE.  
  
##  <a name="a-namemaccelerationratioa--cacceleratedeceleratetransitionmaccelerationratio"></a><a name="m_accelerationratio"></a>CAccelerateDecelerateTransition::m_accelerationRatio  
 Das Verhältnis der Zeit damit verbracht, Beschleunigung.  
  
```  
DOUBLE m_accelerationRatio;  
```  
  
##  <a name="a-namemdecelerationratioa--cacceleratedeceleratetransitionmdecelerationratio"></a><a name="m_decelerationratio"></a>CAccelerateDecelerateTransition::m_decelerationRatio  
 Das Verhältnis der Zeit, die der Dauer verstrichenen.  
  
```  
DOUBLE m_decelerationRatio;  
```  
  
##  <a name="a-namemdurationa--cacceleratedeceleratetransitionmduration"></a><a name="m_duration"></a>CAccelerateDecelerateTransition::m_duration  
 Die Dauer des Übergangs.  
  
```  
UI_ANIMATION_SECONDS m_duration;  
```  
  
##  <a name="a-namemfinalvaluea--cacceleratedeceleratetransitionmfinalvalue"></a><a name="m_finalvalue"></a>CAccelerateDecelerateTransition::m_finalValue  
 Der Wert der Animationsvariablen am Ende des Übergangs.  
  
```  
DOUBLE m_finalValue;  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

