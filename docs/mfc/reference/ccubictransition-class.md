---
title: CCubicTransition-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCubicTransition
- AFXANIMATIONCONTROLLER/CCubicTransition
- AFXANIMATIONCONTROLLER/CCubicTransition::CCubicTransition
- AFXANIMATIONCONTROLLER/CCubicTransition::Create
- AFXANIMATIONCONTROLLER/CCubicTransition::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CCubicTransition::m_dblFinalVelocity
- AFXANIMATIONCONTROLLER/CCubicTransition::m_duration
dev_langs:
- C++
helpviewer_keywords:
- CCubicTransition [MFC], CCubicTransition
- CCubicTransition [MFC], Create
- CCubicTransition [MFC], m_dblFinalValue
- CCubicTransition [MFC], m_dblFinalVelocity
- CCubicTransition [MFC], m_duration
ms.assetid: 4fc30e9c-160c-45e1-bdbe-51adf8fee9c5
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 4a770b6508067913aec51b8b3878f33e30eed4bb
ms.openlocfilehash: 428b9e05cc2d4f1ead76d8842a31c36637fbb4f0
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="ccubictransition-class"></a>CCubicTransition-Klasse
Kapselt einen kubischen Übergang.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CCubicTransition : public CBaseTransition;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CCubicTransition::CCubicTransition](#ccubictransition)|Ein Übergangsobjekt erstellt und initialisiert seine Parameter.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CCubicTransition::Create](#create)|Ruft den Übergangsbibliothek, um die gekapselte COM-Übergangsobjekt zu erstellen. (Überschreibt [CBaseTransition:: Create](../../mfc/reference/cbasetransition-class.md#create).)|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CCubicTransition::m_dblFinalValue](#m_dblfinalvalue)|Der Wert der Animationsvariablen am Ende des Übergangs.|  
|[CCubicTransition::m_dblFinalVelocity](#m_dblfinalvelocity)|Die Geschwindigkeit der Animationsvariablen am Ende des Übergangs.|  
|[CCubicTransition::m_duration](#m_duration)|Die Dauer des Übergangs.|  
  
## <a name="remarks"></a>Hinweise  
 Während einen kubischen Übergang ändert den Wert der Animationsvariablen ihrem ursprünglichen Wert in einem angegebenen Endwert über die Dauer des Übergangs, endend mit einem angegebenen Geschwindigkeit. Da alle Übergänge automatisch gelöscht werden, es wird empfohlen, belegt sie mit dem Operator new. Das gekapselte IUIAnimationTransition-COM-Objekt wird von CAnimationController:: erst erstellt, ist es auf NULL. Ändern Membervariablen, nach der Erstellung dieses COM-Objekt hat keine Auswirkung.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 `CCubicTransition`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxanimationcontroller.h  
  
##  <a name="ccubictransition"></a>CCubicTransition::CCubicTransition  
 Ein Übergangsobjekt erstellt und initialisiert seine Parameter.  
  
```  
CCubicTransition(
    UI_ANIMATION_SECONDS duration,  
    DOUBLE finalValue,  
    DOUBLE finalVelocity);
```  
  
### <a name="parameters"></a>Parameter  
 `duration`  
 Die Dauer des Übergangs.  
  
 `finalValue`  
 Der Wert der Animationsvariablen am Ende des Übergangs.  
  
 `finalVelocity`  
 Die Geschwindigkeit der Animationsvariablen am Ende des Übergangs.  
  
##  <a name="create"></a>CCubicTransition::Create  
 Ruft den Übergangsbibliothek, um die gekapselte COM-Übergangsobjekt zu erstellen.  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* \*not used*\);
```  
  
### <a name="parameters"></a>Parameter  
`pLibrary`  
 Ein Zeiger auf ein [IUIAnimationTransitionLibrary-Schnittstelle](https://msdn.microsoft.com/library/windows/desktop/dd371897), die eine Bibliothek mit standard-Übergänge definiert.  

### <a name="return-value"></a>Rückgabewert  
 True, wenn der Übergang erfolgreich erstellt wurde. andernfalls "false".  
  
##  <a name="m_dblfinalvalue"></a>CCubicTransition::m_dblFinalValue  
 Der Wert der Animationsvariablen am Ende des Übergangs.  
  
```  
DOUBLE m_dblFinalValue;  
```  
  
##  <a name="m_dblfinalvelocity"></a>CCubicTransition::m_dblFinalVelocity  
 Die Geschwindigkeit der Animationsvariablen am Ende des Übergangs.  
  
```  
DOUBLE m_dblFinalVelocity;  
```  
  
##  <a name="m_duration"></a>CCubicTransition::m_duration  
 Die Dauer des Übergangs.  
  
```  
UI_ANIMATION_SECONDS m_duration;  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

