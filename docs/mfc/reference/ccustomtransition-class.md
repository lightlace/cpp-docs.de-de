---
title: CCustomTransitions-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- afxanimationcontroller/CCustomTransition
- CCustomTransition
dev_langs:
- C++
helpviewer_keywords:
- CCustomTransition class
ms.assetid: 5bd3f492-940f-4290-a38b-fa68eb8f8401
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
ms.openlocfilehash: 483fb2ab84d2c41fe4666a4ea333c0be8b07caee
ms.lasthandoff: 02/24/2017

---
# <a name="ccustomtransition-class"></a>CCustomTransition-Klasse
Implementiert einen benutzerdefinierten Übergang.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CCustomTransition : public CBaseTransition;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CCustomTransition::CCustomTransition](#ccustomtransition)|Erstellt einen benutzerdefinierten Übergang-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CCustomTransition::Create](#create)|Ruft die Übergangsbibliothek um gekapselte COM-Übergangsobjekt zu erstellen. (Überschreibt [CBaseTransition:: Create](../../mfc/reference/cbasetransition-class.md#create).)|  
|[CCustomTransition::SetInitialValue](#setinitialvalue)|Legt einen anfänglichen Wert, die auf eine diesem Übergang zugeordnete Animationsvariable angewendet werden.|  
|[CCustomTransition::SetInitialVelocity](#setinitialvelocity)|Legt eine ursprüngliche Geschwindigkeit, die auf eine diesem Übergang zugeordnete Animationsvariable angewendet werden.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CCustomTransition::m_bInitialValueSpecified](#m_binitialvaluespecified)|Gibt an, ob der Anfangswert mit SetInitialValue angegeben wurde.|  
|[CCustomTransition::m_bInitialVelocitySpecified](#m_binitialvelocityspecified)|Gibt an, ob die ursprüngliche Geschwindigkeit mit SetInitialVelocity angegeben wurde.|  
|[CCustomTransition::m_initialValue](#m_initialvalue)|Speichert den ursprünglichen Wert.|  
|[CCustomTransition::m_initialVelocity](#m_initialvelocity)|Speichert die ursprüngliche Geschwindigkeit.|  
|[CCustomTransition::m_pInterpolator](#m_pinterpolator)|Speichert einen Zeiger auf einen benutzerdefinierten Interpolator.|  
  
## <a name="remarks"></a>Hinweise  
 Die CCustomTransitions-Klasse ermöglicht es Entwicklern, benutzerdefinierte Übergänge zu implementieren. Sie wird erstellt und als Standardübergang verwendet, aber ihr Konstruktor akzeptiert als Parameter einen Zeiger auf einen benutzerdefinierten Interpolator. Führen Sie die folgenden Schritte aus, um benutzerdefinierte Übergänge verwenden: 1. Leiten Sie eine Klasse von CCustomInterpolator ab, und implementieren Sie mindestens InterpolateValue-Methode. 2. Stellen Sie sicher, dass die Lebensdauer des benutzerdefinierten Interpolator Objekts muss länger sein als die Dauer der Animation wird. 3. Instanziieren Sie (mit dem Operator new) ein CCustomTransitions-Objekt, und übergeben Sie einen Zeiger auf benutzerdefinierten Interpolator im Konstruktor. 4. Rufen Sie CCustomTransition::SetInitialValue und CCustomTransition::SetInitialVelocity, wenn diese Parameter für benutzerdefinierte Interpolation erforderlich sind. 5. Übergeben Sie den Zeiger auf den benutzerdefinierten Übergang AddTransition-Methode des Animationsobjekts, dessen Wert mit dem benutzerdefinierten Algorithmus animiert werden soll. 6. Wenn der Wert des Animationsobjekts ändern soll wird Windows Animations-API InterpolateValue (und andere relevanten Methoden) in CCustomInterpolator aufrufen.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 `CCustomTransition`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxanimationcontroller.h  
  
##  <a name="a-nameccustomtransitiona--ccustomtransitionccustomtransition"></a><a name="ccustomtransition"></a>CCustomTransition::CCustomTransition  
 Erstellt einen benutzerdefinierten Übergang-Objekt.  
  
```  
CCustomTransition(CCustomInterpolator* pInterpolator);
```  
  
### <a name="parameters"></a>Parameter  
 `pInterpolator`  
 Ein Zeiger auf benutzerdefinierten Interpolator.  
  
##  <a name="a-namecreatea--ccustomtransitioncreate"></a><a name="create"></a>CCustomTransition::Create  
 Ruft die Übergangsbibliothek um gekapselte COM-Übergangsobjekt zu erstellen.  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* */,  
    IUIAnimationTransitionFactory* pFactory);
```  
  
### <a name="parameters"></a>Parameter  
 `pFactory`  
 Ein Zeiger auf Übergangsfactory, die für die Erstellung von benutzerdefinierten Übergänge zuständig ist.  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode kann auch festgelegt werden, Anfangswert und die ursprüngliche Geschwindigkeit auf eine Animationsvariable angewendet werden, die diesem Übergang zugeordnet ist. Zu diesem Zweck müssen Sie SetInitialValue und SetInitialVelocity aufrufen, bevor das Framework das gekapselte Übergang COM-Objekt erstellt (es erfolgt, wenn Sie CAnimationController:: AnimateGroup aufrufen).  
  
##  <a name="a-namembinitialvaluespecifieda--ccustomtransitionmbinitialvaluespecified"></a><a name="m_binitialvaluespecified"></a>CCustomTransition::m_bInitialValueSpecified  
 Gibt an, ob der Anfangswert mit SetInitialValue angegeben wurde.  
  
```  
BOOL m_bInitialValueSpecified;  
```  
  
##  <a name="a-namembinitialvelocityspecifieda--ccustomtransitionmbinitialvelocityspecified"></a><a name="m_binitialvelocityspecified"></a>CCustomTransition::m_bInitialVelocitySpecified  
 Gibt an, ob die ursprüngliche Geschwindigkeit mit SetInitialVelocity angegeben wurde.  
  
```  
BOOL m_bInitialVelocitySpecified;  
```  
  
##  <a name="a-nameminitialvaluea--ccustomtransitionminitialvalue"></a><a name="m_initialvalue"></a>CCustomTransition::m_initialValue  
 Speichert den ursprünglichen Wert.  
  
```  
DOUBLE m_initialValue;  
```  
  
##  <a name="a-nameminitialvelocitya--ccustomtransitionminitialvelocity"></a><a name="m_initialvelocity"></a>CCustomTransition::m_initialVelocity  
 Speichert die ursprüngliche Geschwindigkeit.  
  
```  
DOUBLE m_initialVelocity;  
```  
  
##  <a name="a-namempinterpolatora--ccustomtransitionmpinterpolator"></a><a name="m_pinterpolator"></a>CCustomTransition::m_pInterpolator  
 Speichert einen Zeiger auf einen benutzerdefinierten Interpolator.  
  
```  
CCustomInterpolator* m_pInterpolator;  
```  
  
##  <a name="a-namesetinitialvaluea--ccustomtransitionsetinitialvalue"></a><a name="setinitialvalue"></a>CCustomTransition::SetInitialValue  
 Legt einen anfänglichen Wert, die auf eine diesem Übergang zugeordnete Animationsvariable angewendet werden.  
  
```  
void SetInitialValue(DOUBLE initialValue);
```  
  
### <a name="parameters"></a>Parameter  
 `initialValue`  
  
##  <a name="a-namesetinitialvelocitya--ccustomtransitionsetinitialvelocity"></a><a name="setinitialvelocity"></a>CCustomTransition::SetInitialVelocity  
 Legt eine ursprüngliche Geschwindigkeit, die auf eine diesem Übergang zugeordnete Animationsvariable angewendet werden.  
  
```  
void SetInitialVelocity(DOUBLE initialVelocity);
```  
  
### <a name="parameters"></a>Parameter  
 `initialVelocity`  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

