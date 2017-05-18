---
title: CAutoVectorPtr Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAutoVectorPtr
- ATLBASE/ATL::CAutoVectorPtr
- ATLBASE/ATL::CAutoVectorPtr::CAutoVectorPtr
- ATLBASE/ATL::CAutoVectorPtr::Allocate
- ATLBASE/ATL::CAutoVectorPtr::Attach
- ATLBASE/ATL::CAutoVectorPtr::Detach
- ATLBASE/ATL::CAutoVectorPtr::Free
- ATLBASE/ATL::CAutoVectorPtr::m_p
dev_langs:
- C++
helpviewer_keywords:
- CAutoVectorPtr class
ms.assetid: 0030362b-6bc4-4a47-9b5b-3c3899dceab4
caps.latest.revision: 20
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 8234018b2f6faf8585186491413ecbd688a3b32f
ms.contentlocale: de-de
ms.lasthandoff: 04/29/2017

---
# <a name="cautovectorptr-class"></a>CAutoVectorPtr-Klasse
Diese Klasse stellt von einem intelligenten Zeigerobjekt mit neuen und Operatoren löschen.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template<typename T>  
class CAutoVectorPtr
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Zeigertyp.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAutoVectorPtr::CAutoVectorPtr](#cautovectorptr)|Der Konstruktor.|  
|[CAutoVectorPtr:: ~ CAutoVectorPtr](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAutoVectorPtr::Allocate](#allocate)|Rufen Sie diese Methode zum Belegen des Speichers erforderlich, die für das Array von Objekten, die durch `CAutoVectorPtr`.|  
|[CAutoVectorPtr::Attach](#attach)|Rufen Sie diese Methode, um einem vorhandenen Zeiger Besitz zu nehmen.|  
|[CAutoVectorPtr::Detach](#detach)|Rufen Sie diese Methode, um den Besitz eines Zeigers freigibt.|  
|[CAutoVectorPtr::Free](#free)|Rufen Sie diese Methode zum Löschen eines Objekts verweist, zu einem `CAutoVectorPtr`.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAutoVectorPtr::operator T *](#operator_t__star)|Der Cast-Operator.|  
|[CAutoVectorPtr::operator =](#operator_eq)|Der Zuweisungsoperator.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAutoVectorPtr::m_p](#m_p)|Die Zeiger-Membervariable.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse stellt Methoden zum Erstellen und verwalten einen intelligenten Zeiger, die geschützt werden anhand von Arbeitsspeicherverlusten Ressourcen automatisch freigegeben werden, wenn sie außerhalb des gültigen Bereichs liegt. `CAutoVectorPtr`ähnelt dem `CAutoPtr`, der einzige Unterschied ist, dass `CAutoVectorPtr` verwendet [Vektor neue &#91; &#93;](../../standard-library/new-operators.md#op_new_arr) und [Vektor Delete &#91; &#93;](../../standard-library/new-operators.md#op_delete_arr) zu reservieren und Freigeben von Arbeitsspeicher, anstatt die C++ **neue** und **löschen** Operatoren. Finden Sie unter [CAutoVectorPtrElementTraits](../../atl/reference/cautovectorptrelementtraits-class.md) Wenn Auflistungsklassen von `CAutoVectorPtr` erforderlich sind.  

  
 Finden Sie unter [CAutoPtr](../../atl/reference/cautoptr-class.md) für gezeigt, wie eine intelligenter Zeiger-Klasse.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
##  <a name="allocate"></a>CAutoVectorPtr::Allocate  
 Rufen Sie diese Methode zum Belegen des Speichers erforderlich, die für das Array von Objekten, die durch `CAutoVectorPtr`.  
  
```
bool Allocate(size_t nElements) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nElements`  
 Die Anzahl der Elemente im Array.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt true zurück, wenn der Speicher erfolgreich zugeordnet, "false" bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Debug-Builds wird ein Assertionsfehler auftreten, wenn die [CAutoVectorPtr::m_p](#m_p) Membervariable wird derzeit auf einen vorhandenen Wert zeigt; es ist also nicht gleich NULL.  
  
##  <a name="attach"></a>CAutoVectorPtr::Attach  
 Rufen Sie diese Methode, um einem vorhandenen Zeiger Besitz zu nehmen.  
  
```
void Attach(T* p) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 Die `CAutoVectorPtr` Objekt wird die Besitzrechte des this-Zeigers.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein `CAutoVectorPtr` Objekt übernimmt den Besitz eines Zeigers, wird es automatisch löschen den Zeiger und alle zugeordneten Daten, wenn sie den Gültigkeitsbereich verlässt. Wenn [CAutoVectorPtr::Detach](#detach) wird aufgerufen, der Programmierer ist erneut angegebene Verantwortung für die Freigabe einer zugeordneten Ressourcen.  
  
 Debug-Builds wird ein Assertionsfehler auftreten, wenn die [CAutoVectorPtr::m_p](#m_p) Membervariable wird derzeit auf einen vorhandenen Wert zeigt; es ist also nicht gleich NULL.  
  
##  <a name="cautovectorptr"></a>CAutoVectorPtr::CAutoVectorPtr  
 Der Konstruktor.  
  
```
CAutoVectorPtr() throw();
explicit CAutoVectorPtr(T* p) throw();
CAutoVectorPtr(CAutoVectorPtr<T>& p) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 Einem vorhandenen Zeiger.  
  
### <a name="remarks"></a>Hinweise  
 Die `CAutoVectorPtr` Objekt kann mit einem vorhandenen Zeiger erstellt werden, in diesem Fall, die es überträgt den Besitz des Zeigers.  
  
##  <a name="dtor"></a>CAutoVectorPtr:: ~ CAutoVectorPtr  
 Der Destruktor.  
  
```
~CAutoVectorPtr() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt alle zugeordneten Ressourcen frei. Aufrufe [CAutoVectorPtr::Free](#free).  
  
##  <a name="detach"></a>CAutoVectorPtr::Detach  
 Rufen Sie diese Methode, um den Besitz eines Zeigers freigibt.  
  
```
T* Detach() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt eine Kopie des Zeigers zurück.  
  
### <a name="remarks"></a>Hinweise  
 Gibt den Besitz eines Zeigers frei wird, wird dadurch die [CAutoVectorPtr::m_p](#m_p) Membervariable auf NULL, und gibt eine Kopie des Zeigers zurück. Nach dem Aufruf **trennen**, es wird bis zu dem Programmierer, die freizugeben zugeordneten Ressourcen über den die `CAutoVectorPtr` Objekt möglicherweise zuvor Verantwortung angenommen haben.  
  
##  <a name="free"></a>CAutoVectorPtr::Free  
 Rufen Sie diese Methode zum Löschen eines Objekts verweist, zu einem `CAutoVectorPtr`.  
  
```
void Free() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Objekt verweist die `CAutoVectorPtr` wird freigegeben, und die [CAutoVectorPtr::m_p](#m_p) Membervariable wird auf NULL festgelegt.  
  
##  <a name="m_p"></a>CAutoVectorPtr::m_p  
 Die Zeiger-Membervariable.  
  
```
T* m_p;
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Membervariable enthält die Zeigerinformationen zur.  
  
##  <a name="operator_eq"></a>CAutoVectorPtr::operator =  
 Der Zuweisungsoperator.  
  
```
CAutoVectorPtr<T>& operator= (CAutoVectorPtr<T>& p) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 Ein Zeiger.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Verweis auf eine **CAutoVectorPtr\< T >**.  
  
### <a name="remarks"></a>Hinweise  
 Der Zuweisungsoperator trennt die `CAutoVectorPtr` Objekt aus einem aktuellen Zeiger und fügt Sie den neuen Zeiger `p`, an deren Stelle.  
  
##  <a name="operator_t__star"></a>CAutoVectorPtr::operator T *  
 Der Cast-Operator.  
  
```  
operator T*() const throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt einen Zeiger auf den Object-Datentyp in der Klassenvorlage definiert.  
  
## <a name="see-also"></a>Siehe auch  
 [CAutoPtr-Klasse](../../atl/reference/cautoptr-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)

