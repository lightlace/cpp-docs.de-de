---
title: CParabolicTransitionFromAcceleration-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CParabolicTransitionFromAcceleration
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::CParabolicTransitionFromAcceleration
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::Create
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::m_dblAcceleration
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::m_dblFinalVelocity
dev_langs: C++
helpviewer_keywords:
- CParabolicTransitionFromAcceleration [MFC], CParabolicTransitionFromAcceleration
- CParabolicTransitionFromAcceleration [MFC], Create
- CParabolicTransitionFromAcceleration [MFC], m_dblAcceleration
- CParabolicTransitionFromAcceleration [MFC], m_dblFinalValue
- CParabolicTransitionFromAcceleration [MFC], m_dblFinalVelocity
ms.assetid: 1e59b86f-358b-4da0-a4fd-8eaf5e85e00f
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: bb4ac9cb8ad6921297a99cad79a2b83c7f142b25
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="cparabolictransitionfromacceleration-class"></a>CParabolicTransitionFromAcceleration-Klasse
Kapselt einen Übergang mit parabelförmiger Beschleunigung.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CParabolicTransitionFromAcceleration : public CBaseTransition;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CParabolicTransitionFromAcceleration::CParabolicTransitionFromAcceleration](#cparabolictransitionfromacceleration)|Erstellt einen Übergang mit parabelförmiger Beschleunigung und initialisiert sie mit den angegebenen Parametern.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CParabolicTransitionFromAcceleration::Create](#create)|Ruft den Übergangsbibliothek, um die gekapselte COM-Übergangsobjekt zu erstellen. (Überschreibt [CBaseTransition:: Create](../../mfc/reference/cbasetransition-class.md#create).)|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CParabolicTransitionFromAcceleration::m_dblAcceleration](#m_dblacceleration)|Die Beschleunigung der Animationsvariablen während des Übergangs.|  
|[CParabolicTransitionFromAcceleration::m_dblFinalValue](#m_dblfinalvalue)|Der Wert der Animationsvariablen am Ende des Übergangs.|  
|[CParabolicTransitionFromAcceleration::m_dblFinalVelocity](#m_dblfinalvelocity)|Die Geschwindigkeit der Animationsvariablen am Ende des Übergangs.|  
  
## <a name="remarks"></a>Hinweise  
 Der Wert der Animationsvariablen geändert während eines Übergangs mit parabelförmiger Beschleunigung aus dem Startwert, um den endgültigen Wert endet mit einer angegebenen Geschwindigkeit. Sie können steuern, wie schnell die Variable den endgültigen Wert erreicht, indem Sie die Rate der Beschleunigung angeben. Da alle Übergänge automatisch gelöscht werden, es wird empfohlen, belegt sie mit dem Operator new. Das gekapselte IUIAnimationTransition-COM-Objekt wird von CAnimationController:: erst erstellt, ist es auf NULL. Ändern Membervariablen, nach der Erstellung dieses COM-Objekt hat keine Auswirkung.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CParabolicTransitionFromAcceleration](../../mfc/reference/cparabolictransitionfromacceleration-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxanimationcontroller.h  
  
##  <a name="cparabolictransitionfromacceleration"></a>CParabolicTransitionFromAcceleration::CParabolicTransitionFromAcceleration  
 Erstellt einen Übergang mit parabelförmiger Beschleunigung und initialisiert sie mit den angegebenen Parametern.  
  
```  
CParabolicTransitionFromAcceleration(
    DOUBLE dblFinalValue,  
    DOUBLE dblFinalVelocity,  
    DOUBLE dblAcceleration);
```  
  
### <a name="parameters"></a>Parameter  
 `dblFinalValue`  
 Der Wert der Animationsvariablen am Ende des Übergangs.  
  
 `dblFinalVelocity`  
 Die Geschwindigkeit der Animationsvariablen am Ende des Übergangs.  
  
 `dblAcceleration`  
 Die Beschleunigung der Animationsvariablen während des Übergangs.  
  
##  <a name="create"></a>CParabolicTransitionFromAcceleration::Create  
 Ruft den Übergangsbibliothek, um die gekapselte COM-Übergangsobjekt zu erstellen.  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* /* not used */);
```  
  
### <a name="parameters"></a>Parameter  
 `pLibrary`  
 Ein Zeiger auf den Übergangsbibliothek, die für die Erstellung der standardmäßigen Übergänge verwendet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn der Übergang erfolgreich erstellt wurde. andernfalls "false".  
  
##  <a name="m_dblacceleration"></a>CParabolicTransitionFromAcceleration::m_dblAcceleration  
 Die Beschleunigung der Animationsvariablen während des Übergangs.  
  
```  
DOUBLE m_dblAcceleration;  
```  
  
##  <a name="m_dblfinalvalue"></a>CParabolicTransitionFromAcceleration::m_dblFinalValue  
 Der Wert der Animationsvariablen am Ende des Übergangs.  
  
```  
DOUBLE m_dblFinalValue;  
```  
  
##  <a name="m_dblfinalvelocity"></a>CParabolicTransitionFromAcceleration::m_dblFinalVelocity  
 Die Geschwindigkeit der Animationsvariablen am Ende des Übergangs.  
  
```  
DOUBLE m_dblFinalVelocity;  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)
