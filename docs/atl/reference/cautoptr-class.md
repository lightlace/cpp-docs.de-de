---
title: CAutoPtr Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAutoPtr
- ATLBASE/ATL::CAutoPtr
- ATLBASE/ATL::CAutoPtr::CAutoPtr
- ATLBASE/ATL::CAutoPtr::Attach
- ATLBASE/ATL::CAutoPtr::Detach
- ATLBASE/ATL::CAutoPtr::Free
- ATLBASE/ATL::CAutoPtr::m_p
dev_langs:
- C++
helpviewer_keywords:
- CAutoPtr class
ms.assetid: 08988d53-4fb0-4711-bdfc-8ac29c63f410
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: edf1baff50541dd5f16c27205f300558558d6f92
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="cautoptr-class"></a>CAutoPtr-Klasse
Diese Klasse stellt einen intelligenten Zeiger-Objekt.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <typename T>  
class CAutoPtr
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Zeigertyp.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAutoPtr::CAutoPtr](#cautoptr)|Der Konstruktor.|  
|[CAutoPtr:: ~ CAutoPtr](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAutoPtr::Attach](#attach)|Rufen Sie diese Methode, um einem vorhandenen Zeiger Besitz zu nehmen.|  
|[CAutoPtr::Detach](#detach)|Rufen Sie diese Methode, um den Besitz eines Zeigers freigibt.|  
|[CAutoPtr::Free](#free)|Rufen Sie diese Methode zum Löschen eines Objekts verweist, zu einem `CAutoPtr`.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAutoPtr::operator T *](#operator_t_star)|Der Cast-Operator.|  
|[CAutoPtr::operator =](#operator_eq)|Der Zuweisungsoperator.|  
|[CAutoPtr::operator ->](#operator_ptr)|Der Pointer-to-Member-Operator.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAutoPtr::m_p](#m_p)|Die Zeiger-Membervariable.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse stellt Methoden zum Erstellen und verwalten einen intelligenten Zeiger, die geschützt werden anhand von Arbeitsspeicherverlusten Ressourcen automatisch freigegeben werden, wenn sie außerhalb des gültigen Bereichs liegt.  
  
 Zudem `CAutoPtr`Kopierkonstruktor und der Zuweisung Operator übertragen den Besitz des Zeigers, kopieren Sie den Zeiger Quelle zum Ziel Zeiger und den Quelle Zeiger auf NULL festlegen. Daher ist es unmöglich, zwei `CAutoPtr` -Objekte jeweils die gleichen Zeiger speichern, und dies reduziert die Möglichkeit, dass derselben Zeiger zweimal zu löschen.  
  
 `CAutoPtr` Außerdem vereinfacht die Erstellung von Auflistungen von Zeigern. Statt eine Auflistungsklasse ableiten und überschreiben den Destruktor, ist es einfacher, die eine Auflistung von `CAutoPtr` Objekte. Wenn die Sammlung gelöscht wird, die `CAutoPtr` Objekte verlassen den Gültigkeitsbereich und selbst automatisch gelöscht werden.  
  
 [CHeapPtr](../../atl/reference/cheapptr-class.md) und Varianten arbeiten, auf die gleiche Weise wie `CAutoPtr`, außer dass sie reservieren und Freigeben von Arbeitsspeicher, die mit verschiedenen Heapfunktionen anstelle der C++ **neue** und **löschen** Operatoren. [CAutoVectorPtr](../../atl/reference/cautovectorptr-class.md) ähnelt `CAutoPtr`, der einzige Unterschied wird, verwendet jedoch **new []-Vektor** und **Vektor delete []** zu reservieren und Freigeben von Arbeitsspeicher.  
  
 Siehe auch [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) und [CAutoPtrList](../../atl/reference/cautoptrlist-class.md) Wenn Arrays oder Listen von intelligenten Zeigern erforderlich sind.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
## <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#74](../../atl/codesnippet/cpp/cautoptr-class_1.cpp)]  
  
##  <a name="attach"></a>  CAutoPtr::Attach  
 Rufen Sie diese Methode, um einem vorhandenen Zeiger Besitz zu nehmen.  
  
```
void Attach(T* p) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 Die `CAutoPtr` Objekt wird die Besitzrechte des this-Zeigers.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein `CAutoPtr` Objekt übernimmt den Besitz eines Zeigers, wird es automatisch löschen den Zeiger und alle zugeordneten Daten, wenn sie den Gültigkeitsbereich verlässt. Wenn [CAutoPtr::Detach](#detach) wird aufgerufen, der Programmierer ist erneut angegebene Verantwortung für die Freigabe einer zugeordneten Ressourcen.  
  
 Debug-Builds wird ein Assertionsfehler auftreten, wenn die [CAutoPtr::m_p](#m_p) -Datenmember ist derzeit auf einen vorhandenen Wert zeigt; es ist also nicht gleich NULL.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel in der [CAutoPtr Übersicht](../../atl/reference/cautoptr-class.md).  
  
##  <a name="cautoptr"></a>  CAutoPtr::CAutoPtr  
 Der Konstruktor.  
  
```
CAutoPtr() throw();
explicit CAutoPtr(T* p) throw();

template<typename TSrc>
CAutoPtr(CAutoPtr<TSrc>& p) throw();

template<> 
CAutoPtr(CAutoPtr<T>& p) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 Einem vorhandenen Zeiger.  
  
 `TSrc`  
 Der Typ von einem anderen verwalteten `CAutoPtr`, die zum Initialisieren des aktuellen Objekts verwendet.  
  
### <a name="remarks"></a>Hinweise  
 Die `CAutoPtr` Objekt kann mit einem vorhandenen Zeiger erstellt werden, in diesem Fall, die es überträgt den Besitz des Zeigers.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel in der [CAutoPtr Übersicht](../../atl/reference/cautoptr-class.md).  
  
##  <a name="dtor"></a>  CAutoPtr:: ~ CAutoPtr  
 Der Destruktor.  
  
```
~CAutoPtr() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt alle zugeordneten Ressourcen frei. Aufrufe [CAutoPtr::Free](#free).  
  
##  <a name="detach"></a>  CAutoPtr::Detach  
 Rufen Sie diese Methode, um den Besitz eines Zeigers freigibt.  
  
```
T* Detach() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt eine Kopie des Zeigers zurück.  
  
### <a name="remarks"></a>Hinweise  
 Gibt den Besitz eines Zeigers frei wird, wird dadurch die [CAutoPtr::m_p](#m_p) Data-Member-Variable auf NULL, und gibt eine Kopie des Zeigers zurück. Nach dem Aufruf **trennen**, es wird bis zu dem Programmierer, die freizugeben zugeordneten Ressourcen über den die `CAutoPtr` Objekt möglicherweise zuvor Reponsibility angenommen haben.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel in der [CAutoPtr Übersicht](../../atl/reference/cautoptr-class.md).  
  
##  <a name="free"></a>  CAutoPtr::Free  
 Rufen Sie diese Methode zum Löschen eines Objekts verweist, zu einem `CAutoPtr`.  
  
```
void Free() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Objekt verweist die `CAutoPtr` wird freigegeben, und die [CAutoPtr::m_p](#m_p) Data-Member-Variable auf NULL gesetzt wird.  
  
##  <a name="m_p"></a>  CAutoPtr::m_p  
 Die Zeiger-Membervariable.  
  
```
T* m_p;
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Membervariable enthält die Zeigerinformationen zur.  
  
##  <a name="operator_eq"></a>  CAutoPtr::operator =  
 Der Zuweisungsoperator.  
  
```
template<>
CAutoPtr<T>& operator= (CAutoPtr<T>& p);

template<typename TSrc>
CAutoPtr<T>& operator= (CAutoPtr<TSrc>& p);
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 Ein Zeiger.  
  
 `TSrc`  
 Einen Klassentyp.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Verweis auf eine **CAutoPtr\< T >**.  
  
### <a name="remarks"></a>Hinweise  
 Der Zuweisungsoperator trennt die `CAutoPtr` Objekt aus einem aktuellen Zeiger und fügt Sie den neuen Zeiger `p`, an deren Stelle.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel in der [CAutoPtr Übersicht](../../atl/reference/cautoptr-class.md).  
  
##  <a name="operator_ptr"></a>  CAutoPtr::operator-&gt;  
 Der Pointer-to-Member-Operator.  
  
```
T* operator->() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Wert der [CAutoPtr::m_p](#m_p) Daten Membervariablen gespeichert.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diesen Operator zum Aufrufen einer Methode in einer Klasse, die durch die `CAutoPtr` Objekt. Debug-Builds wird ein Assertionsfehler auftreten, wenn die `CAutoPtr` verweist auf NULL.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel in der [CAutoPtr Übersicht](../../atl/reference/cautoptr-class.md).  
  
##  <a name="operator_t_star"></a>  CAutoPtr::operator T *  
 Der Cast-Operator.  
  
```  
operator T* () const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf den Object-Datentyp in der Klassenvorlage definiert.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel in der [CAutoPtr Übersicht](../../atl/reference/cautoptr-class.md).  
  
## <a name="see-also"></a>Siehe auch  
 [CHeapPtr-Klasse](../../atl/reference/cheapptr-class.md)   
 [CAutoVectorPtr-Klasse](../../atl/reference/cautovectorptr-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
