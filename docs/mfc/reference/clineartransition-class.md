---
title: CLinearTransition-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CLinearTransition
- afxanimationcontroller/CLinearTransition
dev_langs:
- C++
helpviewer_keywords:
- CLinearTransition class
ms.assetid: 7fcb2dba-beb8-4933-9f5d-3b7fb1585ef0
caps.latest.revision: 18
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
ms.openlocfilehash: c39a3961600401f47f2f38d1a0cd735b1237813f
ms.lasthandoff: 02/24/2017

---
# <a name="clineartransition-class"></a>CLinearTransition-Klasse
Kapselt einen linearen Übergang.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CLinearTransition : public CBaseTransition;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CLinearTransition::CLinearTransition](#clineartransition)|Erstellt einen linearen Übergang-Objekt und initialisiert es mit Dauer und endgültigen Wert.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CLinearTransition::Create](#create)|Ruft die Übergangsbibliothek um gekapselte COM-Übergangsobjekt zu erstellen. (Überschreibt [CBaseTransition:: Create](../../mfc/reference/cbasetransition-class.md#create).)|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CLinearTransition::m_dblFinalValue](#m_dblfinalvalue)|Der Wert der Animationsvariablen am Ende des Übergangs.|  
|[CLinearTransition::m_duration](#m_duration)|Die Dauer des Übergangs.|  
  
## <a name="remarks"></a>Hinweise  
 Während eines linearen Übergangs ändert sich der Wert der Animationsvariablen linear vom Anfangswert bis zu einem angegebenen Endwert. Da alle Übergänge automatisch gelöscht werden, es wird empfohlen, sie mit dem Operator new. Das gekapselte IUIAnimationTransition-COM-Objekt wird von CAnimationController:: erst erstellt, ist NULL. Ändern Membervariablen, nach der Erstellung dieses COM-Objekt hat keine Auswirkung.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CLinearTransition](../../mfc/reference/clineartransition-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxanimationcontroller.h  
  
##  <a name="a-nameclineartransitiona--clineartransitionclineartransition"></a><a name="clineartransition"></a>CLinearTransition::CLinearTransition  
 Erstellt einen linearen Übergang-Objekt und initialisiert es mit Dauer und endgültigen Wert.  
  
```  
CLinearTransition(
    UI_ANIMATION_SECONDS duration,  
    DOUBLE dblFinalValue);
```  
  
### <a name="parameters"></a>Parameter  
 `duration`  
 Die Dauer des Übergangs.  
  
 `dblFinalValue`  
 Der Wert der Animationsvariablen am Ende des Übergangs.  
  
##  <a name="a-namecreatea--clineartransitioncreate"></a><a name="create"></a>CLinearTransition::Create  
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
  
##  <a name="a-namemdblfinalvaluea--clineartransitionmdblfinalvalue"></a><a name="m_dblfinalvalue"></a>CLinearTransition::m_dblFinalValue  
 Der Wert der Animationsvariablen am Ende des Übergangs.  
  
```  
DOUBLE m_dblFinalValue;  
```  
  
##  <a name="a-namemdurationa--clineartransitionmduration"></a><a name="m_duration"></a>CLinearTransition::m_duration  
 Die Dauer des Übergangs.  
  
```  
UI_ANIMATION_SECONDS m_duration;  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

