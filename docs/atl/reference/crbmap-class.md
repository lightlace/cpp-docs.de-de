---
title: CRBMap Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRBMap
- ATLCOLL/ATL::CRBMap
- ATLCOLL/ATL::CRBMap::CRBMap
- ATLCOLL/ATL::CRBMap::Lookup
- ATLCOLL/ATL::CRBMap::RemoveKey
- ATLCOLL/ATL::CRBMap::SetAt
dev_langs: C++
helpviewer_keywords: CRBMap class
ms.assetid: 658e94dc-e835-4356-aed1-1513e1f66969
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 127f8b0448d141917193d41d11d5ed95576ff482
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="crbmap-class"></a>CRBMultiMap-Klasse
Diese Klasse stellt eine Zuordnungsstruktur mithilfe einer Binärstruktur Rot Schwarz.  
  
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
 Der Werttyp-Element.  
  
 `KTraits`  
 Der Code verwendet, um wichtige Elemente kopiert oder verschoben. Finden Sie unter [CElementTraits Klasse](../../atl/reference/celementtraits-class.md) Weitere Details.  
  
 `VTraits`  
 Der Code zum Kopieren oder verschieben Wertelemente verwendet.  
  
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
|[CRBMap::RemoveKey](#removekey)|Rufen Sie diese Methode zum Entfernen eines Elements aus der `CRBMap` Objekt anhand des angegebenen Schlüssels.|  
|[CRBMap::SetAt](#setat)|Rufen Sie diese Methode zum Einfügen von einer Element-Paar in der Zuordnung.|  
  
## <a name="remarks"></a>Hinweise  
 `CRBMap`bietet Unterstützung für ein Mapping-Array eines angegebenen Typs, verwalten ein geordnetes Array von Schlüsselelemente und die zugehörigen Werte. Jeder Schlüssel kann nur einen zugeordneten Wert aufweisen. Elemente (bestehend aus einem Schlüssel und Wert) werden in einer binären Struktur gespeichert-Struktur unter Verwendung der [CRBMap::SetAt](#setat) Methode. Elemente können entfernt werden, mithilfe der [CRBMap::RemoveKey](#removekey) -Methode, die löscht das Element mit dem angegebenen Schlüsselwert.  
  
 Die Aufgabenstruktur erfolgt möglich mit Methoden wie z. B. [CRBTree::GetHeadPosition](../../atl/reference/crbtree-class.md#getheadposition), [CRBTree::GetNext](../../atl/reference/crbtree-class.md#getnext), und [CRBTree::GetNextValue](../../atl/reference/crbtree-class.md#getnextvalue).  
  
 Die `KTraits` und `VTraits` Parameter sind Traits-Klassen, die keinen zusätzlichen Code erforderlich, um die Elemente kopiert oder verschoben enthalten.  
  
 `CRBMap`stammt aus [CRBTree](../../atl/reference/crbtree-class.md), die eine Binärstruktur mit dem roten Schwarz-Algorithmus implementiert. [CRBMultiMap](../../atl/reference/crbmultimap-class.md) ist eine Variante, die mehrere Werte für jeden Schlüssel zulässt. Es zu abgeleitet wird `CRBTree`, und gibt so viele Funktionen mit frei `CRBMap`.  
  
 Eine Alternative für beide `CRBMap` und `CRBMultiMap` angeboten wird, durch die [CAtlMap](../../atl/reference/catlmap-class.md) Klasse. Wenn nur eine kleine Anzahl von Elementen gespeichert werden muss, können Sie verwenden die [CSimpleMap](../../atl/reference/csimplemap-class.md) stattdessen.  
  
 Eine vollständige Erläuterung der verschiedenen Auflistungsklassen und ihre Funktionen und Leistungsmerkmale, finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CRBTree](../../atl/reference/crbtree-class.md)  
  
 `CRBMap`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcoll.h  
  
##  <a name="crbmap"></a>CRBMap::CRBMap  
 Der Konstruktor.  
  
```
explicit CRBMap(size_t nBlockSize = 10) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nBlockSize`  
 Die Blockgröße.  
  
### <a name="remarks"></a>Hinweise  
 Die `nBlockSize` Parameter ist ein Maß für die Speichermenge belegt werden, wenn ein neues Element erforderlich ist. Größere Blöcke reduzieren Sie Aufrufe von Reservierungsroutinen Arbeitsspeicher jedoch mehr Ressourcen verwenden. Die Standardeinstellung belegt Speicherplatz für 10 Elemente zu einem Zeitpunkt.  
  
 Finden Sie in der Dokumentation für die Basisklasse [CRBTree](../../atl/reference/crbtree-class.md) Informationen zu anderen Methoden zur Verfügung.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#81](../../atl/codesnippet/cpp/crbmap-class_1.cpp)]  
  
##  <a name="dtor"></a>CRBMap:: ~ CRBMap  
 Der Destruktor.  
  
```
~CRBMap() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt alle zugeordneten Ressourcen frei.  
  
 Finden Sie in der Dokumentation für die Basisklasse [CRBTree](../../atl/reference/crbtree-class.md) Informationen zu anderen Methoden zur Verfügung.  
  
##  <a name="lookup"></a>CRBMap::Lookup  
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
 Variablen, empfängt der gebundene Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 Die erste Form der Methode gibt "true", wenn der Schlüssel gefunden wird, andernfalls "false" zurück. Die zweite und dritte Formulare zurückgeben, einen Zeiger auf eine [CPair](crbtree-class.md#cpair_class).  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie in der Dokumentation für die Basisklasse [CRBTree](../../atl/reference/crbtree-class.md) Informationen zu anderen Methoden zur Verfügung.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#82](../../atl/codesnippet/cpp/crbmap-class_2.cpp)]  
  
##  <a name="removekey"></a>CRBMap::RemoveKey  
 Rufen Sie diese Methode zum Entfernen eines Elements aus der `CRBMap` Objekt anhand des angegebenen Schlüssels.  
  
```
bool RemoveKey(KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Die Schlüssel entsprechend der Element-Paar, die Sie entfernen möchten.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt true zurück, wenn der Schlüssel gefunden und entfernt, bei einem Fehler false.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie in der Dokumentation für die Basisklasse [CRBTree](../../atl/reference/crbtree-class.md) Informationen zu anderen Methoden zur Verfügung.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#83](../../atl/codesnippet/cpp/crbmap-class_3.cpp)]  
  
##  <a name="setat"></a>CRBMap::SetAt  
 Rufen Sie diese Methode zum Einfügen von einer Element-Paar in der Zuordnung.  
  
```
POSITION SetAt(
    KINARGTYPE key,
    VINARGTYPE value) throw(...);
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Der Schlüsselwert, der zum Hinzufügen der `CRBMap` Objekt.  
  
 *value*  
 Der Wert, der zum Hinzufügen der `CRBMap` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Position des Schlüssel/Wert-Element-Paar in der `CRBMap` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 `SetAt`ersetzt ein vorhandenes Element, wenn ein übereinstimmender Schlüssel gefunden wird. Wenn der Schlüssel nicht gefunden wird, wird ein neues Schlüssel/Wert-Paar erstellt.  
  
 Finden Sie in der Dokumentation für die Basisklasse [CRBTree](../../atl/reference/crbtree-class.md) Informationen zu anderen Methoden zur Verfügung.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#84](../../atl/codesnippet/cpp/crbmap-class_4.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [CRBTree-Klasse](../../atl/reference/crbtree-class.md)   
 [CAtlMap-Klasse](../../atl/reference/catlmap-class.md)   
 [CRBMultiMap-Klasse](../../atl/reference/crbmultimap-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
