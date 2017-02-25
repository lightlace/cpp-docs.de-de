---
title: "tiled_extent-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp/Concurrency::tiled_extent"
dev_langs: 
  - "C++"
ms.assetid: 671ecaf8-c7b0-4ac8-bbdc-e30bd92da7c0
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# tiled_extent-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Ein `tiled_extent`\-Objekt ist ein `extent`\-Objekt einer bis drei Dimensionen, das den "extent"\-Bereich in ein\-, zwei\- oder dreidimensionale Kacheln unterteilt.  
  
## Syntax  
  
```  
template <  
   int _Dim0,  
   int _Dim1,  
   int _Dim2  
>  
class tiled_extent : public Concurrency::extent<3>;  
  
template <  
   int _Dim0,  
   int _Dim1  
>  
class tiled_extent<_Dim0, _Dim1, 0> : public Concurrency::extent<2>;  
  
template <  
   int _Dim0  
>  
class tiled_extent<_Dim0, 0, 0> : public Concurrency::extent<1>;  
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
|[tiled\_extent::tiled\_extent\-Konstruktor](../Topic/tiled_extent::tiled_extent%20Constructor.md)|Initialisiert eine neue Instanz der `tiled_extent`\-Klasse.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[tiled\_extent::get\_tile\_extent\-Methode](../Topic/tiled_extent::get_tile_extent%20Method.md)|Gibt ein `extent`\-Objekt zurück, das die Werte der `tiled_extent`\-Vorlagenargumente `_Dim0`, `_Dim1` und `_Dim2` erfasst.|  
|[tiled\_extent::pad\-Methode](../Topic/tiled_extent::pad%20Method.md)|Gibt ein neues `tiled_extent`\-Objekt mit den Wertebereichen zurück, die aufgerundet werden, um durch die Kacheldimensionen teilbar zu sein.|  
|[tiled\_extent::truncate\-Methode](../Topic/tiled_extent::truncate%20Method.md)|Gibt ein neues `tiled_extent`\-Objekt mit den Wertebereichen zurück, die abgerundet werden, um durch die Kacheldimensionen teilbar zu sein.|  
  
### Öffentliche Operatoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[tiled\_extent::operator\=\-Operator](../Topic/tiled_extent::operator=%20Operator.md)|Kopiert den Inhalt des angegebenen `tiled_index`\-Objekts in dieses Objekt.|  
  
### Öffentliche Konstanten  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[tiled\_extent::tile\_dim0\-Konstante](../Topic/tiled_extent::tile_dim0%20Constant.md)|Speichert die Länge der wichtigsten Dimension.|  
|[tiled\_extent::tile\_dim1\-Konstante](../Topic/tiled_extent::tile_dim1%20Constant.md)|Speichert die Länge der zweitwichtigsten Dimension.|  
|[tiled\_extent::tile\_dim2\-Konstante](../Topic/tiled_extent::tile_dim2%20Constant.md)|Speichert die Länge der unwichtigsten Dimension.|  
  
### Öffentliche Datenmember  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[tiled\_extent::tile\_extent\-Datenmember](../Topic/tiled_extent::tile_extent%20Data%20Member.md)|Ruft ein `extent`\-Objekt ab, das die Werte der `tiled_extent`\-Vorlagenargumente `_Dim0`, `_Dim1` und `_Dim2` erfasst.|  
  
## Vererbungshierarchie  
 `extent`  
  
 `tiled_extent`  
  
## Anforderungen  
 **Header:** amp.h  
  
 **Namespace:** Nebenläufigkeit  
  
## Siehe auch  
 [Concurrency\-Namespace \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)