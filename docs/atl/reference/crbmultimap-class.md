---
title: "CRBMultiMap Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CRBMultiMap"
  - "ATL.CRBMultiMap"
  - "ATL::CRBMultiMap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRBMultiMap class"
ms.assetid: 94d3ec0c-3e30-4ab7-a101-d8da4fb8add3
caps.latest.revision: 19
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# CRBMultiMap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt eine Zuordnungsstruktur dar, die alle Schlüssel kann mit mehr als einem Wert, RED\-Schwarz mithilfe einer binären Struktur zugeordnet werden können.  
  
## Syntax  
  
```  
  
      template<  
   typename K,  
   typename V,  
   class KTraits = CElementTraits< K >,  
   class VTraits = CElementTraits< V >  
> class CRBMultiMap : public CRBTree< K, V, KTraits, VTraits >  
```  
  
#### Parameter  
 `K`  
 Der Schlüsselelementtyp.  
  
 *V*  
 Der Wertselementtyp.  
  
 `KTraits`  
 Der Code verwendet, um Schlüsselelemente zu kopieren oder verschieben.  Siehe [CElementTraits\-Klasse](../../atl/reference/celementtraits-class.md) für weitere Details.  
  
 `VTraits`  
 Der Code verwendet, um Wertelemente zu kopieren oder verschieben.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CRBMultiMap::CRBMultiMap](../Topic/CRBMultiMap::CRBMultiMap.md)|Der \-Konstruktor.|  
|[CRBMultiMap::~CRBMultiMap](../Topic/CRBMultiMap::~CRBMultiMap.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CRBMultiMap::FindFirstWithKey](../Topic/CRBMultiMap::FindFirstWithKey.md)|Rufen Sie diese Methode auf, um die Position des ersten Elements mit einer angegebenen Schlüssel zu ermitteln.|  
|[CRBMultiMap::GetNextValueWithKey](../Topic/CRBMultiMap::GetNextValueWithKey.md)|Rufen Sie diese Methode auf, um den Wert abzurufen, der mit einer angegebenen Schlüssel, und aktualisieren Sie den Positionswert.|  
|[CRBMultiMap::GetNextWithKey](../Topic/CRBMultiMap::GetNextWithKey.md)|Rufen Sie diese Methode auf, um das Element abzurufen, das einer angegebenen Schlüssel, und aktualisieren Sie den Positionswert.|  
|[CRBMultiMap::Insert](../Topic/CRBMultiMap::Insert.md)|Rufen Sie diese Methode auf, um ein Elementpaar in die Zuordnung einzufügen.|  
|[CRBMultiMap::RemoveKey](../Topic/CRBMultiMap::RemoveKey.md)|Rufen Sie diese Methode auf, um alle Schlüssel\-Werts\-Elemente für eine angegebene Schlüssel zu entfernen.|  
  
## Hinweise  
 `CRBMultiMap` bietet Unterstützung für ein Zuordnungsarray eines angegebenen Typs und verwaltet ein geordnetes Array Schlüsselelemente und Werte.  Im Gegensatz zur [CRBMap](../../atl/reference/crbmap-class.md)\-Klasse kann jede Schlüssel mit mehr als einem Wert zugeordnet werden.  
  
 Elemente \(einem Schlüssel und einem Wert bestehend\) werden in einer Struktur der binären Struktur, mithilfe der Methode [CRBMultiMap::Insert](../Topic/CRBMultiMap::Insert.md) gespeichert.  Elemente können mit der Methode [CRBMultiMap::RemoveKey](../Topic/CRBMultiMap::RemoveKey.md) entfernt werden, die alle Elemente gelöscht werden, die die angegebene Schlüssel entsprechen.  
  
 Das Durchlaufen der Struktur wird mit Methoden wie [CRBTree::GetHeadPosition](../Topic/CRBTree::GetHeadPosition.md), [CRBTree::GetNext](../Topic/CRBTree::GetNext.md) und [CRBTree::GetNextValue](../Topic/CRBTree::GetNextValue.md) zulässt.  Auf die möglicherweise mehrere Werte pro Schlüssel zuzugreifen kann mithilfe der [CRBMultiMap::FindFirstWithKey](../Topic/CRBMultiMap::FindFirstWithKey.md), [CRBMultiMap::GetNextValueWithKey](../Topic/CRBMultiMap::GetNextValueWithKey.md) und [CRBMultiMap::GetNextWithKey](../Topic/CRBMultiMap::GetNextWithKey.md)\-Methoden möglich.  Im Beispiel für [CRBMultiMap::CRBMultiMap](../Topic/CRBMultiMap::CRBMultiMap.md) für eine Abbildung von diesem in der Praxis.  
  
 Die `KTraits` und `VTraits`\-Parameter sind Merkmalklassen, die jeden ergänzenden Code enthalten, der erforderlich ist, um Elemente zu kopieren oder verschieben.  
  
 `CRBMultiMap` wird von [CRBTree](../../atl/reference/crbtree-class.md) berechnet, das einer binären Struktur mithilfe des RED\-Schwarz Algorithmus implementiert.  Eine Alternative zu `CRBMultiMap` und zu `CRBMap` wird durch die [CAtlMap](../../atl/reference/catlmap-class.md)\-Klasse bereitgestellte.  Wenn nur eine kleine Anzahl Elemente gespeichert werden müssen, erwägen Sie, die [CSimpleMap](../../atl/reference/csimplemap-class.md)\-Klasse stattdessen zu verwenden.  
  
 Weitere finden vollständige Erläuterung der verschiedenen Auflistungsklassen und ihre Funktionen und Leistungsmerkmale, [ATL\-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## Vererbungshierarchie  
 [CRBTree](../../atl/reference/crbtree-class.md)  
  
 `CRBMultiMap`  
  
## Anforderungen  
 **Header:** atlcoll.h  
  
## Siehe auch  
 [CRBTree Class](../../atl/reference/crbtree-class.md)   
 [CAtlMap Class](../../atl/reference/catlmap-class.md)   
 [CRBMap Class](../../atl/reference/crbmap-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)