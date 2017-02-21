---
title: "CRBMap Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CRBMap"
  - "CRBMap"
  - "ATL::CRBMap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRBMap class"
ms.assetid: 658e94dc-e835-4356-aed1-1513e1f66969
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# CRBMap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt eine Zuordnungsstruktur, mit einer RED\-Schwarz binären Struktur dar.  
  
## Syntax  
  
```  
  
      template<   
   typename K,  
   typename V,  
   class KTraits = CElementTraits< K >,  
   class VTraits = CElementTraits< V >   
> class CRBMap : public CRBTree< K, V, KTraits, VTraits >  
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
|[CRBMap::CRBMap](../Topic/CRBMap::CRBMap.md)|Der \-Konstruktor.|  
|[CRBMap::~CRBMap](../Topic/CRBMap::~CRBMap.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CRBMap::Lookup](../Topic/CRBMap::Lookup.md)|Rufen Sie diese Methode auf, um Schlüssel oder Werte im `CRBMap`\-Objekt gesucht wird.|  
|[CRBMap::RemoveKey](../Topic/CRBMap::RemoveKey.md)|Rufen Sie diese Methode auf, um ein Element aus dem `CRBMap`\-Objekt zu entfernen, die Schlüssel angegeben.|  
|[CRBMap::SetAt](../Topic/CRBMap::SetAt.md)|Rufen Sie diese Methode auf, um ein Elementpaar in die Zuordnung einzufügen.|  
  
## Hinweise  
 `CRBMap` bietet Unterstützung für ein Zuordnungsarray eines angegebenen Typs und verwaltet ein geordnetes Array Schlüsselelemente und ihre zugeordneten Werte.  Jede Schlüssel kann nur einen zugeordneten Wert haben.  Elemente \(einem Schlüssel und einem Wert bestehend\) werden in einer Struktur der binären Struktur, mithilfe der Methode [CRBMap::SetAt](../Topic/CRBMap::SetAt.md) gespeichert.  Elemente können mit der Methode [CRBMap::RemoveKey](../Topic/CRBMap::RemoveKey.md) entfernt werden, die das Element mit dem angegebenen Schlüsselwert gelöscht wird.  
  
 Das Durchlaufen der Struktur wird mit Methoden wie [CRBTree::GetHeadPosition](../Topic/CRBTree::GetHeadPosition.md), [CRBTree::GetNext](../Topic/CRBTree::GetNext.md) und [CRBTree::GetNextValue](../Topic/CRBTree::GetNextValue.md) zulässt.  
  
 Die `KTraits` und `VTraits`\-Parameter sind Merkmalklassen, die jeden ergänzenden Code enthalten, der erforderlich ist, um Elemente zu kopieren oder verschieben.  
  
 `CRBMap` wird von [CRBTree](../../atl/reference/crbtree-class.md) berechnet, das einer binären Struktur mithilfe des RED\-Schwarz Algorithmus implementiert.  [CRBMultiMap](../../atl/reference/crbmultimap-class.md) ist eine Variante, die mehrere Werte jede Schlüssel zulässt.  Es wird auch von `CRBTree` und daher von den weist viele Funktionen mit `CRBMap` abgeleitet.  
  
 Eine Alternative zu \- `CRBMap` und zu `CRBMultiMap` wird durch die [CAtlMap](../../atl/reference/catlmap-class.md)\-Klasse bereitgestellte.  Wenn nur eine kleine Anzahl Elemente gespeichert werden müssen, erwägen Sie, die [CSimpleMap](../../atl/reference/csimplemap-class.md)\-Klasse stattdessen zu verwenden.  
  
 Weitere finden vollständige Erläuterung der verschiedenen Auflistungsklassen und ihre Funktionen und Leistungsmerkmale, [ATL\-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## Vererbungshierarchie  
 [CRBTree](../../atl/reference/crbtree-class.md)  
  
 `CRBMap`  
  
## Anforderungen  
 **Header:** atlcoll.h  
  
## Siehe auch  
 [CRBTree Class](../../atl/reference/crbtree-class.md)   
 [CAtlMap Class](../../atl/reference/catlmap-class.md)   
 [CRBMultiMap Class](../../atl/reference/crbmultimap-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)