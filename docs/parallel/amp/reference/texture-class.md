---
title: "texture-Klasse"
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
  - "amp_graphics/Concurrency::graphics::texture"
dev_langs: 
  - "C++"
ms.assetid: 16e85d4d-e80a-474a-995d-8bf63fbdf34c
caps.latest.revision: 9
caps.handback.revision: "4"
ms.author: "mblome"
manager: "ghogen"
---
# texture-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Eine Textur ist ein Datenaggregat in einem `accelerator_view`\-Objekt in der extent\-Domäne.  Es ist eine Auflistung von Variablen, eine für jedes Element in einer extent\-Domäne.  Jede Variable enthält einen Wert, der dem C\+\+ primitivem Typ \(`unsigned int`, `int`, `float`, `double`\), einem Skalarwerttyp \(`norm` oder `unorm`\) oder einem kurzen Vektortyp entspricht.  
  
## Syntax  
  
```  
template <  
   typename _Value_type,  
   int _Rank  
>  
class texture;  
```  
  
#### Parameter  
 `_Value_type`  
 Der Typ der Elemente in der Textur.  
  
 `_Rank`  
 Der Rang der Textur.  
  
## Member  
  
### Öffentliche Typedefs  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|`scalar_type`|Skalare Typen.|  
|`value_type`|Werttypen.|  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[texture::texture\-Konstruktor](../Topic/texture::texture%20Constructor.md)|Initialisiert eine neue Instanz der [texture](../../../parallel/amp/reference/texture-class.md)\-Klasse.|  
|[texture::~texture\-Destruktor](../Topic/texture::~texture%20Destructor.md)|Zerstört das [texture](../../../parallel/amp/reference/texture-class.md)\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[texture::copy\_to\-Methode](../Topic/texture::copy_to%20Method.md)|Kopiert das [texture](../../../parallel/amp/reference/texture-class.md)\-Objekt in das Ziel, indem eine tiefe Kopie erstellt wird.|  
|[texture::data\-Methode](../Topic/texture::data%20Method.md)|Gibt einen CPU\-Zeiger auf Rohdaten dieser Textur zurück.|  
|[texture::get\-Methode](../Topic/texture::get%20Method.md)|Gibt den Wert des Elements am angegebenen Index zurück.|  
|[texture::get\_associated\_accelerator\_view\-Methode](../Topic/texture::get_associated_accelerator_view%20Method.md)|Gibt das [accelerator\_view](../../../parallel/amp/reference/accelerator-view-class.md)\-Objekt zurück, das das gewünschte Ziel zum Kopieren dieser Textur ist.|  
|[texture::get\_depth\_pitch\-Methode](../Topic/texture::get_depth_pitch%20Method.md)|Gibt die Anzahl von Bytes zwischen jedem Tiefensegment in einer 3D\-Stagingtextur auf der CPU zurück.|  
|[texture::get\_row\_pitch\-Methode](../Topic/texture::get_row_pitch%20Method.md)|Gibt die Anzahl von Bytes zwischen jeder Zeile in einer 2D\- oder 3D\-Stagingtextur auf der CPU zurück.|  
|[texture::set\-Methode](../Topic/texture::set%20Method.md)|Legt den Wert des Elements am angegebenen Index ab.|  
  
### Öffentliche Operatoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[texture::operator\(\)\-Operator](../Topic/texture::operator\(\)%20Operator.md)|Gibt den Elementwert zurück, der von den Parametern angegeben wird.|  
|[texture::operator\-Operator](../Topic/texture::operatorOperator.md)|Gibt das Element am angegebenen Index zurück.|  
|[texture::operator\=\-Operator](../Topic/texture::operator=%20Operator.md)|Kopiert das angegebene [texture](../../../parallel/amp/reference/texture-class.md)\-Objekt in dieses Objekt.|  
  
### Öffentliche Konstanten  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[texture::rank\-Konstante](../Topic/texture::rank%20Constant.md)|Ruft den Rang des [texture](../../../parallel/amp/reference/texture-class.md)\-Objekts ab.|  
  
### Öffentliche Datenmember  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[texture::associated\_accelerator\_view\-Datenmember](../Topic/texture::associated_accelerator_view%20Data%20Member.md)|Ruft das [accelerator\_view](../../../parallel/amp/reference/accelerator-view-class.md)\-Objekt ab, das das gewünschte Ziel zum Kopieren dieser Textur ist.|  
|[texture::depth\_pitch\-Datenmember](../Topic/texture::depth_pitch%20Data%20Member.md)|Ruft die Anzahl von Bytes zwischen jedem Tiefensegment in einer 3D\-Stagingtextur auf der CPU ab.|  
|[texture::row\_pitch\-Datenmember](../Topic/texture::row_pitch%20Data%20Member.md)|Ruft die Anzahl von Bytes zwischen jeder Zeile in einer 2D\- oder 3D\-Stagingtextur auf der CPU zurück.|  
  
## Vererbungshierarchie  
 `_Texture_base`  
  
 `texture`  
  
## Anforderungen  
 **Header:** amp\_graphics.h  
  
 **Namespace:** Concurrency::graphics  
  
## Siehe auch  
 [Concurrency::graphics\-Namespace](../../../parallel/amp/reference/concurrency-graphics-namespace.md)