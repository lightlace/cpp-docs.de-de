---
title: Standardnamespace | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 4712e9dc-57ba-43cc-811e-022e1dae4de8
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3f4386d3636744a673a10dd9530fd3836fdb78e6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="default-namespace"></a>Standardnamespace
Die `default` Namespace umfasst die integrierten Typen, die durch C++ unterstützt c++ / CX.  
  
## <a name="syntax"></a>Syntax  
  
```  
namespace default;  
```  
  
### <a name="members"></a>Member  
 Alle integrierte Typen erben die folgenden Member.  
  
|||  
|-|-|  
|[default::(type_name)::Equals](../cppcx/default-type-name-equals-method.md)|Bestimmt, ob das angegebene Objekt mit dem aktuellen Objekt identisch ist.|  
|[default::(type_name)::GetHashCode](../cppcx/default-type-name-gethashcode-method.md)|Gibt den Hashcode für diese Instanz zurück.|  
|[default::(type_name)::GetType](../cppcx/default-type-name-gettype-method.md)|Gibt eine Zeichenfolge zurück, die den aktuellen Typ darstellt.|  
|[default::(type_name)::ToString](../cppcx/default-type-name-tostring-method.md)|Gibt eine Zeichenfolge zurück, die den aktuellen Typ darstellt.|  
  
### <a name="built-in-types"></a>Integrierte Typen  
  
|name|Beschreibung|  
|----------|-----------------|  
|`char16`|Ein nicht numerischer 16-Bit-Wert, der einen Unicode-Codepunkt (UTF-16) darstellt.|  
|`float32`|Eine 32-Bit-IEEE 754-Gleitkommazahl.|  
|`float64`|Eine 64-Bit-IEEE 754-Gleitkommazahl.|  
|`int16`|Eine 16-Bit-Ganzzahl mit Vorzeichen.|  
|`int32`|Eine 32-Bit-Ganzzahl mit Vorzeichen.|  
|`int64`|Eine 64-Bit-Ganzzahl mit Vorzeichen.|  
|`int8`|Eine numerischer 8-Bit-Wert mit Vorzeichen.|  
|`uint16`|Eine 16-Bit-Ganzzahl ohne Vorzeichen.|  
|`uint32`|Eine 32-Bit-Ganzzahl ohne Vorzeichen.|  
|`uint64`|Eine 64-Bit-Ganzzahl ohne Vorzeichen.|  
|`uint8`|Eine numerischer 8-Bit-Wert ohne Vorzeichen.|  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** vccorlib.h  
  
## <a name="see-also"></a>Siehe auch  
 [Visual C++-Sprachreferenz](../cppcx/visual-c-language-reference-c-cx.md)