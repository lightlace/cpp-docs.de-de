---
title: "tiled_index-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp/Concurrency::tiled_index"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tiled_index-Klasse"
ms.assetid: 0ce2ae26-f1bb-4436-b473-a9e1b619bb38
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# tiled_index-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Stellt einen Index für ein [tiled\_extent](../../../parallel/amp/reference/tiled-extent-class.md)\-Objekt bereit.  Diese Klasse verfügt über Eigenschaften, über die auf Elemente relativ zum lokalen Kachelursprung und relativ zum globalen Ursprung zugegriffen werden kann.  Weitere Informationen zu gekachelten Bereichen finden Sie unter [Verwenden von Kacheln](../../../parallel/amp/using-tiles.md).  
  
## Syntax  
  
```  
template <  
   int _Dim0,  
   int _Dim1 = 0,  
   int _Dim2 = 0  
>  
class tiled_index : public _Tiled_index_base<3>;  
  
template <  
   int _Dim0,  
   int _Dim1  
>  
class tiled_index<_Dim0, _Dim1, 0> : public _Tiled_index_base<2>;  
  
template <  
   int _Dim0  
>  
class tiled_index<_Dim0, 0, 0> : public _Tiled_index_base<1>;  
```  
  
#### Parameter  
 `_Dim0`  
 Die Länge der wichtigsten Dimension.  
  
 `_Dim1`  
 Die Länge der zweitwichtigsten Dimension.  
  
 `_Dim2`  
 Die Länge der unwichtigsten Dimension.  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[tiled\_index::tiled\_index\-Konstruktor](../Topic/tiled_index::tiled_index%20Constructor.md)|Initialisiert eine neue Instanz der `tile_index`\-Klasse.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[tiled\_index::get\_tile\_extent\-Methode](../Topic/tiled_index::get_tile_extent%20Method.md)|Gibt ein [extent](../../../parallel/amp/reference/extent-class-cpp-amp.md)\-Objekt zurück, das über die Werte der [tiled\_index](../../../parallel/amp/reference/tiled-index-class.md)\-Vorlagenargumente `_Dim0`, `_Dim1` und `_Dim2` verfügt.|  
  
### Öffentliche Konstanten  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[tiled\_index::barrier\-Konstante](../Topic/tiled_index::barrier%20Constant.md)|Speichert ein [tile\_barrier](../../../parallel/amp/reference/tile-barrier-class.md)\-Objekt, das eine Grenze in der aktuellen Kachel mit Threads darstellt.|  
|||  
|[tiled\_index::global\-Konstante](../Topic/tiled_index::global%20Constant.md)|Speichert ein [index](../../../parallel/amp/reference/index-class.md)\-Objekt von Rang 1, 2 oder 3, das den globalen Index in einem globalen [grid](assetId:///f7d1b6a6-586c-4345-b09a-bfc26c492cb0)\-Objekt darstellt.|  
|[tiled\_index::local\-Konstante](../Topic/tiled_index::local%20Constant.md)|Speichert ein `index`\-Objekt von Rang 1, 2 oder 3, das den relativen Index in der aktuellen Kachel eines [tiled\_extent](../../../parallel/amp/reference/tiled-extent-class.md)\-Objekts darstellt.|  
|[tiled\_index::rank\-Konstante](../Topic/tiled_index::rank%20Constant.md)|Speichert den Rang des [tiled\_index](../../../parallel/amp/reference/tiled-index-class.md)\-Objekts.|  
|[tiled\_index::tile\-Konstante](../Topic/tiled_index::tile%20Constant.md)|Speichert ein `index`\-Objekt von Rang 1, 2 oder 3, das die Koordinaten der aktuellen Kachel eines `tiled_extent`\-Objekts darstellt.|  
|[tiled\_index::tile\_dim0\-Konstante](../Topic/tiled_index::tile_dim0%20Constant.md)|Speichert die Länge der wichtigsten Dimension.|  
|[tiled\_index::tile\_dim1\-Konstante](../Topic/tiled_index::tile_dim1%20Constant.md)|Speichert die Länge der zweitwichtigsten Dimension.|  
|[tiled\_index::tile\_dim2\-Konstante](../Topic/tiled_index::tile_dim2%20Constant.md)|Speichert die Länge der unwichtigsten Dimension.|  
|[tiled\_index::tile\_origin\-Konstante](../Topic/tiled_index::tile_origin%20Constant.md)|Speichert ein `index`\-Objekt von Rang 1, 2 oder 3, das die globalen Koordinaten des Ursprungs der aktuellen Kachel in einem `tiled_extent`\-Objekt darstellt.|  
  
### Öffentliche Datenmember  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[tiled\_index::tile\_extent\-Datenmember](../Topic/tiled_index::tile_extent%20Data%20Member.md)|Ruft ein [extent](../../../parallel/amp/reference/extent-class-cpp-amp.md)\-Objekt ab, das über die Werte der [tiled\_index](../../../parallel/amp/reference/tiled-index-class.md)\-Vorlagenargumente [](../../../parallel/amp/reference/tiled-index-class.md "tiled_index Class")`_Dim0`, `_Dim1` und `_Dim2` verfügt.|  
  
## Vererbungshierarchie  
 `_Tiled_index_base`  
  
 `tiled_index`  
  
## Anforderungen  
 **Header:** amp.h  
  
 **Namespace:** Nebenläufigkeit  
  
## Siehe auch  
 [Concurrency\-Namespace \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)