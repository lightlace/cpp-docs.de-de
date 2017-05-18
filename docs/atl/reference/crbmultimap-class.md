---
title: CRBMultiMap Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRBMultiMap
- ATLCOLL/ATL::CRBMultiMap
- ATLCOLL/ATL::CRBMultiMap::CRBMultiMap
- ATLCOLL/ATL::CRBMultiMap::FindFirstWithKey
- ATLCOLL/ATL::CRBMultiMap::GetNextValueWithKey
- ATLCOLL/ATL::CRBMultiMap::GetNextWithKey
- ATLCOLL/ATL::CRBMultiMap::Insert
- ATLCOLL/ATL::CRBMultiMap::RemoveKey
dev_langs:
- C++
helpviewer_keywords:
- CRBMultiMap class
ms.assetid: 94d3ec0c-3e30-4ab7-a101-d8da4fb8add3
caps.latest.revision: 19
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: a72ddfbf4944f0de5e979f7046872d594017b9cf
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="crbmultimap-class"></a>CRBMultiMap-Klasse
Diese Klasse stellt eine Zuordnungsstruktur, die ermöglicht, dass jeder Schlüssel mit mehr als ein Wert mit einer binären Rot-Schwarz-Struktur verknüpft werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```
template<typename K,
         typename V, 
         class KTraits = CElementTraits<K>, 
         class VTraits = CElementTraits<V>>  
class CRBMultiMap : public CRBTree<K, V, KTraits, VTraits>
```    
  
#### <a name="parameters"></a>Parameter  
 `K`  
 Der Typ des Key-Element.  
  
 *V*  
 Der Wert-Elementtyp.  
  
 `KTraits`  
 Der Code verwendet, um wichtige Elemente kopiert oder verschoben. Finden Sie unter [CElementTraits Klasse](../../atl/reference/celementtraits-class.md) für weitere Details.  
  
 `VTraits`  
 Der Code kopieren oder verschieben Elemente mit dem Wert.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRBMultiMap::CRBMultiMap](#crbmultimap)|Der Konstruktor.|  
|[CRBMultiMap:: ~ CRBMultiMap](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRBMultiMap::FindFirstWithKey](#findfirstwithkey)|Rufen Sie diese Methode, um die Position des ersten Elements mit einem bestimmten Schlüssel zu suchen.|  
|[CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey)|Rufen Sie diese Methode, um einen bestimmten Schlüssel zugeordnete Wert zu erhalten, und aktualisieren Sie den Positionswert.|  
|[CRBMultiMap::GetNextWithKey](#getnextwithkey)|Rufen Sie diese Methode zum Abrufen des Elements mit einem bestimmten Schlüssel verknüpft ist, und aktualisieren Sie den Positionswert.|  
|[CRBMultiMap::Insert](#insert)|Rufen Sie diese Methode, um ein Element in der Zuordnung einzufügen.|  
|[CRBMultiMap::RemoveKey](#removekey)|Rufen Sie diese Methode, um alle Elemente der Schlüssel-Wert für einen bestimmten Schlüssel zu entfernen.|  
  
## <a name="remarks"></a>Hinweise  
 `CRBMultiMap`bietet Unterstützung für eine Zuordnung Array eines beliebigen angegebenen Typs, der ein geordnetes Array von Schlüssel-Elemente und Werte zu verwalten. Im Gegensatz zu den [CRBMap](../../atl/reference/crbmap-class.md) Klasse jeder Schlüssel kann mehrere Werte zugeordnet werden.  
  
 Elemente (bestehend aus einem Schlüssel und Wert) befinden sich in einer binären Struktur-Struktur unter Verwendung der [CRBMultiMap::Insert](#insert) Methode. Elemente können entfernt werden, mithilfe der [CRBMultiMap::RemoveKey](#removekey) -Methode, die alle Elemente gelöscht, die den angegebenen Schlüssel entsprechen.  
  
 Durchlaufen der Struktur ist, ermöglicht mit Methoden wie z. B. [CRBTree::GetHeadPosition](../../atl/reference/crbtree-class.md#getheadposition), [CRBTree::GetNext](../../atl/reference/crbtree-class.md#getnext), und [CRBTree::GetNextValue](../../atl/reference/crbtree-class.md#getnextvalue). Zugriff auf den möglicherweise mehrere Werte pro Schlüssel möglich ist die Verwendung der [CRBMultiMap::FindFirstWithKey](#findfirstwithkey), [CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey), und [CRBMultiMap::GetNextWithKey](#getnextwithkey) Methoden. Siehe das Beispiel für [CRBMultiMap::CRBMultiMap](#crbmultimap) zur Veranschaulichung dieses in der Praxis.  
  
 Die `KTraits` und `VTraits` Parameter sind Klassen, die alle zusätzlichen Code zum Kopieren oder Verschieben von Elementen enthalten.  
  
 `CRBMultiMap`stammt von [CRBTree](../../atl/reference/crbtree-class.md), der eine binäre Struktur, die mit dem Rot-Schwarz-Algorithmus implementiert. Eine Alternative zum `CRBMultiMap` und `CRBMap` wird die [CAtlMap](../../atl/reference/catlmap-class.md) Klasse. Wenn nur eine kleine Anzahl von Elementen gespeichert werden muss, sollten Sie mithilfe der [CSimpleMap](../../atl/reference/csimplemap-class.md) stattdessen.  
  
 Eine vollständige Erläuterung der verschiedenen Auflistungsklassen und ihre Funktionen und Leistungsmerkmale, finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CRBTree](../../atl/reference/crbtree-class.md)  
  
 `CRBMultiMap`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcoll.h  
  
##  <a name="crbmultimap"></a>CRBMultiMap::CRBMultiMap  
 Der Konstruktor.  
  
```
explicit CRBMultiMap(size_t nBlockSize = 10) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nBlockSize`  
 Die Blockgröße.  
  
### <a name="remarks"></a>Hinweise  
 Der `nBlockSize` -Parameter ist ein Maß für die Menge des Arbeitsspeichers, wenn ein neues Element erforderlich ist. Größere Blöcke reduziert Aufrufe an Arbeitsspeicher, aber mehr Ressourcen verwenden. Standardmäßig wird für 10 Elemente gleichzeitig Speicherplatz.  
  
 Finden Sie in der Dokumentation für die Basisklasse [CRBTree](../../atl/reference/crbtree-class.md) Informationen zu den anderen Methoden zur Verfügung.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#85;](../../atl/codesnippet/cpp/crbmultimap-class_1.cpp)]  
  
##  <a name="dtor"></a>CRBMultiMap:: ~ CRBMultiMap  
 Der Destruktor.  
  
```
~CRBMultiMap() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt alle zugeordneten Ressourcen frei.  
  
 Finden Sie in der Dokumentation für die Basisklasse [CRBTree](../../atl/reference/crbtree-class.md) Informationen zu den anderen Methoden zur Verfügung.  
  
##  <a name="findfirstwithkey"></a>CRBMultiMap::FindFirstWithKey  
 Rufen Sie diese Methode, um die Position des ersten Elements mit einem bestimmten Schlüssel zu suchen.  
  
```
POSITION FindFirstWithKey(KINARGTYPE key) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Gibt den Schlüssel, der das Element gefunden wird, werden identifiziert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die POSITION des ersten Elements der Schlüssel-Wert zurück, wenn der Schlüssel gefunden wird, NULL andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Ein Schlüssel in der `CRBMultiMap` kann eine oder mehrere zugeordnete Werte aufweisen. Diese Methode wird die des ersten Werts (die tatsächlich nur ein Wert sein kann) Schlüssel zugeordneten Positionswert, bestimmte bereit. Der zurückgegebene Positionswert kann dann mit verwendet [CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey) oder [CRBMultiMap::GetNextWithKey](#getnextwithkey) den Wert abzurufen, und aktualisieren die Position.  
  
 Finden Sie in der Dokumentation für die Basisklasse [CRBTree](../../atl/reference/crbtree-class.md) Informationen zu den anderen Methoden zur Verfügung.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CRBMultiMap::CRBMultiMap](#crbmultimap).  
  
##  <a name="getnextvaluewithkey"></a>CRBMultiMap::GetNextValueWithKey  
 Rufen Sie diese Methode, um einen bestimmten Schlüssel zugeordnete Wert abrufen und aktualisieren Sie den Positionswert.  
  
```
const V& GetNextValueWithKey(
    POSITION& pos,
    KINARGTYPE key) const throw();
V& GetNextValueWithKey(
    POSITION& pos,
    KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Der Wert, mit entweder einem Aufruf abgerufen [CRBMultiMap::FindFirstWithKey](#findfirstwithkey) oder [CRBMultiMap::GetNextWithKey](#getnextwithkey), oder in einem vorherigen Aufruf `GetNextValueWithKey`.  
  
 `key`  
 Gibt den Schlüssel, der das Element gefunden wird, werden identifiziert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt zurück, das dem angegebenen Schlüssel zugeordnete Elementpaar.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert wird aktualisiert, und zeigen Sie auf den nächsten Wert, der dem Schlüssel zugeordnet. Wenn keine weitere Werte vorhanden sind, wird der Wert auf NULL festgelegt.  
  
 Finden Sie in der Dokumentation für die Basisklasse [CRBTree](../../atl/reference/crbtree-class.md) Informationen zu den anderen Methoden zur Verfügung.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CRBMultiMap::CRBMultiMap](#crbmultimap).  
  
##  <a name="getnextwithkey"></a>CRBMultiMap::GetNextWithKey  
 Rufen Sie diese Methode zum Abrufen des Elements mit einem bestimmten Schlüssel verknüpft ist, und aktualisieren Sie den Positionswert.  
  
```
const CPair* GetNextWithKey(
    POSITION& pos,
    KINARGTYPE key) const throw();
CPair* GetNextWithKey(
    POSITION& pos,
    KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pos`  
 Der Wert, mit entweder einem Aufruf abgerufen [CRBMultiMap::FindFirstWithKey](#findfirstwithkey) oder [CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey), oder in einem vorherigen Aufruf `GetNextWithKey`.  
  
 `key`  
 Gibt den Schlüssel, der das Element gefunden wird, werden identifiziert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die nächste [CRBTree::CPair Klasse](crbtree-class.md#cpair_class) mit dem angegebenen Schlüssel zugeordnete Element.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert wird aktualisiert, und zeigen Sie auf den nächsten Wert, der dem Schlüssel zugeordnet. Wenn keine weitere Werte vorhanden sind, wird der Wert auf NULL festgelegt.  
  
 Finden Sie in der Dokumentation für die Basisklasse [CRBTree](../../atl/reference/crbtree-class.md) Informationen zu den anderen Methoden zur Verfügung.  
  
##  <a name="insert"></a>CRBMultiMap::Insert  
 Rufen Sie diese Methode, um ein Element in der Zuordnung einzufügen.  
  
```
POSITION Insert(KINARGTYPE key, VINARGTYPE value) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Der Schlüsselwert, der zum Hinzufügen der `CRBMultiMap` Objekt.  
  
 *value*  
 Der hinzuzufügende Wert der `CRBMultiMap` zugeordnete Objekt `key`.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Position des Schlüssel/Wert-Element-Paar in der `CRBMultiMap` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie in der Dokumentation für die Basisklasse [CRBTree](../../atl/reference/crbtree-class.md) Informationen zu den anderen Methoden zur Verfügung.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CRBMultiMap::CRBMultiMap](#crbmultimap).  
  
##  <a name="removekey"></a>CRBMultiMap::RemoveKey  
 Rufen Sie diese Methode, um alle Elemente der Schlüssel-Wert für einen bestimmten Schlüssel zu entfernen.  
  
```
size_t RemoveKey(KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Gibt den Schlüssel, der zu löschenden Elemente identifiziert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Werte, die dem angegebenen Schlüssel zugeordnet.  
  
### <a name="remarks"></a>Hinweise  
 `RemoveKey`Löscht alle Elemente der Schlüssel-Wert, der einen Schlüssel verfügen, der entspricht `key`.  
  
 Finden Sie in der Dokumentation für die Basisklasse [CRBTree](../../atl/reference/crbtree-class.md) Informationen zu den anderen Methoden zur Verfügung.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CRBMultiMap::CRBMultiMap](#crbmultimap).  
  
## <a name="see-also"></a>Siehe auch  
 [CRBTree-Klasse](../../atl/reference/crbtree-class.md)   
 [CAtlMap-Klasse](../../atl/reference/catlmap-class.md)   
 [CRBMultiMap-Klasse](../../atl/reference/crbmap-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

