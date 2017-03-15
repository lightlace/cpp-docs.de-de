---
title: CSmoothStopTransition-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSmoothStopTransition
- afxanimationcontroller/CSmoothStopTransition
dev_langs:
- C++
helpviewer_keywords:
- CSmoothStopTransition class
ms.assetid: e1a4b476-6f96-43dd-90db-870a64406b85
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
ms.openlocfilehash: 60cdc3528d10270187dccd42a634f7483c58821f
ms.lasthandoff: 02/24/2017

---
# <a name="csmoothstoptransition-class"></a>CSmoothStopTransition-Klasse
Kapselt einen Übergang mit weicher Beendigung.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CSmoothStopTransition : public CBaseTransition;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSmoothStopTransition::CSmoothStopTransition](#csmoothstoptransition)|Einen Übergang mit weicher Beendigung erstellt und initialisiert seine maximale Dauer und endgültigen Wert.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSmoothStopTransition::Create](#create)|Ruft die Übergangsbibliothek um gekapselte COM-Übergangsobjekt zu erstellen. (Überschreibt [CBaseTransition:: Create](../../mfc/reference/cbasetransition-class.md#create).)|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSmoothStopTransition::m_dblFinalValue](#m_dblfinalvalue)|Der Wert der Animationsvariablen am Ende des Übergangs.|  
|[CSmoothStopTransition::m_maximumDuration](#m_maximumduration)|Die maximale Dauer des Übergangs.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Übergang mit weicher Beendigung wird verlangsamt, einen angegebenen Endwert erreicht, und es mit einer Geschwindigkeit von&0; (null) erreicht. Die Dauer des Übergangs wird von der ursprünglichen Geschwindigkeit, den Unterschied zwischen der ersten und letzten Werte, und der angegebenen maximalen Dauer bestimmt. Wenn keine Lösung bestehend aus einem einzelnen mit parabelförmiger Bogen vorhanden ist, erstellt diese Methode einen kubischen Übergang. Da alle Übergänge automatisch gelöscht werden, es wird empfohlen, sie mit dem Operator new. Das gekapselte IUIAnimationTransition-COM-Objekt wird von CAnimationController:: erst erstellt, ist NULL. Ändern Membervariablen, nach der Erstellung dieses COM-Objekt hat keine Auswirkung.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CSmoothStopTransition](../../mfc/reference/csmoothstoptransition-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxanimationcontroller.h  
  
##  <a name="a-namecreatea--csmoothstoptransitioncreate"></a><a name="create"></a>CSmoothStopTransition::Create  
 Ruft die Übergangsbibliothek um gekapselte COM-Übergangsobjekt zu erstellen.  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* \*not used*\);
```  
  
### <a name="parameters"></a>Parameter  
 `pLibrary`  
 Ein Zeiger auf Übergangsbibliothek, die für die Erstellung der standard-Übergänge zuständig ist.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn der Übergang erfolgreich erstellt wird. andernfalls FALSE.  
  
##  <a name="a-namecsmoothstoptransitiona--csmoothstoptransitioncsmoothstoptransition"></a><a name="csmoothstoptransition"></a>CSmoothStopTransition::CSmoothStopTransition  
 Einen Übergang mit weicher Beendigung erstellt und initialisiert seine maximale Dauer und endgültigen Wert.  
  
```  
CSmoothStopTransition(
    UI_ANIMATION_SECONDS maximumDuration,  
    DOUBLE dblFinalValue);
```  
  
### <a name="parameters"></a>Parameter  
 `maximumDuration`  
 Die maximale Dauer des Übergangs.  
  
 `dblFinalValue`  
 Der Wert der Animationsvariablen am Ende des Übergangs.  
  
##  <a name="a-namemdblfinalvaluea--csmoothstoptransitionmdblfinalvalue"></a><a name="m_dblfinalvalue"></a>CSmoothStopTransition::m_dblFinalValue  
 Der Wert der Animationsvariablen am Ende des Übergangs.  
  
```  
DOUBLE m_dblFinalValue;  
```  
  
##  <a name="a-namemmaximumdurationa--csmoothstoptransitionmmaximumduration"></a><a name="m_maximumduration"></a>CSmoothStopTransition::m_maximumDuration  
 Die maximale Dauer des Übergangs.  
  
```  
UI_ANIMATION_SECONDS m_maximumDuration;  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

