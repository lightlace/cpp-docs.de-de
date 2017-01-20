---
title: "Concurrency::graphics-Namespace"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "amp_graphics/Concurrency::graphics"
  - "amp_short_vectors/Concurrency::graphics"
dev_langs: 
  - "C++"
ms.assetid: 4529d3b1-d7da-4ffb-82bf-080915e0f23e
caps.latest.revision: 14
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Concurrency::graphics-Namespace
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Der Grafiknamespace stellt Typen und Funktionen bereit, die für die Grafikprogrammierung vorgesehen sind.  
  
## Syntax  
  
```  
namespace graphics;  
```  
  
## Member  
  
### Namespaces  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[Concurrency::graphics::direct3d\-Namespace](../../../parallel/amp/reference/concurrency-graphics-direct3d-namespace.md)|Stellt Funktionen für Direct3D\-Interop bereit.|  
  
### Typedefs  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|`uint`|Der Elementtyp für [uint\_2\-Klasse](../../../parallel/amp/reference/uint-2-class.md), [uint\_3\-Klasse](../../../parallel/amp/reference/uint-3-class.md), und [uint\_4\-Klasse](../../../parallel/amp/reference/uint-4-class.md).  Definiert als `typedef unsigned int uint;`.|  
  
### Enumerationen  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[address\_mode\-Enumeration](../Topic/address_mode%20Enumeration.md)|Gibt die unterstützten Adressmodi für das Textursampling an.|  
|[filter\_mode\-Enumeration](../Topic/filter_mode%20Enumeration.md)|Gibt die unterstützten Filtermodi für das Textursampling an.|  
  
### Klassen  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[texture\-Klasse](../../../parallel/amp/reference/texture-class.md)|Eine Textur ist ein Datenaggregat in einer "accelerator\_view" in der extent\-Domäne.  Es ist eine Auflistung von Variablen, eine für jedes Element in einer extent\-Domäne.  Jede Variable enthält einen Wert gemäß primitivem C\+\+\-Typ ohne Vorzeichen \(int, int, Float, Double\) oder skalarer Typnorm bzw. unorm \(definiert in concurrency::graphics\) oder zulässige kurze Vektortypen, die in concurrency::graphics definiert werden.|  
|[writeonly\_texture\_view\-Klasse](../../../parallel/amp/reference/writeonly-texture-view-class.md)|Eine "writeonly\_texture\_view" bietet Nur\-Schreib\-Zugriff auf eine Textur.|  
|[double\_2\-Klasse](../../../parallel/amp/reference/double-2-class.md)|Stellt einen kurzen Vektor von 2 `double`\-Werten dar.|  
|[double\_3\-Klasse](../../../parallel/amp/reference/double-3-class.md)|Stellt einen kurzen Vektor von 3 `double`\-Werten dar.|  
|[double\_4\-Klasse](../../../parallel/amp/reference/double-4-class.md)|Stellt einen kurzen Vektor von 4 `double`\-Werten dar.|  
|[float\_2\-Klasse](../../../parallel/amp/reference/float-2-class.md)|Stellt einen kurzen Vektor von 2 `float`\-Werten dar.|  
|[float\_3\-Klasse](../../../parallel/amp/reference/float-3-class.md)|Stellt einen kurzen Vektor von 3 `float`\-Werten dar.|  
|[float\_4\-Klasse](../../../parallel/amp/reference/float-4-class.md)|Stellt einen kurzen Vektor von 4 `float`\-Werten dar.|  
|[int\_2\-Klasse](../../../parallel/amp/reference/int-2-class.md)|Stellt einen kurzen Vektor von 2 `int`\-Werten dar.|  
|[int\_3\-Klasse](../../../parallel/amp/reference/int-3-class.md)|Stellt einen kurzen Vektor von 3 `int`\-Werten dar.|  
|[int\_4\-Klasse](../../../parallel/amp/reference/int-4-class.md)|Stellt einen kurzen Vektor von 4 `int`\-Werten dar.|  
|[norm\_2\-Klasse](../../../parallel/amp/reference/norm-2-class.md)|Stellt einen kurzen Vektor von 2 `norm`\-Werten dar.|  
|[norm\_3\-Klasse](../../../parallel/amp/reference/norm-3-class.md)|Stellt einen kurzen Vektor von 3 `norm`\-Werten dar.|  
|[norm\_4\-Klasse](../../../parallel/amp/reference/norm-4-class.md)|Stellt einen kurzen Vektor von 4 `norm`\-Werten dar.|  
|[uint\_2\-Klasse](../../../parallel/amp/reference/uint-2-class.md)|Stellt einen kurzen Vektor von 2 `uint`\-Werten dar.|  
|[uint\_3\-Klasse](../../../parallel/amp/reference/uint-3-class.md)|Stellt einen kurzen Vektor von 3 `uint`\-Werten dar.|  
|[uint\_4\-Klasse](../../../parallel/amp/reference/uint-4-class.md)|Stellt einen kurzen Vektor von 4 `uint`\-Werten dar.|  
|[unorm\_2\-Klasse](../../../parallel/amp/reference/unorm-2-class.md)|Stellt einen kurzen Vektor von 2 `unorm`\-Werten dar.|  
|[unorm\_3\-Klasse](../../../parallel/amp/reference/unorm-3-class.md)|Stellt einen kurzen Vektor von 3 `unorm`\-Werten dar.|  
|[unorm\_4\-Klasse](../../../parallel/amp/reference/unorm-4-class.md)|Stellt einen kurzen Vektor von 4 `unorm`\-Werten dar.|  
|[Samplerklasse](../../../parallel/amp/reference/sampler-class.md)|Stellt die Samplerkonfiguration dar, die für Textursampling verwendet wird.|  
|[short\_vector\-Struktur](../../../parallel/amp/reference/short-vector-structure.md)|Stellt eine grundlegende Implementierung eines kurzen Vektors von Werten bereit.|  
|[short\_vector\_traits\-Struktur](../../../parallel/amp/reference/short-vector-traits-structure.md)|Stellt das Abrufen der Länge und des Typs eines kurzen Vektors bereit.|  
|[texture\_view\-Klasse](../../../parallel/amp/reference/texture-view-class.md)|Stellt einer Textur Lese\- und Schreibzugriff zur Verfügung.|  
  
### Funktionen  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[copy\-Funktion](../Topic/copy%20Function.md)|Überladen.  Kopiert den Inhalt der Quelltextur in den Zielhostpuffer.|  
|[copy\_async\-Funktion](../Topic/copy_async%20Function.md)|Überladen.  Kopiert den Inhalt der Quelltextur asynchron in den Zielhostpuffer.|  
  
## Anforderungen  
 **Header:** amp\_graphics.h  
  
 **Namespace:** Nebenläufigkeit  
  
## Siehe auch  
 [Concurrency\-Namespace \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)