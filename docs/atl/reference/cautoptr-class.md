---
title: Klasse CAutoPtr | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
caps.latest.revision: 23
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
ms.openlocfilehash: 309a3d0ddceab2995c85e156c7db09ddd7edfa86
ms.lasthandoff: 02/24/2017

---
# <a name="cautoptr-class"></a>CAutoPtr-Klasse
Diese Klasse stellt ein intelligenter Zeiger-Objekt.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <typename T>  
class CAutoPtr
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Zeigertyp.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAutoPtr::CAutoPtr](#cautoptr)|Der Konstruktor.|  
|[CAutoPtr:: ~ CAutoPtr](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAutoPtr::Attach](#attach)|Rufen Sie diese Methode, um einem vorhandenen Zeiger Besitz.|  
|[CAutoPtr::Detach](#detach)|Rufen Sie diese Methode, um den Besitz eines Zeigers freigibt.|  
|[CAutoPtr::Free](#free)|Rufen Sie diese Methode zum Löschen eines Objekts, auf das ein `CAutoPtr`.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAutoPtr::operator T *](#operator_t_star)|Der Cast-Operator.|  
|[CAutoPtr::operator =](#operator_eq)|Der Zuweisungsoperator.|  
|[CAutoPtr::operator->](#operator_ptr)|Der Zeiger-auf-Member-Operator.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAutoPtr::m_p](#m_p)|Die Zeiger-Membervariable.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse stellt Methoden zum Erstellen und Verwalten von einem intelligenten Zeiger helfen, Schutz vor Speicherverluste von Ressourcen automatisch freigegeben, wenn sie außerhalb des gültigen Bereichs liegt.  
  
 Zudem `CAutoPtr`Kopierkonstruktor und der Zuweisung Operator übertragen des Besitzes des Zeigers, kopieren Sie den Quell-Zeiger auf den Ziel-Zeiger und den Quelle Zeiger auf NULL festlegen. Daher ist es unmöglich, zwei `CAutoPtr` Objekten jeweils den gleichen Zeiger speichern und dadurch den gleichen Zeiger zweimal zu löschen.  
  
 `CAutoPtr`Außerdem vereinfacht die Erstellung von Auflistungen von Zeigern. Statt eine Auflistungsklasse ableiten und den Destruktor überschreiben, ist es einfacher, eine Auflistung von stellen `CAutoPtr` Objekte. Wenn die Auflistung gelöscht wird, die `CAutoPtr` Objekte verlassen den Gültigkeitsbereich und selbst automatisch gelöscht.  
  
 [CHeapPtr](../../atl/reference/cheapptr-class.md) und Varianten funktionieren auf die gleiche Weise wie `CAutoPtr`, außer dass sie reservieren und Freigeben von Arbeitsspeicher, die mit verschiedenen Heapfunktionen anstelle der C++ **neue** und **löschen** Operatoren. [CAutoVectorPtr](../../atl/reference/cautovectorptr-class.md) ähnelt dem `CAutoPtr`, der einzige Unterschied ist, verwendet **new []-Vektor** und **Vektor delete []** zum Zuordnen und Freigeben von Arbeitsspeicher.  
  
 Siehe auch [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) und [CAutoPtrList](../../atl/reference/cautoptrlist-class.md) Wenn Matrizen oder Listen von intelligenten Zeigern erforderlich sind.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
## <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#74;](../../atl/codesnippet/cpp/cautoptr-class_1.cpp)]  
  
##  <a name="attach"></a>CAutoPtr::Attach  
 Rufen Sie diese Methode, um einem vorhandenen Zeiger Besitz.  
  
```
void Attach(T* p) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 Das `CAutoPtr` Objekt wird die Besitzrechte des this-Zeiger.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein `CAutoPtr` Objekt übernimmt den Besitz eines Zeigers, wird es automatisch löschen den Zeiger und alle zugeordneten Daten, wenn sie den Gültigkeitsbereich verlässt. Wenn [CAutoPtr::Detach](#detach) wird aufgerufen, der Programmierer ist erneut angegebenen Verantwortung für die Freigabe alle zugeordneten Ressourcen.  
  
 Debug-Builds wird ein Assertionsfehler auftreten, wenn die [CAutoPtr::m_p](#m_p) Datenmember derzeit verweist, zu einem vorhandenen Wert; es ist also nicht gleich NULL.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel in der [CAutoPtr Übersicht über](../../atl/reference/cautoptr-class.md).  
  
##  <a name="cautoptr"></a>CAutoPtr::CAutoPtr  
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
 Der Typ von einem anderen verwalteten `CAutoPtr`verwendet, um das aktuelle Objekt zu initialisieren.  
  
### <a name="remarks"></a>Hinweise  
 Das `CAutoPtr` -Objekt kann mit einem vorhandenen Zeiger erstellt werden, in diesem Fall, die es überträgt den Besitz des Zeigers.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel in der [CAutoPtr Übersicht über](../../atl/reference/cautoptr-class.md).  
  
##  <a name="dtor"></a>CAutoPtr:: ~ CAutoPtr  
 Der Destruktor.  
  
```
~CAutoPtr() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt alle zugeordneten Ressourcen frei. Aufrufe [CAutoPtr::Free](#free).  
  
##  <a name="detach"></a>CAutoPtr::Detach  
 Rufen Sie diese Methode, um den Besitz eines Zeigers freigibt.  
  
```
T* Detach() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt eine Kopie des Zeigers.  
  
### <a name="remarks"></a>Hinweise  
 Gibt den Besitz eines Zeigers frei wird, wird die [CAutoPtr::m_p](#m_p) Daten-Member-Variable auf NULL, und gibt eine Kopie des Zeigers zurück. Nach dem Aufruf von **trennen**, es wird bis zu der Programmierer freizugeben zugeordneten Ressourcen über die die `CAutoPtr` Objekt möglicherweise zuvor Reponsibility angenommen haben.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel in der [CAutoPtr Übersicht über](../../atl/reference/cautoptr-class.md).  
  
##  <a name="free"></a>CAutoPtr::Free  
 Rufen Sie diese Methode zum Löschen eines Objekts, auf das ein `CAutoPtr`.  
  
```
void Free() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Objekt verweist die `CAutoPtr` wird freigegeben, und die [CAutoPtr::m_p](#m_p) Daten-Member-Variable auf NULL festgelegt ist.  
  
##  <a name="m_p"></a>CAutoPtr::m_p  
 Die Zeiger-Membervariable.  
  
```
T* m_p;
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Membervariable enthält Zeigerinformationen.  
  
##  <a name="operator_eq"></a>CAutoPtr::operator =  
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
 Ein Klassentyp.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Verweis auf eine **CAutoPtr\< T >**.  
  
### <a name="remarks"></a>Hinweise  
 Der Zuweisungsoperator trennt die `CAutoPtr` Objekt aus einem aktuellen Zeiger und fügt den neuen Zeiger `p`, an dessen Stelle.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel in der [CAutoPtr Übersicht über](../../atl/reference/cautoptr-class.md).  
  
##  <a name="operator_ptr"></a>CAutoPtr::operator-&gt;  
 Der Zeiger-auf-Member-Operator.  
  
```
T* operator->() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Wert der [CAutoPtr::m_p](#m_p) Daten Membervariablen gespeichert.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diesen Operator zum Aufrufen einer Methode in einer Klasse verweist, auf die `CAutoPtr` Objekt. Debug-Builds wird ein Assertionsfehler auftreten, wenn die `CAutoPtr` verweist auf NULL.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel in der [CAutoPtr Übersicht über](../../atl/reference/cautoptr-class.md).  
  
##  <a name="operator_t_star"></a>CAutoPtr::operator T *  
 Der Cast-Operator.  
  
```  
operator T* () const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf den Object-Datentyp in der Klassenvorlage definiert.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel in der [CAutoPtr Übersicht über](../../atl/reference/cautoptr-class.md).  
  
## <a name="see-also"></a>Siehe auch  
 [CHeapPtr-Klasse](../../atl/reference/cheapptr-class.md)   
 [CAutoVectorPtr-Klasse](../../atl/reference/cautovectorptr-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

