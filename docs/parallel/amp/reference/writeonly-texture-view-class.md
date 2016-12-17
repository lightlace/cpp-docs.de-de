---
title: "writeonly_texture_view-Klasse"
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
  - "amp_graphics/Concurrency::graphics::writeonly_texture_view"
dev_langs: 
  - "C++"
ms.assetid: 8d117ad3-0a1c-41ae-b29c-7c95fdd4d04d
caps.latest.revision: 9
caps.handback.revision: "4"
ms.author: "mblome"
manager: "ghogen"
---
# writeonly_texture_view-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Bietet lesegeschützten Zugriff auf eine Textur.  
  
## Syntax  
  
```  
template <  
   typename _Value_type,  
   int _Rank  
>  
class writeonly_texture_view;  
  
template <  
   typename _Value_type,  
   int _Rank  
>  
class writeonly_texture_view<_Value_type, _Rank> : public details::_Texture_base<_Value_type, _Rank>;  
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
|`scalar_type`||  
|`value_type`|Der Typ der Elemente in der Textur.|  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[writeonly\_texture\_view::writeonly\_texture\_view\-Konstruktor](../Topic/writeonly_texture_view::writeonly_texture_view%20Constructor.md)|Initialisiert eine neue Instanz der [writeonly\_texture\_view](../../../parallel/amp/reference/writeonly-texture-view-class.md)\-Klasse.|  
|[writeonly\_texture\_view::~writeonly\_texture\_view\-Destruktor](../Topic/writeonly_texture_view::~writeonly_texture_view%20Destructor.md)|Zerstört das [writeonly\_texture\_view](../../../parallel/amp/reference/writeonly-texture-view-class.md)\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[writeonly\_texture\_view::set\-Methode](../Topic/writeonly_texture_view::set%20Method.md)|Legt den Wert des Elements am angegebenen Index ab.|  
  
### Öffentliche Operatoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[writeonly\_texture\_view::operator\=\-Operator](../Topic/writeonly_texture_view::operator=%20Operator.md)|Kopiert das angegebene [writeonly\_texture\_view](../../../parallel/amp/reference/writeonly-texture-view-class.md)\-Objekt in dieses Objekt.|  
  
### Öffentliche Konstanten  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[writeonly\_texture\_view::rank\-Konstante](../Topic/writeonly_texture_view::rank%20Constant.md)|Ruft den Rang des [writeonly\_texture\_view](../../../parallel/amp/reference/writeonly-texture-view-class.md)\-Objekts ab.|  
  
## Vererbungshierarchie  
 `_Texture_base`  
  
 `writeonly_texture_view`  
  
## Anforderungen  
 **Header:** amp\_graphics.h  
  
 **Namespace:** Concurrency::graphics  
  
## Siehe auch  
 [Concurrency::graphics\-Namespace](../../../parallel/amp/reference/concurrency-graphics-namespace.md)