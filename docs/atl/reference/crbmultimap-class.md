---
title: CRBMultiMap Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords: CRBMultiMap class
ms.assetid: 94d3ec0c-3e30-4ab7-a101-d8da4fb8add3
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1e359b6bcb7ba201991575ab310e0db9b3b4f06a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="crbmultimap-class"></a>CRBMultiMap-Klasse
Diese Klasse stellt eine Zuordnungsstruktur, die ermöglicht, dass jeder Schlüssel mehr als ein Wert mit einer Binärstruktur Rot Schwarz zugeordnet werden kann.  
  
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
 Der Werttyp-Element.  
  
 `KTraits`  
 Der Code verwendet, um wichtige Elemente kopiert oder verschoben. Finden Sie unter [CElementTraits Klasse](../../atl/reference/celementtraits-class.md) Weitere Details.  
  
 `VTraits`  
 Der Code zum Kopieren oder verschieben Wertelemente verwendet.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRBMultiMap::CRBMultiMap](#crbmultimap)|Der Konstruktor.|  
|[CRBMultiMap:: ~ CRBMultiMap](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRBMultiMap::FindFirstWithKey](#findfirstwithkey)|Rufen Sie diese Methode, um die Position des ersten Elements mit einem angegebenen Schlüssel zu suchen.|  
|[CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey)|Rufen Sie diese Methode, um einen bestimmten Schlüssel zugeordnete Wert abzurufen, und aktualisieren Sie den Positionswert.|  
|[CRBMultiMap::GetNextWithKey](#getnextwithkey)|Rufen Sie diese Methode, um das einem angegebenen Schlüssel zugeordnete Element abgerufen, und aktualisieren Sie den Positionswert.|  
|[CRBMultiMap::Insert](#insert)|Rufen Sie diese Methode zum Einfügen von einer Element-Paar in der Zuordnung.|  
|[CRBMultiMap::RemoveKey](#removekey)|Rufen Sie diese Methode zum Entfernen aller Schlüssel/Wert-Elemente für einen bestimmten Schlüssel.|  
  
## <a name="remarks"></a>Hinweise  
 `CRBMultiMap`bietet Unterstützung für ein Mapping-Array eines beliebigen angegebenen Typs, das ein geordnetes Array von Schlüsselelemente und-Werte verwalten. Im Gegensatz zu den [CRBMap](../../atl/reference/crbmap-class.md) -Klasse, jeder Schlüssel kann mehrere Werte zugeordnet werden.  
  
 Elemente (bestehend aus einem Schlüssel und Wert) werden in einer binären Struktur gespeichert-Struktur unter Verwendung der [CRBMultiMap::Insert](#insert) Methode. Elemente können entfernt werden, mithilfe der [CRBMultiMap::RemoveKey](#removekey) -Methode, die alle Elemente werden gelöscht, die den angegebenen Schlüssel entsprechen.  
  
 Die Aufgabenstruktur erfolgt möglich mit Methoden wie z. B. [CRBTree::GetHeadPosition](../../atl/reference/crbtree-class.md#getheadposition), [CRBTree::GetNext](../../atl/reference/crbtree-class.md#getnext), und [CRBTree::GetNextValue](../../atl/reference/crbtree-class.md#getnextvalue). Zugreifen auf die potenziell mehrere Werte pro Schlüssel möglich verwendet die [CRBMultiMap::FindFirstWithKey](#findfirstwithkey), [CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey), und [CRBMultiMap::GetNextWithKey ](#getnextwithkey) Methoden. Siehe das Beispiel für [CRBMultiMap::CRBMultiMap](#crbmultimap) eine Abbildung dieser in der Praxis.  
  
 Die `KTraits` und `VTraits` Parameter sind Traits-Klassen, die keinen zusätzlichen Code erforderlich, um die Elemente kopiert oder verschoben enthalten.  
  
 `CRBMultiMap`stammt aus [CRBTree](../../atl/reference/crbtree-class.md), die eine Binärstruktur mit dem roten Schwarz-Algorithmus implementiert. Eine Alternative zum `CRBMultiMap` und `CRBMap` angeboten wird, durch die [CAtlMap](../../atl/reference/catlmap-class.md) Klasse. Wenn nur eine kleine Anzahl von Elementen gespeichert werden muss, können Sie verwenden die [CSimpleMap](../../atl/reference/csimplemap-class.md) stattdessen.  
  
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
 Die `nBlockSize` Parameter ist ein Maß für die Speichermenge belegt werden, wenn ein neues Element erforderlich ist. Größere Blöcke reduzieren Sie Aufrufe von Reservierungsroutinen Arbeitsspeicher jedoch mehr Ressourcen verwenden. Die Standardeinstellung belegt Speicherplatz für 10 Elemente zu einem Zeitpunkt.  
  
 Finden Sie in der Dokumentation für die Basisklasse [CRBTree](../../atl/reference/crbtree-class.md) Informationen zu anderen Methoden zur Verfügung.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#85](../../atl/codesnippet/cpp/crbmultimap-class_1.cpp)]  
  
##  <a name="dtor"></a>CRBMultiMap:: ~ CRBMultiMap  
 Der Destruktor.  
  
```
~CRBMultiMap() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt alle zugeordneten Ressourcen frei.  
  
 Finden Sie in der Dokumentation für die Basisklasse [CRBTree](../../atl/reference/crbtree-class.md) Informationen zu anderen Methoden zur Verfügung.  
  
##  <a name="findfirstwithkey"></a>CRBMultiMap::FindFirstWithKey  
 Rufen Sie diese Methode, um die Position des ersten Elements mit einem angegebenen Schlüssel zu suchen.  
  
```
POSITION FindFirstWithKey(KINARGTYPE key) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Gibt den Schlüssel, der das Element gefunden wird, werden identifiziert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die POSITION des ersten Elements der Schlüssel-Wert zurück, wenn der Schlüssel gefunden wird, NULL andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Ein Schlüssel in der `CRBMultiMap` kann eine oder mehrere zugeordnete Werte aufweisen. Diese Methode stellt die des ersten Werts (der tatsächlich nur ein Wert sein kann) Schlüssel zugeordneten Positionswert, bestimmte bereit. Der Wert für die Position zurückgegeben kann dann verwendet werden, mit [CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey) oder [CRBMultiMap::GetNextWithKey](#getnextwithkey) zum Abrufen des Werts, und aktualisieren die Position.  
  
 Finden Sie in der Dokumentation für die Basisklasse [CRBTree](../../atl/reference/crbtree-class.md) Informationen zu anderen Methoden zur Verfügung.  
  
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
 Der Positionswert abgerufen mit entweder einem Aufruf von [CRBMultiMap::FindFirstWithKey](#findfirstwithkey) oder [CRBMultiMap::GetNextWithKey](#getnextwithkey), oder in einem vorherigen Aufruf `GetNextValueWithKey`.  
  
 `key`  
 Gibt den Schlüssel, der das Element gefunden wird, werden identifiziert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt zurück, das dem angegebenen Schlüssel zugeordnete Element-Paar.  
  
### <a name="remarks"></a>Hinweise  
 Der Positionswert wird aktualisiert, und zeigen Sie auf den nächsten Wert, der dem Schlüssel zugeordnet. Wenn keine weitere Werte vorhanden sind, wird der Positionswert auf NULL festgelegt.  
  
 Finden Sie in der Dokumentation für die Basisklasse [CRBTree](../../atl/reference/crbtree-class.md) Informationen zu anderen Methoden zur Verfügung.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CRBMultiMap::CRBMultiMap](#crbmultimap).  
  
##  <a name="getnextwithkey"></a>CRBMultiMap::GetNextWithKey  
 Rufen Sie diese Methode, um das einem angegebenen Schlüssel zugeordnete Element abrufen und aktualisieren Sie den Positionswert.  
  
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
 Der Positionswert abgerufen mit entweder einem Aufruf von [CRBMultiMap::FindFirstWithKey](#findfirstwithkey) oder [CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey), oder in einem vorherigen Aufruf `GetNextWithKey`.  
  
 `key`  
 Gibt den Schlüssel, der das Element gefunden wird, werden identifiziert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die nächste [CRBTree::CPair Klasse](crbtree-class.md#cpair_class) mit dem angegebenen Schlüssel zugeordnete Element.  
  
### <a name="remarks"></a>Hinweise  
 Der Positionswert wird aktualisiert, und zeigen Sie auf den nächsten Wert, der dem Schlüssel zugeordnet. Wenn keine weitere Werte vorhanden sind, wird der Positionswert auf NULL festgelegt.  
  
 Finden Sie in der Dokumentation für die Basisklasse [CRBTree](../../atl/reference/crbtree-class.md) Informationen zu anderen Methoden zur Verfügung.  
  
##  <a name="insert"></a>CRBMultiMap::Insert  
 Rufen Sie diese Methode zum Einfügen von einer Element-Paar in der Zuordnung.  
  
```
POSITION Insert(KINARGTYPE key, VINARGTYPE value) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Der Schlüsselwert, der zum Hinzufügen der `CRBMultiMap` Objekt.  
  
 *value*  
 Der hinzuzufügende Wert der `CRBMultiMap` Objekt zugeordneten `key`.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Position des Schlüssel/Wert-Element-Paar in der `CRBMultiMap` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie in der Dokumentation für die Basisklasse [CRBTree](../../atl/reference/crbtree-class.md) Informationen zu anderen Methoden zur Verfügung.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CRBMultiMap::CRBMultiMap](#crbmultimap).  
  
##  <a name="removekey"></a>CRBMultiMap::RemoveKey  
 Rufen Sie diese Methode zum Entfernen aller Schlüssel/Wert-Elemente für einen bestimmten Schlüssel.  
  
```
size_t RemoveKey(KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Gibt den Schlüssel, der zu löschenden Elemente identifiziert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der mit dem angegebenen Schlüssel zugeordneten Werte zurück.  
  
### <a name="remarks"></a>Hinweise  
 `RemoveKey`Löscht alle Schlüssel-Wert-Elemente, deren ein Schlüssels entspricht `key`.  
  
 Finden Sie in der Dokumentation für die Basisklasse [CRBTree](../../atl/reference/crbtree-class.md) Informationen zu anderen Methoden zur Verfügung.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CRBMultiMap::CRBMultiMap](#crbmultimap).  
  
## <a name="see-also"></a>Siehe auch  
 [CRBTree-Klasse](../../atl/reference/crbtree-class.md)   
 [CAtlMap-Klasse](../../atl/reference/catlmap-class.md)   
 [CRBMultiMap-Klasse](../../atl/reference/crbmap-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
