---
title: aggregierbar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.aggregatable
dev_langs:
- C++
helpviewer_keywords:
- aggregatable attribute
ms.assetid: 9253a46a-cd76-41f2-b3b6-86f709bb069c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1d80b2fb707145f698e8d9bb883059478c3da10b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="aggregatable"></a>aggregatable
Gibt an, dass die Klasse Aggregation unterstützt.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      [ aggregatable(   
   value  
) ]  
```  
  
#### <a name="parameters"></a>Parameter  
 *Wert* (optional)  
 Ein Parameter, um anzugeben, wann das COM-Objekt aggregiert werden können:  
  
-   **nie** das COM-Objekt kann nicht aggregiert werden.  
  
-   **zulässige** das COM-Objekt direkt erstellt werden kann oder aggregiert werden können. Dies ist die Standardeinstellung.  
  
-   **immer** das COM-Objekt kann nicht direkt erstellt werden und nur aggregiert werden können. Beim Aufruf `CoCreateInstance` für dieses Objekt müssen Sie angeben, des aggregieren Objekts **IUnknown** Schnittstelle (steuernde **IUnknown**).  
  
## <a name="remarks"></a>Hinweise  
 Die **aggregierbar** C++-Attribut hat die gleiche Funktionalität wie die [aggregierbar](http://msdn.microsoft.com/library/windows/desktop/aa366721) MIDL-Attribut. Dies bedeutet, dass der Compiler übergibt die **aggregierbar** -Attribut über der generierten IDL-Datei.  
  
 Dieses Attribut erfordert, dass die Attribute [coclass](../windows/coclass.md), [progid](../windows/progid.md), oder [vi_progid](../windows/vi-progid.md) (oder ein anderes Attribut, das eines der genannten impliziert) auch auf demselben Element angewendet werden. Wenn ein einzelnes Attribut verwendet wird, werden die anderen beiden automatisch angewendet. Wenn z.B. **progid** angewendet wird, werden **vi_progid** und **coclass** ebenso angewendet.  
  
 **ATL-Projekte**  
  
 Wenn dieses Attribut in einem Projekt verwendet wird, das ATL verwendet, ändert sich das Verhalten des Attributs. Zusätzlich zu den zuvor beschriebenen Verhalten fügt das Attribut auch einen der folgenden Makros hinzu Zielklasse:  
  
|Parameterwert|Eingefügte-Makro|  
|---------------------|--------------------|  
|**Nie**|[DECLARE_NOT_AGGREGATABLE](../atl/reference/aggregation-and-class-factory-macros.md#declare_not_aggregatable)|  
|**Zulässig**|[DECLARE_POLY_AGGREGATABLE](../atl/reference/aggregation-and-class-factory-macros.md#declare_poly_aggregatable)|  
|**Immer**|[DECLARE_ONLY_AGGREGATABLE](../atl/reference/aggregation-and-class-factory-macros.md#declare_only_aggregatable)|  
  
## <a name="example"></a>Beispiel  
  
```  
// cpp_attr_ref_aggregatable.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module(name="MyModule")];  
  
[ coclass, aggregatable(allowed),  
  uuid("1a8369cc-1c91-42c4-befa-5a5d8c9d2529")]  
class CMyClass {};  
```  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|**Klasse**, `struct`|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Ein Attribut oder mehrere Attribute der folgenden: **coclass**, **progid**, oder **vi_progid**.|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [Klassenattribute](../windows/class-attributes.md)   
 [TypeDef, Enum, Union- und Struct-Attribute](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Aggregation](http://msdn.microsoft.com/library/windows/desktop/ms686558)   
