---
title: CAccelerateDecelerateTransition-Class1 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAccelerateDecelerateTransition
- afxanimationcontroller/CAccelerateDecelerateTransition
dev_langs:
- C++
helpviewer_keywords:
- CAccelerateDecelerateTransition class [MFC]
ms.assetid: b1f31ee8-bb11-4ccc-b124-365fb02b025c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d1dac40e91dd7b0a91c5d76b0d665d075e562267
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cacceleratedeceleratetransition-class"></a>CAccelerateDecelerateTransition-Klasse
Implementiert einen Übergang mit Beschleunigung/Verlangsamung.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CAccelerateDecelerateTransition : public CBaseTransition;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAccelerateDecelerateTransition::CAccelerateDecelerateTransition](#cacceleratedeceleratetransition)|Erstellt ein Übergangsobjekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAccelerateDecelerateTransition::Create](#create)|Ruft den Übergangsbibliothek, um die gekapselte COM-Übergangsobjekt zu erstellen. (Überschreibt [CBaseTransition:: Create](../../mfc/reference/cbasetransition-class.md#create).)|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAccelerateDecelerateTransition::m_accelerationRatio](#m_accelerationratio)|Das Verhältnis der die Zeit für die Dauer zu beschleunigen.|  
|[CAccelerateDecelerateTransition::m_decelerationRatio](#m_decelerationratio)|Das Verhältnis der Zeit verstrichenen die Dauer.|  
|[CAccelerateDecelerateTransition::m_duration](#m_duration)|Die Dauer des Übergangs.|  
|[CAccelerateDecelerateTransition::m_finalValue](#m_finalvalue)|Der Wert der Animationsvariablen am Ende des Übergangs.|  
  
## <a name="remarks"></a>Hinweise  
 Während eine Beschleunigung-Übergang verlangsamen, Animationsvariablen beschleunigt, und klicken Sie dann über die Dauer des Übergangs, endend mit einem angegebenen Wert verlangsamt. Sie können steuern, wie schnell die Variable beschleunigt und verlangsamt unabhängig, indem verschiedene Beschleunigung und Verlangsamung Verhältnissen. Bei die ursprüngliche Geschwindigkeit 0 (null) ist, ist das Verhältnis Acceleration den Anteil der Dauer, die die Variable ausgeben zu beschleunigen. Ebenso mit der Verlangsamungsrate. Wenn die ursprüngliche Geschwindigkeit ungleich NULL ist, ist es der Bruchteil der Zeit zwischen der Geschwindigkeit erreichen von 0 (null) und das Ende des Übergangs an. Das Beschleunigungsverhältnis und der Verlangsamungsrate sollte auf ein Maximum von 1.0 Summe. Da alle Übergänge automatisch gelöscht werden, es wird empfohlen, belegt sie mit dem Operator new. Das gekapselte IUIAnimationTransition-COM-Objekt wird von CAnimationController:: erst erstellt, ist es auf NULL. Ändern Membervariablen, nach der Erstellung dieses COM-Objekt hat keine Auswirkung.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 `CAccelerateDecelerateTransition`   
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxanimationcontroller.h  
  
##  <a name="cacceleratedeceleratetransition"></a>  CAccelerateDecelerateTransition::CAccelerateDecelerateTransition  
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
 Das Verhältnis der die Zeit für die Dauer zu beschleunigen.  
  
 `decelerationRatio`  
 Das Verhältnis der Zeit verstrichenen die Dauer.  
  
##  <a name="create"></a>  CAccelerateDecelerateTransition::Create  
 Ruft den Übergangsbibliothek, um die gekapselte COM-Übergangsobjekt zu erstellen.  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* *\not used*\);
```  
  
### <a name="parameters"></a>Parameter  
`pLibrary`  
 Ein Zeiger auf ein [IUIAnimationTransitionLibrary-Schnittstelle](https://msdn.microsoft.com/library/windows/desktop/dd371897), die eine Bibliothek mit standard-Übergänge definiert.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn der Übergang erfolgreich erstellt wurde. andernfalls "false".  
  
##  <a name="m_accelerationratio"></a>  CAccelerateDecelerateTransition::m_accelerationRatio  
 Das Verhältnis der die Zeit für die Dauer zu beschleunigen.  
  
```  
DOUBLE m_accelerationRatio;  
```  
  
##  <a name="m_decelerationratio"></a>  CAccelerateDecelerateTransition::m_decelerationRatio  
 Das Verhältnis der Zeit verstrichenen die Dauer.  
  
```  
DOUBLE m_decelerationRatio;  
```  
  
##  <a name="m_duration"></a>  CAccelerateDecelerateTransition::m_duration  
 Die Dauer des Übergangs.  
  
```  
UI_ANIMATION_SECONDS m_duration;  
```  
  
##  <a name="m_finalvalue"></a>  CAccelerateDecelerateTransition::m_finalValue  
 Der Wert der Animationsvariablen am Ende des Übergangs.  
  
```  
DOUBLE m_finalValue;  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)
