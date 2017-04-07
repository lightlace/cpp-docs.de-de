---
title: Klasse CAutoVectorPtr | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: bb4bbd110552d1e3cf604add44de7e428d2703ee
ms.lasthandoff: 02/24/2017

---
# <a name="cautovectorptr-class"></a>CAutoVectorPtr-Klasse
Diese Klasse stellt ein intelligenter Zeiger-Objekt, das mit der neuen Vektor dar und delete-Operator.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
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
|[CAutoVectorPtr::Allocate](#allocate)|Rufen Sie diese Methode, um das Array von Objekten, die auf den erforderlichen Speicher `CAutoVectorPtr`.|  
|[CAutoVectorPtr::Attach](#attach)|Rufen Sie diese Methode, um einem vorhandenen Zeiger Besitz.|  
|[CAutoVectorPtr::Detach](#detach)|Rufen Sie diese Methode, um den Besitz eines Zeigers freigibt.|  
|[CAutoVectorPtr::Free](#free)|Rufen Sie diese Methode zum Löschen eines Objekts, auf das ein `CAutoVectorPtr`.|  
  
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
 Diese Klasse stellt Methoden zum Erstellen und Verwalten von einem intelligenten Zeiger helfen, Schutz vor Speicherverluste von Ressourcen automatisch freigegeben, wenn sie außerhalb des gültigen Bereichs liegt. `CAutoVectorPtr`ähnelt dem `CAutoPtr`, der einzige Unterschied ist, dass `CAutoVectorPtr` verwendet [new []-Vektor](../../standard-library/new-operators.md#operator_new_arr) und [Vektor delete []](../../standard-library/new-operators.md#operator_delete_arr) zum Zuordnen und Freigeben von Arbeitsspeicher, anstatt die C++ **neue** und **löschen** Operatoren. Finden Sie unter [CAutoVectorPtrElementTraits](../../atl/reference/cautovectorptrelementtraits-class.md) Wenn Auflistungsklassen von `CAutoVectorPtr` erforderlich sind.  

  
 Finden Sie unter [CAutoPtr](../../atl/reference/cautoptr-class.md) ein Beispiel für die Verwendung einer intelligenten Zeiger-Klasse.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
##  <a name="allocate"></a>CAutoVectorPtr::Allocate  
 Rufen Sie diese Methode, um das Array von Objekten, die auf den erforderlichen Speicher `CAutoVectorPtr`.  
  
```
bool Allocate(size_t nElements) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nElements`  
 Die Anzahl der Elemente im Array.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt true zurück, wenn der Speicher erfolgreich belegt, bei einem Fehler False.  
  
### <a name="remarks"></a>Hinweise  
 Debug-Builds wird ein Assertionsfehler auftreten, wenn die [CAutoVectorPtr::m_p](#m_p) Membervariable zeigt derzeit zu einem vorhandenen Wert; es ist also nicht gleich NULL.  
  
##  <a name="attach"></a>CAutoVectorPtr::Attach  
 Rufen Sie diese Methode, um einem vorhandenen Zeiger Besitz.  
  
```
void Attach(T* p) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 Das `CAutoVectorPtr` Objekt wird die Besitzrechte des this-Zeiger.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein `CAutoVectorPtr` Objekt übernimmt den Besitz eines Zeigers, wird es automatisch löschen den Zeiger und alle zugeordneten Daten, wenn sie den Gültigkeitsbereich verlässt. Wenn [CAutoVectorPtr::Detach](#detach) wird aufgerufen, der Programmierer ist erneut angegebenen Verantwortung für die Freigabe alle zugeordneten Ressourcen.  
  
 Debug-Builds wird ein Assertionsfehler auftreten, wenn die [CAutoVectorPtr::m_p](#m_p) Membervariable zeigt derzeit zu einem vorhandenen Wert; es ist also nicht gleich NULL.  
  
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
 Das `CAutoVectorPtr` -Objekt kann mit einem vorhandenen Zeiger erstellt werden, in diesem Fall, die es überträgt den Besitz des Zeigers.  
  
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
 Gibt eine Kopie des Zeigers.  
  
### <a name="remarks"></a>Hinweise  
 Gibt den Besitz eines Zeigers frei wird, wird die [CAutoVectorPtr::m_p](#m_p) Membervariable den Wert NULL hat, und gibt eine Kopie des Zeigers zurück. Nach dem Aufruf von **trennen**, wird bis zu der Programmierer freizugeben belegten Ressourcen über die die `CAutoVectorPtr` Objekt möglicherweise zuvor Verantwortung angenommen haben.  
  
##  <a name="free"></a>CAutoVectorPtr::Free  
 Rufen Sie diese Methode zum Löschen eines Objekts, auf das ein `CAutoVectorPtr`.  
  
```
void Free() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Objekt verweist die `CAutoVectorPtr` wird freigegeben, und die [CAutoVectorPtr::m_p](#m_p) Member-Variable auf NULL festgelegt ist.  
  
##  <a name="m_p"></a>CAutoVectorPtr::m_p  
 Die Zeiger-Membervariable.  
  
```
T* m_p;
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Membervariable enthält Zeigerinformationen.  
  
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
 Der Zuweisungsoperator trennt die `CAutoVectorPtr` Objekt aus einem aktuellen Zeiger und fügt den neuen Zeiger `p`, an dessen Stelle.  
  
##  <a name="operator_t__star"></a>CAutoVectorPtr::operator T *  
 Der Cast-Operator.  
  
```  
operator T*() const throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt einen Zeiger auf den Object-Datentyp in der Klassenvorlage definiert.  
  
## <a name="see-also"></a>Siehe auch  
 [CAutoPtr-Klasse](../../atl/reference/cautoptr-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

