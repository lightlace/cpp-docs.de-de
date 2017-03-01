---
title: 'Concurrency:: Graphics-Namespace | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_graphics/Concurrency::graphics
- amp_short_vectors/Concurrency::graphics
dev_langs:
- C++
ms.assetid: 4529d3b1-d7da-4ffb-82bf-080915e0f23e
caps.latest.revision: 14
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: fd29b427307e336d560a2caf42e4fc5228e8071f
ms.lasthandoff: 02/24/2017

---
# <a name="concurrencygraphics-namespace"></a>Concurrency::graphics-Namespace
Der Grafiknamespace stellt Typen und Funktionen bereit, die für die Grafikprogrammierung vorgesehen sind.  
  
## <a name="syntax"></a>Syntax  
  
```  
namespace graphics;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="namespaces"></a>Namespaces  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Concurrency::Graphics::Direct3D-Namespace](concurrency-graphics-direct3d-namespace.md)|Stellt Funktionen für Direct3D-Interop bereit.|  
  
### <a name="typedefs"></a>Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`uint`|Der Elementtyp für [uint_2-Klasse](uint-2-class.md), [uint_3-Klasse](uint-3-class.md), und [uint_4-Klasse](uint-4-class.md). Definiert als `typedef unsigned int uint;`.|  
  
### <a name="enumerations"></a>Enumerationen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Address_mode-Enumeration](concurrency-graphics-namespace-enums.md#address_mode).|Gibt die unterstützten Adressmodi für das Textursampling an.|  
|[Filter_mode-Enumeration](concurrency-graphics-namespace-enums.md#filter_mode)|Gibt die unterstützten Filtermodi für das Textursampling an.|  
  
### <a name="classes"></a>Klassen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Texture-Klasse](texture-class.md)|Eine Textur ist ein Datenaggregat in einer "accelerator_view" in der extent-Domäne. Es ist eine Auflistung von Variablen, eine für jedes Element in einer extent-Domäne. Jede Variable enthält einen Wert gemäß primitivem C++-Typ ohne Vorzeichen (int, int, Float, Double) oder skalarer Typnorm bzw. unorm (definiert in concurrency::graphics) oder zulässige kurze Vektortypen, die in concurrency::graphics definiert werden.|  
|[Writeonly_texture_view-Klasse](writeonly-texture-view-class.md)|Eine "writeonly_texture_view" bietet Nur-Schreib-Zugriff auf eine Textur.|  
|[double_2-Klasse](double-2-class.md)|Stellt einen kurzen Vektor von 2 `double`-Werten dar.|  
|[double_3-Klasse](double-3-class.md)|Stellt einen kurzen Vektor von 3 `double` Werte.|  
|[double_4-Klasse](double-4-class.md)|Stellt einen kurzen Vektor von 4 `double` Werte.|  
|[float_2-Klasse](float-2-class.md)|Stellt einen kurzen Vektor von 2 `float`-Werten dar.|  
|[float_3-Klasse](float-3-class.md)|Stellt einen kurzen Vektor von 3 `float` Werte.|  
|[float_4-Klasse](float-4-class.md)|Stellt einen kurzen Vektor von 4 `float` Werte.|  
|[int_2-Klasse](int-2-class.md)|Stellt einen kurzen Vektor von 2 `int`-Werten dar.|  
|[int_3-Klasse](int-3-class.md)|Stellt einen kurzen Vektor von 3 `int` Werte.|  
|[int_4-Klasse](int-4-class.md)|Stellt einen kurzen Vektor von 4 `int` Werte.|  
|[norm_2-Klasse](norm-2-class.md)|Stellt einen kurzen Vektor von 2 `norm`-Werten dar.|  
|[norm_3-Klasse](norm-3-class.md)|Stellt einen kurzen Vektor von 3 `norm` Werte.|  
|[norm_4-Klasse](norm-4-class.md)|Stellt einen kurzen Vektor von 4 `norm` Werte.|  
|[uint_2-Klasse](uint-2-class.md)|Stellt einen kurzen Vektor von 2 `uint`-Werten dar.|  
|[uint_3-Klasse](uint-3-class.md)|Stellt einen kurzen Vektor von 3 `uint` Werte.|  
|[uint_4-Klasse](uint-4-class.md)|Stellt einen kurzen Vektor von 4 `uint` Werte.|  
|[unorm_2-Klasse](unorm-2-class.md)|Stellt einen kurzen Vektor von 2 `unorm`-Werten dar.|  
|[unorm_3-Klasse](unorm-3-class.md)|Stellt einen kurzen Vektor von 3 `unorm` Werte.|  
|[unorm_4-Klasse](unorm-4-class.md)|Stellt einen kurzen Vektor von 4 `unorm` Werte.|  
|[samplerklasse](sampler-class.md)|Stellt die Samplerkonfiguration dar, die für Textursampling verwendet wird.|  
|[Short_vector-Struktur](short-vector-structure.md)|Stellt eine grundlegende Implementierung eines kurzen Vektors von Werten.|  
|[Short_vector_traits-Struktur](short-vector-traits-structure.md)|Stellt das Abrufen der Länge und des Typs eines kurzen Vektors bereit.|  
|[Texture_view-Klasse](texture-view-class.md)|Stellt einer Textur Lese- und Schreibzugriff zur Verfügung.|  
  
### <a name="functions"></a>Funktionen  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Copy-Funktion](concurrency-graphics-namespace-functions.md#copy)|Überladen. Kopiert den Inhalt der Quelltextur in den Zielhostpuffer.|  
|[Copy_async-Funktion](concurrency-graphics-namespace-functions.md#copy_async)|Überladen. Kopiert den Inhalt der Quelltextur asynchron in den Zielhostpuffer.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** amp_graphics.h  
  
 **Namespace:** Parallelität  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace (C++-AMP)](concurrency-namespace-cpp-amp.md)

