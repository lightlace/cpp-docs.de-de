---
title: CConstantTransition-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- afxanimationcontroller/CConstantTransition
- CConstantTransition
dev_langs:
- C++
helpviewer_keywords:
- CConstantTransition class
ms.assetid: f6fa4780-a71b-4cd6-80aa-d4792ace36c2
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: e6c8b8e27cd6618a7dfe690a58ba470a667adf1d
ms.lasthandoff: 02/24/2017

---
# <a name="cconstanttransition-class"></a>CConstantTransition-Klasse
Kapselt einen konstanten Übergang.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CConstantTransition : public CBaseTransition;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CConstantTransition::CConstantTransition](#cconstanttransition)|Ein Übergangsobjekt erstellt und initialisiert seine Dauer.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CConstantTransition::Create](#create)|Ruft die Übergangsbibliothek um gekapselte COM-Übergangsobjekt zu erstellen. (Überschreibt [CBaseTransition:: Create](../../mfc/reference/cbasetransition-class.md#create).)|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CConstantTransition::m_duration](#m_duration)|Die Dauer des Übergangs.|  
  
## <a name="remarks"></a>Hinweise  
 Während eines Übergangs konstant bleibt der Wert einer Animationsvariablen den Anfangswert für die Dauer des Übergangs. Da alle Übergänge automatisch gelöscht werden, es wird empfohlen, sie mit dem Operator new. Das gekapselte IUIAnimationTransition-COM-Objekt wird von CAnimationController:: erst erstellt, ist NULL. Ändern Membervariablen, nach der Erstellung dieses COM-Objekt hat keine Auswirkung.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 `CConstantTransition`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxanimationcontroller.h  
  
##  <a name="a-namecconstanttransitiona--cconstanttransitioncconstanttransition"></a><a name="cconstanttransition"></a>CConstantTransition::CConstantTransition  
 Ein Übergangsobjekt erstellt und initialisiert seine Dauer.  
  
```  
CConstantTransition (UI_ANIMATION_SECONDS duration);
```  
  
### <a name="parameters"></a>Parameter  
 `duration`  
 Die Dauer des Übergangs.  
  
##  <a name="a-namecreatea--cconstanttransitioncreate"></a><a name="create"></a>CConstantTransition::Create  
 Ruft die Übergangsbibliothek um gekapselte COM-Übergangsobjekt zu erstellen.  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* \*not used*\);
```  
  
### <a name="parameters"></a>Parameter  
 `pLibrary`  
 Ein Zeiger auf eine [IUIAnimationTransitionLibrary-Schnittstelle](https://msdn.microsoft.com/library/windows/desktop/dd371897), die eine Bibliothek mit standard-Übergänge definiert.  

### <a name="return-value"></a>Rückgabewert  
 True, wenn der Übergang erfolgreich erstellt wird. andernfalls FALSE.  
  
##  <a name="a-namemdurationa--cconstanttransitionmduration"></a><a name="m_duration"></a>CConstantTransition::m_duration  
 Die Dauer des Übergangs.  
  
```  
UI_ANIMATION_SECONDS m_duration;  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

