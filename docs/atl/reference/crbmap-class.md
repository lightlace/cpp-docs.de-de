---
title: CRBMultiMap-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CRBMap
- CRBMap
- ATL::CRBMap
dev_langs:
- C++
helpviewer_keywords:
- CRBMap class
ms.assetid: 658e94dc-e835-4356-aed1-1513e1f66969
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 7b1cd9e54a18746e26929e9768a990bbe0ba6553
ms.lasthandoff: 02/24/2017

---
# <a name="crbmap-class"></a>CRBMultiMap-Klasse
Diese Klasse stellt eine Zuordnungsstruktur einer binären Rot-Schwarz-Struktur.  
  
## <a name="syntax"></a>Syntax  
  
```
template <typename K,
          typename V, 
          class KTraits = CElementTraits<K>, 
          class VTraits = CElementTraits<V>> 
class CRBMap : public CRBTree<K, V, KTraits, VTraits>
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
|[CRBMap::CRBMap](#crbmap)|Der Konstruktor.|  
|[CRBMap:: ~ CRBMap](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRBMap::Lookup](#lookup)|Rufen Sie diese Methode zum Nachschlagen der Schlüssel oder Werte in der `CRBMap` Objekt.|  
|[CRBMap::RemoveKey](#removekey)|Rufen Sie diese Methode zum Entfernen eines Elements aus der `CRBMap` -Objekt, den Schlüssel.|  
|[CRBMap::SetAt](#setat)|Rufen Sie diese Methode, um ein Element in der Zuordnung einzufügen.|  
  
## <a name="remarks"></a>Hinweise  
 `CRBMap`bietet Unterstützung für eine Zuordnung Array eines beliebigen angegebenen Typs, der ein geordnetes Array von wichtige Elemente und die zugehörigen Werte verwalten. Jeder Schlüssel kann nur einen zugeordneten Wert aufweisen. Elemente (bestehend aus einem Schlüssel und Wert) befinden sich in einer binären Struktur-Struktur unter Verwendung der [CRBMap::SetAt](#setat) Methode. Elemente können entfernt werden, mithilfe der [CRBMap::RemoveKey](#removekey) -Methode, die das Element mit dem angegebenen Schlüssel-Wert wird gelöscht.  
  
 Durchlaufen der Struktur ist, ermöglicht mit Methoden wie z. B. [CRBTree::GetHeadPosition](../../atl/reference/crbtree-class.md#getheadposition), [CRBTree::GetNext](../../atl/reference/crbtree-class.md#getnext), und [CRBTree::GetNextValue](../../atl/reference/crbtree-class.md#getnextvalue).  
  
 Die `KTraits` und `VTraits` Parameter sind Klassen, die alle zusätzlichen Code zum Kopieren oder Verschieben von Elementen enthalten.  
  
 `CRBMap`stammt von [CRBTree](../../atl/reference/crbtree-class.md), der eine binäre Struktur, die mit dem Rot-Schwarz-Algorithmus implementiert. [CRBMultiMap](../../atl/reference/crbmultimap-class.md) ist eine Variante, die mehrere Werte für jeden Schlüssel zulässt. Sie zu abgeleitet `CRBTree`, und so viele Funktionen mit `CRBMap`.  
  
 Eine Alternative zum beide `CRBMap` und `CRBMultiMap` wird die [CAtlMap](../../atl/reference/catlmap-class.md) Klasse. Wenn nur eine kleine Anzahl von Elementen gespeichert werden muss, sollten Sie mithilfe der [CSimpleMap](../../atl/reference/csimplemap-class.md) stattdessen.  
  
 Eine vollständige Erläuterung der verschiedenen Auflistungsklassen und ihre Funktionen und Leistungsmerkmale, finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CRBTree](../../atl/reference/crbtree-class.md)  
  
 `CRBMap`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcoll.h  
  
##  <a name="a-namecrbmapa--crbmapcrbmap"></a><a name="crbmap"></a>CRBMap::CRBMap  
 Der Konstruktor.  
  
```
explicit CRBMap(size_t nBlockSize = 10) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nBlockSize`  
 Die Blockgröße.  
  
### <a name="remarks"></a>Hinweise  
 Der `nBlockSize` -Parameter ist ein Maß für die Menge des Arbeitsspeichers, wenn ein neues Element erforderlich ist. Größere Blöcke reduziert Aufrufe an Arbeitsspeicher, aber mehr Ressourcen verwenden. Standardmäßig wird für 10 Elemente gleichzeitig Speicherplatz.  
  
 Finden Sie in der Dokumentation für die Basisklasse [CRBTree](../../atl/reference/crbtree-class.md) Informationen zu den anderen Methoden zur Verfügung.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#81;](../../atl/codesnippet/cpp/crbmap-class_1.cpp)]  
  
##  <a name="a-namedtora--crbmapcrbmap"></a><a name="dtor"></a>CRBMap:: ~ CRBMap  
 Der Destruktor.  
  
```
~CRBMap() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt alle zugeordneten Ressourcen frei.  
  
 Finden Sie in der Dokumentation für die Basisklasse [CRBTree](../../atl/reference/crbtree-class.md) Informationen zu den anderen Methoden zur Verfügung.  
  
##  <a name="a-namelookupa--crbmaplookup"></a><a name="lookup"></a>CRBMap::Lookup  
 Rufen Sie diese Methode zum Nachschlagen der Schlüssel oder Werte in der `CRBMap` Objekt.  
  
```
bool Lookup(KINARGTYPE key, VOUTARGTYPE value) const throw(...);
const CPair* Lookup(KINARGTYPE key) const throw();
CPair* Lookup(KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Gibt den Schlüssel, der identifiziert das Element gesucht werden soll.  
  
 *value*  
 Variable, der gebundene Wert erhält.  
  
### <a name="return-value"></a>Rückgabewert  
 Die erste Form der Methode zurückgibt true, wenn der Schlüssel, andernfalls false gefunden wird. Die zweite und dritte Formulare zurückgeben, einen Zeiger auf eine [CPair](crbtree-class.md#cpair_class).  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie in der Dokumentation für die Basisklasse [CRBTree](../../atl/reference/crbtree-class.md) Informationen zu den anderen Methoden zur Verfügung.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#82;](../../atl/codesnippet/cpp/crbmap-class_2.cpp)]  
  
##  <a name="a-nameremovekeya--crbmapremovekey"></a><a name="removekey"></a>CRBMap::RemoveKey  
 Rufen Sie diese Methode zum Entfernen eines Elements aus der `CRBMap` -Objekt, den Schlüssel.  
  
```
bool RemoveKey(KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Die entsprechenden Elementpaar, die Sie entfernen möchten.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt true zurück, wenn der Schlüssel gefunden und entfernt wurde, bei einem Fehler false.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie in der Dokumentation für die Basisklasse [CRBTree](../../atl/reference/crbtree-class.md) Informationen zu den anderen Methoden zur Verfügung.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&83;](../../atl/codesnippet/cpp/crbmap-class_3.cpp)]  
  
##  <a name="a-namesetata--crbmapsetat"></a><a name="setat"></a>CRBMap::SetAt  
 Rufen Sie diese Methode, um ein Element in der Zuordnung einzufügen.  
  
```
POSITION SetAt(
    KINARGTYPE key,
    VINARGTYPE value) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Der Schlüsselwert, der zum Hinzufügen der `CRBMap` Objekt.  
  
 *value*  
 Der hinzuzufügende Wert der `CRBMap` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Position des Schlüssel/Wert-Element-Paar in der `CRBMap` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 `SetAt`ersetzt ein vorhandenes Element, wenn ein übereinstimmender Schlüssel gefunden wird. Wenn der Schlüssel nicht gefunden wird, wird ein neues Schlüssel/Wert-Paar erstellt.  
  
 Finden Sie in der Dokumentation für die Basisklasse [CRBTree](../../atl/reference/crbtree-class.md) Informationen zu den anderen Methoden zur Verfügung.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#84;](../../atl/codesnippet/cpp/crbmap-class_4.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [CRBTree-Klasse](../../atl/reference/crbtree-class.md)   
 [CAtlMap-Klasse](../../atl/reference/catlmap-class.md)   
 [CRBMultiMap-Klasse](../../atl/reference/crbmultimap-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

